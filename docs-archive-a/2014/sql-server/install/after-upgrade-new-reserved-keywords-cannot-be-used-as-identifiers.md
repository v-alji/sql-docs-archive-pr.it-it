---
title: Dopo l'aggiornamento, le nuove parole chiave riservate non possono essere usate come identificatori | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- keywords [SQL Server], after upgrade
- keywords [SQL Server], reserved
- keywords [SQL Server]
ms.assetid: cb242081-54f8-4273-a8ef-52f3751c25ef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 36f7f8cadcba5e114feee4a3c42de6f40070ce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628243"
---
# <a name="after-upgrade-new-reserved-keywords-cannot-be-used-as-identifiers"></a><span data-ttu-id="48794-102">Dopo l'aggiornamento, le parole chiave riservate non possono essere utilizzate come identificatori.</span><span class="sxs-lookup"><span data-stu-id="48794-102">After upgrade, new reserved keywords cannot be used as identifiers</span></span>
  <span data-ttu-id="48794-103">È stato rilevato l'utilizzo di parole che sono parole chiave riservate.</span><span class="sxs-lookup"><span data-stu-id="48794-103">Upgrade Advisor detected the use of words that are reserved keywords.</span></span> <span data-ttu-id="48794-104">Una parola chiave riservata non può essere utilizzata come identificatore o nome di oggetto a meno che il nome non sia delimitato.</span><span class="sxs-lookup"><span data-stu-id="48794-104">A reserved keyword cannot be used as an identifier or object name unless the name is delimited.</span></span>  
  
## <a name="component"></a><span data-ttu-id="48794-105">Componente</span><span class="sxs-lookup"><span data-stu-id="48794-105">Component</span></span>  
 <span data-ttu-id="48794-106">Motore di database</span><span class="sxs-lookup"><span data-stu-id="48794-106">Database Engine</span></span>  
  
## <a name="description"></a><span data-ttu-id="48794-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48794-107">Description</span></span>  
 <span data-ttu-id="48794-108">A livello di compatibilità 90 o inferiore, le parole seguenti non sono parole chiave riservate e possono essere utilizzate come identificatori o nomi di oggetto negli script [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48794-108">At compatibility level 90 or lower, the following words are not reserved keywords and can be used as identifiers or object names in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="48794-109">A livello di compatibilità 100, tali parole sono parole chiave completamente riservate e non devono essere utilizzate con identificatori o nomi di oggetto.</span><span class="sxs-lookup"><span data-stu-id="48794-109">At compatibility level 100, these words are fully reserved keywords and should not be used as identifiers or object names.</span></span>  
  
-   <span data-ttu-id="48794-110">EXTERNAL</span><span class="sxs-lookup"><span data-stu-id="48794-110">EXTERNAL</span></span>  
  
-   <span data-ttu-id="48794-111">MERGE</span><span class="sxs-lookup"><span data-stu-id="48794-111">MERGE</span></span>  
  
-   <span data-ttu-id="48794-112">PIVOT</span><span class="sxs-lookup"><span data-stu-id="48794-112">PIVOT</span></span>  
  
-   <span data-ttu-id="48794-113">REVERT</span><span class="sxs-lookup"><span data-stu-id="48794-113">REVERT</span></span>  
  
-   <span data-ttu-id="48794-114">STOPLIST</span><span class="sxs-lookup"><span data-stu-id="48794-114">STOPLIST</span></span>  
  
-   <span data-ttu-id="48794-115">TABLESAMPLE</span><span class="sxs-lookup"><span data-stu-id="48794-115">TABLESAMPLE</span></span>  
  
-   <span data-ttu-id="48794-116">UNPIVOT</span><span class="sxs-lookup"><span data-stu-id="48794-116">UNPIVOT</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="48794-117">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="48794-117">Corrective Action</span></span>  
 <span data-ttu-id="48794-118">È consigliabile rinominare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="48794-118">We recommend that you rename the object.</span></span> <span data-ttu-id="48794-119">Se questa operazione non può essere eseguita prima dell'aggiornamento, utilizzare uno dei metodi seguenti fino a quando non risulta possibile modificare il nome:</span><span class="sxs-lookup"><span data-stu-id="48794-119">If that cannot be done before upgrading, use one of the following methods until the name can be changed:</span></span>  
  
-   <span data-ttu-id="48794-120">Mantenere il livello di compatibilità del database 90 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="48794-120">Retain the database compatibility level setting of 90 or lower.</span></span>  
  
-   <span data-ttu-id="48794-121">Fare riferimento all'oggetto utilizzando identificatori delimitati.</span><span class="sxs-lookup"><span data-stu-id="48794-121">Refer to the object by using delimited identifiers.</span></span> <span data-ttu-id="48794-122">L'istruzione, ad esempio, `CREATE TABLE [MERGE] ([MERGE] int);` utilizza le parentesi quadre per delimitare il nome dell'oggetto merge.</span><span class="sxs-lookup"><span data-stu-id="48794-122">For example, the statement `CREATE TABLE [MERGE] ([MERGE] int);` uses brackets to delimit the object name MERGE.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="48794-123">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="48794-123">External Resources</span></span>  
 [<span data-ttu-id="48794-124">Parole chiave riservate &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="48794-124">Reserved Keywords &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reserved-keywords-transact-sql)  
  
 [<span data-ttu-id="48794-125">MERGE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="48794-125">MERGE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/merge-transact-sql)  
  
 [<span data-ttu-id="48794-126">Identificatori delimitati (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="48794-126">Delimited Identifiers (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112509)  
  
 [<span data-ttu-id="48794-127">Livello di compatibilità ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="48794-127">ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level)  
  
  
