---
title: Visualizzare le voci di log nella finestra Registra eventi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], viewing
- Integration Services packages, logs
- packages [Integration Services], logs
ms.assetid: c02123c3-67fc-4370-ad14-91ed259f1873
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16b6f11758d7de2c833731cd007426000a01d8ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712115"
---
# <a name="view-log-entries-in-the-log-events-window"></a><span data-ttu-id="51837-102">Visualizzare le voci di log nella finestra Registra eventi</span><span class="sxs-lookup"><span data-stu-id="51837-102">View Log Entries in the Log Events Window</span></span>
  <span data-ttu-id="51837-103">In questo argomento viene descritta la procedura per eseguire un pacchetto e visualizzare le voci di log scritte da tale pacchetto.</span><span class="sxs-lookup"><span data-stu-id="51837-103">This procedure describes how to run a package and view the log entries it writes.</span></span> <span data-ttu-id="51837-104">È possibile visualizzare le voci di log in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="51837-104">You can view the log entries in real time.</span></span> <span data-ttu-id="51837-105">Le voci di log scritte nella finestra **Registra eventi** possono inoltre essere copiate e salvate per analisi ulteriori.</span><span class="sxs-lookup"><span data-stu-id="51837-105">The log entries that are written to the **Log Events** window can also be copied and saved for further analysis.</span></span>  
  
 <span data-ttu-id="51837-106">Per scrivere le voci di log nella finestra **Registra eventi** non è necessario scriverle in un log.</span><span class="sxs-lookup"><span data-stu-id="51837-106">It is not necessary to write the log entries to a log to write the entries to the **Log Events** window.</span></span>  
  
### <a name="to-view-log-entries"></a><span data-ttu-id="51837-107">Per visualizzare voci di log</span><span class="sxs-lookup"><span data-stu-id="51837-107">To view log entries</span></span>  
  
1.  <span data-ttu-id="51837-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="51837-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="51837-109">Scegliere **Registra eventi** dal menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="51837-109">On the **SSIS** menu, click **Log Events**.</span></span> <span data-ttu-id="51837-110">Facoltativamente, è possibile visualizzare la finestra **Registra eventi** eseguendo il mapping tra il comando View.LogEvents e una combinazione di tasti scelta dall'utente nella pagina **Tastiera** della finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="51837-110">You can optionally display the **Log Events** window by mapping the View.LogEvents command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
3.  <span data-ttu-id="51837-111">Dal menu **Debug** scegliere **Avvia debug**.</span><span class="sxs-lookup"><span data-stu-id="51837-111">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="51837-112">Quando il runtime rileva i messaggi personalizzati e gli eventi per cui è attivata la registrazione, le voci di log per ogni evento o messaggio vengono scritte nella finestra **Registra eventi** .</span><span class="sxs-lookup"><span data-stu-id="51837-112">As the runtime encounters the events and custom messages that are enabled for logging, log entries for each event or message are written to the **Log Events** window.</span></span>  
  
4.  <span data-ttu-id="51837-113">Dal menu **Debug** scegliere **Arresta debug**.</span><span class="sxs-lookup"><span data-stu-id="51837-113">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
     <span data-ttu-id="51837-114">Le voci di log rimangono disponibili nella finestra **Registra eventi** finché non si esegue nuovamente il pacchetto, non si esegue un pacchetto diverso o non si chiude [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51837-114">The log entries remain available in the **Log Events** window until you rerun the package, run a different package, or close [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span>  
  
5.  <span data-ttu-id="51837-115">Esaminare le voci di log nella finestra **Registra eventi** .</span><span class="sxs-lookup"><span data-stu-id="51837-115">View the log entries in the **Log Events** window.</span></span>  
  
6.  <span data-ttu-id="51837-116">Facoltativamente, selezionare le voci di log da copiare, fare clic con il pulsante destro del mouse e quindi scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="51837-116">Optionally, click the log entries to copy, right-click, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="51837-117">Facoltativamente, fare doppio clic su una voce di log e, nella finestra di dialogo **Voce log** , esaminare i dettagli della singola voce di log selezionata.</span><span class="sxs-lookup"><span data-stu-id="51837-117">Optionally, double-click a log entry, and in the **Log Entry** dialog box, view the details for a single log entry.</span></span>  
  
8.  <span data-ttu-id="51837-118">Nella finestra di dialogo **Voce log** usare le frecce SU o GIÙ per visualizzare la voce di log precedente o successiva e quindi fare clic sull'icona Copia per copiare la voce di log selezionata.</span><span class="sxs-lookup"><span data-stu-id="51837-118">In the **Log Entry** dialog box, click the up and down arrows to display the previous or next log entry, and click the copy icon to copy the log entry.</span></span>  
  
9. <span data-ttu-id="51837-119">Aprire un editor di testo, incollare e quindi salvare la voce di log in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="51837-119">Open a text editor, paste, and then save the log entry to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51837-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51837-120">See Also</span></span>  
 [<span data-ttu-id="51837-121">Registrazione di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="51837-121">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
