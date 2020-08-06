---
title: Creare una Knowledge Base | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.selectkb.f1
- sql12.dqs.kb.newkb.f1
ms.assetid: 2733a284-975f-4650-abcc-cc2aad074cab
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 281fa663362cc4462cd4e32839c1eaf6908394e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624972"
---
# <a name="create-a-knowledge-base"></a><span data-ttu-id="b5c2c-102">Creare una Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="b5c2c-102">Create a Knowledge Base</span></span>
  <span data-ttu-id="b5c2c-103">In questo argomento viene descritto come creare una Knowledge Base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) e prepararla per le attività di gestione del dominio, individuazione delle informazioni o aggiunta di criteri di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-103">This topic describes how to create a knowledge base in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), and prepare it for domain management, knowledge discovery, or adding a matching policy.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b5c2c-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b5c2c-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b5c2c-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b5c2c-105">Prerequisites</span></span>  
 <span data-ttu-id="b5c2c-106">Per creare una Knowledge Base, è necessario avere installato il [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] e il [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5c2c-106">To create a knowledge base, you must have installed [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b5c2c-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b5c2c-107">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b5c2c-108">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b5c2c-108">Permissions</span></span>  
 <span data-ttu-id="b5c2c-109">Per creare una Knowledge Base, è necessario disporre del ruolo dqs_kb_editor o dqs_administrator nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-109">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to create a knowledge base.</span></span>  
  
##  <a name="create-a-knowledge-base"></a><a name="Createaknowledgebase"></a><span data-ttu-id="b5c2c-110">Creare una Knowledge base</span><span class="sxs-lookup"><span data-stu-id="b5c2c-110">Create a knowledge base</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="b5c2c-111">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="b5c2c-111">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="b5c2c-112">Nella schermata iniziale del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] fare clic su **Nuova Knowledge Base**.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-112">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="b5c2c-113">Immettere un nome e una descrizione per la nuova Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-113">Enter a name and description for the new knowledge base.</span></span>  
  
4.  <span data-ttu-id="b5c2c-114">In **Crea Knowledge Base da**selezionare l'elemento sui cui basare la Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-114">In **Create knowledge base from**, select what to base the knowledge base on:</span></span>  
  
    -   <span data-ttu-id="b5c2c-115">Selezionare **Nessuno** se non si desidera basare la nuova Knowledge Base su una Knowledge Base esistente o su un file di dati.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-115">Select **None** if you do not want to base the new knowledge base on an existing knowledge base or data file.</span></span>  
  
    -   <span data-ttu-id="b5c2c-116">Selezionare **Knowledge Base esistente** per basare la nuova Knowledge Base su una Knowledge Base già creata nel [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]o sulla Knowledge Base predefinita.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-116">Select **Existing Knowledge Base** to base the new knowledge base on a knowledge base that has already been created on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], or on the default knowledge base.</span></span> <span data-ttu-id="b5c2c-117">Selezionare la Knowledge Base dall'elenco a discesa **Seleziona Knowledge Base** o fare clic su **Sfoglia** per visualizzare la finestra di dialogo **Selezionare una Knowledge Base** , selezionare una Knowledge Base esistente su cui basare la nuova Knowledge Base, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-117">Select the knowledge base from the **Select Knowledge Base** drop-down list, or click **Browse** to display the **Select a Knowledge Base** dialog box, select an existing knowledge base to base the new knowledge base on, and then click **OK**.</span></span> <span data-ttu-id="b5c2c-118">Quando si seleziona una Knowledge Base dalla tabella, i domini e le regole di corrispondenza nella Knowledge Base verranno visualizzati nel riquadro a destra della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-118">When you select a knowledge base from the tablet, the domains and matching rules in the knowledge base will be displayed in the right-hand pane of the dialog box.</span></span> <span data-ttu-id="b5c2c-119">È anche possibile selezionare **Dati DQS** , la Knowledge Base predefinita che contiene i domini comuni predefiniti e le informazioni correlate a dati di società, indirizzi e soggetti negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-119">You can also select the **DQS Data** knowledge base, which is the default knowledge base that contains common out-of-the-box domains and knowledge related to U.S. company, address, and party data.</span></span>  
  
    -   <span data-ttu-id="b5c2c-120">Selezionare **Importa da file DQS** per basare la nuova Knowledge Base su un file DQS nel [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5c2c-120">Select **Import from DQS File** to base the new knowledge base on a DQS file on [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span> <span data-ttu-id="b5c2c-121">Fare clic su **Sfoglia**, selezionare un file di dati DQS con un'estensione DQS, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-121">Click **Browse**, select a DQS data file with an extension of .dqs, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="b5c2c-122">In **Seleziona attività**selezionare l'attività che si desidera eseguire sulla nuova Knowledge Base:</span><span class="sxs-lookup"><span data-stu-id="b5c2c-122">In **Select Activity**, select the activity that you want to perform on the new knowledge base:</span></span>  
  
    -   <span data-ttu-id="b5c2c-123">Selezionare **Gestione dominio** per creare la Knowledge Base e visualizzare le schermate per la modifica dei domini nella Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-123">Select **Domain Management** to create the knowledge base and enter the screens that you use to modify the domains in the knowledge base.</span></span>  
  
    -   <span data-ttu-id="b5c2c-124">Selezionare **Individuazione informazioni** per creare la Knowledge Base e avviare la procedura guidata che consente di analizzare un campione di dati e di popolare i domini della Knowledge Base con i risultati.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-124">Select **Knowledge Discovery** to create the knowledge base and enter the wizard that you use to analyze a data sample and populate the domains of the knowledge base with the results.</span></span>  
  
    -   <span data-ttu-id="b5c2c-125">Selezionare **Criteri di corrispondenza** per creare criteri di corrispondenza e aggiungerli alla Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-125">Select **Matching Policy** to create a matching policy and add it to the knowledge base.</span></span>  
  
6.  <span data-ttu-id="b5c2c-126">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-126">Click **Create**.</span></span>  
  
##  <a name="follow-up-after-creating-a-knowledge-base"></a><a name="FollowUp"></a> <span data-ttu-id="b5c2c-127">Completamento: fasi successive alla creazione di una Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="b5c2c-127">Follow Up: After Creating a Knowledge Base</span></span>  
 <span data-ttu-id="b5c2c-128">Dopo avere creato una Knowledge Base, vengono visualizzate una procedura guidata che consente di eseguire l'individuazione delle informazioni, una procedura guidata per creare i criteri di corrispondenza o le pagine per eseguire la gestione del dominio.</span><span class="sxs-lookup"><span data-stu-id="b5c2c-128">After you create a knowledge base, you are presented with a wizard that you can use to perform knowledge discovery, a wizard to create a matching policy, or pages to perform domain management.</span></span> <span data-ttu-id="b5c2c-129">Per altre informazioni sull'individuazione delle informazioni, sulla gestione del dominio o sui criteri di corrispondenza, vedere [Eseguire l'individuazione di informazioni](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gestione di un dominio](../../2014/data-quality-services/managing-a-domain.md), o [Creare criteri di corrispondenza](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b5c2c-129">For more information about the knowledge discovery, domain management, or matching policy, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
