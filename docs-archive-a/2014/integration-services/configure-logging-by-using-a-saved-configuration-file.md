---
title: Configurare la registrazione usando un file di configurazione salvato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], logs
- logs [Integration Services], containers
ms.assetid: e5fdbbcb-94ca-4912-aa7c-0d89cebbd308
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8eb517462d9e932906f739678fbd46c1004fb84d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629979"
---
# <a name="configure-logging-by-using-a-saved-configuration-file"></a><span data-ttu-id="03301-102">Configurazione della registrazione tramite un file di configurazione salvato</span><span class="sxs-lookup"><span data-stu-id="03301-102">Configure Logging by Using a Saved Configuration File</span></span>
  <span data-ttu-id="03301-103">In questo argomento viene descritta la procedura per configurare la registrazione per nuovi contenitori di un pacchetto semplicemente caricando un file di configurazione della registrazione.</span><span class="sxs-lookup"><span data-stu-id="03301-103">This procedure describes how to configure logging for new containers in a package by loading a previously saved logging configuration file.</span></span>  
  
 <span data-ttu-id="03301-104">Per impostazione predefinita, tutti i contenitori di un pacchetto utilizzano la stessa configurazione di registrazione del contenitore padre.</span><span class="sxs-lookup"><span data-stu-id="03301-104">By default, all containers in a package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="03301-105">Le attività del contenitore Ciclo Foreach, ad esempio, utilizzano la stessa configurazione di registrazione del contenitore.</span><span class="sxs-lookup"><span data-stu-id="03301-105">For example, the tasks in a Foreach Loop use the same logging configuration as the Foreach Loop.</span></span>  
  
### <a name="to-configure-logging-for-a-container"></a><span data-ttu-id="03301-106">Per configurare la registrazione per un contenitore</span><span class="sxs-lookup"><span data-stu-id="03301-106">To configure logging for a container</span></span>  
  
1.  <span data-ttu-id="03301-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="03301-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="03301-108">Scegliere **Registrazione** dal menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="03301-108">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="03301-109">Espandere la visualizzazione albero dei pacchetti e selezionare il contenitore da configurare.</span><span class="sxs-lookup"><span data-stu-id="03301-109">Expand the package tree view and select the container to configure.</span></span>  
  
4.  <span data-ttu-id="03301-110">Nella scheda **Provider e log** selezionare i log da usare per il contenitore.</span><span class="sxs-lookup"><span data-stu-id="03301-110">On the **Providers and Logs** tab, select the logs to use for the container.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="03301-111">È possibile creare log solo a livello di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="03301-111">You can create logs only at the package level.</span></span> <span data-ttu-id="03301-112">Per altre informazioni, vedere [Abilitare la registrazione di pacchetti in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="03301-112">For more information, see [Enable Package Logging in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
5.  <span data-ttu-id="03301-113">Nella scheda **Dettagli** fare clic su **Carica**.</span><span class="sxs-lookup"><span data-stu-id="03301-113">Click the **Details** tab and click **Load**.</span></span>  
  
6.  <span data-ttu-id="03301-114">Individuare il file di configurazione della registrazione desiderato e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="03301-114">Locate the logging configuration file you want to use and click **Open**.</span></span>  
  
7.  <span data-ttu-id="03301-115">Facoltativamente, selezionare una voce di log diversa selezionando la casella di controllo corrispondente nella colonna **Eventi** .</span><span class="sxs-lookup"><span data-stu-id="03301-115">Optionally, select a different log entry to log by selecting its check box in the **Events** column.</span></span> <span data-ttu-id="03301-116">Fare clic su **Avanzate** per selezionare il tipo di informazioni da registrare per tale voce.</span><span class="sxs-lookup"><span data-stu-id="03301-116">Click **Advanced** to select the type of information to log for this entry.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="03301-117">Il nuovo contenitore potrebbe includere voci di log aggiuntive non disponibili per il contenitore inizialmente utilizzato per creare la configurazione della registrazione.</span><span class="sxs-lookup"><span data-stu-id="03301-117">The new container may include additional log entries that are not available for the container originally used to create the logging configuration.</span></span> <span data-ttu-id="03301-118">Se si desidera registrare queste voci, è necessario selezionarle in modo manuale.</span><span class="sxs-lookup"><span data-stu-id="03301-118">These additional log entries must be selected manually if you want them to be logged.</span></span>  
  
8.  <span data-ttu-id="03301-119">Per salvare la configurazione della registrazione aggiornata, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="03301-119">To save the updated version of the logging configuration, click **Save**.</span></span>  
  
9. <span data-ttu-id="03301-120">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="03301-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03301-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03301-121">See Also</span></span>  
 [<span data-ttu-id="03301-122">Registrazione di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="03301-122">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
