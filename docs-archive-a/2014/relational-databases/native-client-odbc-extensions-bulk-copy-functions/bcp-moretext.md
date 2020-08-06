---
title: bcp_moretext | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_moretext
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_moretext function
ms.assetid: 23e98015-a8e4-4434-9b3f-9c7350cf965f
author: rothja
ms.author: jroth
ms.openlocfilehash: 00c0eb1c8739e94380b12034cebc70d8e22b79c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626763"
---
# <a name="bcp_moretext"></a><span data-ttu-id="baa16-102">bcp_moretext</span><span class="sxs-lookup"><span data-stu-id="baa16-102">bcp_moretext</span></span>
  <span data-ttu-id="baa16-103">Invia parte di un valore del tipo di dati Long a lunghezza variabile a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa16-103">Sends part of a long, variable-length data type value to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baa16-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="baa16-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_moretext (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
LPCBYTE   
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="baa16-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="baa16-105">Arguments</span></span>  
 <span data-ttu-id="baa16-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="baa16-106">*hdbc*</span></span>  
 <span data-ttu-id="baa16-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="baa16-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="baa16-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="baa16-108">*cbData*</span></span>  
 <span data-ttu-id="baa16-109">Numero di byte di dati copiati in SQL Server dai dati a cui viene fatto riferimento da *pData*.</span><span class="sxs-lookup"><span data-stu-id="baa16-109">Is the number of bytes of data being copied to SQL Server from the data referenced by *pData*.</span></span> <span data-ttu-id="baa16-110">Un valore di SQL_NULL_DATA indica NULL.</span><span class="sxs-lookup"><span data-stu-id="baa16-110">A value of SQL_NULL_DATA indicates NULL.</span></span>  
  
 <span data-ttu-id="baa16-111">*pData*</span><span class="sxs-lookup"><span data-stu-id="baa16-111">*pData*</span></span>  
 <span data-ttu-id="baa16-112">Puntatore al blocco di dati Long a lunghezza variabile supportati da inviare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="baa16-112">Is a pointer to the supported, long, variable-length data chunk to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="returns"></a><span data-ttu-id="baa16-113">Restituisce</span><span class="sxs-lookup"><span data-stu-id="baa16-113">Returns</span></span>  
 <span data-ttu-id="baa16-114">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="baa16-114">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baa16-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="baa16-115">Remarks</span></span>  
 <span data-ttu-id="baa16-116">Questa funzione può essere utilizzata in combinazione con [bcp_bind](bcp-bind.md) e [bcp_sendrow](bcp-sendrow.md) per copiare i valori dei dati Long a lunghezza variabile per SQL Server in diversi blocchi più piccoli.</span><span class="sxs-lookup"><span data-stu-id="baa16-116">This function can be used in conjunction with [bcp_bind](bcp-bind.md) and [bcp_sendrow](bcp-sendrow.md) to copy long, variable-length data values to SQL Server in a number of smaller chunks.</span></span> <span data-ttu-id="baa16-117">**bcp_moretext** può essere utilizzato con colonne con i tipi di dati SQL Server seguenti: `text` , `ntext` , `image` , `varchar(max)` , `nvarchar(max)` , `varbinary(max)` , tipo definito dall'utente (UDT) e XML.</span><span class="sxs-lookup"><span data-stu-id="baa16-117">**bcp_moretext** can be used with columns that have the following SQL Server data types: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, user-defined type (UDT), and XML.</span></span> <span data-ttu-id="baa16-118">**bcp_moretext** non supporta le conversioni dei dati, i dati forniti devono corrispondere al tipo di dati della colonna di destinazione.</span><span class="sxs-lookup"><span data-stu-id="baa16-118">**bcp_moretext** does not support data conversions, the data supplied must match the data type of the target column.</span></span>  
  
 <span data-ttu-id="baa16-119">Se **bcp_bind** viene chiamato con un parametro *pData* non null per i tipi di dati supportati da **bcp_moretext**, `bcp_sendrow` Invia l'intero valore di dati, indipendentemente dalla lunghezza.</span><span class="sxs-lookup"><span data-stu-id="baa16-119">If **bcp_bind** is called with a nonNULL *pData* parameter for data types that are supported by **bcp_moretext**, `bcp_sendrow` sends the entire data value, regardless of length.</span></span> <span data-ttu-id="baa16-120">Se, tuttavia, **bcp_bind** dispone di un parametro *pData* null per i tipi di dati supportati, è possibile utilizzare **bcp_moretext** per copiare i dati immediatamente dopo una restituzione corretta da per `bcp_sendrow` indicare che tutte le colonne associate con dati presenti sono state elaborate.</span><span class="sxs-lookup"><span data-stu-id="baa16-120">If, however, **bcp_bind** has a NULL *pData* parameter for supported data types, **bcp_moretext** can be used to copy data immediately after a successful return from `bcp_sendrow` indicating that any bound columns with data present have been processed.</span></span>  
  
 <span data-ttu-id="baa16-121">Se si utilizza **bcp_moretext** per inviare una colonna con tipo di dati supportato in una riga, è necessario utilizzarla anche per inviare tutte le altre colonne con tipo di dati supportato nella riga.</span><span class="sxs-lookup"><span data-stu-id="baa16-121">If you use **bcp_moretext** to send one supported data type column in a row, you must also use it to send all other supported data type columns in the row.</span></span> <span data-ttu-id="baa16-122">Non è possibile ignorare alcuna colonna.</span><span class="sxs-lookup"><span data-stu-id="baa16-122">No columns may be skipped.</span></span> <span data-ttu-id="baa16-123">I tipi di dati supportati sono SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT e SQLXML.</span><span class="sxs-lookup"><span data-stu-id="baa16-123">Supported data types are SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT and SQLXML.</span></span> <span data-ttu-id="baa16-124">Anche SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY e SQLVARBINARY rientrano in questa categoria se la colonna è di tipo varchar(max), nvarchar(max) o varbinary(max), rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="baa16-124">SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY and SQLVARBINARY also fall into this category if the column is a varchar(max), nvarchar(max) or varbinary(max), respectively.</span></span>  
  
 <span data-ttu-id="baa16-125">La chiamata di **bcp_bind** o [bcp_collen](bcp-collen.md) imposta la lunghezza totale di tutte le parti di dati da copiare nella colonna SQL Server.</span><span class="sxs-lookup"><span data-stu-id="baa16-125">Calling either **bcp_bind** or [bcp_collen](bcp-collen.md) sets the total length of all data parts to be copied to the SQL Server column.</span></span> <span data-ttu-id="baa16-126">Un tentativo di invio SQL Server un numero di byte maggiore di quello specificato nella chiamata a **bcp_bind** o `bcp_collen` genera un errore.</span><span class="sxs-lookup"><span data-stu-id="baa16-126">An attempt to send SQL Server more bytes than specified in the call to **bcp_bind** or `bcp_collen` generates an error.</span></span> <span data-ttu-id="baa16-127">Questo errore si verifica, ad esempio, in un'applicazione che ha utilizzato per `bcp_collen` impostare la lunghezza dei dati disponibili per una `text` colonna SQL Server su 4500, quindi chiamata **bcp_moretext** cinque volte, indicando a ogni chiamata che la lunghezza del buffer di dati era 1000 byte.</span><span class="sxs-lookup"><span data-stu-id="baa16-127">This error would arise, for example, in an application which used `bcp_collen` to set the length of available data for an SQL Server `text` column to 4500, then called **bcp_moretext** five times while indicating on each call that the data buffer length was 1000 bytes long.</span></span>  
  
 <span data-ttu-id="baa16-128">Se una riga copiata contiene più di una colonna Long a lunghezza variabile, **bcp_moretext** invia prima i dati alla colonna con la numerazione ordinale più bassa, seguita dalla successiva colonna con numerazione ordinale più bassa e così via.</span><span class="sxs-lookup"><span data-stu-id="baa16-128">If a copied row contains more than one long, variable-length column, **bcp_moretext** first sends its data to the lowest ordinally numbered column, followed by the next lowest ordinally numbered column, and so on.</span></span> <span data-ttu-id="baa16-129">Una corretta impostazione della lunghezza totale dei dati previsti è importante.</span><span class="sxs-lookup"><span data-stu-id="baa16-129">Correct setting of the total length of expected data is important.</span></span> <span data-ttu-id="baa16-130">Non è possibile segnalare, al di fuori dell'impostazione della lunghezza, che tutti i dati per una colonna sono stati ricevuti dalla copia bulk.</span><span class="sxs-lookup"><span data-stu-id="baa16-130">There is no way to signal, outside of the length setting, that all data for a column has been received by bulk copy.</span></span>  
  
 <span data-ttu-id="baa16-131">Quando si `var(max)` inviano valori al server utilizzando bcp_sendrow e bcp_moretext, non è necessario chiamare bcp_collen per impostare la lunghezza della colonna.</span><span class="sxs-lookup"><span data-stu-id="baa16-131">When `var(max)` values are sent to the server using bcp_sendrow and bcp_moretext, it is not necessary to call bcp_collen to set the column length.</span></span> <span data-ttu-id="baa16-132">Al contrario, solo per questi tipi, il valore viene terminato chiamando bcp_sendrow con una lunghezza pari a zero.</span><span class="sxs-lookup"><span data-stu-id="baa16-132">Instead, for these types only, the value is terminated by calling bcp_sendrow with a length of zero.</span></span>  
  
 <span data-ttu-id="baa16-133">Un'applicazione in genere chiama `bcp_sendrow` e **bcp_moretext** all'interno dei cicli per inviare un certo numero di righe di dati.</span><span class="sxs-lookup"><span data-stu-id="baa16-133">An application normally calls `bcp_sendrow` and **bcp_moretext** within loops to send a number of rows of data.</span></span> <span data-ttu-id="baa16-134">Ecco una descrizione di come eseguire questa operazione per una tabella contenente due `text` colonne:</span><span class="sxs-lookup"><span data-stu-id="baa16-134">Here's an outline of how to do this for a table containing two `text` columns:</span></span>  
  
```  
while (there are still rows to send)  
{  
bcp_sendrow(...);  
  
for (all the data in the first varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
for (all the data in the second varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
}  
  
```  
  
## <a name="example"></a><span data-ttu-id="baa16-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="baa16-135">Example</span></span>  
 <span data-ttu-id="baa16-136">Questo esempio illustra come usare **bcp_moretext** con **bcp_bind** e `bcp_sendrow` :</span><span class="sxs-lookup"><span data-stu-id="baa16-136">This example shows how to use **bcp_moretext** with **bcp_bind** and `bcp_sendrow`:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      idRow = 5;  
char*      pPart1 = "This text value isn't very long,";  
char*      pPart2 = " but it's broken into three parts";  
char*      pPart3 = " anyhow.";  
DBINT      cbAllParts;  
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
if (bcp_init(hdbc, "comdb..articles", NULL, NULL, DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idRow, 0, SQL_VARLEN_DATA, NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
cbAllParts = (DBINT) (strnlen(pPart1, sizeof(pPart1) + 1) + strnlen(pPart2, sizeof(pPart2) + 1) + strnlen(pPart3, sizeof(pPart3) + 1));  
if (bcp_bind(hdbc, NULL, 0, cbAllParts, NULL, 0, SQLTEXT, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Send this row, with the text value broken into three chunks.   
if (bcp_sendrow(hdbc) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart1, sizeof(pPart1) + 1), pPart1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart2, sizeof(pPart2) + 1), pPart2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart3, sizeof(pPart3) + 1), pPart3) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// All done. Get the number of rows processed (should be one).  
nRowsProcessed = bcp_done(hdbc);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="baa16-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baa16-137">See Also</span></span>  
 [<span data-ttu-id="baa16-138">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="baa16-138">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
