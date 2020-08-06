---
title: Eseguire una stored procedure (utilizzando la sintassi RPC) ed elaborare i codici restituiti e i parametri di output (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- RPC syntax
- stored procedures [SQL Server], RPC syntax
ms.assetid: 1eb60087-da67-433f-9b45-4028595e68ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 34ef1083c1fb829c2f5cdb947f46d2e64f6c8b49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713148"
---
# <a name="execute-a-stored-procedure-using-rpc-syntax-and-process-return-codes-and-output-parameters-ole-db"></a><span data-ttu-id="7fab9-102">Eseguire una stored procedure mediante la sintassi dell'istruzione RPC ed elaborare i codici restituiti e i parametri di output (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="7fab9-102">Execute a Stored Procedure (Using RPC Syntax) and Process Return Codes and Output Parameters (OLE DB)</span></span>
  <span data-ttu-id="7fab9-103">Le stored procedure di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] possono includere parametri di output e codici restituiti di tipo integer.</span><span class="sxs-lookup"><span data-stu-id="7fab9-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stored procedures can have integer return codes and output parameters.</span></span> <span data-ttu-id="7fab9-104">I codici restituiti e i parametri di output vengono inviati nell'ultimo pacchetto dal server e non sono pertanto disponibili all'applicazione fino al completo rilascio del set di righe.</span><span class="sxs-lookup"><span data-stu-id="7fab9-104">The return codes and output parameters are sent in the last packet from the server and are therefore not available to the application until the rowset is completely released.</span></span> <span data-ttu-id="7fab9-105">Se il comando restituisce più risultati, i dati del parametro di output sono disponibili quando `IMultipleResults::GetResult` restituisce DB_S_NORESULT o l'interfaccia `IMultipleResults` viene completamente rilasciata, indipendentemente da quale dei due eventi si verifica per primo.</span><span class="sxs-lookup"><span data-stu-id="7fab9-105">If the command returns multiple results, output parameter data is available when `IMultipleResults::GetResult` returns DB_S_NORESULT, or when the `IMultipleResults` interface is completely released, whichever occurs first.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7fab9-106">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="7fab9-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="7fab9-107">Se non è disponibile, agli utenti verrà richiesto di immettere le credenziali in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7fab9-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="7fab9-108">Evitare di archiviare le credenziali in un file.</span><span class="sxs-lookup"><span data-stu-id="7fab9-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="7fab9-109">Se è necessario rendere persistenti le credenziali, è consigliabile crittografarle usando l'[API di crittografia Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="7fab9-109">If you must persist credentials, you should encrypt them with the [Win32 Crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-process-return-codes-and-output-parameters"></a><span data-ttu-id="7fab9-110">Per elaborare i codici restituiti e i parametri di output</span><span class="sxs-lookup"><span data-stu-id="7fab9-110">To process return codes and output parameters</span></span>  
  
1.  <span data-ttu-id="7fab9-111">Costruire un'istruzione SQL che utilizzi la sequenza di escape RPC.</span><span class="sxs-lookup"><span data-stu-id="7fab9-111">Construct an SQL statement that uses the RPC escape sequence.</span></span>  
  
2.  <span data-ttu-id="7fab9-112">Chiamare il metodo `ICommandWithParameters::SetParameterInfo` per descrivere i parametri al provider.</span><span class="sxs-lookup"><span data-stu-id="7fab9-112">Call the `ICommandWithParameters::SetParameterInfo` method to describe parameters to the provider.</span></span> <span data-ttu-id="7fab9-113">Inserire le informazioni sul parametro in una matrice delle strutture PARAMBINDINFO.</span><span class="sxs-lookup"><span data-stu-id="7fab9-113">Fill in the parameter information in an array of PARAMBINDINFO structures.</span></span>  
  
3.  <span data-ttu-id="7fab9-114">Creare un set di associazioni (uno per ogni creatore di parametro) tramite una matrice di strutture DBBINDING.</span><span class="sxs-lookup"><span data-stu-id="7fab9-114">Create a set of bindings (one for each parameter maker) by using an array of DBBINDING structures.</span></span>  
  
4.  <span data-ttu-id="7fab9-115">Creare una funzione di accesso per i parametri definiti tramite il metodo `IAccessor::CreateAccessor`.</span><span class="sxs-lookup"><span data-stu-id="7fab9-115">Create an accessor for the defined parameters by using the `IAccessor::CreateAccessor` method.</span></span> <span data-ttu-id="7fab9-116">`CreateAccessor` consente di creare una funzione di accesso da un set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="7fab9-116">`CreateAccessor` creates an accessor from a set of bindings.</span></span>  
  
