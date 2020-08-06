---
title: Testo di ricerca con caratteri jolly
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vswildcardsbuilder
helpviewer_keywords:
- searches [SQL Server Management Studio], wildcards
- Query Editor [SQL Server Management Studio], wildcard searches
- wildcard options [SQL Server Management Studio]
ms.assetid: 449600f8-cc87-4b3f-878a-59c158a88a40
author: rothja
ms.author: jroth
ms.openlocfilehash: cc4e24c3dce73e46350b0c106429c42ab5f0edb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637731"
---
# <a name="search-text-with-wildcards"></a><span data-ttu-id="86356-102">Testo di ricerca con caratteri jolly</span><span class="sxs-lookup"><span data-stu-id="86356-102">Search Text with Wildcards</span></span>
  <span data-ttu-id="86356-103">Le espressioni seguenti possono sostituire caratteri o cifre nel campo **Trova** della finestra di dialogo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Trova e sostituisci**di**.</span><span class="sxs-lookup"><span data-stu-id="86356-103">The following expressions can replace characters or digits in the **Find what** field of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] **Find and Replace** dialog box.</span></span>  
  
#### <a name="to-search-using-wildcards"></a><span data-ttu-id="86356-104">Per eseguire la ricerca utilizzando caratteri jolly</span><span class="sxs-lookup"><span data-stu-id="86356-104">To search using wildcards</span></span>  
  
1.  <span data-ttu-id="86356-105">Per consentire l'uso di caratteri jolly nel campo **Trova** durante operazioni Ricerca veloce, **Cerca nei file**, **Sostituzione veloce**o **Sostituisci nei file** , selezionare l'opzione **Utilizza** in **Opzioni di ricerca** e quindi scegliere **Caratteri jolly**.</span><span class="sxs-lookup"><span data-stu-id="86356-105">To enable the use of wildcards in the **Find what** field during Quick Find, **Find in Files**, **Quick Replace**, or **Replace in Files** operations, select the **Use** option under **Find Options** and then choose **Wildcards**.</span></span>  
  
2.  <span data-ttu-id="86356-106">Accanto al campo **Trova** viene reso disponibile il pulsante triangolare per **l'elenco dei riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="86356-106">The triangular **Reference List** button next to the **Find what** field then becomes available.</span></span> <span data-ttu-id="86356-107">Fare clic su di esso per visualizzare l'elenco dei caratteri jolly disponibili.</span><span class="sxs-lookup"><span data-stu-id="86356-107">Click this button to display a list of the available wildcards.</span></span> <span data-ttu-id="86356-108">L'elemento scelto dall' **Elenco riferimenti**viene inserito nella stringa **Trova** .</span><span class="sxs-lookup"><span data-stu-id="86356-108">When you choose any item from the **Reference List**, it is inserted into the **Find what** string.</span></span>  
  
 <span data-ttu-id="86356-109">Nella tabella seguente sono descritti i caratteri jolly disponibili nell' **Elenco riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="86356-109">The following table describes the wildcards available in the **Reference List**.</span></span>  
  
|<span data-ttu-id="86356-110">Expression</span><span class="sxs-lookup"><span data-stu-id="86356-110">Expression</span></span>|<span data-ttu-id="86356-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86356-111">Syntax</span></span>|<span data-ttu-id="86356-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86356-112">Description</span></span>|  
|----------------|------------|-----------------|  
|<span data-ttu-id="86356-113">Un solo carattere</span><span class="sxs-lookup"><span data-stu-id="86356-113">Any single character</span></span>|<span data-ttu-id="86356-114">?</span><span class="sxs-lookup"><span data-stu-id="86356-114">?</span></span>|<span data-ttu-id="86356-115">Individua un qualsiasi singolo carattere.</span><span class="sxs-lookup"><span data-stu-id="86356-115">Matches any single character.</span></span>|  
|<span data-ttu-id="86356-116">Una sola cifra</span><span class="sxs-lookup"><span data-stu-id="86356-116">Any single digit</span></span>|#|<span data-ttu-id="86356-117">Individua una qualsiasi singola cifra.</span><span class="sxs-lookup"><span data-stu-id="86356-117">Matches any single digit.</span></span> <span data-ttu-id="86356-118">Ad esempio, 7# individua i numeri che comprendono 7 seguito da un altro numero. In questo caso potrebbe essere 71 ma non 17.</span><span class="sxs-lookup"><span data-stu-id="86356-118">For example, 7# matches numbers that include 7 followed by another number, such as 71, but not 17.</span></span>|  
|<span data-ttu-id="86356-119">Qualsiasi carattere esterno al set</span><span class="sxs-lookup"><span data-stu-id="86356-119">Characters not in set</span></span>|<span data-ttu-id="86356-120">[!</span><span class="sxs-lookup"><span data-stu-id="86356-120">[!</span></span> <span data-ttu-id="86356-121">]</span><span class="sxs-lookup"><span data-stu-id="86356-121">]</span></span>|<span data-ttu-id="86356-122">Individua qualsiasi carattere non specificato nel set.</span><span class="sxs-lookup"><span data-stu-id="86356-122">Matches any one character that is not specified in the set.</span></span>|  
|<span data-ttu-id="86356-123">Zero o più caratteri</span><span class="sxs-lookup"><span data-stu-id="86356-123">One or more characters</span></span>|*|<span data-ttu-id="86356-124">Individua uno o più caratteri.</span><span class="sxs-lookup"><span data-stu-id="86356-124">Matches any one or more characters.</span></span> <span data-ttu-id="86356-125">Ad esempio, nuovo\* individua qualsiasi testo che comprende "nuovo", come nuovofile.txt.</span><span class="sxs-lookup"><span data-stu-id="86356-125">For example, new\* matches any text that includes "new", such as newfile.txt.</span></span>|  
|<span data-ttu-id="86356-126">Qualsiasi carattere del set</span><span class="sxs-lookup"><span data-stu-id="86356-126">Set of characters</span></span>|<span data-ttu-id="86356-127">[ ]</span><span class="sxs-lookup"><span data-stu-id="86356-127">[ ]</span></span>|<span data-ttu-id="86356-128">Individua qualsiasi carattere specificato nel set.</span><span class="sxs-lookup"><span data-stu-id="86356-128">Matches any one of the characters specified in the set.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86356-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86356-129">See Also</span></span>  
 <span data-ttu-id="86356-130">[Ricerca e sostituzione](search-and-replace.md) </span><span class="sxs-lookup"><span data-stu-id="86356-130">[Search and Replace](search-and-replace.md) </span></span>  
 [<span data-ttu-id="86356-131">Eseguire ricerche di testo con espressioni regolari</span><span class="sxs-lookup"><span data-stu-id="86356-131">Search Text with Regular Expressions</span></span>](search-text-with-regular-expressions.md)  
