---
title: IBCPSession2::BCPSetBulkMode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BCPSetBulkMode function
ms.assetid: babba19f-e67b-450c-b0e6-523a0f9d23ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 9605ff9b8effde1b4a77ba0d8554c719a8a8d1e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636709"
---
# <a name="ibcpsession2bcpsetbulkmode"></a><span data-ttu-id="68588-102">IBCPSession2::BCPSetBulkMode</span><span class="sxs-lookup"><span data-stu-id="68588-102">IBCPSession2::BCPSetBulkMode</span></span>
  <span data-ttu-id="68588-103">IBCPSession2::BCPSetBulkMode offre un'alternativa a [IBCPSession::BCPColFmt &#40;OLE DB&#41;](ibcpsession-bcpcolfmt-ole-db.md) per specificare il formato della colonna.</span><span class="sxs-lookup"><span data-stu-id="68588-103">IBCPSession2::BCPSetBulkMode provides an alternative to [IBCPSession::BCPColFmt &#40;OLE DB&#41;](ibcpsession-bcpcolfmt-ole-db.md) for specifying the column format.</span></span> <span data-ttu-id="68588-104">A differenza di IBCPSession::BCPColFmt, che imposta i singoli attributi di formato di colonna, IBCPSession2::BCPSetBulkMode imposta tutti gli attributi.</span><span class="sxs-lookup"><span data-stu-id="68588-104">Unlike IBCPSession::BCPColFmt, which sets individual column format attributes, IBCPSession2::BCPSetBulkMode sets all attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68588-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68588-105">Syntax</span></span>  
  
```  
  
HRESULT BCPSetBulkMode (  
      int property,  
   void * pField,  
   int cbField,  
   void * pRow,  
   int cbRow  
);  
```  
  
## <a name="arguments"></a><span data-ttu-id="68588-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="68588-106">Arguments</span></span>  
 <span data-ttu-id="68588-107">*property*</span><span class="sxs-lookup"><span data-stu-id="68588-107">*property*</span></span>  
 <span data-ttu-id="68588-108">Costante di tipo BYTE.</span><span class="sxs-lookup"><span data-stu-id="68588-108">A constant of type BYTE.</span></span> <span data-ttu-id="68588-109">Per un elenco di costanti, vedere la tabella nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="68588-109">See the table in the Remarks section for a list of the constants.</span></span>  
  
 <span data-ttu-id="68588-110">*pField*</span><span class="sxs-lookup"><span data-stu-id="68588-110">*pField*</span></span>  
 <span data-ttu-id="68588-111">Puntatore al valore del carattere di terminazione del campo.</span><span class="sxs-lookup"><span data-stu-id="68588-111">The pointer to the field terminator value.</span></span>  
  
 <span data-ttu-id="68588-112">cbField</span><span class="sxs-lookup"><span data-stu-id="68588-112">cbField</span></span>  
 <span data-ttu-id="68588-113">Lunghezza, in byte, del valore del carattere di terminazione del campo.</span><span class="sxs-lookup"><span data-stu-id="68588-113">The length in bytes of the field terminator value.</span></span>  
  
 <span data-ttu-id="68588-114">pRow</span><span class="sxs-lookup"><span data-stu-id="68588-114">pRow</span></span>  
 <span data-ttu-id="68588-115">Puntatore al valore del carattere di terminazione della riga.</span><span class="sxs-lookup"><span data-stu-id="68588-115">The pointer to the row terminator value.</span></span>  
  
 <span data-ttu-id="68588-116">cbRow</span><span class="sxs-lookup"><span data-stu-id="68588-116">cbRow</span></span>  
 <span data-ttu-id="68588-117">Lunghezza, in byte, del valore del carattere di terminazione della riga.</span><span class="sxs-lookup"><span data-stu-id="68588-117">The length in bytes of the row terminator value.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="68588-118">Restituisce</span><span class="sxs-lookup"><span data-stu-id="68588-118">Returns</span></span>  
 <span data-ttu-id="68588-119">IBCPSession2::BCPSetBulkMode può restituire uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="68588-119">IBCPSession2::BCPSetBulkMode can return one of the following:</span></span>  
  