5.  <span data-ttu-id="7fab9-117">Completare la struttura DBPARAMS.</span><span class="sxs-lookup"><span data-stu-id="7fab9-117">Fill in the DBPARAMS structure.</span></span>  
  
6.  <span data-ttu-id="7fab9-118">Chiamare il comando `Execute`, rappresentato in questo caso da una chiamata a una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="7fab9-118">Call the `Execute` command (in this case, a call to a stored procedure).</span></span>  
  
7.  <span data-ttu-id="7fab9-119">Elaborare il set di righe e rilasciarlo utilizzando il metodo `IRowset::Release`.</span><span class="sxs-lookup"><span data-stu-id="7fab9-119">Process the rowset and release it by using the `IRowset::Release` method.</span></span>  
  
8.  <span data-ttu-id="7fab9-120">Elaborare il codice restituito e i valori del parametro di output ricevuti dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="7fab9-120">Process the return code and output parameter values received from the stored procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fab9-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="7fab9-121">Example</span></span>  
 <span data-ttu-id="7fab9-122">In questo esempio viene illustrata l'elaborazione di un set di righe, di un codice restituito e di un parametro di output.</span><span class="sxs-lookup"><span data-stu-id="7fab9-122">The example shows processing a rowset, a return code, and an output parameter.</span></span> <span data-ttu-id="7fab9-123">I set di risultati non vengono elaborati.</span><span class="sxs-lookup"><span data-stu-id="7fab9-123">Result sets are not processed.</span></span> <span data-ttu-id="7fab9-124">Questo esempio non è supportato in IA64.</span><span class="sxs-lookup"><span data-stu-id="7fab9-124">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="7fab9-125">Per l'esempio è necessario il database di esempio AdventureWorks, che è possibile scaricare dalla home page del sito relativo a [progetti della community ed esempi per Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384).</span><span class="sxs-lookup"><span data-stu-id="7fab9-125">This sample requires the AdventureWorks sample database, which you can download from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.</span></span>  
  
 <span data-ttu-id="7fab9-126">Eseguire il primo listato di codice ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) per creare la stored procedure utilizzata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7fab9-126">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the stored procedure used by the application.</span></span>  
  
 <span data-ttu-id="7fab9-127">Compilare il secondo listato di codice (C++) con ole32.lib oleaut32.lib ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="7fab9-127">Compile with ole32.lib oleaut32.lib and execute the second (C++) code listing.</span></span> <span data-ttu-id="7fab9-128">In questa applicazione viene eseguita la connessione all'istanza predefinita di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="7fab9-128">This application connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="7fab9-129">In alcuni sistemi operativi Windows sarà necessario modificare (local) o (localhost) impostando il valore sul nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fab9-129">On some Windows operating systems, you will need to change (localhost) or (local) to the name of your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="7fab9-130">Per connettersi a un'istanza denominata, modificare la stringa di connessione da L"(local)" in L"(local)\\\nome", dove nome rappresenta l'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="7fab9-130">To connect to a named instance, change the connection string from L"(local)" to L"(local)\\\name" , where name is the named instance.</span></span> <span data-ttu-id="7fab9-131">Per impostazione predefinita, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Express viene installato in un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="7fab9-131">By default, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Express installs to a named instance.</span></span> <span data-ttu-id="7fab9-132">Verificare che nella variabile di ambiente INCLUDE sia presente la directory che contiene sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="7fab9-132">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
 <span data-ttu-id="7fab9-133">Eseguire il terzo listato di codice ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) per eliminare la stored procedure utilizzata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7fab9-133">Execute the third ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the stored procedure used by the application.</span></span>  
  
```  
USE AdventureWorks  
if exists (SELECT * FROM sys.objects WHERE object_id = OBJECT_ID(N'[myProc]'))  
   DROP PROCEDURE myProc  
GO  
  
CREATE PROCEDURE myProc   
    @inparam nvarchar(5),  
    @outparam int OUTPUT  
  
AS  
SELECT Color, ListPrice   
FROM Production.Product WHERE Size > @inparam  
SELECT @outparam = 100  
  
IF  (@outparam > 0)  
    RETURN 999  
ELSE  
    RETURN 888  
GO  
```  
  
