---
title: MSSQLSERVER_360 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 360 (Database Engine error)
ms.assetid: e2b7c1b2-3679-4206-9b25-6bd55ef96a2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b30311d7f55231c1e7a6d5969d49c5d1bc07a848
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627282"
---
# <a name="mssqlserver_360"></a><span data-ttu-id="d44a7-102">MSSQLSERVER_360</span><span class="sxs-lookup"><span data-stu-id="d44a7-102">MSSQLSERVER_360</span></span>
    
## <a name="details"></a><span data-ttu-id="d44a7-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d44a7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d44a7-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="d44a7-104">Product Name</span></span>|<span data-ttu-id="d44a7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d44a7-105">SQL Server</span></span>|  
|<span data-ttu-id="d44a7-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="d44a7-106">Event ID</span></span>|<span data-ttu-id="d44a7-107">360</span><span class="sxs-lookup"><span data-stu-id="d44a7-107">360</span></span>|  
|<span data-ttu-id="d44a7-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="d44a7-108">Event Source</span></span>|<span data-ttu-id="d44a7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d44a7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d44a7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d44a7-110">Component</span></span>|<span data-ttu-id="d44a7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d44a7-111">SQLEngine</span></span>|  
|<span data-ttu-id="d44a7-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="d44a7-112">Symbolic Name</span></span>|<span data-ttu-id="d44a7-113">DML_UPDATE_SPARSE_AND_COLSET</span><span class="sxs-lookup"><span data-stu-id="d44a7-113">DML_UPDATE_SPARSE_AND_COLSET</span></span>|  
|<span data-ttu-id="d44a7-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="d44a7-114">Message Text</span></span>|<span data-ttu-id="d44a7-115">L'elenco delle colonne di destinazione di un'istruzione INSERT, UPDATE o MERGE non può includere sia una colonna di tipo sparse sia il set di colonne che contiene tale colonna.</span><span class="sxs-lookup"><span data-stu-id="d44a7-115">The target column list of an INSERT, UPDATE, or MERGE statement cannot contain both a sparse column and the column set that contains the sparse column.</span></span> <span data-ttu-id="d44a7-116">Riscrivere l'istruzione in modo che includa la colonna di tipo sparse o il set di colonne, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="d44a7-116">Rewrite the statement to include either the sparse column or the column set, but not both.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d44a7-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="d44a7-117">Explanation</span></span>  
 <span data-ttu-id="d44a7-118">Un set di colonne è una rappresentazione XML non tipizzata che combina alcune colonne di una tabella in un output strutturato.</span><span class="sxs-lookup"><span data-stu-id="d44a7-118">A column set is an untyped XML representation that combines some columns of a table into a structured output.</span></span> <span data-ttu-id="d44a7-119">È stato effettuato un tentativo di modificare sia il set di colonne che una colonna inclusa nel set, provocando due riferimenti alla stessa colonna.</span><span class="sxs-lookup"><span data-stu-id="d44a7-119">An attempt was made to modify both the column set and a column that is included in the column set, causing two references to the same column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d44a7-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="d44a7-120">User Action</span></span>  
 <span data-ttu-id="d44a7-121">Riscrivere l'istruzione in modo che includa i riferimenti o alla colonna oppure al set di colonne, ma non a entrambi.</span><span class="sxs-lookup"><span data-stu-id="d44a7-121">Rewrite the statement to include references to either the column or the column set, but do not include both in the statement.</span></span>  
  
  
