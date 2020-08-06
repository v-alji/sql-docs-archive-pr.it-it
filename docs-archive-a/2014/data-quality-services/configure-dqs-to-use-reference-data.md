---
title: Configurare DQS per l'uso di dati di riferimento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.admin.config.rds.f1
- sql12.dqs.administration.rdsconfiguration.f1
- sql12.dqs.administration.configuration.createDirectRDS.f1
ms.assetid: fae745e7-57a7-4cbc-8979-56ea8e392e4e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 670e984c2afabb70dece75d94701d7a3a03c95bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712412"
---
# <a name="configure-dqs-to-use-reference-data"></a><span data-ttu-id="f4e67-102">Configurazione di DQS per l'utilizzo di dati di riferimento</span><span class="sxs-lookup"><span data-stu-id="f4e67-102">Configure DQS to Use Reference Data</span></span>
  <span data-ttu-id="f4e67-103">In questo argomento viene descritta la procedura di configurazione di [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) per l'utilizzo di dati di riferimento nelle attività di pulizia dei dati.</span><span class="sxs-lookup"><span data-stu-id="f4e67-103">This topic describes how to configure [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) to use reference data for cleansing your data.</span></span> <span data-ttu-id="f4e67-104">È possibile usare i dati di riferimento da Azure Marketplace o da provider di dati di riferimento di terze parti online diretti.</span><span class="sxs-lookup"><span data-stu-id="f4e67-104">You could either use reference data from Azure Marketplace or from direct online third-party reference data providers.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="f4e67-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f4e67-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="f4e67-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="f4e67-106">Prerequisites</span></span>  
 <span data-ttu-id="f4e67-107">Per utilizzare dati di riferimento da Marketplace, è necessario disporre di una chiave account Marketplace valida.</span><span class="sxs-lookup"><span data-stu-id="f4e67-107">To use reference data from Marketplace, you must have a valid Marketplace account key.</span></span> <span data-ttu-id="f4e67-108">Per informazioni dettagliate sulla creazione di una chiave account Marketplace, vedere [creare un account](https://go.microsoft.com/fwlink/?LinkId=212936) ( https://go.microsoft.com/fwlink/?LinkId=212936) .</span><span class="sxs-lookup"><span data-stu-id="f4e67-108">For detailed information about creating a Marketplace account key, see [Create Your Account](https://go.microsoft.com/fwlink/?LinkId=212936) (https://go.microsoft.com/fwlink/?LinkId=212936).</span></span> <span data-ttu-id="f4e67-109">La chiave account Marketplace può inoltre essere creata dall'interno di [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] facendo clic su **Configurazione** in **Amministrazione** nella schermata iniziale di [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] e scegliendo **Crea ID account DataMarket** nella scheda **Dati di riferimento** .</span><span class="sxs-lookup"><span data-stu-id="f4e67-109">You can also create a Marketplace account key from within [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] by clicking **Configuration** under **Administration** in the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, and then clicking **Create a DataMarket Account ID** under the **Reference Data** tab.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f4e67-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f4e67-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f4e67-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f4e67-111">Permissions</span></span>  
 <span data-ttu-id="f4e67-112">Per configurare le impostazioni per il servizio dati di riferimento in DQS, è necessario disporre del ruolo dqs_administrator per il database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="f4e67-112">You must have the dqs_administrator role on the DQS_MAIN database to configure reference data service settings in DQS.</span></span>  
  
##  <a name="configure-dqs-to-use-reference-data-from-marketplace"></a><a name="Marketplace"></a> <span data-ttu-id="f4e67-113">Configurazione di DQS per l'utilizzo di dati di riferimento da Marketplace</span><span class="sxs-lookup"><span data-stu-id="f4e67-113">Configure DQS to Use Reference Data from Marketplace</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="f4e67-114">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="f4e67-114">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="f4e67-115">Nella schermata iniziale di [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , in **Amministrazione**, fare clic su **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="f4e67-115">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, under **Administration**, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="f4e67-116">Nella scheda **Dati di riferimento** , nell'area **Impostazioni di rete** digitare i valori appropriati nelle caselle **Server proxy** e **Porta** se l'organizzazione utilizza un server proxy per connettersi a Internet.</span><span class="sxs-lookup"><span data-stu-id="f4e67-116">In the **Reference Data** tab, under the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** boxes if you or your organization uses proxy server to connect to the Internet.</span></span>  
  
4.  <span data-ttu-id="f4e67-117">Specificare la chiave account Marketplace nella casella **ID account DataMarket** e fare clic sull'icona **Convalida ID account DataMarket** per convalidare la chiave account.</span><span class="sxs-lookup"><span data-stu-id="f4e67-117">Specify the Marketplace account key in the **DataMarket Account ID** box, and click the **Validate DataMarket Account ID** icon to validate the account key.</span></span> <span data-ttu-id="f4e67-118">Viene visualizzato un messaggio che informa se la chiave account Marketplace specificata è valida.</span><span class="sxs-lookup"><span data-stu-id="f4e67-118">A message appears to display whether the specified Marketplace account key is valid.</span></span>  
  
 <span data-ttu-id="f4e67-119">È ora possibile utilizzare in DQS i servizi dati di riferimento Marketplace sottoscritti per la chiave account Marketplace specificata.</span><span class="sxs-lookup"><span data-stu-id="f4e67-119">You are now ready to use the reference data services from Marketplace in DQS that are subscribed for the specified Marketplace account key.</span></span>  
  
##  <a name="configure-dqs-to-use-reference-data-from-direct-online-third-party-reference-data-providers"></a><a name="ThirdParty"></a> <span data-ttu-id="f4e67-120">Configurazione di DQS per l'utilizzo di dati di riferimento direttamente da provider di dati di riferimento di terze parti online</span><span class="sxs-lookup"><span data-stu-id="f4e67-120">Configure DQS to Use Reference Data from Direct Online Third-Party Reference Data Providers</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="f4e67-121">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="f4e67-121">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="f4e67-122">Nella schermata iniziale di [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , in **Amministrazione**, fare clic su **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="f4e67-122">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, under **Administration**, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="f4e67-123">Nella scheda **Dati di riferimento** , nell'area **Impostazioni di rete** digitare i valori appropriati nelle caselle **Server proxy** e **Porta** se l'organizzazione utilizza un server proxy per connettersi a Internet.</span><span class="sxs-lookup"><span data-stu-id="f4e67-123">In the **Reference Data** tab, under the **Network Settings** area, type appropriate values in the **Proxy Server** and **Port** boxes if you or your organization uses proxy server to connect to the Internet.</span></span>  
  
4.  <span data-ttu-id="f4e67-124">Nell'area **Impostazioni del servizio dati di riferimento di terze parti online diretto** , fare clic sull'icona **Aggiungi nuovo provider del servizio dati di riferimento** .</span><span class="sxs-lookup"><span data-stu-id="f4e67-124">In the **Direct Online 3rd Party Reference Data Service Settings** area, click the **Add new reference data service provider** icon.</span></span>  
  
5.  <span data-ttu-id="f4e67-125">Nella finestra di dialogo **Crea nuovo provider del servizio dati di riferimento di terze parti online diretto** specificare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4e67-125">In the **Create New Direct Online 3rd Party Reference Data Service Provider** dialog box, specify the following details:</span></span>  
  
    1.  <span data-ttu-id="f4e67-126">Nella finestra di dialogo **Nome** digitare un nome per il nuovo provider del servizio dati di riferimento diretto.</span><span class="sxs-lookup"><span data-stu-id="f4e67-126">In the **Name** box, type a name of the new direct reference data service provider.</span></span>  
  
    2.  <span data-ttu-id="f4e67-127">(Nella finestra di dialogo **Descrizione** digitare una descrizione per il nuovo provider del servizio dati di riferimento diretto (opzione facoltativa).</span><span class="sxs-lookup"><span data-stu-id="f4e67-127">(Optional) In the **Description** box, type a description of the new direct reference data service provider.</span></span>  
  
    3.  <span data-ttu-id="f4e67-128">Nella finestra di dialogo **Categoria** digitare la categoria dei dati forniti dal nuovo provider del servizio dati di riferimento diretto.</span><span class="sxs-lookup"><span data-stu-id="f4e67-128">In the **Category** box, type the category of the data provided by the new direct reference data service provider.</span></span>  
  
    4.  <span data-ttu-id="f4e67-129">Nella casella Schema, specificare lo schema che definisce la sequenza di campi (nomi colonna) da utilizzare dal provider del servizio dati di riferimento diretto.</span><span class="sxs-lookup"><span data-stu-id="f4e67-129">In the Schema box, specify the schema that defines the string of fields (column names) to be used from the direct reference data service provider.</span></span> <span data-ttu-id="f4e67-130">Un nome campo non deve contenere spazi e i campi devono essere separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="f4e67-130">A field name should not contain a space, and the fields should be separated by commas.</span></span> <span data-ttu-id="f4e67-131">Ad esempio: `FirstName, LastName, City, State`.</span><span class="sxs-lookup"><span data-stu-id="f4e67-131">For example: `FirstName, LastName, City, State`.</span></span>  
  
    5.  <span data-ttu-id="f4e67-132">Nella finestra di dialogo **URI** digitare l'URI del nuovo provider del servizio dati di riferimento diretto.</span><span class="sxs-lookup"><span data-stu-id="f4e67-132">In the **URI** box, type the URI of the direct reference data service provider.</span></span> <span data-ttu-id="f4e67-133">In DQS sono consentiti unicamente URI sicuri (con indirizzo che inizia per "https://").</span><span class="sxs-lookup"><span data-stu-id="f4e67-133">Only secure URIs (address starting with "https://") are allowed in DQS.</span></span>  
  
    6.  <span data-ttu-id="f4e67-134">Nella casella **Dimensioni massime batch** , digitare il numero massimo di record per batch che verrà inviato al provider del servizio dati di riferimento per la pulizia.</span><span class="sxs-lookup"><span data-stu-id="f4e67-134">In the **Max Batch Size** box, type the maximum number of records per batch that will be sent to the reference data service provider for cleansing.</span></span> <span data-ttu-id="f4e67-135">È possibile specificare un massimo di 100 record per batch per l'attività di pulizia.</span><span class="sxs-lookup"><span data-stu-id="f4e67-135">A maximum of 100 records per batch can be specified for the cleansing activity.</span></span>  
  
    7.  <span data-ttu-id="f4e67-136">Nella finestra di dialogo **ID account** digitare l'ID account del sottoscrittore al provider del servizio dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f4e67-136">In the **Account ID** box, type the account ID of the subscriber with the reference data service provider.</span></span>  
  
6.  <span data-ttu-id="f4e67-137">Scegliere **OK** per salvare i dati e chiudere la finestra di dialogo **Crea nuovo provider del servizio dati di riferimento di terze parti online diretto** .</span><span class="sxs-lookup"><span data-stu-id="f4e67-137">Click **OK** to save the data, and close the **Create New Direct Online 3rd Party Reference Data Service Provider** dialog box.</span></span> <span data-ttu-id="f4e67-138">Il provider di dati di riferimento di terze parti online diretto appena aggiunto diventa disponibile nella **Griglia provider del servizio dati di riferimento diretti** in DQS.</span><span class="sxs-lookup"><span data-stu-id="f4e67-138">The newly added direct online third party reference data provider becomes available in the **Direct Reference Data Service Providers Grid** in DQS.</span></span>  
  
 <span data-ttu-id="f4e67-139">È ora possibile utilizzare i servizi dati di riferimento dal provider del servizio dati di riferimento di terze parti online diretto appena aggiunto in DQS.</span><span class="sxs-lookup"><span data-stu-id="f4e67-139">You are now ready to use the reference data services from the newly configured direct online third-party reference data service provider in DQS.</span></span>  
  
##  <a name="follow-up-after-configuring-dqs-to-use-reference-data"></a><a name="FollowUp"></a><span data-ttu-id="f4e67-140">Completamento: dopo la configurazione di DQS per l'utilizzo dei dati di riferimento</span><span class="sxs-lookup"><span data-stu-id="f4e67-140">Follow Up: After Configuring DQS to use Reference Data</span></span>  
 <span data-ttu-id="f4e67-141">È ora necessario eseguire il mapping dei domini della Knowledge Base richiesti ai dati di riferimento disponibili dai provider di dati appena configurati.</span><span class="sxs-lookup"><span data-stu-id="f4e67-141">You must now map the required knowledge base domains to the reference data available from the data providers you just configured.</span></span> <span data-ttu-id="f4e67-142">A tale scopo, vedere [alleghi un dominio o un dominio composito ai dati di riferimento](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span><span class="sxs-lookup"><span data-stu-id="f4e67-142">To do so, see [Attach a Domain or Composite Domain to Reference Data](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span></span>  
  
  