```  
// compile with: ole32.lib oleaut32.lib  
void InitializeAndEstablishConnection();  
  
#define UNICODE  
#define DBINITCONSTANTS  
#define INITGUID  
#define OLEDBVER 0x0250   // to include correct interfaces  
  
#include <windows.h>  
#include <stdio.h>  
#include <stddef.h>  
#include <iostream>  
#include <oledb.h>  
#include <oledberr.h>  
#include <SQLNCLI.h>  
  
using namespace std;  
IDBInitialize* pIDBInitialize = NULL;  
IDBCreateSession* pIDBCreateSession = NULL;  
IDBCreateCommand* pIDBCreateCommand = NULL;  
ICommandText* pICommandText = NULL;  
IRowset* pIRowset = NULL;  
ICommandWithParameters* pICommandWithParams = NULL;  
IAccessor* pIAccessor = NULL;  
IDBProperties* pIDBProperties = NULL;  
WCHAR* pStringsBuffer;  
DBBINDING* pBindings;  
const ULONG nInitProps = 4;  
DBPROP InitProperties[nInitProps];  
const ULONG nPropSet = 1;  
DBPROPSET rgInitPropSet[nPropSet];  
HRESULT hr;  
HACCESSOR hAccessor;  
const ULONG nParams = 3;   // Number of parameters in the command  
DBPARAMBINDINFO ParamBindInfo[nParams];  
ULONG i;  
ULONG cbColOffset = 0;  
  
DB_UPARAMS ParamOrdinals[nParams];  
DBROWCOUNT cNumRows = 0;  
DBPARAMS Params;  
  
// Declare an array of DBBINDING structures, one for each parameter in the command.  
DBBINDING acDBBinding[nParams];  
DBBINDSTATUS acDBBindStatus[nParams];  
  
// The following buffer is used to store parameter values.  
typedef struct tagSPROCPARAMS {  
   long lReturnValue;  
   long outParam;  
   long inParam;  
} SPROCPARAMS;  
  
int main() {  
   // The command to execute.    
   // WCHAR* wCmdString = L"{? = call myProc(?,?)}";  
   WCHAR* wCmdString = L"{rpc myProc}";  
   SPROCPARAMS sprocparams = {0,0,14};  
  
   // All the initialization activities in a separate function.  
   InitializeAndEstablishConnection();  
  
   // Create a new activity from the data source object.  
   if (FAILED(pIDBInitialize->QueryInterface(IID_IDBCreateSession,   
                                             (void**) &pIDBCreateSession))) {  
      cout << "Failed to access IDBCreateSession interface.\n";  
      goto EXIT;  
   }  
  
   if ( FAILED(pIDBCreateSession->CreateSession( NULL, IID_IDBCreateCommand,   
                                                (IUnknown**) &pIDBCreateCommand))) {  
      cout << "pIDBCreateSession->CreateSession failed.\n";  
      goto EXIT;  
   }  
  
   // Create a Command object.  
   if (FAILED(pIDBCreateCommand->CreateCommand( NULL,         
                                                IID_ICommandText,   
                                                (IUnknown**) &pICommandText))) {  
      cout << "Failed to access ICommand interface.\n";  
      goto EXIT;  
   }  
  
   // Set the command text.  
   if (FAILED(pICommandText->SetCommandText(DBGUID_DBSQL, wCmdString))) {  
      cout << "Failed to set command text.\n";  
      goto EXIT;  
   }  
  
   // Describe the command parameters (parameter name, provider specific name of  
   // the parameter's data type, and so on.) in an array of DBPARAMBINDINFO   
   // structures.  This information is then used by SetParameterInfo().  
   ParamBindInfo[0].pwszDataSourceType = L"DBTYPE_I4";  
   ParamBindInfo[0].pwszName = L"@ReturnVal";   // return value from sp  
   ParamBindInfo[0].ulParamSize = sizeof(long);  
   ParamBindInfo[0].dwFlags = DBPARAMFLAGS_ISOUTPUT;  
   ParamBindInfo[0].bPrecision = 11;  
   ParamBindInfo[0].bScale = 0;  
   ParamOrdinals[0] = 1;  
  
   ParamBindInfo[1].pwszDataSourceType = L"DBTYPE_I4";  
   ParamBindInfo[1].pwszName = L"@inparam";  
   ParamBindInfo[1].ulParamSize = sizeof(long);  
   ParamBindInfo[1].dwFlags = DBPARAMFLAGS_ISINPUT;  
   ParamBindInfo[1].bPrecision = 11;  
   ParamBindInfo[1].bScale = 0;  
   ParamOrdinals[1] = 2;  
  
   ParamBindInfo[2].pwszDataSourceType = L"DBTYPE_I4";  
   ParamBindInfo[2].pwszName = L"@outparam";  
   ParamBindInfo[2].ulParamSize = sizeof(long);  
   ParamBindInfo[2].dwFlags = DBPARAMFLAGS_ISOUTPUT;  
   ParamBindInfo[2].bPrecision = 11;  
   ParamBindInfo[2].bScale = 0;  
   ParamOrdinals[2] = 3;  
  
   //Set the parameters information.  
   if ( FAILED(pICommandText->QueryInterface( IID_ICommandWithParameters,  
                                            (void**)&pICommandWithParams))) {  
      cout << "Failed to obtain ICommandWithParameters.\n";  
      goto EXIT;  
   }  
  
   if ( FAILED(pICommandWithParams->SetParameterInfo(nParams,   
                                                     ParamOrdinals,   
                                                     ParamBindInfo))) {  
      cout << "Failed in setting parameter information.(SetParameterInfo)\n";  
      goto EXIT;  
   }  
  
   // Describe the consumer buffer by filling in the array of DBBINDING structures.  
   // Each binding associates a single parameter to the consumer's buffer.  
   for ( i = 0 ; i < nParams ; i++ ) {  
      acDBBinding[i].obLength = 0;  
      acDBBinding[i].obStatus = 0;  
      acDBBinding[i].pTypeInfo = NULL;  
      acDBBinding[i].pObject = NULL;  
      acDBBinding[i].pBindExt = NULL;  
      acDBBinding[i].dwPart = DBPART_VALUE;  
      acDBBinding[i].dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
      acDBBinding[i].dwFlags = 0;  
      acDBBinding[i].bScale = 0;  
   }  
  
   acDBBinding[0].iOrdinal = 1;  
   acDBBinding[0].obValue = offsetof(SPROCPARAMS, lReturnValue);  
   acDBBinding[0].eParamIO = DBPARAMIO_OUTPUT;  
   acDBBinding[0].cbMaxLen = sizeof(long);  
   acDBBinding[0].wType = DBTYPE_I4;  
   acDBBinding[0].bPrecision = 11;  
  
   acDBBinding[1].iOrdinal = 2;  
   acDBBinding[1].obValue = offsetof(SPROCPARAMS, inParam);  
   acDBBinding[1].eParamIO = DBPARAMIO_INPUT;  
   acDBBinding[1].cbMaxLen = sizeof(long);  
   acDBBinding[1].wType = DBTYPE_I4;  
   acDBBinding[1].bPrecision = 11;  
  
   acDBBinding[2].iOrdinal = 3;  
   acDBBinding[2].obValue = offsetof(SPROCPARAMS, outParam);  
   acDBBinding[2].eParamIO = DBPARAMIO_OUTPUT;  
   acDBBinding[2].cbMaxLen = sizeof(long);  
   acDBBinding[2].wType = DBTYPE_I4;  
   acDBBinding[2].bPrecision = 11;  
  
   // Create an accessor from the above set of bindings.  
   hr = pICommandWithParams->QueryInterface(IID_IAccessor, (void**)&pIAccessor);  
   if (FAILED(hr))  
      cout << "Failed to get IAccessor interface.\n";  
  
   hr = pIAccessor->CreateAccessor( DBACCESSOR_PARAMETERDATA,  
                                    nParams,   
                                    acDBBinding,   
                                    sizeof(SPROCPARAMS),   
                                    &hAccessor,  
                                    acDBBindStatus);  
  
   if (FAILED(hr))  
      cout << "Failed to create accessor for the defined parameters.\n";  
  
   // Fill in DBPARAMS structure for the command execution. This structure   
   // specifies the parameter values in the command and is then passed to Execute.  
   Params.pData = &sprocparams;  
   Params.cParamSets = 1;  
   Params.hAccessor = hAccessor;  
  
   // Execute the command.  
   if (FAILED(hr = pICommandText->Execute( NULL,   
                                           IID_IRowset,   
                                           &Params,   
                                           &cNumRows,   
                                           (IUnknown **) &pIRowset))) {  
      cout << "Failed to execute command.\n";  
      goto EXIT;  
   }  
  
   printf("After command execution but before rowset processing.\n\n");  
   printf("  Return value = %d\n", sprocparams.lReturnValue);  
   printf("  Output parameter value = %d\n", sprocparams.outParam);  
   printf("  These are the same default values set in the application.\n\n\n");  
  
   // This result set is not important, so release it without processing.  
   pIRowset->Release();  
  
   printf("After processing the result set...\n");  
   printf("  Return value = %d\n", sprocparams.lReturnValue);  
   printf("  Output parameter value = %d\n\n", sprocparams.outParam);  
  
   // Release memory.  
   pIAccessor->ReleaseAccessor(hAccessor, NULL);  
   pIAccessor->Release();  
   pICommandWithParams->Release();  
   pICommandText->Release();  
   pIDBCreateCommand->Release();  
   pIDBCreateSession->Release();      
  
   if (FAILED(pIDBInitialize->Uninitialize()))  
      // Uninitialize is not required, but it fails if an interface  
      // has not been released.  This can be used for debugging.  
      cout << "Problem uninitializing.\n";  
  
   pIDBInitialize->Release();  
  
   CoUninitialize();  
   return 0;  
  
EXIT:  
   if (pIAccessor != NULL)  
      pIAccessor->Release();  
   if (pICommandWithParams != NULL)  
      pICommandWithParams->Release();  
   if (pICommandText != NULL)  
      pICommandText->Release();  
   if (pIDBCreateCommand != NULL)  
      pIDBCreateCommand->Release();  
   if (pIDBCreateSession != NULL)  
      pIDBCreateSession->Release();  
   if (pIDBInitialize != NULL)  
      if (FAILED(pIDBInitialize->Uninitialize()))  
         // Uninitialize is not required, but it fails if an interface has not   
         // been released.  This can be used for debugging.  
         cout << "Problem in uninitializing.\n";  
      pIDBInitialize->Release();  
  
   CoUninitialize();  
}  
  
void InitializeAndEstablishConnection() {      
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQL Server Native Client OLE DB provider.      
   hr = CoCreateInstance( CLSID_SQLNCLI11,   
                          NULL,   
                          CLSCTX_INPROC_SERVER,IID_IDBInitialize,   
                          (void **) &pIDBInitialize);  
  
   if (FAILED(hr))  
      cout << "Failed in CoCreateInstance().\n";  
  
   // Initialize the property values needed to establish the connection.  
   for (i = 0 ; i < nInitProps ; i++ )  
      VariantInit(&InitProperties[i].vValue);  
  
   //Specify server name.  
   InitProperties[0].dwPropertyID = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt = VT_BSTR;  
  
   // Replace "MySqlServer" with proper value.  
   InitProperties[0].vValue.bstrVal = SysAllocString(L"(local)");  
   InitProperties[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid = DB_NULLID;  
  
   // Specify database name.  
   InitProperties[1].dwPropertyID = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt = VT_BSTR;  
   InitProperties[1].vValue.bstrVal = SysAllocString(L"AdventureWorks");  
   InitProperties[1].dwOptions = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid = DB_NULLID;  
  
   InitProperties[2].dwPropertyID = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt = VT_BSTR;  
   InitProperties[2].vValue.bstrVal = SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid = DB_NULLID;  
  
   // Properties are set, construct the DBPROPSET structure (rgInitPropSet) used to pass   
   // an array of // DBPROP structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties = 4;  
   rgInitPropSet[0].rgProperties = InitProperties;  
  
   // Set initialization properties.  
   hr = pIDBInitialize->QueryInterface( IID_IDBProperties, (void **)&pIDBProperties);  
   if ( FAILED(hr))  
      cout << "Failed to obtain IDBProperties interface.\n";  
  
   hr = pIDBProperties->SetProperties( nPropSet, rgInitPropSet);  
   if (FAILED(hr))   
      cout << "Failed to set initialization properties.\n";  
  
   pIDBProperties->Release();  
  
   // Now establish a connection to the data source.  
   if ( FAILED(pIDBInitialize->Initialize()) )  
      cout << "Problem in initializing.\n";  
}  
```  
  
```  
USE AdventureWorks  
DROP PROCEDURE myProc  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="7fab9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fab9-134">See Also</span></span>  
 [<span data-ttu-id="7fab9-135">Procedure relative all'elaborazione dei risultati &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="7fab9-135">Processing Results How-to Topics &#40;OLE DB&#41;</span></span>](processing-results-how-to-topics-ole-db.md)  
  
  
