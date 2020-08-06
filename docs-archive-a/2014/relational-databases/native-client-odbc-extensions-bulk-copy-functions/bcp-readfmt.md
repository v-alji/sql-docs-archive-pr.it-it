---
title: bcp_readfmt | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_readfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_readfmt function
ms.assetid: 654001c8-ae9f-425c-b820-f0191bf89367
author: rothja
ms.author: jroth
ms.openlocfilehash: 37032ec276be8b914d73e834453cc5d87cdedbbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626760"
---
# <a name="bcp_readfmt"></a><span data-ttu-id="30988-102">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="30988-102">bcp_readfmt</span></span>
  <span data-ttu-id="30988-103">Legge una definizione di formato di file di dati dal file di formato specificato.</span><span class="sxs-lookup"><span data-stu-id="30988-103">Reads a data file format definition from the specified format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30988-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30988-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_readfmt (  
HDBC   
hdbc  
,  
LPCTSTR   
szFormatFile  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="30988-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="30988-105">Arguments</span></span>  
 <span data-ttu-id="30988-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="30988-106">*hdbc*</span></span>  
 <span data-ttu-id="30988-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="30988-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="30988-108">*szFormatFile*</span><span class="sxs-lookup"><span data-stu-id="30988-108">*szFormatFile*</span></span>  
 <span data-ttu-id="30988-109">Percorso e nome del file contenente i valori di formato per il file di dati.</span><span class="sxs-lookup"><span data-stu-id="30988-109">Is the path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="30988-110">Restituisce</span><span class="sxs-lookup"><span data-stu-id="30988-110">Returns</span></span>  
 <span data-ttu-id="30988-111">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="30988-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30988-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="30988-112">Remarks</span></span>  
 <span data-ttu-id="30988-113">Dopo `bcp_readfmt` la lettura dei valori di formato, effettua le chiamate appropriate a [bcp_columns](bcp-columns.md) e [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="30988-113">After `bcp_readfmt` reads the format values, it makes the appropriate calls to [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span> <span data-ttu-id="30988-114">L'utente può evitare di analizzare un file di formato ed effettuare queste chiamate.</span><span class="sxs-lookup"><span data-stu-id="30988-114">There is no need for you to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="30988-115">Per salvare in modo permanente un file di formato, chiamare [bcp_writefmt](bcp-writefmt.md).</span><span class="sxs-lookup"><span data-stu-id="30988-115">To persist a format file, call [bcp_writefmt](bcp-writefmt.md).</span></span> <span data-ttu-id="30988-116">Le chiamate a `bcp_readfmt` possono fare riferimento ai formati salvati.</span><span class="sxs-lookup"><span data-stu-id="30988-116">Calls to `bcp_readfmt` can reference saved formats.</span></span> <span data-ttu-id="30988-117">Per ulteriori informazioni, vedere [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="30988-117">For more information, see [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="30988-118">In alternativa, l'utilità di copia bulk (**bcp**) può salvare i formati di dati definiti dall'utente nei file a cui può fare riferimento `bcp_readfmt` .</span><span class="sxs-lookup"><span data-stu-id="30988-118">Alternately, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by `bcp_readfmt`.</span></span> <span data-ttu-id="30988-119">Per ulteriori informazioni sull'utilità **bcp** e sulla struttura dei file di formato dei dati **bcp** , vedere [importazione ed esportazione Bulk di dati &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30988-119">For more information about the **bcp** utility and the structure of **bcp** data format files, see [Bulk Import and Export of Data &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="30988-120">Il `BCPDELAYREADFMT` valore del parametro *eOption* di [bcp_control](bcp-control.md) modifica il comportamento di bcp_readfmt.</span><span class="sxs-lookup"><span data-stu-id="30988-120">The `BCPDELAYREADFMT` value of the *eOption* parameter of [bcp_control](bcp-control.md) modifies the behavior of bcp_readfmt.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30988-121">Il file di formato deve essere stato prodotto dalla versione 4,2 o successiva dell'utilità **bcp** .</span><span class="sxs-lookup"><span data-stu-id="30988-121">The format file must have been produced by version 4.2 or later of the **bcp** utility.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30988-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="30988-122">Example</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("myTable"), _T("myData.csv"),  
   _T("myErrors"),    DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_readfmt(hdbc, _T("myFmtFile.fmt")) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_exec(hdbc, &nRowsProcessed) == SUCCEED)  
   {  
   cout << nRowsProcessed << " rows copied to SQL Server\n";  
   }  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="30988-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30988-123">See Also</span></span>  
 [<span data-ttu-id="30988-124">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="30988-124">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
