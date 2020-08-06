---
title: Creazione di un'origine dati (esercitazione di base sul data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d7107c32-69ed-49a8-9b6e-32753eebf42c
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d8d5974c3685476f5d7a5751fb71bfa98384cf36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626994"
---
# <a name="creating-a-data-source-basic-data-mining-tutorial"></a><span data-ttu-id="8443a-102">Creazione di un'origine dati (Esercitazione di base sul data mining)</span><span class="sxs-lookup"><span data-stu-id="8443a-102">Creating a Data Source (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="8443a-103">Un' *origine dati* è una connessione dati salvata e gestita nel progetto e distribuita nel [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span><span class="sxs-lookup"><span data-stu-id="8443a-103">A *data source* is a data connection that is saved and managed in your project and deployed to your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="8443a-104">L'origine dati contiene il nome del server e del database in cui si trovano i dati di origine in aggiunta ad altre proprietà di connessione necessarie.</span><span class="sxs-lookup"><span data-stu-id="8443a-104">The data source contains the names of the server and database where your source data resides, in addition to any other required connection properties.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8443a-105">Il nome del database è [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8443a-105">The name of the database is [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="8443a-106">Se il database non è ancora stato installato, vedere la pagina relativa ai [database di esempio di Microsoft SQL](https://go.microsoft.com/fwlink/?LinkId=88417) .</span><span class="sxs-lookup"><span data-stu-id="8443a-106">If you have not already installed this database, see the [Microsoft SQL Sample Databases](https://go.microsoft.com/fwlink/?LinkId=88417) page.</span></span>  
  
### <a name="to-create-a-data-source"></a><span data-ttu-id="8443a-107">Per creare un'origine dati</span><span class="sxs-lookup"><span data-stu-id="8443a-107">To create a data source</span></span>  
  
1.  <span data-ttu-id="8443a-108">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sulla cartella **origini dati** e scegliere **nuova origine dati**.</span><span class="sxs-lookup"><span data-stu-id="8443a-108">In **Solution Explorer**, right-click the **Data Sources** folder and select **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="8443a-109">Nella pagina **Creazione guidata origine dati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8443a-109">On the **Welcome to the Data Source Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="8443a-110">Nella pagina **Selezione metodo di definizione connessione** fare clic su **nuova** per aggiungere una connessione al [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span><span class="sxs-lookup"><span data-stu-id="8443a-110">On the **Select how to define the connection** page, click **New** to add a connection to the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
4.  <span data-ttu-id="8443a-111">Nell'elenco **provider** in **gestione connessione**selezionare **Native OLE DB nativo\SQL Server Native Client 11,0**.</span><span class="sxs-lookup"><span data-stu-id="8443a-111">In the **Provider** list in **Connection Manager**, select **Native OLE DB\SQL Server Native Client 11.0**.</span></span>  
  
5.  <span data-ttu-id="8443a-112">Nella casella **nome server** Digitare o selezionare il nome del server in cui è installato [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8443a-112">In the **Server name** box, type or select the name of the server on which you installed [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span>  
  
     <span data-ttu-id="8443a-113">Ad esempio, digitare **localhost** se il database è ospitato nel server locale.</span><span class="sxs-lookup"><span data-stu-id="8443a-113">For example, type **localhost** if the database is hosted on the local server.</span></span>  
  
6.  <span data-ttu-id="8443a-114">Nel gruppo **accedi al server** selezionare **Usa autenticazione di Windows**.</span><span class="sxs-lookup"><span data-stu-id="8443a-114">In the **Log onto the server** group, select **Use Windows Authentication**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="8443a-115">Se possibile, gli implementatori devono utilizzare l'autenticazione di Windows, che fornisce un metodo di autenticazione più sicuro rispetto all'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8443a-115">Whenever possible, implementers should use Windows Authentication, as it provides a more secure authentication method than SQL Server Authentication.</span></span> <span data-ttu-id="8443a-116">Tuttavia, l'autenticazione di SQL Server è disponibile per la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="8443a-116">However, SQL Server Authentication is provided for backward compatibility.</span></span> <span data-ttu-id="8443a-117">Per ulteriori informazioni sui metodi di autenticazione, vedere [motore di database configurazione-provisioning dell'account](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="8443a-117">For more information about authentication methods, see [Database Engine Configuration - Account Provisioning](../../2014/sql-server/install/database-engine-configuration-account-provisioning.md).</span></span>  
  
7.  <span data-ttu-id="8443a-118">Nell'elenco **selezionare o immettere un nome di database** selezionare [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8443a-118">In the **Select or enter a database name** list, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8443a-119">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8443a-119">Click **Next**.</span></span>  
  
9. <span data-ttu-id="8443a-120">Nella pagina **informazioni di rappresentazione** , fare clic su **Usa account del servizio**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8443a-120">On the **Impersonation Information** page, click **Use the service account**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="8443a-121">Nella pagina **Completamento procedura guidata** si noti che, per impostazione predefinita, l'origine dati è denominata Adventure Works DW 2012.</span><span class="sxs-lookup"><span data-stu-id="8443a-121">On the **Completing the Wizard** page, notice that, by default, the data source is named Adventure Works DW 2012.</span></span>  
  
10. <span data-ttu-id="8443a-122">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="8443a-122">Click **Finish**.</span></span>  
  
     <span data-ttu-id="8443a-123">La nuova origine dati, Adventure Works DW 2012, viene visualizzata nella cartella **origini dati** in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="8443a-123">The new data source, Adventure Works DW 2012, appears in the **Data Sources** folder in Solution Explorer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8443a-124">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="8443a-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8443a-125">Creazione di una vista origine dati &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="8443a-125">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="8443a-126">Attività precedente della lezione</span><span class="sxs-lookup"><span data-stu-id="8443a-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="8443a-127">Creazione di un progetto Analysis Services &#40;esercitazione di base sul data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="8443a-127">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="8443a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8443a-128">See Also</span></span>  
 <span data-ttu-id="8443a-129">[Creare un'origine dati &#40;SSAS multidimensionale&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="8443a-129">[Create a Data Source &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/create-a-data-source-ssas-multidimensional) </span></span>  
 <span data-ttu-id="8443a-130">[Definizione di un'origine dati](../analysis-services/lesson-1-2-defining-a-data-source.md) </span><span class="sxs-lookup"><span data-stu-id="8443a-130">[Defining a Data Source](../analysis-services/lesson-1-2-defining-a-data-source.md) </span></span>  
 [<span data-ttu-id="8443a-131">Impostare opzioni di rappresentazione &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="8443a-131">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/set-impersonation-options-ssas-multidimensional)  
  
  
