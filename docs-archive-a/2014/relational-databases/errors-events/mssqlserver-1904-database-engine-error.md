---
title: MSSQLSERVER_1904 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1904 (Database Engine error)
ms.assetid: 2a35d57d-74e2-45a2-8f67-3f2e51d69712
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 568cfe7499c041c2ee6a8ac3698b31698171bece
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627782"
---
# <a name="mssqlserver_1904"></a><span data-ttu-id="b9f93-102">MSSQLSERVER_1904</span><span class="sxs-lookup"><span data-stu-id="b9f93-102">MSSQLSERVER_1904</span></span>
    
## <a name="details"></a><span data-ttu-id="b9f93-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b9f93-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b9f93-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b9f93-104">Product Name</span></span>|<span data-ttu-id="b9f93-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b9f93-105">SQL Server</span></span>|  
|<span data-ttu-id="b9f93-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b9f93-106">Event ID</span></span>|<span data-ttu-id="b9f93-107">1904</span><span class="sxs-lookup"><span data-stu-id="b9f93-107">1904</span></span>|  
|<span data-ttu-id="b9f93-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b9f93-108">Event Source</span></span>|<span data-ttu-id="b9f93-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b9f93-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b9f93-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b9f93-110">Component</span></span>|<span data-ttu-id="b9f93-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b9f93-111">SQLEngine</span></span>|  
|<span data-ttu-id="b9f93-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b9f93-112">Symbolic Name</span></span>|<span data-ttu-id="b9f93-113">KEYCOUNT</span><span class="sxs-lookup"><span data-stu-id="b9f93-113">KEYCOUNT</span></span>|  
|<span data-ttu-id="b9f93-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b9f93-114">Message Text</span></span>|<span data-ttu-id="b9f93-115">Per l'oggetto %S_MSG '%.\*ls' nella tabella '%.\*ls' sono presenti %d nomi di colonna nell'elenco chiavi %S_MSG.</span><span class="sxs-lookup"><span data-stu-id="b9f93-115">The %S_MSG '%.\*ls' on table '%.\*ls' has %d column names in %S_MSG key list.</span></span> <span data-ttu-id="b9f93-116">Il limite massimo per l'elenco delle colonne chiave per indici o statistiche è di %d.</span><span class="sxs-lookup"><span data-stu-id="b9f93-116">The maximum limit for index or statistics key column list is %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b9f93-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b9f93-117">Explanation</span></span>  
 <span data-ttu-id="b9f93-118">Il numero di colonne chiave nell'elenco per le statistiche o l'indice specificato supera il numero massimo di colonne consentite.</span><span class="sxs-lookup"><span data-stu-id="b9f93-118">The key column list for the specified index or statistics exceeds the maximum number of columns allowed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b9f93-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b9f93-119">User Action</span></span>  
 <span data-ttu-id="b9f93-120">Modificare l'elenco delle colonne chiave in modo da non includere un numero di colonne superiore a quello specificato.</span><span class="sxs-lookup"><span data-stu-id="b9f93-120">Modify the key column list to include no more than the specified maximum number of columns.</span></span>  
  
 <span data-ttu-id="b9f93-121">Per gli indici non cluster, utilizzare la clausola INCLUDE nell'istruzione CREATE INDEX per aggiungere colonne all'indice come colonne non chiave.</span><span class="sxs-lookup"><span data-stu-id="b9f93-121">For nonclustered indexes, consider using the INCLUDE clause in the CREATE INDEX statement to add columns to the index as nonkey columns.</span></span> <span data-ttu-id="b9f93-122">In questo modo si evita di superare la limitazione relativa alla dimensione di indice corrente che consente al massimo 16 colonne chiave.</span><span class="sxs-lookup"><span data-stu-id="b9f93-122">This method avoids exceeding the current index size limitation of a maximum of 16 key columns.</span></span> <span data-ttu-id="b9f93-123">Per altre informazioni, vedere [Creare indici con colonne incluse](../indexes/create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="b9f93-123">For more information, see [Create Indexes with Included Columns](../indexes/create-indexes-with-included-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f93-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9f93-124">See Also</span></span>  
 <span data-ttu-id="b9f93-125">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b9f93-125">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="b9f93-126">CREATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b9f93-126">CREATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-statistics-transact-sql)  
  
  
