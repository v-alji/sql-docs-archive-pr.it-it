---
title: bcp_colptr | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colptr
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colptr function
ms.assetid: 02ece13e-1da3-4f9d-b860-3177e43d2471
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b725ace58ee1768fbca1a433cdea27e3e0e546e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725692"
---
# <a name="bcp_colptr"></a><span data-ttu-id="70469-102">bcp_colptr</span><span class="sxs-lookup"><span data-stu-id="70469-102">bcp_colptr</span></span>
  <span data-ttu-id="70469-103">Imposta l'indirizzo dei dati della variabile di programma per la copia corrente su [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70469-103">Sets the program variable data address for the current copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70469-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70469-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_colptr (  
HDBC   
hdbc  
,  
LPCBYTE   
pData  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="70469-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="70469-105">Arguments</span></span>  
 <span data-ttu-id="70469-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="70469-106">*hdbc*</span></span>  
 <span data-ttu-id="70469-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="70469-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="70469-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="70469-108">*pData*</span></span>  
 <span data-ttu-id="70469-109">Puntatore ai dati da copiare.</span><span class="sxs-lookup"><span data-stu-id="70469-109">Is a pointer to the data to copy.</span></span> <span data-ttu-id="70469-110">Se il tipo di dati associato è un tipo di valore di grandi dimensioni, ad esempio SQLTEXT o SQLIMAGE, *pData* può essere null.</span><span class="sxs-lookup"><span data-stu-id="70469-110">If the bound data type is large value type (such as SQLTEXT or SQLIMAGE), *pData* can be NULL.</span></span> <span data-ttu-id="70469-111">Un valore NULL *pData* indica che i valori di dati Long verranno inviati a SQL Server in blocchi utilizzando [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="70469-111">A NULL *pData* indicates long data values will be sent to SQL Server in chunks using [bcp_moretext](bcp-moretext.md).</span></span>  
  
 <span data-ttu-id="70469-112">Se *pData* è impostato su null e la colonna corrispondente al campo associato non è un tipo di valore di grandi dimensioni, **bcp_colptr** ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="70469-112">If *pData* is set to NULL and the column corresponding to the bound field is not a large value type, **bcp_colptr** fails.</span></span>  
  
 <span data-ttu-id="70469-113">Per ulteriori informazioni sui tipi di valore di grandi dimensioni, vedere [bcp_bind](bcp-bind.md)**.**</span><span class="sxs-lookup"><span data-stu-id="70469-113">For more information on large value types, see [bcp_bind](bcp-bind.md)**.**</span></span>  
  
 <span data-ttu-id="70469-114">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="70469-114">*idxServerCol*</span></span>  
 <span data-ttu-id="70469-115">Posizione ordinale della colonna nella tabella di database in cui vengono copiati i dati.</span><span class="sxs-lookup"><span data-stu-id="70469-115">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="70469-116">La prima colonna di una tabella è la colonna 1.</span><span class="sxs-lookup"><span data-stu-id="70469-116">The first column in a table is column 1.</span></span> <span data-ttu-id="70469-117">La posizione ordinale di una colonna viene segnalata da [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="70469-117">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="70469-118">Restituisce</span><span class="sxs-lookup"><span data-stu-id="70469-118">Returns</span></span>  
 <span data-ttu-id="70469-119">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="70469-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70469-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="70469-120">Remarks</span></span>  
 <span data-ttu-id="70469-121">La funzione **bcp_colptr** consente di modificare l'indirizzo dei dati di origine per una determinata colonna durante la copia dei dati in SQL Server con [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="70469-121">The **bcp_colptr** function allows you to change the address of source data for a particular column when copying data to SQL Server with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
 <span data-ttu-id="70469-122">Inizialmente, il puntatore ai dati utente viene impostato da una chiamata a **bcp_bind**.</span><span class="sxs-lookup"><span data-stu-id="70469-122">Initially, the pointer to user data is set by a call to **bcp_bind**.</span></span> <span data-ttu-id="70469-123">Se l'indirizzo dei dati della variabile di programma cambia tra le chiamate a **bcp_sendrow**, è possibile chiamare **bcp_colptr** per reimpostare il puntatore ai dati.</span><span class="sxs-lookup"><span data-stu-id="70469-123">If the program variable data address changes between calls to **bcp_sendrow**, you can call **bcp_colptr** to reset the pointer to the data.</span></span> <span data-ttu-id="70469-124">La chiamata successiva a **bcp_sendrow** invia i dati indirizzati dalla chiamata al **bcp_colptr**.</span><span class="sxs-lookup"><span data-stu-id="70469-124">The next call to **bcp_sendrow** sends the data addressed by the call to **bcp_colptr**.</span></span>  
  
 <span data-ttu-id="70469-125">Deve essere presente una chiamata di **bcp_colptr** separata per ogni colonna della tabella di cui si desidera modificare l'indirizzo dati.</span><span class="sxs-lookup"><span data-stu-id="70469-125">There must be a separate **bcp_colptr** call for every column in the table whose data address you want to modify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70469-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70469-126">See Also</span></span>  
 [<span data-ttu-id="70469-127">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="70469-127">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