|||  
|-|-|  
|`S_OK`|<span data-ttu-id="68588-120">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="68588-120">The method succeeded.</span></span>|  
|`E_FAIL`|<span data-ttu-id="68588-121">Si è verificato un errore specifico del provider. Per informazioni dettagliate, usare l'interfaccia ISQLServerErrorInfo.</span><span class="sxs-lookup"><span data-stu-id="68588-121">A provider specific error occurred, for detailed information use the ISQLServerErrorInfo interface.</span></span>|  
|`E_UNEXPECTED`|<span data-ttu-id="68588-122">La chiamata al metodo non era prevista.</span><span class="sxs-lookup"><span data-stu-id="68588-122">The call to the method was unexpected.</span></span> <span data-ttu-id="68588-123">Ad esempio, il `IBCPSession2::BCPInit` metodo non è stato chiamato prima di chiamare IBCPSession2:: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="68588-123">For example, the `IBCPSession2::BCPInit` method was not called before calling IBCPSession2::BCPSetBulkMode.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="68588-124">L'argomento non è valido.</span><span class="sxs-lookup"><span data-stu-id="68588-124">The argument was invalid.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="68588-125">Errore di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="68588-125">Out of memory error.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68588-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="68588-126">Remarks</span></span>  
 <span data-ttu-id="68588-127">IBCPSession2::BCPSetBulkMode può essere usato per creare una copia bulk da una query o una tabella.</span><span class="sxs-lookup"><span data-stu-id="68588-127">IBCPSession2::BCPSetBulkMode can be used to bulk copy out of either a query or a table.</span></span> <span data-ttu-id="68588-128">Quando si utilizza IBCPSession2::BCPSetBulkMode per eseguire una copia bulk da un'istruzione di query, è necessario chiamare tale metodo prima di `IBCPSession::BCPControl(BCP_OPTIONS_HINTS, ...)` per specificare l'istruzione di query.</span><span class="sxs-lookup"><span data-stu-id="68588-128">When IBCPSession2::BCPSetBulkMode is used to bulk copy out of a query statement, it must be called before calling `IBCPSession::BCPControl(BCP_OPTIONS_HINTS, ...)` to specify the query statement.</span></span>  
  
 <span data-ttu-id="68588-129">È necessario evitare di combinare la sintassi di chiamata RPC con la sintassi di query batch (ad esempio `{rpc func};SELECT * from Tbl`) in un unico testo di comando.</span><span class="sxs-lookup"><span data-stu-id="68588-129">You should avoid combining RPC call syntax with batch query syntax (`{rpc func};SELECT * from Tbl`, for example) in a single command text.</span></span>  <span data-ttu-id="68588-130">Un'operazione di questo tipo comporterebbe la restituzione di un errore da parte di ICommandPrepare::Prepare, rendendo impossibile il recupero dei metadati.</span><span class="sxs-lookup"><span data-stu-id="68588-130">This will cause ICommandPrepare::Prepare to return an error and prevent you from retrieving metadata.</span></span> <span data-ttu-id="68588-131">Utilizzare la sintassi ODBC CALL (ad esempio `{call func}; SELECT * from Tbl`) se è necessario combinare l'esecuzione della stored procedure e una query batch in un singolo testo di comando.</span><span class="sxs-lookup"><span data-stu-id="68588-131">Use ODBC CALL syntax (`{call func}; SELECT * from Tbl`, for example) if you need to combine stored procedure execution and batch query in a single command text.</span></span>  
  
 <span data-ttu-id="68588-132">Nella tabella seguente sono elencate le costanti per il parametro *property*.</span><span class="sxs-lookup"><span data-stu-id="68588-132">The following table lists the constants for the *property* parameter.</span></span>  
  
