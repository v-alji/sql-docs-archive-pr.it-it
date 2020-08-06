---
title: Aggiungere un log per i contatori delle prestazioni del flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- performance counters [Integration Services]
- counters [Integration Services]
- logs [Integration Services], data flow counters
ms.assetid: b500d166-33ba-4b82-a92d-b0a333924e8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 489bde1b0e5769f05d1063eb0af2376b659574de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721680"
---
# <a name="add-a-log-for-data-flow-performance-counters"></a><span data-ttu-id="c08af-102">Aggiunta di un registro per i contatori delle prestazioni del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="c08af-102">Add a Log for Data Flow Performance Counters</span></span>
  <span data-ttu-id="c08af-103">In questo argomento viene descritta la procedura per l'aggiunta di un registro per i contatori delle prestazioni forniti dal motore del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="c08af-103">This procedure describes how to add a log for the performance counters that the data flow engine provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c08af-104">se [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] viene installato in un computer che esegue [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)]e il computer viene aggiornato a [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], il processo di aggiornamento rimuove i contatori delle prestazioni [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dal computer.</span><span class="sxs-lookup"><span data-stu-id="c08af-104">If you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] on a computer that is running [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)], and then upgrade that computer to [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], the upgrade process removes the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters from the computer.</span></span> <span data-ttu-id="c08af-105">Per ripristinare i contatori delle prestazioni [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nel computer, eseguire il programma di installazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in modalità di ripristino.</span><span class="sxs-lookup"><span data-stu-id="c08af-105">To restore the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] performance counters on the computer, run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup in repair mode.</span></span>  
  
### <a name="to-add-logging-of-performance-counters"></a><span data-ttu-id="c08af-106">Per attivare la creazione di registri dei contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="c08af-106">To add logging of performance counters</span></span>  
  
1.  <span data-ttu-id="c08af-107">Nel **Pannello di controllo**fare clic su **Strumenti di amministrazione**nella visualizzazione classica.</span><span class="sxs-lookup"><span data-stu-id="c08af-107">In **Control Panel**, if you are using Classic view, click **Administrative Tools**.</span></span> <span data-ttu-id="c08af-108">Nella visualizzazione Categoria fare clic su **Prestazioni e manutenzione** e quindi su **Strumenti di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="c08af-108">If you are using Category view, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="c08af-109">Fare clic su **Prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="c08af-109">Click **Performance**.</span></span>  
  
3.  <span data-ttu-id="c08af-110">Nella finestra di dialogo **Prestazioni** espandere il nodo **Avvisi e registri di prestazioni**, fare clic con il pulsante destro del mouse su **Registri contatori**e quindi fare clic su **Nuove impostazioni registro**.</span><span class="sxs-lookup"><span data-stu-id="c08af-110">In the **Performance** dialog box, expand **Performance Logs and Alerts**, right-click **Counter Logs**, and then click **New Log Settings**.</span></span> <span data-ttu-id="c08af-111">Digitare il nome del registro,</span><span class="sxs-lookup"><span data-stu-id="c08af-111">Type the name of the log.</span></span> <span data-ttu-id="c08af-112">ad esempio **MioRegistro**.</span><span class="sxs-lookup"><span data-stu-id="c08af-112">For example, type **MyLog**.</span></span>  
  
4.  <span data-ttu-id="c08af-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c08af-113">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="c08af-114">Nella finestra di dialogo **MioRegistro** fare clic su **Aggiungi contatori**.</span><span class="sxs-lookup"><span data-stu-id="c08af-114">In the **MyLog** dialog box, click **Add Counters**.</span></span>  
  
6.  <span data-ttu-id="c08af-115">Fare clic su **Utilizza contatori del computer locale** per la registrazione dei contatori delle prestazioni nel computer locale oppure fare clic su **Seleziona contatori dal computer** , quindi selezionare un computer dall'elenco in cui registrare i contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c08af-115">Click **Use local computer counters** to log performance counters on the local computer, or click **Select counters from computer** and then select a computer from the list to log performance counters on the specified computer.</span></span>  
  
7.  <span data-ttu-id="c08af-116">Nella finestra di dialogo **Aggiungi contatori** selezionare **SQL Server:SSIS Pipeline** (SQL Server:Pipeline SSIS) nell'elenco **Oggetto prestazione** .</span><span class="sxs-lookup"><span data-stu-id="c08af-116">In the **Add Counters** dialog box, select **SQL Server:SSIS Pipeline** in the **Performance object** list.</span></span>  
  
8.  <span data-ttu-id="c08af-117">Per selezionare contatori delle prestazioni, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c08af-117">To select performance counters, do one of the following:</span></span>  
  
    -   <span data-ttu-id="c08af-118">Selezionare **All Counters** (Tutti i contatori) per registrare tutti i contatori delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c08af-118">Select **All Counters** to log all performance counters.</span></span>  
  
    -   <span data-ttu-id="c08af-119">Selezionare **Select counters in list** (Seleziona i contatori dall'elenco) e selezionare i contatori delle prestazioni da usare.</span><span class="sxs-lookup"><span data-stu-id="c08af-119">Select **Select counters in list** and select the performance counters to use.</span></span>  
  
9. <span data-ttu-id="c08af-120">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c08af-120">Click **Add**.</span></span>  
  
10. <span data-ttu-id="c08af-121">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="c08af-121">Click **Close**.</span></span>  
  
11. <span data-ttu-id="c08af-122">Nella finestra di dialogo **MioRegistro** esaminare l'elenco della registrazione dei contatori delle prestazioni nell'elenco **Contatori** .</span><span class="sxs-lookup"><span data-stu-id="c08af-122">In the **MyLog** dialog box, review the list of logging performance counters in the **Counters** list.</span></span>  
  
12. <span data-ttu-id="c08af-123">Per aggiungere altri contatori, ripetere i passaggi da 5 a 10.</span><span class="sxs-lookup"><span data-stu-id="c08af-123">To add additional counters, repeat steps 5 through 10.</span></span>  
  
13. <span data-ttu-id="c08af-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c08af-124">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c08af-125">Il servizio Avvisi e registri di prestazioni deve essere avviato in base a un account locale o un account di dominio appartenente al gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="c08af-125">You must start the Performance Logs and Alerts service using a local account or a domain account that is a member of the Administrators group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08af-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c08af-126">See Also</span></span>  
 <span data-ttu-id="c08af-127">[Contatori delle prestazioni](performance/performance-counters.md) </span><span class="sxs-lookup"><span data-stu-id="c08af-127">[Performance Counters](performance/performance-counters.md) </span></span>  
 [<span data-ttu-id="c08af-128">Visualizzare le voci di log nella finestra Registra eventi</span><span class="sxs-lookup"><span data-stu-id="c08af-128">View Log Entries in the Log Events Window</span></span>](../../2014/integration-services/view-log-entries-in-the-log-events-window.md)  
  
  
