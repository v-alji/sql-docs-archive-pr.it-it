---
title: bcp_setbulkmode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bcp_setbulkmode function
ms.assetid: de56f206-1f7e-4c03-bf22-da9c7f9f4433
author: rothja
ms.author: jroth
ms.openlocfilehash: 1b7a68dfb3c868422b2e01cccf511a623d3afe52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629806"
---
# <a name="bcp_setbulkmode"></a><span data-ttu-id="4790d-102">bcp_setbulkmode</span><span class="sxs-lookup"><span data-stu-id="4790d-102">bcp_setbulkmode</span></span>
  <span data-ttu-id="4790d-103">bcp_setbulkmode consente di specificare il formato della colonna in un'operazione di copia bulk, impostando tutti gli attributi di colonna in una singola chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="4790d-103">bcp_setbulkmode lets you specify the column format in a bulk copy operation, setting all the column attributes in a single function call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4790d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4790d-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_setbulkmode (  
   HDBC   
hdbc  
,  
   INT   
property  
,  
   void *   
pField  
,  
   INT   
cbField  
,  
   void *   
pRow  
,  
   INT   
cbRow  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="4790d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4790d-105">Arguments</span></span>  
 <span data-ttu-id="4790d-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="4790d-106">*hdbc*</span></span>  
 <span data-ttu-id="4790d-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="4790d-107">The bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="4790d-108">*property*</span><span class="sxs-lookup"><span data-stu-id="4790d-108">*property*</span></span>  
 <span data-ttu-id="4790d-109">Costante di tipo BYTE.</span><span class="sxs-lookup"><span data-stu-id="4790d-109">A constant of type BYTE.</span></span> <span data-ttu-id="4790d-110">Per un elenco di costanti, vedere la tabella nella sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="4790d-110">See the table in the Remarks section for a list of the constants.</span></span>  
  
 <span data-ttu-id="4790d-111">*pField*</span><span class="sxs-lookup"><span data-stu-id="4790d-111">*pField*</span></span>  
 <span data-ttu-id="4790d-112">Puntatore al valore del carattere di terminazione del campo.</span><span class="sxs-lookup"><span data-stu-id="4790d-112">The pointer to the field terminator value.</span></span>  
  
 <span data-ttu-id="4790d-113">*cbField*</span><span class="sxs-lookup"><span data-stu-id="4790d-113">*cbField*</span></span>  
 <span data-ttu-id="4790d-114">Lunghezza, in byte, del valore del carattere di terminazione del campo.</span><span class="sxs-lookup"><span data-stu-id="4790d-114">The length (in bytes) of the field terminator value.</span></span>  
  
 <span data-ttu-id="4790d-115">*pRow*</span><span class="sxs-lookup"><span data-stu-id="4790d-115">*pRow*</span></span>  
 <span data-ttu-id="4790d-116">Puntatore al valore del carattere di terminazione della riga.</span><span class="sxs-lookup"><span data-stu-id="4790d-116">The pointer to the row terminator value.</span></span>  
  
 <span data-ttu-id="4790d-117">*cbRow*</span><span class="sxs-lookup"><span data-stu-id="4790d-117">*cbRow*</span></span>  
 <span data-ttu-id="4790d-118">Lunghezza, in byte, del valore del carattere di terminazione della riga.</span><span class="sxs-lookup"><span data-stu-id="4790d-118">The length in bytes of the row terminator value.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="4790d-119">Restituisce</span><span class="sxs-lookup"><span data-stu-id="4790d-119">Returns</span></span>  
 <span data-ttu-id="4790d-120">SUCCEED o FAIL</span><span class="sxs-lookup"><span data-stu-id="4790d-120">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4790d-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4790d-121">Remarks</span></span>  
 <span data-ttu-id="4790d-122">bcp_setbulkmode può essere utilizzato per eseguire una copia bulk da una query o da una tabella.</span><span class="sxs-lookup"><span data-stu-id="4790d-122">bcp_setbulkmode can be used to bulk copy out of either a query or a table.</span></span> <span data-ttu-id="4790d-123">Quando bcp_setbulkmode viene utilizzata per la copia bulk di un'istruzione di query, è necessario chiamare il metodo prima di chiamare bcp_control con BCP_HINT.</span><span class="sxs-lookup"><span data-stu-id="4790d-123">When bcp_setbulkmode is used to bulk copy out a query statement, it must be called before calling bcp_control with BCP_HINT.</span></span>  
  
 <span data-ttu-id="4790d-124">bcp_setbulkmode è un'alternativa all'uso di [bcp_setcolfmt](bcp-setcolfmt.md) e [bcp_columns](bcp-columns.md), che consentono solo di specificare il formato di una colonna per ogni chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="4790d-124">bcp_setbulkmode is an alternative to using [bcp_setcolfmt](bcp-setcolfmt.md) and [bcp_columns](bcp-columns.md), which only let you specify the format of one column per function call.</span></span>  
  
 <span data-ttu-id="4790d-125">Nella tabella seguente sono elencate le costanti per il parametro *property*.</span><span class="sxs-lookup"><span data-stu-id="4790d-125">The following table lists the constants for the *property* parameter.</span></span>  
  
