---
title: Connettere un'applicazione del servizio PowerPivot a un'applicazione Web di SharePoint in Amministrazione centrale | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5da8e29-7ffd-44e7-bf61-344fa5bea8ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5fc6dcde4cc2d18c3650adbab0ec71ef5c6265cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635797"
---
# <a name="connect-a-powerpivot-service-application-to-a-sharepoint-web-application-in-central-administration"></a><span data-ttu-id="7af5b-102">Connettere un'applicazione del servizio PowerPivot a un'applicazione Web SharePoint in Amministrazione centrale</span><span class="sxs-lookup"><span data-stu-id="7af5b-102">Connect a PowerPivot Service Application to a SharePoint Web Application in Central Administration</span></span>
  <span data-ttu-id="7af5b-103">Un'applicazione di servizio PowerPivot può essere utilizzata da un numero qualsiasi di applicazioni Web SharePoint nella farm.</span><span class="sxs-lookup"><span data-stu-id="7af5b-103">A PowerPivot service application can be used by any number of SharePoint Web applications in the farm.</span></span> <span data-ttu-id="7af5b-104">Per rendere disponibile un'applicazione di servizio PowerPivot, aggiungerla a un elenco di associazioni al servizio.</span><span class="sxs-lookup"><span data-stu-id="7af5b-104">To make a PowerPivot service application available, you add it to a service association list.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7af5b-105">Per assicurare il corretto funzionamento del dashboard di gestione PowerPivot, è necessario che almeno un'applicazione di servizio PowerPivot sia presente nel gruppo predefinito.</span><span class="sxs-lookup"><span data-stu-id="7af5b-105">You must have one PowerPivot service application in the default group to ensure that PowerPivot Management Dashboard works properly.</span></span> <span data-ttu-id="7af5b-106">Non aggiungere più di un'applicazione di servizio PowerPivot al gruppo predefinito.</span><span class="sxs-lookup"><span data-stu-id="7af5b-106">Do not add more than one PowerPivot service application to the default group.</span></span> <span data-ttu-id="7af5b-107">L'aggiunta di più voci dello stesso tipo di applicazione di servizio non è una configurazione supportata e potrebbe provocare errori.</span><span class="sxs-lookup"><span data-stu-id="7af5b-107">Adding multiple entries of the same service application type is not a supported configuration and might cause errors.</span></span> <span data-ttu-id="7af5b-108">Se si creano applicazioni di servizio aggiuntive, aggiungerle agli elenchi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7af5b-108">If you are creating additional service applications, add them to custom lists.</span></span>  
  
 <span data-ttu-id="7af5b-109">In questo argomento sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7af5b-109">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="7af5b-110">Aggiungere l'applicazione di servizio PowerPivot al gruppo predefinito</span><span class="sxs-lookup"><span data-stu-id="7af5b-110">Add PowerPivot Services Application to the Default Group</span></span>](#default)  
  
 [<span data-ttu-id="7af5b-111">Aggiungere l'applicazione di servizio PowerPivot a un elenco personalizzato di associazioni al servizio</span><span class="sxs-lookup"><span data-stu-id="7af5b-111">Add PowerPivot Services Application a Custom Service Association List</span></span>](#custom)  
  
##  <a name="add-powerpivot-services-application-to-the-default-group"></a><a name="default"></a><span data-ttu-id="7af5b-112">Aggiungere l'applicazione di servizi PowerPivot al gruppo predefinito</span><span class="sxs-lookup"><span data-stu-id="7af5b-112">Add PowerPivot Services Application to the Default Group</span></span>  
 <span data-ttu-id="7af5b-113">Un elenco di associazioni al servizio è un elenco di servizi condivisi che forniscono risorse ad altre applicazioni Web SharePoint nella farm.</span><span class="sxs-lookup"><span data-stu-id="7af5b-113">A service association list is a list of shared services that provide resources to other SharePoint Web applications in the farm.</span></span> <span data-ttu-id="7af5b-114">Per la farm è disponibile un gruppo predefinito di associazioni al servizio.</span><span class="sxs-lookup"><span data-stu-id="7af5b-114">There is one default group of service associations for the farm.</span></span>  
  
 <span data-ttu-id="7af5b-115">Per essere nell'elenco, un'applicazione di servizio PowerPivot può essere aggiunta al momento della creazione o in seguito eseguendo i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="7af5b-115">To be on the list, a PowerPivot service application can either be added when you create the application or afterwards by using the following steps.</span></span>  
  
1.  <span data-ttu-id="7af5b-116">In Amministrazione centrale, in **Gestione applicazioni**, fare clic su **Configura associazioni dell'applicazione di servizio**.</span><span class="sxs-lookup"><span data-stu-id="7af5b-116">In Central Administration, in **Application Management**, click **Configure service application associations**.</span></span>  
  
2.  <span data-ttu-id="7af5b-117">In Gruppo proxy applicazioni fare clic su **predefinito**.</span><span class="sxs-lookup"><span data-stu-id="7af5b-117">In Application Proxy Group, click **default**.</span></span>  
  
3.  <span data-ttu-id="7af5b-118">Selezionare la casella di controllo accanto all'applicazione di servizio PowerPivot (indicata dal nome del tipo `PowerPivot Service Application Proxy`).</span><span class="sxs-lookup"><span data-stu-id="7af5b-118">Select the checkbox next to the PowerPivot service application (indicated by type name `PowerPivot Service Application Proxy`).</span></span> <span data-ttu-id="7af5b-119">Se sono presenti più applicazioni di servizio PowerPivot, sceglierne solo una.</span><span class="sxs-lookup"><span data-stu-id="7af5b-119">If you have more than one PowerPivot service application, choose just one.</span></span>  
  
4.  <span data-ttu-id="7af5b-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7af5b-120">Click **OK**.</span></span>  
  
##  <a name="add-powerpivot-services-application-a-custom-service-association-list"></a><a name="custom"></a><span data-ttu-id="7af5b-121">Aggiunta di un'applicazione di servizi PowerPivot a un elenco di associazioni di servizi personalizzato</span><span class="sxs-lookup"><span data-stu-id="7af5b-121">Add PowerPivot Services Application a Custom Service Association List</span></span>  
 <span data-ttu-id="7af5b-122">Il gruppo predefinito può essere sostituito da un elenco personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7af5b-122">The default group can be replaced by a custom list.</span></span> <span data-ttu-id="7af5b-123">Un elenco personalizzato viene creato in modo specifico per una sola applicazione Web SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7af5b-123">A custom list is created specifically for a single SharePoint Web application.</span></span> <span data-ttu-id="7af5b-124">Il gruppo predefinito viene sostituito solo dalle associazioni al servizio specificate da un amministratore di farm o del servizio.</span><span class="sxs-lookup"><span data-stu-id="7af5b-124">It overrides the default group and replaces it with only those service associations that a farm or service administrator specifies.</span></span> <span data-ttu-id="7af5b-125">Se sono state create più applicazioni di servizio PowerPivot, è necessario utilizzare un elenco personalizzato per specificare quale utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7af5b-125">If you created multiple PowerPivot service applications, you must use a custom list to specify which one to use.</span></span> <span data-ttu-id="7af5b-126">Un elenco personalizzato non può essere riutilizzato da altre applicazioni Web.</span><span class="sxs-lookup"><span data-stu-id="7af5b-126">A custom list cannot be reused by other Web applications.</span></span> <span data-ttu-id="7af5b-127">Si applica solo all'applicazione Web per cui è stato creato.</span><span class="sxs-lookup"><span data-stu-id="7af5b-127">It applies only to the Web application for which it was created.</span></span>  
  
1.  <span data-ttu-id="7af5b-128">In **Gestione applicazioni**di Amministrazione centrale fare clic su **Gestisci applicazioni Web**.</span><span class="sxs-lookup"><span data-stu-id="7af5b-128">In Central Administration, in **Application Management**, click **Manage web applications**.</span></span>  
  
2.  <span data-ttu-id="7af5b-129">Selezionare l'applicazione, ad esempio SharePoint -80.</span><span class="sxs-lookup"><span data-stu-id="7af5b-129">Select the application (for example, SharePoint -80).</span></span>  
  
3.  <span data-ttu-id="7af5b-130">In Applicazioni Web, in Gestisci, fare clic su **Connessioni servizio**.</span><span class="sxs-lookup"><span data-stu-id="7af5b-130">In Web Applications, in Manage, click **Service Connections**.</span></span>  
  
4.  <span data-ttu-id="7af5b-131">In **Modifica il gruppo di connessioni seguente**selezionare **[personalizzato]**.</span><span class="sxs-lookup"><span data-stu-id="7af5b-131">In **Edit the following group of connections**, select **[custom]**.</span></span>  
  
5.  <span data-ttu-id="7af5b-132">Selezionare la casella di controllo accanto a ogni connessione all'applicazione di servizio che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7af5b-132">Select the checkbox next to each service application connection you want to use.</span></span> <span data-ttu-id="7af5b-133">Se sono presenti più applicazioni di servizio PowerPivot (indicato dal tipo impostato su `PowerPivot Service Application Proxy`), assicurarsi di sceglierne una sola.</span><span class="sxs-lookup"><span data-stu-id="7af5b-133">If you have multiple PowerPivot service applications (indicated by Type set to `PowerPivot Service Application Proxy`), be sure to choose only one.</span></span>  
  
6.  <span data-ttu-id="7af5b-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7af5b-134">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7af5b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7af5b-135">See Also</span></span>  
 <span data-ttu-id="7af5b-136">[Creazione e configurazione di un'applicazione di servizio PowerPivot in Amministrazione centrale](create-and-configure-power-pivot-service-application-in-ca.md) </span><span class="sxs-lookup"><span data-stu-id="7af5b-136">[Create and Configure a PowerPivot Service Application in Central Administration](create-and-configure-power-pivot-service-application-in-ca.md) </span></span>  
 [<span data-ttu-id="7af5b-137">Configurazione iniziale &#40;PowerPivot per SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="7af5b-137">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
  
