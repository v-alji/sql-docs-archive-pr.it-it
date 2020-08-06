---
title: Importare una Knowledge Base da un file DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9b9786fe-9e80-429a-afcb-dc3b3dd6f0b0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 522c5f6d8f962cef77e215c21133927e8da4d04f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716883"
---
# <a name="import-a-knowledge-base-from-a-dqs-file"></a><span data-ttu-id="dc04c-102">Importazione di una Knowledge Base da un file DQS</span><span class="sxs-lookup"><span data-stu-id="dc04c-102">Import a Knowledge Base from a .dqs File</span></span>
  <span data-ttu-id="dc04c-103">In questo argomento viene descritto come importare un'intera Knowledge Base da un file di dati con estensione DQS in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="dc04c-103">This topic describes how to import an entire knowledge base from a .dqs data file in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="dc04c-104">Il file di dati viene creato esportando una Knowledge Base esistente dall'interno dell'applicazione [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] (vedere [Esportare una Knowledge Base in un File DQS](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span><span class="sxs-lookup"><span data-stu-id="dc04c-104">You create the data file by exporting an existing knowledge base from within the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application (see [Export a Knowledge Base to a .dqs File](../../2014/data-quality-services/export-a-knowledge-base-to-a-dqs-file.md)).</span></span>  
  
 <span data-ttu-id="dc04c-105">L'utilizzo di un file di dati DQS per l'esportazione del contenuto di una Knowledge Base e la successiva reimportazione del contenuto in un'altra Knowledge Base nello stesso [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] , o su un [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] diverso, semplifica il processo di generazione delle informazioni e consente di risparmiare tempo e impegno.</span><span class="sxs-lookup"><span data-stu-id="dc04c-105">Using a .dqs data file to export the contents of a knowledge base and then import the contents into another knowledge base on the same [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] or a different [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] simplifies the knowledge generation process, saving time and effort.</span></span> <span data-ttu-id="dc04c-106">La procedura permette di condividere una Knowledge Base e le relative informazioni con altri utenti, consentendo in tal modo anche ad essi un notevole risparmio di tempo.</span><span class="sxs-lookup"><span data-stu-id="dc04c-106">It enables you to share a knowledge base and its knowledge with others, saving them time.</span></span> <span data-ttu-id="dc04c-107">Il file DQS conterrà tutte le informazioni della Knowledge Base, compresi domini e i criteri di corrispondenza, tranne le informazioni sui dati di riferimento collegati.</span><span class="sxs-lookup"><span data-stu-id="dc04c-107">The .dqs file will contain all knowledge base information, including domains and the matching policy, except for the attached reference data information.</span></span> <span data-ttu-id="dc04c-108">Verranno importati sia i dati pubblicati che quelli non pubblicati.</span><span class="sxs-lookup"><span data-stu-id="dc04c-108">Published and unpublished data will be imported.</span></span>  
  
 <span data-ttu-id="dc04c-109">I file di dati DQS sono crittografati, pertanto non è possibile visualizzarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="dc04c-109">A .dqs data file is encrypted, so cannot be viewed.</span></span>  
  
 <span data-ttu-id="dc04c-110">Quando si importa una Knowledge Base, è possibile utilizzare lo stesso nome, a meno che il nome della Knowledge Base già esista nell'applicazione client, nel qual caso sarà necessario modificarlo.</span><span class="sxs-lookup"><span data-stu-id="dc04c-110">When you import a knowledge base, you can use the same name, unless the knowledge base name already exists in the client application, in which case you must rename it.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dc04c-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="dc04c-111">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="dc04c-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="dc04c-112">Prerequisites</span></span>  
 <span data-ttu-id="dc04c-113">Per importare una Knowledge Base da un file DQS, è necessario avere già esportato la Knowledge Base nel file DQS.</span><span class="sxs-lookup"><span data-stu-id="dc04c-113">To import a knowledge base from a .dqs file, you must have already exported the knowledge base into the .dqs file.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dc04c-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="dc04c-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dc04c-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="dc04c-115">Permissions</span></span>  
 <span data-ttu-id="dc04c-116">Per importare una Knowledge Base da un file DQS è necessario disporre del ruolo dqs_kb_editor o dqs_administrator nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="dc04c-116">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import a knowledge base from a .dqs data file.</span></span>  
  
##  <a name="import-a-knowledge-base-from-a-dqs-file"></a><a name="Import"></a><span data-ttu-id="dc04c-117">Importare una Knowledge base da un file DQS</span><span class="sxs-lookup"><span data-stu-id="dc04c-117">Import a knowledge base from a .dqs file</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="dc04c-118">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="dc04c-118">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="dc04c-119">Nella schermata iniziale del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] fare clic su **Nuova Knowledge Base**.</span><span class="sxs-lookup"><span data-stu-id="dc04c-119">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New knowledge base**.</span></span>  
  
