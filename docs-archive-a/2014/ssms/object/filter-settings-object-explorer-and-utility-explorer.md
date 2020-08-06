---
title: Impostazioni filtro (Esplora oggetti ed Esplora utilità) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.filtersettings.f1
- sql12.swb.common.filtersettings.f1
ms.assetid: 4aab04bc-e1ab-4d4b-ab74-b287fc805bc2
author: stevestein
ms.author: sstein
ms.openlocfilehash: c31fbcbef9cbab86a7bd3ab7b2fae21e626aaa59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623007"
---
# <a name="filter-settings-object-explorer-and-utility-explorer"></a><span data-ttu-id="33c29-102">Impostazioni filtro (Esplora oggetti ed Esplora utilità)</span><span class="sxs-lookup"><span data-stu-id="33c29-102">Filter Settings (Object Explorer and Utility Explorer)</span></span>
  <span data-ttu-id="33c29-103">Utilizzare questa finestra di dialogo per specificare un filtro.</span><span class="sxs-lookup"><span data-stu-id="33c29-103">Use this dialog box to specify a filter.</span></span> <span data-ttu-id="33c29-104">Un filtro consente di configurare Esplora oggetti e Gestione Utilità in modo da visualizzare solo gli elementi che soddisfano determinati criteri.</span><span class="sxs-lookup"><span data-stu-id="33c29-104">A filter allows you to configure Object Explorer and Utility Explorer to display only items that meet specific criteria.</span></span> <span data-ttu-id="33c29-105">È possibile, ad esempio, utilizzare un filtro per visualizzare solo i processi i cui nomi contengono la parola "Manutenzione".</span><span class="sxs-lookup"><span data-stu-id="33c29-105">For example, you can use a filter to show only jobs with names that contain the word "Maintenance."</span></span> <span data-ttu-id="33c29-106">L'intestazione della finestra di dialogo **Impostazioni filtro** contiene il nome del server e può contenere anche il nome del database.</span><span class="sxs-lookup"><span data-stu-id="33c29-106">The header for the **Filter Settings** dialog box contains the name of the server, and it may contain the name of the database.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="33c29-107">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="33c29-107">UI element list</span></span>  
 <span data-ttu-id="33c29-108">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="33c29-108">**Property**</span></span>  
 <span data-ttu-id="33c29-109">Consente di visualizzare la proprietà in base a cui applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="33c29-109">Displays the property to filter on.</span></span>  
  
 <span data-ttu-id="33c29-110">**Operatore**</span><span class="sxs-lookup"><span data-stu-id="33c29-110">**Operator**</span></span>  
 <span data-ttu-id="33c29-111">Consente di selezionare il modo in cui il valore viene applicato alla proprietà dal filtro.</span><span class="sxs-lookup"><span data-stu-id="33c29-111">Select the way that the filter applies the value to the property.</span></span> <span data-ttu-id="33c29-112">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33c29-112">There are the following options:</span></span>  
  
-   <span data-ttu-id="33c29-113">**Uguale a**</span><span class="sxs-lookup"><span data-stu-id="33c29-113">**Equals**</span></span>  
  
     <span data-ttu-id="33c29-114">Il filtro visualizza gli elementi in cui la proprietà e il valore corrispondono esattamente.</span><span class="sxs-lookup"><span data-stu-id="33c29-114">The filter shows items where the property and the value are an exact match.</span></span>  
  
-   <span data-ttu-id="33c29-115">**Contiene**</span><span class="sxs-lookup"><span data-stu-id="33c29-115">**Contains**</span></span>  
  
     <span data-ttu-id="33c29-116">Il filtro visualizza gli elementi in cui la proprietà contiene il valore.</span><span class="sxs-lookup"><span data-stu-id="33c29-116">The filter shows items where the property contains the value.</span></span> <span data-ttu-id="33c29-117">La proprietà può contenere altro testo.</span><span class="sxs-lookup"><span data-stu-id="33c29-117">The property may contain other text.</span></span>  
  
-   <span data-ttu-id="33c29-118">**Non contiene**</span><span class="sxs-lookup"><span data-stu-id="33c29-118">**Does not contain**</span></span>  
  
     <span data-ttu-id="33c29-119">Il filtro visualizza gli elementi in cui la proprietà non contiene il valore.</span><span class="sxs-lookup"><span data-stu-id="33c29-119">The filter shows items that where the property does not contain the value.</span></span>  
  
-   <span data-ttu-id="33c29-120">**Minore di**</span><span class="sxs-lookup"><span data-stu-id="33c29-120">**Less than**</span></span>  
  
     <span data-ttu-id="33c29-121">Questo operatore è disponibile per le date e visualizza gli elementi la cui data è precedente al valore immesso.</span><span class="sxs-lookup"><span data-stu-id="33c29-121">Available for dates, this filter shows items whose date is before the value provided.</span></span>  
  
