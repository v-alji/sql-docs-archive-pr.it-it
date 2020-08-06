---
title: Risultati opzioni query (pagina griglia) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.grid.f1
ms.assetid: 764bf435-3aab-4c62-b4e0-64fe020a5a95
author: rothja
ms.author: jroth
ms.openlocfilehash: bf300dd5071128b0259230ae788a27595bd8d29e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636374"
---
# <a name="query-options-results-grid-page"></a><span data-ttu-id="d1168-102">Risultati di Opzioni query (pagina Griglia)</span><span class="sxs-lookup"><span data-stu-id="d1168-102">Query Options Results (Grid Page)</span></span>
  <span data-ttu-id="d1168-103">Utilizzare questa pagina per specificare le opzioni di visualizzazione di un set di risultati di query in formato griglia.</span><span class="sxs-lookup"><span data-stu-id="d1168-103">Use this page to specify the options for displaying a query result set in grid format.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d1168-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d1168-104">Options</span></span>  
 <span data-ttu-id="d1168-105">**Includi la query nel set di risultati**</span><span class="sxs-lookup"><span data-stu-id="d1168-105">**Include the query in the result set**</span></span>  
 <span data-ttu-id="d1168-106">Restituisce il testo della query come parte del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="d1168-106">Returns the text of the query as part of the result set.</span></span>  
  
 <span data-ttu-id="d1168-107">**Includi intestazioni di colonna nelle operazioni di copia o salvataggio dei risultati**</span><span class="sxs-lookup"><span data-stu-id="d1168-107">**Include column headers when copying or saving the results**</span></span>  
 <span data-ttu-id="d1168-108">Consente di includere le intestazioni di colonna (titoli) durante la copia dei risultati negli Appunti o il salvataggio in un file.</span><span class="sxs-lookup"><span data-stu-id="d1168-108">Include column headers (titles) when results are copied to the clipboard, or saved in a file.</span></span> <span data-ttu-id="d1168-109">Deselezionare questa casella di controllo se si desidera che i risultati salvati o copiati contengano solo i dati senza le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="d1168-109">Clear this check box if you do not want saved or copied result data to have only the data, and not the column headings.</span></span>  
  
 <span data-ttu-id="d1168-110">**Elimina risultati dopo l'esecuzione**</span><span class="sxs-lookup"><span data-stu-id="d1168-110">**Discard results after execution**</span></span>  
 <span data-ttu-id="d1168-111">Consente di liberare memoria eliminando i risultati delle query dopo la loro visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="d1168-111">Free memory by discarding the query results after the screen display has received them.</span></span>  
  
 <span data-ttu-id="d1168-112">**Visualizza risultati in una scheda separata**</span><span class="sxs-lookup"><span data-stu-id="d1168-112">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="d1168-113">Consente di visualizzare il set dei risultati in una nuova finestra del documento anziché nella parte inferiore della finestra del documento della query.</span><span class="sxs-lookup"><span data-stu-id="d1168-113">Display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="d1168-114">**Passa alla scheda dei risultati al termine della query**</span><span class="sxs-lookup"><span data-stu-id="d1168-114">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="d1168-115">Consente di impostare automaticamente lo stato attivo dello schermo sul set dei risultati.</span><span class="sxs-lookup"><span data-stu-id="d1168-115">Automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="d1168-116">**Dimensioni massime caratteri recuperati**</span><span class="sxs-lookup"><span data-stu-id="d1168-116">**Maximum Characters Retrieved**</span></span>  
 <span data-ttu-id="d1168-117">**Dati non XML**:</span><span class="sxs-lookup"><span data-stu-id="d1168-117">**Non XML data**:</span></span>  
  
 <span data-ttu-id="d1168-118">Consente di immettere un valore compreso tra 1 e 65535 per specificare il numero massimo di caratteri che sarà possibile visualizzare in ogni cella.</span><span class="sxs-lookup"><span data-stu-id="d1168-118">Enter a number from 1 through 65535 to specify the maximum number of characters that will be displayed in each cell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d1168-119">Se si specifica un numero elevato di caratteri, i dati nel set di risultati potrebbero non essere visualizzati completamente.</span><span class="sxs-lookup"><span data-stu-id="d1168-119">Specifying a large number of characters may cause data in the result set to appear truncated.</span></span> <span data-ttu-id="d1168-120">Il numero massimo di caratteri visualizzati in ogni cella dipende dalle dimensioni del carattere.</span><span class="sxs-lookup"><span data-stu-id="d1168-120">The maximum number of characters displayed in each cell is dependent on the font size.</span></span> <span data-ttu-id="d1168-121">Se si specifica un valore elevato in questa casella e vengono restituiti set di risultati di notevoli dimensioni, la memoria per [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] potrebbe risultare insufficiente con effetti negativi sulle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="d1168-121">When large result sets are returned, a high value in this box can cause [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to run low on memory and hinder system performance.</span></span>  
  
 <span data-ttu-id="d1168-122">**Dati XML**:</span><span class="sxs-lookup"><span data-stu-id="d1168-122">**XML data**:</span></span>  
  
 <span data-ttu-id="d1168-123">Consente di selezionare i valori **1 MB**, **2 MB**o **5 MB**.</span><span class="sxs-lookup"><span data-stu-id="d1168-123">Select **1 MB**, **2 MB**, or **5 MB**.</span></span> <span data-ttu-id="d1168-124">Selezionare **illimitato** per recuperare tutti i caratteri.</span><span class="sxs-lookup"><span data-stu-id="d1168-124">Select **Unlimited** to retrieve all characters.</span></span>  
  
 <span data-ttu-id="d1168-125">**Ripristina predefiniti**</span><span class="sxs-lookup"><span data-stu-id="d1168-125">**Reset to Default**</span></span>  
 <span data-ttu-id="d1168-126">Reimposta le impostazioni predefinite originali per tutti i valori nella pagina.</span><span class="sxs-lookup"><span data-stu-id="d1168-126">Resets all values on this page to the original default values.</span></span>  
  
  