|<span data-ttu-id="68588-133">Proprietà</span><span class="sxs-lookup"><span data-stu-id="68588-133">Property</span></span>|<span data-ttu-id="68588-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68588-134">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="68588-135">BCP_OUT_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="68588-135">BCP_OUT_CHARACTER_MODE</span></span>|<span data-ttu-id="68588-136">Specifica la modalità di output carattere.</span><span class="sxs-lookup"><span data-stu-id="68588-136">Specifies character output mode.</span></span><br /><br /> <span data-ttu-id="68588-137">Corrisponde all'opzione-c in BCP.EXE e a IBCPSession:: BCPColFmt con la proprietà *eUserDataType* impostata su `BCP_TYPE_SQLCHARACTER` .</span><span class="sxs-lookup"><span data-stu-id="68588-137">Corresponds to the -c option in BCP.EXE, and to IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLCHARACTER`.</span></span>|  
|<span data-ttu-id="68588-138">BCP_OUT_WIDE_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="68588-138">BCP_OUT_WIDE_CHARACTER_MODE</span></span>|<span data-ttu-id="68588-139">Specifica la modalità di output Unicode.</span><span class="sxs-lookup"><span data-stu-id="68588-139">Specifies Unicode output mode.</span></span><br /><br /> <span data-ttu-id="68588-140">Corrisponde all'opzione-w in BCP.EXE e IBCPSession:: BCPColFmt con la proprietà *eUserDataType* impostata su `BCP_TYPE_SQLNCHAR` .</span><span class="sxs-lookup"><span data-stu-id="68588-140">Corresponds to the -w option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLNCHAR`.</span></span>|  
|<span data-ttu-id="68588-141">BCP_OUT_NATIVE_TEXT_MODE</span><span class="sxs-lookup"><span data-stu-id="68588-141">BCP_OUT_NATIVE_TEXT_MODE</span></span>|<span data-ttu-id="68588-142">Specifica tipi nativi per i tipi non carattere e Unicode per i tipi carattere.</span><span class="sxs-lookup"><span data-stu-id="68588-142">Specifies native types for non-character types and Unicode for character types.</span></span><br /><br /> <span data-ttu-id="68588-143">Corrisponde all'opzione-N in BCP.EXE e IBCPSession:: BCPColFmt con la proprietà *eUserDataType* impostata su `BCP_TYPE_SQLNCHAR` se il tipo di colonna è una stringa o `BCP_TYPE_DEFAULT` se non è una stringa.</span><span class="sxs-lookup"><span data-stu-id="68588-143">Corresponds to the -N option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLNCHAR` if the column type is a string or `BCP_TYPE_DEFAULT` if not a string.</span></span>|  
|<span data-ttu-id="68588-144">BCP_OUT_NATIVE_MODE</span><span class="sxs-lookup"><span data-stu-id="68588-144">BCP_OUT_NATIVE_MODE</span></span>|<span data-ttu-id="68588-145">Specifica tipi di database nativi.</span><span class="sxs-lookup"><span data-stu-id="68588-145">Specifies native database types.</span></span><br /><br /> <span data-ttu-id="68588-146">Corrisponde all'opzione-n in BCP.EXE e IBCPSession:: BCPColFmt con la proprietà *eUserDataType* impostata su `BCP_TYPE_DEFAULT` .</span><span class="sxs-lookup"><span data-stu-id="68588-146">Corresponds to the -n option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_DEFAULT`.</span></span>|  
  
 <span data-ttu-id="68588-147">È possibile chiamare IBCPSession::BCPControl e IBCPSession2::BCPSetBulkMode per le opzioni IBCPSession::BCPControl che non sono in conflitto con IBCPSession2::BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="68588-147">You can call IBCPSession::BCPControl and IBCPSession2::BCPSetBulkMode for IBCPSession::BCPControl options that do not conflict with IBCPSession2::BCPSetBulkMode.</span></span> <span data-ttu-id="68588-148">Ad esempio, è possibile chiamare IBCPSession:: BCPControl con `BCP_OPTION_FIRST` e IBCPSession2:: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="68588-148">For example, you can call IBCPSession::BCPControl with `BCP_OPTION_FIRST` and IBCPSession2::BCPSetBulkMode.</span></span>  
  
 <span data-ttu-id="68588-149">Non è possibile chiamare IBCPSession:: BCPControl con `BCP_OPTION_TEXTFILE` e IBCPSession2:: BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="68588-149">You cannot call IBCPSession::BCPControl with `BCP_OPTION_TEXTFILE` and IBCPSession2::BCPSetBulkMode.</span></span>  
  
 <span data-ttu-id="68588-150">Se si tenta di chiamare IBCPSession2::BCPSetBulkMode con una sequenza di chiamate di funzione che include IBCPSession::BCPColFmt, IBCPSession::BCPControl e IBCPSession::BCPReadFmt, una delle chiamate di funzione restituirà un errore nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="68588-150">If you attempt to call IBCPSession2::BCPSetBulkMode with a sequence of function calls that includes IBCPSession::BCPColFmt, IBCPSession::BCPControl, and IBCPSession::BCPReadFmt, one of the function calls will return a sequence error failure.</span></span> <span data-ttu-id="68588-151">Se si sceglie di correggere l'errore, chiamare IBCPSession::BCPInit per reimpostare le impostazioni e ricominciare.</span><span class="sxs-lookup"><span data-stu-id="68588-151">If you choose to correct the failure, call IBCPSession::BCPInit to reset the settings and start over.</span></span>  
  
 <span data-ttu-id="68588-152">Nella tabella seguente sono illustrati alcuni esempi di chiamate di funzione che comportano un errore nella sequenza della funzione:</span><span class="sxs-lookup"><span data-stu-id="68588-152">The following table presents some examples of function calls that result in a function sequence error:</span></span>  
  
 <span data-ttu-id="68588-153">Sequenza di chiamata</span><span class="sxs-lookup"><span data-stu-id="68588-153">Call sequence</span></span>  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_IN);  