-   <span data-ttu-id="33c29-122">**Minore o uguale a**</span><span class="sxs-lookup"><span data-stu-id="33c29-122">**Less than or equal**</span></span>  
  
     <span data-ttu-id="33c29-123">Questo operatore è disponibile per le date e visualizza gli elementi la cui data corrisponde o è precedente al valore immesso.</span><span class="sxs-lookup"><span data-stu-id="33c29-123">Available for dates, this filter shows items whose date contains or is before the value provided.</span></span>  
  
-   <span data-ttu-id="33c29-124">**Maggiore di**</span><span class="sxs-lookup"><span data-stu-id="33c29-124">**Greater than**</span></span>  
  
     <span data-ttu-id="33c29-125">Questo operatore è disponibile per le date e visualizza gli elementi la cui data è successiva al valore immesso.</span><span class="sxs-lookup"><span data-stu-id="33c29-125">Available for dates, this filter shows items whose date is after the value provided.</span></span>  
  
-   <span data-ttu-id="33c29-126">**Maggiore o uguale a**</span><span class="sxs-lookup"><span data-stu-id="33c29-126">**Greater than or equal**</span></span>  
  
     <span data-ttu-id="33c29-127">Questo operatore è disponibile per le date e visualizza gli elementi la cui data corrisponde o è successiva al valore immesso.</span><span class="sxs-lookup"><span data-stu-id="33c29-127">Available for dates, this filter shows items whose date contains or is after the value provided.</span></span>  
  
-   <span data-ttu-id="33c29-128">**Compreso tra**</span><span class="sxs-lookup"><span data-stu-id="33c29-128">**Between**</span></span>  
  
     <span data-ttu-id="33c29-129">Questo operatore è disponibile per le date e visualizza gli elementi la cui data è compresa tra due date immesse.</span><span class="sxs-lookup"><span data-stu-id="33c29-129">Available for dates, this filter shows items whose date is between two dates provided.</span></span> <span data-ttu-id="33c29-130">Per aggiungere un'altra riga che consenta l'immissione della seconda data selezionare **Compreso tra** e premere TAB.</span><span class="sxs-lookup"><span data-stu-id="33c29-130">Select **Between** and press TAB to add another row allowing entry of the second date.</span></span>  
  
-   <span data-ttu-id="33c29-131">**Non compreso tra**</span><span class="sxs-lookup"><span data-stu-id="33c29-131">**Not between**</span></span>  
  
     <span data-ttu-id="33c29-132">Questo operatore è disponibile per le date e visualizza gli elementi la cui data è precedente o successiva alle due date immesse.</span><span class="sxs-lookup"><span data-stu-id="33c29-132">Available for dates, this filter shows items whose date is before or after two dates provided.</span></span> <span data-ttu-id="33c29-133">Per aggiungere un'altra riga che consenta l'immissione della seconda data selezionare **Non compreso tra** e premere TAB per uscire dalla colonna **Operatore** .</span><span class="sxs-lookup"><span data-stu-id="33c29-133">Select **Not Between** and tab out of the **Operator** column to add another row allowing entry of the second date.</span></span>  
  
 <span data-ttu-id="33c29-134">**Valore**</span><span class="sxs-lookup"><span data-stu-id="33c29-134">**Value**</span></span>  
 <span data-ttu-id="33c29-135">Consente di digitare il valore da confrontare con la proprietà.</span><span class="sxs-lookup"><span data-stu-id="33c29-135">Type the value to compare to the property.</span></span> <span data-ttu-id="33c29-136">Fare clic sulla freccia a discesa per visualizzare un calendario che consente di selezionare la data.</span><span class="sxs-lookup"><span data-stu-id="33c29-136">For dates, click the down arrow to show a calendar for selecting the date.</span></span>  
  
 <span data-ttu-id="33c29-137">**Cancella filtro**</span><span class="sxs-lookup"><span data-stu-id="33c29-137">**Clear Filter**</span></span>  
 <span data-ttu-id="33c29-138">Consente di eliminare tutte le impostazioni correnti del filtro.</span><span class="sxs-lookup"><span data-stu-id="33c29-138">Removes all current filter settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c29-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33c29-139">See Also</span></span>  
 <span data-ttu-id="33c29-140">[Usa SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="33c29-140">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="33c29-141">Attività e funzionalità di Utilità SQL Server</span><span class="sxs-lookup"><span data-stu-id="33c29-141">SQL Server Utility Features and Tasks</span></span>](../../relational-databases/manage/sql-server-utility-features-and-tasks.md)  
  
  
