---
title: Gestione di modelli (SQL Server componenti aggiuntivi Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, importing
- mining models, deleting
- mining models, managing
- mining models, training
- mining models, processing
- mining models, exporting
ms.assetid: c11380f0-7c24-4668-9cdf-9c53e4aff665
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5f4b5961ec79bb949bf7fa5f53a980f066e81379
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635843"
---
# <a name="manage-models-sql-server-data-mining-add-ins"></a><span data-ttu-id="0e956-102">Gestione modelli (componenti aggiuntivi Data mining di SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0e956-102">Manage Models (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="0e956-103">![Pulsante Gestione modelli, barra multifunzione Data mining](media/dmc-manage.gif "Pulsante Gestione modelli, barra multifunzione Data mining")</span><span class="sxs-lookup"><span data-stu-id="0e956-103">![Manage Models button, Data Mining ribbon](media/dmc-manage.gif "Manage Models button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="0e956-104">La finestra di dialogo **Gestisci modelli** consente di interagire con i modelli di data mining e le strutture di data mining esistenti archiviati nel [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server al quale si è attualmente connessi.</span><span class="sxs-lookup"><span data-stu-id="0e956-104">The **Manage Models** dialog box enables you to interact with existing mining models and mining structures that are stored in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server to which you are currently connected.</span></span> <span data-ttu-id="0e956-105">È inoltre possibile visualizzare e gestire strutture e modelli temporanei creati durante la connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="0e956-105">You can also view and manage temporary structures and models that have been created during the current session.</span></span> <span data-ttu-id="0e956-106">Se sono stati utilizzati sia modelli di sessione che modelli archiviati in un server, nella finestra di dialogo saranno visibili entrambi i tipi di modelli.</span><span class="sxs-lookup"><span data-stu-id="0e956-106">If you have used both session models and models stored on a server, both are visible in the dialog box.</span></span>  
  
## <a name="using-the-manage-models-wizard"></a><span data-ttu-id="0e956-107">Utilizzo della procedura guidata Gestione modelli</span><span class="sxs-lookup"><span data-stu-id="0e956-107">Using the Manage Models Wizard</span></span>  
 <span data-ttu-id="0e956-108">Quando si fa clic su **Gestisci modelli**, viene visualizzata la finestra di dialogo **Gestisci strutture e modelli di data mining** , che consente di accedere alle seguenti funzionalità per la gestione di modelli e strutture data mining esistenti:</span><span class="sxs-lookup"><span data-stu-id="0e956-108">When you click **Manage Models**, the **Manage Mining Structures and Models** dialog box opens, providing access to the following functionality for managing existing data mining models and structures:</span></span>  
  
-   <span data-ttu-id="0e956-109">Ridenominazione di un modello o di una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="0e956-109">Rename a mining model or structure</span></span>  
  
-   <span data-ttu-id="0e956-110">Eliminazione di un modello o di una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="0e956-110">Delete a mining model or structure</span></span>  
  
-   <span data-ttu-id="0e956-111">Cancellazione di un modello o di una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="0e956-111">Clear a mining model or structure</span></span>  
  
-   <span data-ttu-id="0e956-112">Elaborazione di una struttura di data mining con dati nuovi o esistenti</span><span class="sxs-lookup"><span data-stu-id="0e956-112">Process a mining structure, using either new or existing data</span></span>  
  
-   <span data-ttu-id="0e956-113">Esportazione o importazione di un modello o di una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="0e956-113">Export or import a mining model or structure</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e956-114">Non è possibile creare query o modelli utilizzando questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0e956-114">You cannot create queries or models by using this dialog box.</span></span> <span data-ttu-id="0e956-115">Per creare una nuova struttura di data mining, utilizzare una delle procedure guidate disponibili nel client di data mining per Excel oppure utilizzare la **query di data mining Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="0e956-115">To create a new mining structure, use one of the wizards provided in the Data Mining Client for Excel, or use the **Data Mining Query Advanced Editor**.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="0e956-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e956-116">Requirements</span></span>  
 <span data-ttu-id="0e956-117">Per gestire i modelli di data mining, è innanzitutto necessario creare una connessione a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0e956-117">To manage data mining models, you must first create a connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="0e956-118">È necessaria una connessione anche se si stanno utilizzando modelli di sessione archiviati in un file temporaneo.</span><span class="sxs-lookup"><span data-stu-id="0e956-118">A connection is required even if you are working with session models stored in a temporary file.</span></span> <span data-ttu-id="0e956-119">Per ulteriori informazioni su come creare o modificare una connessione, vedere [connettersi ai dati di origine &#40;client di data mining per&#41;Excel ](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="0e956-119">For more information about how to create or change a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="0e956-120">Se l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a cui si è connessi non contiene strutture o modelli di data mining esistenti, sarà possibile crearli utilizzando le procedure guidate e altri strumenti disponibili in questo componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="0e956-120">If the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you connect to does not contain any existing data mining structures or data mining models, you can create them by using the wizards and other tools provided by this add-in.</span></span> <span data-ttu-id="0e956-121">È inoltre possibile creare nuovi modelli utilizzando il **modello di Data Mining Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="0e956-121">You can also create new models by using the **Data Mining Model Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e956-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e956-122">See Also</span></span>  
 <span data-ttu-id="0e956-123">[Documentazione di modelli di data mining &#40;componenti aggiuntivi Data mining per Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="0e956-123">[Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="0e956-124">Distribuzione e scalabilità di modelli di data mining &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="0e956-124">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)   

  
