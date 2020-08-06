---
title: Creare un progetto Data Quality | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dqproject.newdqproject.f1
helpviewer_keywords:
- create,data quality project
- data quality project,create
ms.assetid: 19c52d2b-d28e-4449-ab59-5fe0dc326cd9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3bab14b34123464450bcf0de7540364fc642343e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712387"
---
# <a name="create-a-data-quality-project"></a><span data-ttu-id="30aec-102">Creare un progetto Data Quality</span><span class="sxs-lookup"><span data-stu-id="30aec-102">Create a Data Quality Project</span></span>
  <span data-ttu-id="30aec-103">In questo argomento viene descritto come creare un progetto Data Quality mediante il [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30aec-103">This topic describes how to create a data quality project by using [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)].</span></span> <span data-ttu-id="30aec-104">Un progetto Data Quality viene utilizzato per eseguire l'attività di pulizia o di corrispondenza in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="30aec-104">A data quality project is used to run the cleansing or matching activity in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="30aec-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="30aec-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="30aec-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="30aec-106">Prerequisites</span></span>  
 <span data-ttu-id="30aec-107">È necessario disporre di una Knowledge Base pertinente da utilizzare nel progetto Data Quality per l'attività di pulizia e di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="30aec-107">You must have a relevant knowledge base to use in the data quality project for the cleansing or matching activity.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="30aec-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="30aec-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="30aec-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="30aec-109">Permissions</span></span>  
 <span data-ttu-id="30aec-110">Per creare un progetto Data Quality, è necessario disporre del ruolo dqs_kb_editor o dqs_kb_operator nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="30aec-110">You must have the dqs_kb_editor or dqs_kb_operator role on the DQS_MAIN database to create a data quality project.</span></span>  
  
##  <a name="create-a-data-quality-project"></a><a name="Create"></a><span data-ttu-id="30aec-111">Creazione di un progetto Data Quality</span><span class="sxs-lookup"><span data-stu-id="30aec-111">Create a Data Quality Project</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="30aec-112">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="30aec-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="30aec-113">Nella schermata iniziale del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] fare clic su **Nuovo progetto Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="30aec-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **New data quality project**.</span></span>  
  
3.  <span data-ttu-id="30aec-114">Nella schermata **Nuovo progetto Data Quality** :</span><span class="sxs-lookup"><span data-stu-id="30aec-114">In the **New Data Quality Project** screen:</span></span>  
  
    1.  <span data-ttu-id="30aec-115">Nella casella **Nome** digitare un nome per il nuovo progetto Data Quality.</span><span class="sxs-lookup"><span data-stu-id="30aec-115">In the **Name** box, type a name for the new data quality project.</span></span>  
  
    2.  <span data-ttu-id="30aec-116">Nella casella **Descrizione** digitare una descrizione per il nuovo progetto Data Quality (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="30aec-116">(Optional) In the **Description** box, type a description for the new data quality project.</span></span>  
  
    3.  <span data-ttu-id="30aec-117">Nell'elenco **Usa Knowledge Base** fare clic per selezionare una Knowledge Base da utilizzare per il progetto Data Quality.</span><span class="sxs-lookup"><span data-stu-id="30aec-117">In the **Use Knowledge base** list, click to select a knowledge base to be used for the data quality project.</span></span> <span data-ttu-id="30aec-118">Nell'area **Dettagli Knowledge Base: <Nome_Knowledge_Base>** sul lato destro vengono visualizzati i nomi di dominio disponibili nella knowledge base selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aec-118">The **Knowledge base details: <Knowledge_Base_Name>** area on the right side displays the domain names available in the selected knowledge base.</span></span>  
  
    4.  <span data-ttu-id="30aec-119">Nell'area **Seleziona attività** fare clic su un'attività che si desidera eseguire utilizzando questo progetto Data Quality:</span><span class="sxs-lookup"><span data-stu-id="30aec-119">In the **Select Activity** area, click on an activity that you want to perform using this data quality project:</span></span>  
  
        -   <span data-ttu-id="30aec-120">**Pulizia**: selezionare questa attività per pulire i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="30aec-120">**Cleansing**: Select this activity to cleanse the source data.</span></span>  
  
        -   <span data-ttu-id="30aec-121">**Corrispondenza**: selezionare questa attività per eseguire una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="30aec-121">**Matching**: Select this activity to perform matching.</span></span> <span data-ttu-id="30aec-122">Questa attività è disponibile solo se la Knowledge Base selezionata per il progetto Data Quality contiene i criteri di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="30aec-122">This activity is available only if the knowledge base selected for the data quality project contains a matching policy.</span></span>  
  
4.  <span data-ttu-id="30aec-123">Fare clic su **Crea** per creare un progetto Data Quality.</span><span class="sxs-lookup"><span data-stu-id="30aec-123">Click **Create** to create a data quality project.</span></span>  
  
##  <a name="follow-up-after-creating-a-data-quality-project"></a><a name="FollowUp"></a><span data-ttu-id="30aec-124">Completamento: fasi successive alla creazione di un progetto Data Quality</span><span class="sxs-lookup"><span data-stu-id="30aec-124">Follow Up: After Creating a Data Quality Project</span></span>  
 <span data-ttu-id="30aec-125">Dopo avere creato un progetto Data Quality, viene visualizzata una procedura guidata che è possibile utilizzare per eseguire l'attività selezionata: pulizia o corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="30aec-125">After you create a data quality project, you are presented with a wizard that you use to perform the selected activity: cleansing or matching.</span></span> <span data-ttu-id="30aec-126">Per altre informazioni sulle attività di pulizia e corrispondenza, vedere [Pulizia dei dati](../../2014/data-quality-services/data-cleansing.md) e [Corrispondenza di dati](../../2014/data-quality-services/data-matching.md).</span><span class="sxs-lookup"><span data-stu-id="30aec-126">For more information about the cleansing and matching activities, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md) and [Data Matching](../../2014/data-quality-services/data-matching.md).</span></span>  
  
  