BCPSetBulkMode();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPSetBulkMode();  
BCPReadFmt();  
```  
  
```  
BCPInit(NULL, "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_HINTS, "select ...");  
BCPSetBulkMode();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPSetBulkMode();  
BCPColFmt();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPReadFmt();  
BCPColFmt();  
```  
  
```  
BCPInit(NULL, "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPSetBulkMode();  
BCPControl(BCP_OPTION_HINTS, "select ...");  
BCPReadFmt();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPColumns();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPSetColFmt();  
```  
  
## <a name="example"></a><span data-ttu-id="68588-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="68588-154">Example</span></span>  
 <span data-ttu-id="68588-155">Nell'esempio seguente vengono creati quattro file utilizzando impostazioni diverse per IBCPSession2::BCPSetBulkMode.</span><span class="sxs-lookup"><span data-stu-id="68588-155">The following sample creates four files using different settings of IBCPSession2::BCPSetBulkMode.</span></span>  
  
```  
  
// compile with: sqlncli11.lib oleaut32.lib ole32.lib  
  
#include <stdio.h>  
#include "sqlncli.h"  
  
IDBInitialize*  g_pIDBInitialize = NULL;  
IBCPSession2 * g_pIBcpSession = NULL;  
class COLEDBPropSet : public DBPROPSET {  
public:  
   COLEDBPropSet() {  
      rgProperties = NULL;  
      cProperties = 0;  
   };  
   COLEDBPropSet(const GUID& guid) {  
      rgProperties = NULL;  
      cProperties = 0;  
      guidPropertySet = guid;  
   };  
   ~COLEDBPropSet() {  
      for ( ULONG i = 0 ; i < cProperties ; i++ )  
         VariantClear(&rgProperties[i].vValue);  
      CoTaskMemFree(rgProperties);  
   }  
   void SetGUID(const GUID& guid) {  
      guidPropertySet = guid;  
   };  
   bool AddProperty(DWORD dwPropertyID, bool bValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID = dwPropertyID;  
      rgProperties[cProperties].vValue.vt = VT_BOOL;  
      rgProperties[cProperties].vValue.boolVal = (bValue) ? VARIANT_TRUE : VARIANT_FALSE;  
      cProperties++;  
      return true;  
   };  
   bool AddProperty(DWORD dwPropertyID, long nValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID  = dwPropertyID;  
      rgProperties[cProperties].vValue.vt     = VT_I4;  
      rgProperties[cProperties].vValue.lVal   = nValue;  
      cProperties++;  
      return true;  
   };  
   bool AddProperty(DWORD dwPropertyID,LPCWSTR szValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID = dwPropertyID;  
      rgProperties[cProperties].vValue.vt = VT_BSTR;  
      rgProperties[cProperties].vValue.bstrVal = SysAllocString(szValue);  
      cProperties++;  
      return true;  
   };  
   bool Add() {  
      DBPROP* p = (DBPROP*)CoTaskMemRealloc(rgProperties, (cProperties + 1) * sizeof(DBPROP));  
      if (p != NULL) {  
         rgProperties = p;  
         rgProperties[cProperties].dwOptions = DBPROPOPTIONS_REQUIRED;  
         rgProperties[cProperties].colid = DB_NULLID;  
         rgProperties[cProperties].vValue.vt = VT_EMPTY;  
         return true;  
      }  
      else  
         return false;  
   };  
};  
  
void OLEDBCleanUp() {  
   if (g_pIDBInitialize) {  
      g_pIDBInitialize->Release();  
      g_pIDBInitialize = NULL;  
   }  
   if (g_pIBcpSession) {  
      g_pIBcpSession->Release();  
      g_pIBcpSession = NULL;  
   }  
}  
  
BOOL MakeOLEDBConnect(LPWSTR  pServer) {  
   BOOL ret = true;  
   IDBProperties * pIDBProperties = NULL;  
   IDBCreateSession * pIDBCreateSession = NULL;  
   COLEDBPropSet PropSet(DBPROPSET_DBINIT);  
   COLEDBPropSet BcpProperty(DBPROPSET_SQLSERVERDATASOURCE);  
   try {  
      HRESULT hr = CoInitializeEx(NULL,COINIT_MULTITHREADED);   
      hr = CoCreateInstance(SQLNCLI_CLSID, NULL, CLSCTX_INPROC_SERVER, IID_IDBInitialize, (LPVOID *)&g_pIDBInitialize);  
      if (FAILED(hr)) {  
         printf("CoCreateInstance failed\n");  
         return false;  
      }  
      PropSet.AddProperty(DBPROP_INIT_DATASOURCE, (LPWSTR)pServer);  
      PropSet.AddProperty(DBPROP_AUTH_INTEGRATED, L"SSPI");  
      hr = g_pIDBInitialize->QueryInterface(IID_IDBProperties, (void**) &pIDBProperties);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->QueryInterface(IID_IDBProperties...) failed\n");  
         throw false;  
      }  
      hr = pIDBProperties->SetProperties(1, &PropSet);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->SetProperties(...) failed\n");  
         throw false;  
      }  
      hr = g_pIDBInitialize->Initialize();  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->Initialize() failed\n");  
         throw false;  
      }  
      BcpProperty.AddProperty(SSPROP_ENABLEFASTLOAD, true);  
      BcpProperty.AddProperty(SSPROP_ENABLEBULKCOPY, true);  
      hr = pIDBProperties->SetProperties(1, &BcpProperty);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->SetProperties() for bcp failed\n");  
         throw false;  
      }  
      hr = g_pIDBInitialize->QueryInterface(IID_IDBCreateSession, (void**) &pIDBCreateSession);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->QueryInterface(IID_IDBCreateSession..) failed\n");  
         throw false;  
      }  
  
      hr = pIDBCreateSession->CreateSession(NULL, IID_IBCPSession2, (IUnknown**) &g_pIBcpSession);  
      if (FAILED(hr)) {  
         printf("g_pIDBCreateSession->CreateSession() failed\n");  
         throw false;  
      }  
   }  
   catch(...) {  
      ret = false;  
   }  
   if (pIDBProperties)  
      pIDBProperties->Release();  
   if (pIDBCreateSession)  
      pIDBCreateSession->Release();  
   return ret;  
}  
  
