---
title: Editor destinazione SQL (pagina Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.advanced.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 9b46bcf8-ddaf-4d7d-90a6-80bc19517e9b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ccf25ad888c93f694678a152417affe5c0e16091
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625457"
---
# <a name="sql-destination-editor-advanced-page"></a><span data-ttu-id="ae6a8-102">Editor destinazione SQL Server (pagina Avanzate)</span><span class="sxs-lookup"><span data-stu-id="ae6a8-102">SQL Destination Editor (Advanced Page)</span></span>
  <span data-ttu-id="ae6a8-103">Usare la pagina **Avanzate** della finestra di dialogo **Editor destinazione SQL** per specificare le opzioni di inserimento bulk avanzate.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-103">Use the **Advanced** page of the **SQL Destination Editor** dialog box to specify advanced bulk insert options.</span></span>  
  
 <span data-ttu-id="ae6a8-104">Per ulteriori informazioni sulla destinazione SQL Server, vedere [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="ae6a8-104">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae6a8-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ae6a8-105">Options</span></span>  
 <span data-ttu-id="ae6a8-106">**Mantieni valori Identity**</span><span class="sxs-lookup"><span data-stu-id="ae6a8-106">**Keep identity**</span></span>  
 <span data-ttu-id="ae6a8-107">Consente di specificare se l'attività deve inserire valori nelle colonne Identity.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-107">Specify whether the task should insert values into identity columns.</span></span> <span data-ttu-id="ae6a8-108">Il valore predefinito di questa proprietà è `False`.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-108">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="ae6a8-109">**Mantieni valori Null**</span><span class="sxs-lookup"><span data-stu-id="ae6a8-109">**Keep nulls**</span></span>  
 <span data-ttu-id="ae6a8-110">Consente di specificare se l'attività deve mantenere i valori Null.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-110">Specify whether the task should keep null values.</span></span> <span data-ttu-id="ae6a8-111">Il valore predefinito di questa proprietà è `False`.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-111">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="ae6a8-112">**Blocco a livello di tabella**</span><span class="sxs-lookup"><span data-stu-id="ae6a8-112">**Table lock**</span></span>  
 <span data-ttu-id="ae6a8-113">Consente di specificare se la tabella viene bloccata durante il caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-113">Specify whether the table is locked when the data is loaded.</span></span> <span data-ttu-id="ae6a8-114">Il valore predefinito di questa proprietà è `True`.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-114">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="ae6a8-115">**Vincoli CHECK**</span><span class="sxs-lookup"><span data-stu-id="ae6a8-115">**Check constraints**</span></span>  
 <span data-ttu-id="ae6a8-116">Consente di specificare se l'attività deve verificare i vincoli.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-116">Specify whether the task should check constraints.</span></span> <span data-ttu-id="ae6a8-117">Il valore predefinito di questa proprietà è `True`.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-117">The default value of this property is `True`.</span></span>  
  
 <span data-ttu-id="ae6a8-118">**Attive trigger**</span><span class="sxs-lookup"><span data-stu-id="ae6a8-118">**Fire triggers**</span></span>  
 <span data-ttu-id="ae6a8-119">Consente di specificare se l'inserimento bulk deve attivare i trigger nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-119">Specify whether the bulk insert should fire triggers on tables.</span></span> <span data-ttu-id="ae6a8-120">Il valore predefinito di questa proprietà è `False`.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-120">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="ae6a8-121">**Prima riga**</span><span class="sxs-lookup"><span data-stu-id="ae6a8-121">**First Row**</span></span>  
 <span data-ttu-id="ae6a8-122">Consente di specificare la prima riga da inserire.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-122">Specify the first row to insert.</span></span> <span data-ttu-id="ae6a8-123">Il valore predefinito della proprietà è **-1**, a indicare che non è stato assegnato alcun valore.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-123">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae6a8-124">Deselezionare la casella in **Editor destinazione SQL** per indicare che non si vuole assegnare alcun valore alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-124">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="ae6a8-125">Usare -1 nella finestra **Proprietà** , in **Editor avanzato**e nel modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-125">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="ae6a8-126">**Ultima riga**</span><span class="sxs-lookup"><span data-stu-id="ae6a8-126">**Last Row**</span></span>  
 <span data-ttu-id="ae6a8-127">Consente di specificare l'ultima riga da inserire.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-127">Specify the last row to insert.</span></span> <span data-ttu-id="ae6a8-128">Il valore predefinito della proprietà è **-1**, a indicare che non è stato assegnato alcun valore.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-128">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae6a8-129">Deselezionare la casella in **Editor destinazione SQL** per indicare che non si vuole assegnare alcun valore alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-129">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="ae6a8-130">Usare -1 nella finestra **Proprietà** , in **Editor avanzato**e nel modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-130">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="ae6a8-131">**Numero massimo di errori**</span><span class="sxs-lookup"><span data-stu-id="ae6a8-131">**Maximum number of errors**</span></span>  
 <span data-ttu-id="ae6a8-132">Consente di specificare il numero massimo di errori che possono verificarsi prima dell'arresto dell'inserimento bulk.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-132">Specify the number of errors that can occur before the bulk insert stops.</span></span> <span data-ttu-id="ae6a8-133">Il valore predefinito della proprietà è **-1**, a indicare che non è stato assegnato alcun valore.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-133">The default value of this property is **-1**, indicating that no value has been assigned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae6a8-134">Deselezionare la casella in **Editor destinazione SQL** per indicare che non si vuole assegnare alcun valore alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-134">Clear the text box in the **SQL Destination Editor** to indicate that you do not want to assign a value for this property.</span></span> <span data-ttu-id="ae6a8-135">Usare -1 nella finestra **Proprietà** , in **Editor avanzato**e nel modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-135">Use -1 in the **Properties** window, the **Advanced Editor**, and the object model.</span></span>  
  
 <span data-ttu-id="ae6a8-136">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="ae6a8-136">**Timeout**</span></span>  
 <span data-ttu-id="ae6a8-137">Consente di specificare il numero di secondi di attesa prima che l'inserimento bulk venga arrestato a causa di un timeout.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-137">Specify the number of seconds to wait before the bulk insert stops because of a time-out.</span></span>  
  
 <span data-ttu-id="ae6a8-138">**Colonne di ordinamento**</span><span class="sxs-lookup"><span data-stu-id="ae6a8-138">**Order columns**</span></span>  
 <span data-ttu-id="ae6a8-139">Consente di digitare i nomi delle colonne di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-139">Type the names of the sort columns.</span></span> <span data-ttu-id="ae6a8-140">È possibile ordinare ogni colonna in ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-140">Each column can be sorted in ascending or descending order.</span></span> <span data-ttu-id="ae6a8-141">Se si utilizzando più colonne di ordinamento, delimitare l'elenco con virgole.</span><span class="sxs-lookup"><span data-stu-id="ae6a8-141">If you use multiple sort columns, delimit the list with commas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae6a8-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae6a8-142">See Also</span></span>  
 <span data-ttu-id="ae6a8-143">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ae6a8-143">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ae6a8-144">[Editor destinazione SQL &#40;pagina Gestione connessione&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="ae6a8-144">[SQL Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/sql-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="ae6a8-145">[Editor destinazione SQL &#40;pagina mapping&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="ae6a8-145">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="ae6a8-146">Caricamento bulk dei dati tramite la destinazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae6a8-146">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
