---
title: Opzioni (risultati delle query-SQL Server-risultati nella pagina della griglia) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLResultsToGrid
ms.assetid: f88a0f5c-e800-473b-ae23-c3943de5ed63
author: rothja
ms.author: jroth
ms.openlocfilehash: 3f9cec7e544c295420a9ae2a25e96ea9aa82030b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718647"
---
# <a name="options-query-results-sql-server-results-to-grid-page"></a><span data-ttu-id="3c60e-102">Opzioni (risultati delle query-SQL Server-risultati nella pagina della griglia)</span><span class="sxs-lookup"><span data-stu-id="3c60e-102">Options (Query Results-SQL Server-Results to Grid Page)</span></span>
  <span data-ttu-id="3c60e-103">Utilizzare questa pagina per specificare le opzioni di visualizzazione di un set di risultati di query in formato griglia.</span><span class="sxs-lookup"><span data-stu-id="3c60e-103">Use this page to specify the options for displaying a query result set in grid format.</span></span> <span data-ttu-id="3c60e-104">Le modifiche apportate a queste opzioni vengono applicate solo alle nuove query di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c60e-104">Changes to these options are applied only to new [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="3c60e-105">Per modificare le opzioni per le query correnti, scegliere **Opzioni query** dal menu **query** oppure fare clic con il pulsante destro del mouse nella [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] finestra query e scegliere **Opzioni query**.</span><span class="sxs-lookup"><span data-stu-id="3c60e-105">To change the options for the current queries, click **Query Options** on the **Query** menu, or right-click in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window and select **Query Options**.</span></span> <span data-ttu-id="3c60e-106">Nel riquadro sinistro della finestra di dialogo **Opzioni query** fare clic su **Griglia** in **Risultati**.</span><span class="sxs-lookup"><span data-stu-id="3c60e-106">In the left pane of the **Query Options** dialog box, under **Results**, click **Grid**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="3c60e-107">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="3c60e-107">UI element list</span></span>  
 <span data-ttu-id="3c60e-108">**Includi la query nel set di risultati**</span><span class="sxs-lookup"><span data-stu-id="3c60e-108">**Include the query in the result set**</span></span>  
 <span data-ttu-id="3c60e-109">Restituisce il testo della query all'interno dell'output della query.</span><span class="sxs-lookup"><span data-stu-id="3c60e-109">Returns the text of the query as part of the query output.</span></span>  
  
 <span data-ttu-id="3c60e-110">**Includi intestazioni di colonna nelle operazioni di copia o salvataggio dei risultati**</span><span class="sxs-lookup"><span data-stu-id="3c60e-110">**Include column headers when copying or saving the results**</span></span>  
 <span data-ttu-id="3c60e-111">Selezionare questa casella di controllo per includere le intestazioni di colonna quando i risultati vengono copiati negli Appunti o salvati in un file.</span><span class="sxs-lookup"><span data-stu-id="3c60e-111">Select this check box to include column headers when results are copied to the clipboard, or saved in a file.</span></span> <span data-ttu-id="3c60e-112">Deselezionare la casella se si desidera salvare o copiare i dati dei risultati senza le intestazioni di colonna.</span><span class="sxs-lookup"><span data-stu-id="3c60e-112">Clear this check box if you want saved or copied result data to have only the data and not the column headings.</span></span>  
  
 <span data-ttu-id="3c60e-113">**Elimina risultati dopo l'esecuzione**</span><span class="sxs-lookup"><span data-stu-id="3c60e-113">**Discard results after execution**</span></span>  
 <span data-ttu-id="3c60e-114">Impedisce la visualizzazione dei risultati della query nel riquadro di revisione.</span><span class="sxs-lookup"><span data-stu-id="3c60e-114">Prevents query results from being displayed in the reviewing pane.</span></span> <span data-ttu-id="3c60e-115">I risultati vengono eliminati immediatamente dopo l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3c60e-115">The results are discarded immediately after execution.</span></span> <span data-ttu-id="3c60e-116">La specifica di questa opzione consente di risparmiare memoria.</span><span class="sxs-lookup"><span data-stu-id="3c60e-116">Specifying this option helps save memory.</span></span>  
  
 <span data-ttu-id="3c60e-117">**Visualizza risultati in una scheda separata**</span><span class="sxs-lookup"><span data-stu-id="3c60e-117">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="3c60e-118">Selezionare questa casella di controllo per visualizzare il set di risultati in una nuova scheda invece che nella parte inferiore della finestra del documento di query.</span><span class="sxs-lookup"><span data-stu-id="3c60e-118">Select this check box to display the result set in a new tab, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="3c60e-119">**Passa alla scheda dei risultati al termine della query**</span><span class="sxs-lookup"><span data-stu-id="3c60e-119">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="3c60e-120">Selezionare questa casella di controllo per impostare automaticamente lo stato attivo sul riquadro dei risultati al termine della query.</span><span class="sxs-lookup"><span data-stu-id="3c60e-120">Click to automatically set the screen focus to the results pane upon execution of a query.</span></span>  
  
 <span data-ttu-id="3c60e-121">**Dimensioni massime caratteri recuperati**</span><span class="sxs-lookup"><span data-stu-id="3c60e-121">**Maximum Characters Retrieved**</span></span>  
 <span data-ttu-id="3c60e-122">**Dati non XML**:</span><span class="sxs-lookup"><span data-stu-id="3c60e-122">**Non XML data**:</span></span>  
  
 <span data-ttu-id="3c60e-123">Consente di immettere un valore compreso tra 1 e 65535 per specificare il numero massimo di caratteri che sarà possibile visualizzare in ogni cella.</span><span class="sxs-lookup"><span data-stu-id="3c60e-123">Enter a number from 1 through 65535 to specify the maximum number of characters that will be displayed in each cell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c60e-124">Se si specifica un numero elevato di caratteri, i dati nel set di risultati potrebbero non essere visualizzati completamente.</span><span class="sxs-lookup"><span data-stu-id="3c60e-124">Specifying a large number of characters may cause data in the result set to appear truncated.</span></span> <span data-ttu-id="3c60e-125">Il numero massimo di caratteri visualizzati in ogni cella dipende dalle dimensioni del carattere.</span><span class="sxs-lookup"><span data-stu-id="3c60e-125">The maximum number of characters displayed in each cell is dependent on the font size.</span></span> <span data-ttu-id="3c60e-126">Se si specifica un valore elevato in questa casella e vengono restituiti set di risultati di notevoli dimensioni, la memoria per [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] potrebbe risultare insufficiente con effetti negativi sulle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="3c60e-126">When large result sets are returned, a high value in this box can cause [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to run low on memory and hinder system performance.</span></span>  
  
 <span data-ttu-id="3c60e-127">**Dati XML**:</span><span class="sxs-lookup"><span data-stu-id="3c60e-127">**XML data**:</span></span>  
  
 <span data-ttu-id="3c60e-128">Consente di selezionare i valori **1 MB**, **2 MB**o **5 MB**.</span><span class="sxs-lookup"><span data-stu-id="3c60e-128">Select **1 MB**, **2 MB**, or **5 MB**.</span></span> <span data-ttu-id="3c60e-129">Selezionare **illimitato** per recuperare tutti i caratteri.</span><span class="sxs-lookup"><span data-stu-id="3c60e-129">Select **Unlimited** to retrieve all characters.</span></span>  
  
 <span data-ttu-id="3c60e-130">**Ripristina predefiniti**</span><span class="sxs-lookup"><span data-stu-id="3c60e-130">**Reset to Default**</span></span>  
 <span data-ttu-id="3c60e-131">Reimposta le impostazioni predefinite originali per tutti i valori nella pagina.</span><span class="sxs-lookup"><span data-stu-id="3c60e-131">Resets all values on this page to the original default values.</span></span>  
  
  