3.  <span data-ttu-id="dc04c-120">Immettere un nome per la Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="dc04c-120">Enter a name for the knowledge base.</span></span>  
  
4.  <span data-ttu-id="dc04c-121">Fare clic sulla freccia in giù per **Crea Knowledge Base da**, quindi selezionare **Importa da file DQS**.</span><span class="sxs-lookup"><span data-stu-id="dc04c-121">Click the down arrow for **Create knowledge base from**, and then select **Import from DQS file**.</span></span>  
  
5.  <span data-ttu-id="dc04c-122">Per **Seleziona il file di dati**, fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="dc04c-122">For **Select data file**, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="dc04c-123">Nella finestra di dialogo **Importa da file di dati** spostarsi nella cartella contenente il file DQS da importare, quindi fare clic sul nome del file.</span><span class="sxs-lookup"><span data-stu-id="dc04c-123">In the **Import from Data File** dialog box, move to the folder that contains the .dqs file that you want to import, and then click the name of the file.</span></span> <span data-ttu-id="dc04c-124">Fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="dc04c-124">Click **Open**.</span></span>  
  
7.  <span data-ttu-id="dc04c-125">Verificare che la Knowledge Base e i domini corretti vengano visualizzati nell'elenco dei **Domini** .</span><span class="sxs-lookup"><span data-stu-id="dc04c-125">Verify that the correct knowledge base and domains are displayed in the **Domain** list.</span></span>  
  
8.  <span data-ttu-id="dc04c-126">Selezionare l'attività che si desidera eseguire, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="dc04c-126">Select the activity that you want to perform, and then click **Create**.</span></span>  
  
9. <span data-ttu-id="dc04c-127">Nella finestra di dialogo **Importa Knowledge Base** verificare che la riga dello stato indichi che l'importazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="dc04c-127">In the **Import Knowledge Base** dialog box, verify that the status line indicates that the import completed.</span></span> <span data-ttu-id="dc04c-128">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc04c-128">Click **OK**.</span></span>  
  
10. <span data-ttu-id="dc04c-129">Completare l'individuazione delle informazioni, la gestione del dominio o l'attività dei criteri di corrispondenza richieste, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="dc04c-129">Complete the knowledge discovery, domain management, or matching policy tasks that you need to perform, and then click **Finish**.</span></span>  
  
11. <span data-ttu-id="dc04c-130">Fare clic su **Pubblica** per pubblicare le informazioni nella Knowledge Base o **No** per non pubblicarle.</span><span class="sxs-lookup"><span data-stu-id="dc04c-130">Click **Publish** to publish the knowledge in the knowledge base, or **No** not to.</span></span>  
  
12. <span data-ttu-id="dc04c-131">Se si è scelto di pubblicare la Knowledge Base, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc04c-131">If you published the knowledge base, click **OK**.</span></span>  
  
13. <span data-ttu-id="dc04c-132">Nella pagina iniziale di Data Quality Services, verificare che la Knowledge Base sia elencata in **Knowledge Base recenti**.</span><span class="sxs-lookup"><span data-stu-id="dc04c-132">In the Data Quality Services home page, verify that the knowledge base is listed under **Recent knowledge bases**.</span></span>  
  
##  <a name="follow-up-after-importing-a-knowledge-base-from-a-dqs-file"></a><a name="FollowUp"></a> <span data-ttu-id="dc04c-133">Completamento: Dopo avere importato una Knowledge Base da un file DQS</span><span class="sxs-lookup"><span data-stu-id="dc04c-133">Follow Up: After Importing a Knowledge Base from a .dqs File</span></span>  
 <span data-ttu-id="dc04c-134">Dopo avere importato una Knowledge Base da un file DQS, è possibile aggiungervi informazioni o utilizzarla per progetti di pulizia o di individuazione delle corrispondenze, a seconda del suo contenuto.</span><span class="sxs-lookup"><span data-stu-id="dc04c-134">After you import a knowledge base from a .dqs file, you can add knowledge to the knowledge base or use the knowledge base in a cleansing or matching project, depending on the contents of the knowledge base.</span></span> <span data-ttu-id="dc04c-135">Per altre informazioni, vedere [Eseguire l'individuazione di informazioni](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gestione di un dominio](../../2014/data-quality-services/managing-a-domain.md), [Gestione di un dominio composito](../../2014/data-quality-services/managing-a-composite-domain.md), [Creare criteri di corrispondenza](../../2014/data-quality-services/create-a-matching-policy.md), [Pulizia dei dati](../../2014/data-quality-services/data-cleansing.md), o [Corrispondenza di dati](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="dc04c-135">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), [Managing a Composite Domain](../../2014/data-quality-services/managing-a-composite-domain.md), [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md), [Data Cleansing](../../2014/data-quality-services/data-cleansing.md), or [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
