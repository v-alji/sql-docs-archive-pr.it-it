---
title: Finestra di dialogo Confronto (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.definecolumncollation
- vdtsql.chm:65561
ms.assetid: e4020f79-7abf-4839-b9b2-984ef7049817
author: stevestein
ms.author: sstein
ms.openlocfilehash: d551b2ae7ca27250c144afedf13038efd78ad6ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638201"
---
# <a name="collation-dialog-box-visual-database-tools"></a><span data-ttu-id="9a275-102">Finestra di dialogo Confronto (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9a275-102">Collation Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="9a275-103">Questa finestra di dialogo consente di specificare una sequenza di confronto per la colonna.</span><span class="sxs-lookup"><span data-stu-id="9a275-103">This dialog box lets you specify a collation sequence for the column.</span></span> <span data-ttu-id="9a275-104">La sequenza di confronto di una colonna viene utilizzata nelle operazioni in cui i valori della colonna vengono confrontati con quelli di un'altra colonna o rispetto a valori costanti.</span><span class="sxs-lookup"><span data-stu-id="9a275-104">A column's collation sequence is used in any operation that compares values of the column to another column or to constant values.</span></span> <span data-ttu-id="9a275-105">Influisce inoltre sul comportamento di alcune funzioni stringa, quali SUBSTRING e CHARINDEX.</span><span class="sxs-lookup"><span data-stu-id="9a275-105">It also affects the behavior of some string functions, such as SUBSTRING and CHARINDEX.</span></span> <span data-ttu-id="9a275-106">Per un elenco completo degli effetti dell'impostazione di confronto di una colonna, vedere la documentazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a275-106">For a complete list of the effects of a column's collation setting, see the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentation.</span></span>  
  
 <span data-ttu-id="9a275-107">Questa finestra di dialogo viene visualizzata quando si eseguono le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a275-107">This dialog box appears:</span></span>  
  
-   <span data-ttu-id="9a275-108">Se si specifica un nome di confronto non valido nel campo **Confronto** della scheda **Proprietà colonne** .</span><span class="sxs-lookup"><span data-stu-id="9a275-108">If you enter an invalid collation name in the **Collation** field on the **Column Properties** tab.</span></span>  
  
-   <span data-ttu-id="9a275-109">Se si fa clic nel campo **Confronto** della scheda **Proprietà colonne** e sui puntini di sospensione ( **...** ) a destra del campo.</span><span class="sxs-lookup"><span data-stu-id="9a275-109">If you click in the **Collation** field on the **Column Properties** tab, and then click the ellipsis button (**...**) to the right of the field.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9a275-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9a275-110">Options</span></span>  
 <span data-ttu-id="9a275-111">**Confronto SQL**</span><span class="sxs-lookup"><span data-stu-id="9a275-111">**SQL Collation**</span></span>  
 <span data-ttu-id="9a275-112">Consente di scegliere tra le sequenze di confronto definite da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e disponibili nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9a275-112">Choose among the collation sequences defined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the drop-down list.</span></span>  
  
 <span data-ttu-id="9a275-113">**Confronto Windows**</span><span class="sxs-lookup"><span data-stu-id="9a275-113">**Windows Collation**</span></span>  
 <span data-ttu-id="9a275-114">Consente di scegliere tra le sequenze di confronto definite da Windows e disponibili nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9a275-114">Choose among the collation sequences defined by Windows from the drop-down list.</span></span>  
  
 <span data-ttu-id="9a275-115">**Ordinamento binario**</span><span class="sxs-lookup"><span data-stu-id="9a275-115">**Binary Sort**</span></span>  
 <span data-ttu-id="9a275-116">Consente di selezionare i codici binari dei valori di tipo carattere per i confronti.</span><span class="sxs-lookup"><span data-stu-id="9a275-116">Use the binary codes of character values for comparisons.</span></span> <span data-ttu-id="9a275-117">Se si seleziona questa opzione, alcune opzioni di confronto alfabetico non saranno più disponibili.</span><span class="sxs-lookup"><span data-stu-id="9a275-117">If you select this option, certain alphabetic comparison options become unavailable.</span></span> <span data-ttu-id="9a275-118">I confronti senza distinzione fra maiuscole e minuscole, ad esempio, non saranno disponibili poiché le lettere maiuscole e le lettere minuscole hanno codifiche binarie diverse.</span><span class="sxs-lookup"><span data-stu-id="9a275-118">For example, case-insensitive comparisons become unavailable because uppercase letters and lowercase letters have different binary encodings.</span></span> <span data-ttu-id="9a275-119">È disponibile solo se si seleziona **Confronto Windows**.</span><span class="sxs-lookup"><span data-stu-id="9a275-119">Applies only if you select **Windows collation**.</span></span>  
  
 <span data-ttu-id="9a275-120">**Ordinamento dizionario**</span><span class="sxs-lookup"><span data-stu-id="9a275-120">**Dictionary Sort**</span></span>  
 <span data-ttu-id="9a275-121">Consente di utilizzare le opzioni di confronto alfabetico.</span><span class="sxs-lookup"><span data-stu-id="9a275-121">Use alphabetic comparison options.</span></span> <span data-ttu-id="9a275-122">È disponibile solo se si seleziona **Confronto Windows**.</span><span class="sxs-lookup"><span data-stu-id="9a275-122">Applies only if you select **Windows collation**.</span></span> <span data-ttu-id="9a275-123">Le opzioni di confronto alfabetico sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a275-123">The alphabetic comparisons options are:</span></span>  
  
-   <span data-ttu-id="9a275-124">**Distinzione maiuscole/minuscole** Selezionare questa opzione se si vuole che per i confronti venga fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="9a275-124">**Case Sensitive** Select this if you want comparisons to consider uppercase and lowercase letters to be unequal.</span></span>  
  
-   <span data-ttu-id="9a275-125">**Distinzione caratteri accentati/non accentati** Selezionare questa opzione se si vuole che per i confronti venga fatta distinzione tra lettere accentate e lettere non accentate.</span><span class="sxs-lookup"><span data-stu-id="9a275-125">**Accent Sensitive** Select this if you want comparisons to consider accented and unaccented letters to be unequal.</span></span> <span data-ttu-id="9a275-126">Selezionando questa opzione, anche le lettere accentate in modo diverso verranno considerate come lettere diverse.</span><span class="sxs-lookup"><span data-stu-id="9a275-126">If you select this, comparisons will also consider differently accented letters to be unequal.</span></span>  
  
-   <span data-ttu-id="9a275-127">**Distinzione Kana** Selezionare questa opzione se si vuole che per i confronti venga fatta distinzione tra le sillabe giapponesi katakana e hiragana.</span><span class="sxs-lookup"><span data-stu-id="9a275-127">**Kana Sensitive** Select this if you want comparisons to consider katakana and hiragana Japanese syllables to be unequal.</span></span>  
  
-   <span data-ttu-id="9a275-128">**Distinzione larghezza** Selezionare questa opzione se si vuole che per i confronti venga fatta distinzione tra caratteri a byte singolo e a byte doppio.</span><span class="sxs-lookup"><span data-stu-id="9a275-128">**Width Sensitive** Select this if you want comparisons to consider half-width and full-width characters to be unequal.</span></span>  
  
 <span data-ttu-id="9a275-129">**Pulsante Ripristina**</span><span class="sxs-lookup"><span data-stu-id="9a275-129">**Restore Default Button**</span></span>  
 <span data-ttu-id="9a275-130">Applica alla colonna la sequenza di confronto predefinita per il database.</span><span class="sxs-lookup"><span data-stu-id="9a275-130">Apply the default collation sequence for the database to the column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a275-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a275-131">See Also</span></span>  
 [<span data-ttu-id="9a275-132">Utilizzo di colonne in query di aggregazione &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9a275-132">Work with Columns in Aggregate Queries &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
