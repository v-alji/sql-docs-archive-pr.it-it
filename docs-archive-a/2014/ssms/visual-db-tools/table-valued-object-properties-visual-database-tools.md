---
title: Proprietà di oggetti con valori di tabella (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.designers.properties.TVO
ms.assetid: eaf06cbf-8242-4483-894f-80ae02a4840e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6f1c1e6414d0059dfd1d43bbbb40eabdfc9470b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720687"
---
# <a name="table-valued-object-properties-visual-database-tools"></a><span data-ttu-id="8b020-102">Proprietà di oggetti con valori di tabella (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8b020-102">Table-Valued Object Properties (Visual Database Tools)</span></span>
  <span data-ttu-id="8b020-103">Queste proprietà vengono visualizzate nella finestra Proprietà quando si seleziona un oggetto con valori di tabella in **Progettazione query e Progettazione viste**.</span><span class="sxs-lookup"><span data-stu-id="8b020-103">These properties appear in the Properties window when you select a table-valued object in **Query and View Designer**.</span></span> <span data-ttu-id="8b020-104">Un oggetto con valori di tabella può essere una vista, un sinonimo, una tabella derivata o una funzione con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8b020-104">The table-valued object could be a view, synonym, derived table, or table-valued function.</span></span> <span data-ttu-id="8b020-105">Se non specificato diversamente, tali proprietà sono di sola lettura nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="8b020-105">Unless otherwise noted, these properties are read-only in the **Properties** window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b020-106">Le proprietà illustrate in questo argomento sono ordinate per categoria anziché alfabeticamente.</span><span class="sxs-lookup"><span data-stu-id="8b020-106">The properties in this topic are ordered by category rather than alphabet.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b020-107">È possibile che le finestre di dialogo e i comandi di menu visualizzati varino da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="8b020-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8b020-108">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="8b020-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="8b020-109">**Categoria Identità**</span><span class="sxs-lookup"><span data-stu-id="8b020-109">**Identity Category**</span></span>  
 <span data-ttu-id="8b020-110">Viene espansa per visualizzare le proprietà **Nome** e **Tipo TVO** .</span><span class="sxs-lookup"><span data-stu-id="8b020-110">Expands to show the **Name** and **TVO Type** properties.</span></span>  
  
 <span data-ttu-id="8b020-111">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8b020-111">**Name**</span></span>  
 <span data-ttu-id="8b020-112">Consente di visualizzare il nome dell'oggetto con valori di tabella selezionato.</span><span class="sxs-lookup"><span data-stu-id="8b020-112">Shows the name of the selected table-valued object.</span></span>  
  
 <span data-ttu-id="8b020-113">**Tipo TVO**</span><span class="sxs-lookup"><span data-stu-id="8b020-113">**TVO Type**</span></span>  
 <span data-ttu-id="8b020-114">Consente di visualizzare il tipo di oggetto con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8b020-114">Shows which type of table-valued object.</span></span> <span data-ttu-id="8b020-115">Può essere una tabella di base, una vista, una funzione con valori di tabella o una tabella derivata.</span><span class="sxs-lookup"><span data-stu-id="8b020-115">It can be either a base table, view, table-valued function, or a derived table.</span></span>  
  
 <span data-ttu-id="8b020-116">**Categoria Progettazione query**</span><span class="sxs-lookup"><span data-stu-id="8b020-116">**Query DesignerCategory**</span></span>  
 <span data-ttu-id="8b020-117">Viene espansa per visualizzare le proprietà **Alias**, **Elenco colonne**, **Nome completo**ed **Elenco parametri**.</span><span class="sxs-lookup"><span data-stu-id="8b020-117">Expands to show properties for **Alias**, **Column List**, **Full Name**, and **Parameter List**.</span></span>  
  
 <span data-ttu-id="8b020-118">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8b020-118">**Alias**</span></span>  
 <span data-ttu-id="8b020-119">Consente di visualizzare l'alias dell'oggetto con valori di tabella selezionato.</span><span class="sxs-lookup"><span data-stu-id="8b020-119">Shows the alias for the selected table-valued object.</span></span> <span data-ttu-id="8b020-120">Per aggiungere o modificare un alias, digitarlo nel campo.</span><span class="sxs-lookup"><span data-stu-id="8b020-120">To add or change an alias, type it into the field.</span></span>  
  
 <span data-ttu-id="8b020-121">**Elenco colonne**</span><span class="sxs-lookup"><span data-stu-id="8b020-121">**Column List**</span></span>  
 <span data-ttu-id="8b020-122">Consente di visualizzare le colonne incluse nell'oggetto con valori di tabella selezionato.</span><span class="sxs-lookup"><span data-stu-id="8b020-122">Shows the columns included in the selected table-valued object.</span></span> <span data-ttu-id="8b020-123">Per visualizzarle in una finestra separata, fare clic su Elenco colonne e quindi sui puntini di sospensione (...) a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8b020-123">To see them in a separate window, click Column List and then click the ellipses (...) to the right of the property.</span></span>  
  
 <span data-ttu-id="8b020-124">**Nome completo**</span><span class="sxs-lookup"><span data-stu-id="8b020-124">**Full Name**</span></span>  
 <span data-ttu-id="8b020-125">Consente di visualizzare il nome dell'oggetto con valori di tabella selezionato, nonché informazioni aggiuntive, ad esempio lo schema o l'origine dei dati dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="8b020-125">Shows the name of the selected table-valued object, including additional information such as the schema or data source of the object.</span></span>  
  
 <span data-ttu-id="8b020-126">**Elenco parametri**</span><span class="sxs-lookup"><span data-stu-id="8b020-126">**Parameter List**</span></span>  
 <span data-ttu-id="8b020-127">Consente di visualizzare i parametri definiti per la funzione con valori di tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="8b020-127">Shows the parameters defined for selected table-valued function.</span></span> <span data-ttu-id="8b020-128">Per definire un valore per i parametri, fare clic su Elenco parametri e quindi sui puntini di sospensione (...) a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8b020-128">To define a value for the parameters, click Parameter List and then click the ellipses (...) to the right of the property.</span></span> <span data-ttu-id="8b020-129">Verrà visualizzata la finestra di dialogo Parametri della funzione, in cui è possibile digitare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="8b020-129">In the Function Parameters dialog box, type in values.</span></span> <span data-ttu-id="8b020-130">Questa proprietà è disponibile solo quando viene selezionata una funzione con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="8b020-130">This property is only available when a table-valued function is selected.</span></span>  
  
  
