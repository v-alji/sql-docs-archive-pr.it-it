---
title: Eseguire una stored procedure (usando la sintassi ODBC CALL) ed elaborare i codici restituiti e i parametri di output (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [ODBC]
- ODBC CALL syntax
ms.assetid: 921a24d1-ea09-4a3c-980a-4dcbd0a43d31
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d862c2feed8a8f3678c0b9150021bee56dbeb0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713151"
---
# <a name="execute-a-stored-procedure-using-odbc-call-syntax-and-process-return-codes-and-output-parameters-ole-db"></a><span data-ttu-id="4fdcb-102">Eseguire una stored procedure mediante la sintassi dell'istruzione ODBC RPC ed elaborare i codici restituiti e i parametri di output (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="4fdcb-102">Execute a Stored Procedure (Using ODBC CALL Syntax) and Process Return Codes and Output Parameters (OLE DB)</span></span>
  <span data-ttu-id="4fdcb-103">Le stored procedure di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] possono includere parametri di output e codici restituiti di tipo integer.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stored procedures can have integer return codes and output parameters.</span></span> <span data-ttu-id="4fdcb-104">I codici restituiti e i parametri di output vengono inviati nell'ultimo pacchetto dal server e non sono pertanto disponibili all'applicazione fino al completo rilascio del set di righe.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-104">The return codes and output parameters are sent in the last packet from the server and are therefore not available to the application until the rowset is completely released.</span></span> <span data-ttu-id="4fdcb-105">Se il comando restituisce più risultati, i dati dei parametri di output sono disponibili quando `IMultipleResults::GetResult` restituisce DB_S_NORESULT o l'interfaccia `IMultipleResults` viene completamente rilasciata, a seconda dell'evento che si verifica per primo.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-105">If the command returns multiple results, output parameter data is available when `IMultipleResults::GetResult` returns DB_S_NORESULT or the `IMultipleResults` interface is completely released, whichever occurs first.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4fdcb-106">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="4fdcb-107">Se non è disponibile, agli utenti verrà richiesto di immettere le credenziali in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="4fdcb-108">Evitare di archiviare le credenziali in un file.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="4fdcb-109">Se è necessario rendere persistenti le credenziali, è consigliabile crittografarle usando l'[API di crittografia Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="4fdcb-109">If you must persist credentials, you should encrypt them with the [Win32 Crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-process-return-codes-and-output-parameters"></a><span data-ttu-id="4fdcb-110">Per elaborare i codici restituiti e i parametri di output</span><span class="sxs-lookup"><span data-stu-id="4fdcb-110">To process return codes and output parameters</span></span>  
  
1.  <span data-ttu-id="4fdcb-111">Costruire un'istruzione SQL in cui venga utilizzata la sequenza di escape ODBC CALL.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-111">Construct an SQL statement that uses the ODBC CALL escape sequence.</span></span> <span data-ttu-id="4fdcb-112">Nell'istruzione devono essere utilizzati marcatori di parametro per ogni parametro di input, input/output e output e per il valore restituito della procedura, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-112">The statement should use parameter markers for each input/output and output parameter, and for the procedure return value (if any).</span></span> <span data-ttu-id="4fdcb-113">Per i parametri di input, è possibile utilizzare marcatori di parametro o specificare valori a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-113">For input parameters, you can use the parameter markers, or hard code the values.</span></span>  
  
2.  <span data-ttu-id="4fdcb-114">Creare un set di associazioni (uno per ogni marcatore di parametro) tramite una matrice di strutture DBBINDING.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-114">Create a set of bindings (one for each parameter maker) by using an array of DBBINDING structure.</span></span>  
  
3.  <span data-ttu-id="4fdcb-115">Creare una funzione di accesso per i parametri definiti tramite il metodo `IAccessor::CreateAccessor`.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-115">Create an accessor for the defined parameters by using the `IAccessor::CreateAccessor` method.</span></span> <span data-ttu-id="4fdcb-116">`CreateAccessor` consente di creare una funzione di accesso da un set di associazioni.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-116">`CreateAccessor` creates an accessor from a set of bindings.</span></span>  
  