|<span data-ttu-id="4790d-126">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4790d-126">Property</span></span>|<span data-ttu-id="4790d-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4790d-127">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="4790d-128">BCP_OUT_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="4790d-128">BCP_OUT_CHARACTER_MODE</span></span>|<span data-ttu-id="4790d-129">Specifica la modalità di output carattere.</span><span class="sxs-lookup"><span data-stu-id="4790d-129">Specifies character output mode.</span></span><br /><br /> <span data-ttu-id="4790d-130">Corrisponde all'opzione-c in BCP.EXE e a bcp_setcolfmt con la `BCP_FMT_TYPE` proprietà impostata su `SQLCHARACTER` .</span><span class="sxs-lookup"><span data-stu-id="4790d-130">Corresponds to the -c option in BCP.EXE, and to bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLCHARACTER`.</span></span>|  
|<span data-ttu-id="4790d-131">BCP_OUT_WIDE_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="4790d-131">BCP_OUT_WIDE_CHARACTER_MODE</span></span>|<span data-ttu-id="4790d-132">Specifica la modalità di output Unicode.</span><span class="sxs-lookup"><span data-stu-id="4790d-132">Specifies Unicode output mode.</span></span><br /><br /> <span data-ttu-id="4790d-133">Corrisponde all'opzione-w in BCP.EXE e bcp_setcolfmt con la `BCP_FMT_TYPE` proprietà impostata su `SQLNCHAR` .</span><span class="sxs-lookup"><span data-stu-id="4790d-133">Corresponds to the -w option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLNCHAR`.</span></span>|  
|<span data-ttu-id="4790d-134">BCP_OUT_NATIVE_TEXT_MODE</span><span class="sxs-lookup"><span data-stu-id="4790d-134">BCP_OUT_NATIVE_TEXT_MODE</span></span>|<span data-ttu-id="4790d-135">Specifica tipi nativi per i tipi non carattere e Unicode per i tipi carattere.</span><span class="sxs-lookup"><span data-stu-id="4790d-135">Specifies native types for non-character types and Unicode for character types.</span></span><br /><br /> <span data-ttu-id="4790d-136">Corrisponde all'opzione-N in BCP.EXE e bcp_setcolfmt con la `BCP_FMT_TYPE` proprietà impostata su `SQLNCHAR` se il tipo di colonna è una stringa (impostazione predefinita se non è una stringa).</span><span class="sxs-lookup"><span data-stu-id="4790d-136">Corresponds to the -N option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLNCHAR` if the column type is a string (default if not a string).</span></span>|  
|<span data-ttu-id="4790d-137">BCP_OUT_NATIVE_MODE</span><span class="sxs-lookup"><span data-stu-id="4790d-137">BCP_OUT_NATIVE_MODE</span></span>|<span data-ttu-id="4790d-138">Specifica tipi di database nativi.</span><span class="sxs-lookup"><span data-stu-id="4790d-138">Specifies native database types.</span></span><br /><br /> <span data-ttu-id="4790d-139">Corrisponde all'opzione-n in BCP.EXE e bcp_setcolfmt con la `BCP_FMT_TYPE` proprietà impostata sul valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="4790d-139">Corresponds to the -n option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to the default.</span></span>|  
  
 <span data-ttu-id="4790d-140">Non usare bcp_setbulkmode con una sequenza di chiamate di funzione che include bcp_setcolfmt, bcp_control e bcp_readfmt.</span><span class="sxs-lookup"><span data-stu-id="4790d-140">You should not use bcp_setbulkmode with a sequence of function calls that includes bcp_setcolfmt, bcp_control, and bcp_readfmt.</span></span> <span data-ttu-id="4790d-141">Ad esempio, non è necessario chiamare bcp_control (BCPTEXTFILE) e bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="4790d-141">For example, you should not call bcp_control(BCPTEXTFILE) and bcp_setbulkmode.</span></span>  
  
 <span data-ttu-id="4790d-142">È possibile chiamare bcp_control e bcp_setbulkmode per le opzioni di bcp_control che non sono in conflitto con bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="4790d-142">You can call bcp_control and bcp_setbulkmode for bcp_control options that do not conflict with bcp_setbulkmode.</span></span> <span data-ttu-id="4790d-143">Ad esempio, è possibile chiamare bcp_control (BCPFIRST) e bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="4790d-143">For example, you can call bcp_control(BCPFIRST) and bcp_setbulkmode.</span></span>  
  
 <span data-ttu-id="4790d-144">Se si tenta di chiamare bcp_setbulkmode con una sequenza di chiamate di funzione che include bcp_setcolfmt, bcp_control e bcp_readfmt, una delle chiamate di funzione restituirà un errore di sequenza.</span><span class="sxs-lookup"><span data-stu-id="4790d-144">If you attempt to call bcp_setbulkmode with a sequence of function calls that includes bcp_setcolfmt, bcp_control, and bcp_readfmt, one of the function calls will return a sequence error failure.</span></span> <span data-ttu-id="4790d-145">Se si sceglie di correggere l'errore, chiamare bcp_init per reimpostare tutte le impostazioni e ricominciare.</span><span class="sxs-lookup"><span data-stu-id="4790d-145">If you choose to correct the failure, call bcp_init to reset all the settings and start over.</span></span>  
  
 <span data-ttu-id="4790d-146">Nella tabella seguente sono illustrati alcuni esempi di chiamate di funzione che comportano un errore nella sequenza della funzione:</span><span class="sxs-lookup"><span data-stu-id="4790d-146">The following table presents some examples of function calls that result in a function sequence error:</span></span>  
  
 <span data-ttu-id="4790d-147">Sequenza di chiamata</span><span class="sxs-lookup"><span data-stu-id="4790d-147">Call sequence</span></span>  
  
