---
title: Opzioni (risultati query-SQL Server-pagina risultati in formato testo) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLResultsToText
ms.assetid: 2ccbdf17-e14f-42f1-a836-ca999a3432c9
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ece458e4bab9a57cb6692d4ac6dfdf2e8f4bd22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718641"
---
# <a name="options-query-results-sql-server-results-to-text-page"></a><span data-ttu-id="374e9-102">Opzioni (risultati query-SQL Server-pagina risultati in formato testo)</span><span class="sxs-lookup"><span data-stu-id="374e9-102">Options (Query Results-SQL Server-Results to Text Page)</span></span>
  <span data-ttu-id="374e9-103">Utilizzare questa pagina per specificare le opzioni di visualizzazione di un set di risultati di una query in formato testo.</span><span class="sxs-lookup"><span data-stu-id="374e9-103">Use this page to specify the options for displaying a query result set in text format.</span></span> <span data-ttu-id="374e9-104">Le modifiche apportate a queste opzioni vengono applicate solo alle nuove query di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="374e9-104">Changes to these options are applied only to new [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="374e9-105">Per modificare le opzioni per le query correnti, scegliere **Opzioni query** dal menu **query** oppure fare clic con il pulsante destro del mouse nella [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] finestra query e scegliere **Opzioni query**.</span><span class="sxs-lookup"><span data-stu-id="374e9-105">To change the options for the current queries, click **Query Options** on the **Query** menu, or right-click in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window, and select **Query Options**.</span></span> <span data-ttu-id="374e9-106">Nella finestra di dialogo **Opzioni query** fare clic su **Testo** in **Risultati**.</span><span class="sxs-lookup"><span data-stu-id="374e9-106">In the **Query Options** dialog box, under **Results**, click **Text**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="374e9-107">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="374e9-107">UI element list</span></span>  
 <span data-ttu-id="374e9-108">**Formato di output**</span><span class="sxs-lookup"><span data-stu-id="374e9-108">**Output format**</span></span>  
 <span data-ttu-id="374e9-109">Per impostazione predefinita, l'output viene visualizzato in colonne create utilizzando gli spazi per separare i risultati.</span><span class="sxs-lookup"><span data-stu-id="374e9-109">By default the output is displayed in columns created by padding the results with spaces.</span></span> <span data-ttu-id="374e9-110">Altre opzioni consentono di utilizzare virgole, tabulazioni o spazi per separare le colonne.</span><span class="sxs-lookup"><span data-stu-id="374e9-110">Other options are to use commas, tabs, or spaces to separate columns.</span></span> <span data-ttu-id="374e9-111">Selezionare **Delimitatore personalizzato** in questo elenco a discesa per specificare un carattere di delimitazione diverso nella casella di testo **Delimitatore personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="374e9-111">Select **Custom delimiter** from this drop-down list to specify a different delimiting character in the **Custom delimiter** text box.</span></span>  
  
 <span data-ttu-id="374e9-112">**Delimitatore personalizzato**</span><span class="sxs-lookup"><span data-stu-id="374e9-112">**Custom delimiter**</span></span>  
 <span data-ttu-id="374e9-113">Consente di specificare il carattere che si desidera utilizzare per separare le colonne.</span><span class="sxs-lookup"><span data-stu-id="374e9-113">Specify the character of your choice to separate columns.</span></span> <span data-ttu-id="374e9-114">Questa casella di testo è disponibile solo facendo clic su Delimitatore personalizzato nella casella di riepilogo a discesa **Formato di output**.</span><span class="sxs-lookup"><span data-stu-id="374e9-114">This text box is available only if you clicked Custom delimiter in the **Output format** drop-down list box.</span></span>  
  
 <span data-ttu-id="374e9-115">**Includi intestazioni di colonna nel set di risultati**</span><span class="sxs-lookup"><span data-stu-id="374e9-115">**Include column headers in the result set**</span></span>  
 <span data-ttu-id="374e9-116">Deselezionare questa casella di controllo se non si desidera applicare un titolo alle colonne.</span><span class="sxs-lookup"><span data-stu-id="374e9-116">Clear this check box if you do not want each column labeled with a column title.</span></span>  
  
 <span data-ttu-id="374e9-117">**Includi la query nel set di risultati**</span><span class="sxs-lookup"><span data-stu-id="374e9-117">**Include the query in the result set**</span></span>  
 <span data-ttu-id="374e9-118">Selezionare questa casella di controllo per includere il testo della query in esecuzione nel riquadro dei risultati prima dei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="374e9-118">Select this check box to include the text of the query that is running in the results pane before the results of the query.</span></span>  
  
 <span data-ttu-id="374e9-119">**Scorri i risultati ricevuti**</span><span class="sxs-lookup"><span data-stu-id="374e9-119">**Scroll as results are received**</span></span>  
 <span data-ttu-id="374e9-120">Selezionare questa casella di controllo per mantenere visualizzati gli ultimi record restituiti alla fine del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="374e9-120">Select this check box to keep the display focus on the most recently returned records at the end of the results set.</span></span> <span data-ttu-id="374e9-121">Deselezionare la casella per mantenere visualizzata la prima riga restituita.</span><span class="sxs-lookup"><span data-stu-id="374e9-121">Clear this check box to keep the display focus on the first rows received.</span></span>  
  
 <span data-ttu-id="374e9-122">**Allinea a destra i valori numerici**</span><span class="sxs-lookup"><span data-stu-id="374e9-122">**Right align numeric values**</span></span>  
 <span data-ttu-id="374e9-123">Selezionare questa casella di controllo per allineare i valori numeri a destra nella colonna</span><span class="sxs-lookup"><span data-stu-id="374e9-123">Select this check box to align numeric values to the right of the column.</span></span> <span data-ttu-id="374e9-124">in modo da semplificare l'esame delle cifre con un numero di posizioni decimali predefinito.</span><span class="sxs-lookup"><span data-stu-id="374e9-124">This can make it easier to review numbers with a fixed number of decimal places.</span></span>  
  
 <span data-ttu-id="374e9-125">**Elimina risultati dopo l'esecuzione della query**</span><span class="sxs-lookup"><span data-stu-id="374e9-125">**Discard result after query executes**</span></span>  
 <span data-ttu-id="374e9-126">Selezionare questa casella di controllo per scartare i risultati della query dopo che vengono visualizzati nel riquadro dei risultati della finestra di query.</span><span class="sxs-lookup"><span data-stu-id="374e9-126">Select this check box to discard the query results after they are displayed in the results pane of the query window.</span></span>  
  
 <span data-ttu-id="374e9-127">**Visualizza risultati in una scheda separata**</span><span class="sxs-lookup"><span data-stu-id="374e9-127">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="374e9-128">Selezionare questa casella di controllo per visualizzare il set di risultati in una nuova finestra del documento invece che nella parte inferiore della finestra della query.</span><span class="sxs-lookup"><span data-stu-id="374e9-128">Select this check box to display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="374e9-129">**Passa alla scheda dei risultati al termine della query**</span><span class="sxs-lookup"><span data-stu-id="374e9-129">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="374e9-130">Selezionare questa casella per impostare lo stato attivo dello schermo sul set di risultati.</span><span class="sxs-lookup"><span data-stu-id="374e9-130">Select this check box to automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="374e9-131">**Numero massimo di caratteri visualizzati in ogni colonna**</span><span class="sxs-lookup"><span data-stu-id="374e9-131">**Maximum number of characters displayed in each column**</span></span>  
 <span data-ttu-id="374e9-132">Questo valore viene impostato in modo predefinito su 256.</span><span class="sxs-lookup"><span data-stu-id="374e9-132">This value defaults to 256.</span></span> <span data-ttu-id="374e9-133">È possibile scegliere un valore superiore per visualizzare set di risultati di dimensioni maggiori senza troncamenti.</span><span class="sxs-lookup"><span data-stu-id="374e9-133">Increase this value to display larger result sets without truncation.</span></span> <span data-ttu-id="374e9-134">Il valore massimo è 8192.</span><span class="sxs-lookup"><span data-stu-id="374e9-134">The maximum value is 8,192.</span></span>  
  
 <span data-ttu-id="374e9-135">**Ripristina predefiniti**</span><span class="sxs-lookup"><span data-stu-id="374e9-135">**Reset to Default**</span></span>  
 <span data-ttu-id="374e9-136">Reimposta le impostazioni predefinite originali per tutti i valori nella pagina.</span><span class="sxs-lookup"><span data-stu-id="374e9-136">Resets all values on this page to the original default values.</span></span>  
  
  