BOOL BCPSetBulkMode(LPWSTR pszServer, LPTSTR pszQureryOut, char BCPType, LPWSTR pszDataFile) {  
   HRESULThr;  
   if (!MakeOLEDBConnect(pszServer))  
      return false;  
   hr = g_pIBcpSession->BCPInit(NULL, pszDataFile, NULL, BCP_DIRECTION_OUT );   // bcp init for queryout  
   if (FAILED(hr)) {  
      printf("BCP init failed\n");  
      OLEDBCleanUp();  
      return false;  
   }  
   // setbulkmode  
   char ColTerm[] = "\t";  
   char RowTerm[] = "\r\n";  
   wchar_t wColTerm[] = L"\t";  
   wchar_t wRowTerm[] = L"\r\n";  
   BYTE * pColTerm = NULL;  
   int cbColTerm = NULL;  
   BYTE * pRowTerm = 0;  
   int cbRowTerm = 0;  
   int bulkmode = -1;  
  
   if(BCPType == 'c') {   // bcp -c  
      pColTerm = (BYTE*)ColTerm;  
      pRowTerm = (BYTE*)RowTerm;  
      cbColTerm = 1;  
      cbRowTerm = 2;  
      bulkmode = BCP_OUT_CHARACTER_MODE;  
   }  
   else  
      if(BCPType == 'w') {   // bcp -w  
         pColTerm = (BYTE*)wColTerm;  
         pRowTerm = (BYTE*)wRowTerm;  
         cbColTerm = 2;  
         cbRowTerm = 4;  
         bulkmode = BCP_OUT_WIDE_CHARACTER_MODE;  
      }  
      else  
         if (BCPType == 'n')   // bcp -n  
            bulkmode = BCP_OUT_NATIVE_MODE;  
         else  
            if (BCPType == 'N')   // bcp -n  
               bulkmode = BCP_OUT_NATIVE_TEXT_MODE;  
            else {  
               printf("unknown bcp mode\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            hr = g_pIBcpSession->BCPSetBulkMode(bulkmode, pColTerm, cbColTerm, pRowTerm, cbRowTerm);  
            if (FAILED(hr)) {  
               printf("BCPSetBulkMode failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
  
            // set queryout TSQL statement  
            hr = g_pIBcpSession->BCPControl(BCP_OPTION_HINTS, pszQureryOut);  
            if (FAILED(hr)) {  
               printf("BCPControl failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            // bcp copy  
            DBROWCOUNT nRowsInserted = 0;  
            hr = g_pIBcpSession->BCPExec(&nRowsInserted);  
            if (FAILED(hr)) {  
               printf("BCPExec failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            printf("bcp done\n");  
            OLEDBCleanUp();  
            return true;  
}  
  
int main() {  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -c test', 1,2") , 'c', L"bcpc.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -w test', 1,2") , 'w', L"bcpw.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -c test', 1,2") , 'n', L"bcpn.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -w test', 1,2") , 'N', L"bcp_N.dat");  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="68588-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68588-156">See Also</span></span>  
 [<span data-ttu-id="68588-157">IBCPSession2 &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="68588-157">IBCPSession2 &#40;OLE DB&#41;</span></span>](ibcpsession2-ole-db.md)  
  
  