4.  <span data-ttu-id="4fdcb-117">Completare la struttura DBPARAMS.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-117">Fill in the DBPARAMS structure.</span></span>  
  
5.  <span data-ttu-id="4fdcb-118">Chiamare il comando `Execute`, rappresentato in questo caso da una chiamata a una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-118">Call the `Execute` command (in this case, a call to a stored procedure).</span></span>  
  
6.  <span data-ttu-id="4fdcb-119">Elaborare il set di righe e rilasciarlo utilizzando il metodo `IRowset::Release`.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-119">Process the rowset and release it by using the `IRowset::Release` method.</span></span>  
  
7.  <span data-ttu-id="4fdcb-120">Elaborare il codice restituito e i valori del parametro di output ricevuti dalla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-120">Process the return code and output parameter values received from the stored procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fdcb-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="4fdcb-121">Example</span></span>  
 <span data-ttu-id="4fdcb-122">In questo esempio viene illustrata l'elaborazione di un set di righe, di un codice restituito e di un parametro di output.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-122">The example shows processing a rowset, a return code, and an output parameter.</span></span> <span data-ttu-id="4fdcb-123">I set di risultati non vengono elaborati.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-123">Result sets are not processed.</span></span> <span data-ttu-id="4fdcb-124">Questo esempio non è supportato in IA64.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-124">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="4fdcb-125">Per l'esempio è necessario il database di esempio AdventureWorks, che è possibile scaricare dalla home page del sito relativo a [progetti della community ed esempi per Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkID=85384).</span><span class="sxs-lookup"><span data-stu-id="4fdcb-125">This sample requires the AdventureWorks sample database, which you can download from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.</span></span>  
  
 <span data-ttu-id="4fdcb-126">Eseguire il primo listato di codice ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) per creare la stored procedure utilizzata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-126">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the stored procedure used by the application.</span></span>  
  
 <span data-ttu-id="4fdcb-127">Compilare il secondo listato di codice (C++) con ole32.lib oleaut32.lib ed eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-127">Compile with ole32.lib oleaut32.lib and execute the second (C++) code listing.</span></span> <span data-ttu-id="4fdcb-128">In questa applicazione viene eseguita la connessione all'istanza predefinita di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-128">This application connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="4fdcb-129">In alcuni sistemi operativi Windows sarà necessario modificare (local) o (localhost) impostando il valore sul nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fdcb-129">On some Windows operating systems, you will need to change (localhost) or (local) to the name of your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="4fdcb-130">Per connettersi a un'istanza denominata, modificare la stringa di connessione da L"(local)" in L"(local)\\\nome", dove nome rappresenta l'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-130">To connect to a named instance, change the connection string from L"(local)" to L"(local)\\\name" , where name is the named instance.</span></span> <span data-ttu-id="4fdcb-131">Per impostazione predefinita, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Express viene installato in un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-131">By default, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Express installs to a named instance.</span></span> <span data-ttu-id="4fdcb-132">Verificare che nella variabile di ambiente INCLUDE sia presente la directory che contiene sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-132">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
 <span data-ttu-id="4fdcb-133">Eseguire il terzo listato di codice ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) per eliminare la stored procedure utilizzata dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4fdcb-133">Execute the third ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the stored procedure used by the application.</span></span>  
  