```  
bcp_init("table", DB_IN);  
bcp_setbulkmode();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_setbulkmode();  
bcp_readfmt();  
```  
  
```  
bcp_init(NULL, DB_OUT);  
bcp_control(BCPHINTS, "select ...");  
bcp_setbulkmode();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_setbulkmode();  
bcp_setcolfmt();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_readfmt();  
bcp_setcolfmt();  
```  
  
```  
bcp_init(NULL, DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_setbulkmode();  
bcp_control(BCPHINTS, "select ...");  
bcp_readfmt();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_columns();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_setcolfmt();  
```  
  
## <a name="example"></a><span data-ttu-id="4790d-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="4790d-148">Example</span></span>  
 <span data-ttu-id="4790d-149">Nell'esempio seguente vengono creati quattro file utilizzando impostazioni diverse per bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="4790d-149">The following sample creates four files using different settings of bcp_setbulkmode.</span></span>  
  
```  
// compile with: sqlncli11.lib odbc32.lib  
  
#include <windows.h>  
#include <stdio.h>  
#include <tchar.h>  
#include <sqlext.h>  
#include "sqlncli.h"  
  
// Global variables  
SQLHENV g_hEnv = NULL;  
SQLHDBC g_hDbc = NULL;  
  
void ODBCCleanUp() {  
   if (g_hDbc) {  
      SQLDisconnect(g_hDbc);  
      SQLFreeHandle(SQL_HANDLE_DBC, g_hDbc);  
      g_hDbc = NULL;  
   }  
   if (g_hEnv) {  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      g_hEnv = NULL;  
   }  
}  
  
BOOL MakeODBCConnection(TCHAR * pszServer) {  
   TCHAR szConnectionString[500];  
   TCHAR szOutConnectionString[500];  
   SQLSMALLINT iLen;  
   SQLRETURN rc;  
  
   _sntprintf_s(szConnectionString, 500, TEXT("DRIVER={SQL Server Native Client 11.0};Server=%s;Trusted_connection=yes;"), pszServer);  
   rc = SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HANDLE,&g_hEnv);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLAllocHandle(SQL_HANDLE_ENV...) failed\n");  
      return false;  
   }  
   rc = SQLSetEnvAttr(g_hEnv,SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, SQL_IS_UINTEGER);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLSetEnvAttr failed\n");  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      return false;  
   }  
   rc = SQLAllocHandle( SQL_HANDLE_DBC, g_hEnv , &g_hDbc);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLAllocHandle(SQL_HANDLE_DBC...) failed\n");  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      return false;  
   }  
   // Enable BCP  
   rc = SQLSetConnectAttr(g_hDbc, SQL_COPT_SS_BCP, (SQLPOINTER)SQL_BCP_ON, SQL_IS_INTEGER);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLSetConnectAttr(.. SQL_COPT_SS_BCP, (SQLPOINTER)SQL_BCP_ON ...) failed\n");  
      ODBCCleanUp();  
      return false;  
   }  
   // connecting ...  
   rc = SQLDriverConnect(g_hDbc,NULL, (SQLTCHAR*)szConnectionString, SQL_NTS, (SQLTCHAR*)szOutConnectionString, 500, &iLen, SQL_DRIVER_NOPROMPT);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLDriverConnect(SQL_HANDLE_DBC...) failed\n");  
      ODBCCleanUp();  
      return false;  
   }  
   return true;  
}  
  
BOOL BCPSetBulkMode(TCHAR * pszServer, TCHAR * pszQureryOut, char BCPType, TCHAR * pszDataFile) {  
   SQLRETURN rc;  
  
   if (!MakeODBCConnection(pszServer))  
      return false;  
   rc = bcp_init(g_hDbc, NULL, pszDataFile, NULL, DB_OUT);   // bcp init for queryout  
   if (SUCCEED != rc) {  
      printf("bcp_init failed\n");  
      ODBCCleanUp();  
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
  
   if (BCPType == 'c') {   // bcp -c  
      pColTerm = (BYTE*)ColTerm;  
      pRowTerm = (BYTE*)RowTerm;  
      cbColTerm = 1;  
      cbRowTerm = 2;  
      bulkmode = BCP_OUT_CHARACTER_MODE;  
   }  
   else  
      if (BCPType == 'w') {   // bcp -w   
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
               ODBCCleanUp();  
               return false;  
            }  
            rc = bcp_setbulkmode(g_hDbc, bulkmode, pColTerm, cbColTerm, pRowTerm, cbRowTerm);  
            if (SUCCEED != rc) {  
               printf("bcp_setbulkmode failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            // set queryout TSQL statement  
            rc = bcp_control(g_hDbc, BCPHINTS , pszQureryOut);  
            if (SUCCEED != rc) {  
               printf("bcp_control(..BCP_OPTION_HINTS..) failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            // bcp copy  
            DBINT nRowsInserted = 0;  
            rc = bcp_exec(g_hDbc, &nRowsInserted);  
            if (SUCCEED != rc) {  
               printf("bcp_exec failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            printf("bcp done\n");  
            ODBCCleanUp();  
            return true;  
}  
  
int main() {  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -c test', 1,2") , 'c', TEXT("bcpc.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -w test', 1,2") , 'w', TEXT("bcpw.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -c test', 1,2") , 'n', TEXT("bcpn.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -w test', 1,2") , 'N', TEXT("bcp_N.dat"));  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4790d-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4790d-150">See Also</span></span>  
 [<span data-ttu-id="4790d-151">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="4790d-151">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
