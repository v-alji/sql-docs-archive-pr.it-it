---
title: Usare le relazioni di valori in un dominio composito | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dm.cdvaluerelations.f1
ms.assetid: 5ee468f0-8538-4620-90e8-63f466c9000e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 135934ec99fed612609e5e1b962f08bb93b98ede
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726267"
---
# <a name="use-value-relations-in-a-composite-domain"></a><span data-ttu-id="6983a-102">Utilizzare le relazioni di valori in un dominio composito</span><span class="sxs-lookup"><span data-stu-id="6983a-102">Use Value Relations in a Composite Domain</span></span>
  <span data-ttu-id="6983a-103">In questo argomento viene descritto come visualizzare le combinazioni di valori presenti nel dominio composito durante il processo di individuazione delle informazioni in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="6983a-103">This topic describes how to view value combinations found for the composite domain during the knowledge discovery process in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="6983a-104">In questa pagina viene illustrato il numero di occorrenze delle combinazioni di valori.</span><span class="sxs-lookup"><span data-stu-id="6983a-104">This page shows the number of occurrences of the value combinations.</span></span> <span data-ttu-id="6983a-105">La gestione dei valori non è supportata per i domini compositi, pertanto non è possibile eseguire alcuna operazione su questi valori.</span><span class="sxs-lookup"><span data-stu-id="6983a-105">Value management is not supported for composite domains, so you cannot perform any operations on these values.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6983a-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6983a-106">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6983a-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6983a-107">Prerequisites</span></span>  
 <span data-ttu-id="6983a-108">Per visualizzare le relazioni di valori, è necessario avere creato e aperto un dominio composito.</span><span class="sxs-lookup"><span data-stu-id="6983a-108">To view value relations, you must have created and opened a composite domain.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6983a-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6983a-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6983a-110">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6983a-110">Permissions</span></span>  
 <span data-ttu-id="6983a-111">Per visualizzare le relazioni di valori in un dominio composito, è necessario disporre del ruolo dqs_kb_editor o dqs_administrator nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="6983a-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to view value relations in a composite domain.</span></span>  
  
##  <a name="view-value-relations"></a><a name="Use"></a><span data-ttu-id="6983a-112">Visualizza relazioni tra valori</span><span class="sxs-lookup"><span data-stu-id="6983a-112">View Value Relations</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="6983a-113">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="6983a-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="6983a-114">Nella schermata iniziale del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] aprire o creare una Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="6983a-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open or create a knowledge base.</span></span> <span data-ttu-id="6983a-115">Selezionare **Gestione dominio** come attività, quindi fare clic su **Apri** o **Crea**.</span><span class="sxs-lookup"><span data-stu-id="6983a-115">Select **Domain Management** as the activity, and then click **Open** or **Create**.</span></span> <span data-ttu-id="6983a-116">Per ulteriori informazioni, vedere [Creare una Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md) o [Apertura di una Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="6983a-116">For more information, see [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md) or [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
3.  <span data-ttu-id="6983a-117">**Dall'elenco di domini** nella pagina **Gestione dominio** selezionare il dominio composito per il quale si desidera creare una regola di dominio o creare un nuovo dominio composito.</span><span class="sxs-lookup"><span data-stu-id="6983a-117">From the **Domain list** on the **Domain Management** page, select the composite domain that you want to create a domain rule for, or create a new composite domain.</span></span> <span data-ttu-id="6983a-118">Se è necessario creare un nuovo dominio, vedere [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md).</span><span class="sxs-lookup"><span data-stu-id="6983a-118">If you have to create a new domain, see [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md).</span></span>  
  
4.  <span data-ttu-id="6983a-119">Fare clic sulla scheda **Relazioni valore** .</span><span class="sxs-lookup"><span data-stu-id="6983a-119">Click the **Value Relations** tab.</span></span>  
  
5.  <span data-ttu-id="6983a-120">Visualizzare le frequenze riportate per ogni combinazione di valori.</span><span class="sxs-lookup"><span data-stu-id="6983a-120">View the frequencies displayed for each value combination.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6983a-121">Nella tabella **Valore** viene visualizzata ogni combinazione di valori presente nel dominio composito.</span><span class="sxs-lookup"><span data-stu-id="6983a-121">The **Value** table shows each combination of values that exists in the composite domain.</span></span> <span data-ttu-id="6983a-122">Ogni valore viene mostrato nel singolo dominio a cui si applica.</span><span class="sxs-lookup"><span data-stu-id="6983a-122">Each value is shown in the single domain that it applies to.</span></span> <span data-ttu-id="6983a-123">L'ordinamento predefinito della tabella delle relazioni di valori è per frequenza, ma è possibile fare clic su un'altra colonna per ordinare in base a tale colonna.</span><span class="sxs-lookup"><span data-stu-id="6983a-123">The default sorting of the value relations table is by frequency, but you can click on another column to sort by that column.</span></span> <span data-ttu-id="6983a-124">Vengono visualizzati solo i valori con una frequenza maggiore o uguale a 20.</span><span class="sxs-lookup"><span data-stu-id="6983a-124">Only those values with a frequency greater than or equal to 20 are displayed.</span></span>  
  
6.  <span data-ttu-id="6983a-125">Non è possibile modificare alcun valore nella tabella.</span><span class="sxs-lookup"><span data-stu-id="6983a-125">You cannot change any of the values in the table.</span></span> <span data-ttu-id="6983a-126">Se sono state eseguite le altre operazioni, fare clic su **Fine** per completare l'attività di gestione del dominio.</span><span class="sxs-lookup"><span data-stu-id="6983a-126">If you have performed other operations, click **Finish** to complete the domain management activity.</span></span> <span data-ttu-id="6983a-127">In caso contrario, fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="6983a-127">Otherwise, click **Cancel**.</span></span>  
  
##  <a name="follow-up-after-viewing-value-relations"></a><a name="FollowUp"></a><span data-ttu-id="6983a-128">Completamento: fasi successive alla visualizzazione delle relazioni tra valori</span><span class="sxs-lookup"><span data-stu-id="6983a-128">Follow Up: After Viewing Value Relations</span></span>  
 <span data-ttu-id="6983a-129">Dopo avere visualizzato le relazioni di valori, è possibile eseguire ulteriori attività di gestione del dominio, quali l'individuazione delle informazioni per aggiungere informazioni al dominio o l'aggiunta di criteri di corrispondenza al dominio.</span><span class="sxs-lookup"><span data-stu-id="6983a-129">After you view value relations, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="6983a-130">Per altre informazioni, vedere [Eseguire l'individuazione delle informazioni](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gestione di un dominio](../../2014/data-quality-services/managing-a-domain.md) o [Creare criteri di corrispondenza](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="6983a-130">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