```  
USE AdventureWorks  
if exists (SELECT * FROM sys.objects WHERE object_id = OBJECT_ID(N'[myProc]'))  
   DROP PROCEDURE myProc  
GO  
  
CREATE PROCEDURE myProc   
    @inparam nvarchar(5),,  
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
  
ULONG ParamOrdinals[nParams];  
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
   WCHAR* wCmdString = L"{? = call myProc(?,?)}";  
  
   SPROCPARAMS sprocparams = {0,0,14};  
  
   // All the initialization activities in a separate function.  
   InitializeAndEstablishConnection();  
  
   // Create a new activity from the data source object.  
   if ( FAILED(pIDBInitialize->QueryInterface( IID_IDBCreateSession,   
      (void**) &pIDBCreateSession))) {  
         cout << "Failed to access IDBCreateSession interface.\n";  
         goto EXIT;  
   }  
   if (FAILED(pIDBCreateSession->CreateSession( NULL, IID_IDBCreateCommand,   
      (IUnknown**) &pIDBCreateCommand))) {  
         cout << "pIDBCreateSession->CreateSession failed.\n";  
      goto EXIT;  
   }  
  
   // Create a Command object.  
   if (FAILED(pIDBCreateCommand->CreateCommand(NULL, IID_ICommandText,   
      (IUnknown**) &pICommandText))) {  
         cout << "Failed to access ICommand interface.\n";  
         goto EXIT;  
   }  
  
   // Set the command text.  
   if (FAILED(pICommandText->SetCommandText(DBGUID_DBSQL, wCmdString))) {  
      cout << "Failed to set command text.\n";  
      goto EXIT;  
   }  
   // No need to describe command parameters (parameter name, data type  
   // etc) in DBPARAMBINDINFO structure and then SetParameterInfo(). The  
   // provider obtains this information by calling appropriate helper  
   // function.  
  
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
   }   // end for  
  
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
   hr = pICommandText->QueryInterface( IID_IAccessor, (void**)&pIAccessor);  
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
   if ( FAILED(hr = pICommandText->Execute( NULL,   
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
  
   // Result set is not important in this example; release it without processing.  
   pIRowset->Release();  
  
   printf("After processing the result set...\n");  
   printf("  Return value = %d\n", sprocparams.lReturnValue);  
   printf("  Output parameter value = %d\n\n", sprocparams.outParam);  
  
   // Release memory.  
   pIAccessor->ReleaseAccessor(hAccessor, NULL);  
   pIAccessor->Release();  
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
   if (pICommandText != NULL)  
      pICommandText->Release();  
   if (pIDBCreateCommand != NULL)  
      pIDBCreateCommand->Release();  
   if (pIDBCreateSession != NULL)  
      pIDBCreateSession->Release();  
   if (pIDBInitialize != NULL)  
      if (FAILED(pIDBInitialize->Uninitialize()))  
         // Uninitialize is not required, but it fails if an  
         // interface has not been released.  This can be used for debugging.  
         cout << "Problem in uninitializing.\n";  
      pIDBInitialize->Release();  
  
   CoUninitialize();  
};  
  
void InitializeAndEstablishConnection() {      
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQL Server Native Client OLE DB provider.      
   hr = CoCreateInstance( CLSID_SQLNCLI11,   
                          NULL,   
                          CLSCTX_INPROC_SERVER,  
                          IID_IDBInitialize,   
                          (void **) &pIDBInitialize);  
   if (FAILED(hr))  
      cout << "Failed in CoCreateInstance().\n";  
  
   // Initialize the property values needed to establish the connection.  
   for ( i = 0 ; i < nInitProps ; i++ )  
      VariantInit(&InitProperties[i].vValue);  
  
   // Specify server name.  
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
  
   // Now that properties are set, construct the DBPROPSET structure  
   // (rgInitPropSet).  The DBPROPSET structure is used to pass an array  
   // of DBPROP structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties = 4;  
   rgInitPropSet[0].rgProperties = InitProperties;  
  
   // Set initialization properties.  
   hr = pIDBInitialize->QueryInterface(IID_IDBProperties, (void **)&pIDBProperties);  
   if (FAILED(hr))  
      cout << "Failed to obtain IDBProperties interface.\n";  
  
   hr = pIDBProperties->SetProperties(nPropSet, rgInitPropSet);  
   if (FAILED(hr))  
      cout << "Failed to set initialization properties.\n";  
  
   pIDBProperties->Release();  
  
   // Now establish a connection to the data source.  
   if (FAILED(pIDBInitialize->Initialize()))  
      cout << "Problem in initializing.\n";  
}  
```  
  
```  
USE AdventureWorks  
DROP PROCEDURE myProc  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4fdcb-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fdcb-134">See Also</span></span>  
 [<span data-ttu-id="4fdcb-135">Procedure relative all'elaborazione dei risultati &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="4fdcb-135">Processing Results How-to Topics &#40;OLE DB&#41;</span></span>](processing-results-how-to-topics-ole-db.md)  
  
  
