---
title: Procedura di creazione e modifica di un servizio CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 1b3d47a5-dc89-482d-bbc7-fff04f194c43
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d90534b475901b08fcd2e09acdc0f7976f0fb6e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712299"
---
# <a name="how-to-create-and-edit-a-cdc-service"></a><span data-ttu-id="422d7-102">Procedura di creazione e modifica di un servizio CDC</span><span class="sxs-lookup"><span data-stu-id="422d7-102">How to Create and Edit a CDC Service</span></span>
  <span data-ttu-id="422d7-103">In queste procedure viene illustrato come creare e modificare un nuovo servizio Oracle CDC da CDC Service Configuration Console.</span><span class="sxs-lookup"><span data-stu-id="422d7-103">These procedures describe how to create and edit a new Oracle CDC Service from the CDC Service Configuration Console.</span></span>  
  
 <span data-ttu-id="422d7-104">Per questa procedura è necessario un utente di Windows con privilegi di amministratore per il computer in cui viene configurato il servizio Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="422d7-104">This procedure requires a Windows user with administrator privileges on the computer where the Oracle CDC service is configured.</span></span>  
  
### <a name="to-create-a-new-cdc-service"></a><span data-ttu-id="422d7-105">Per creare un nuovo servizio CDC</span><span class="sxs-lookup"><span data-stu-id="422d7-105">To create a new CDC service</span></span>  
  
1.  <span data-ttu-id="422d7-106">Dal menu **Start** , selezionare **CDC Service Configuration for Oracle**.</span><span class="sxs-lookup"><span data-stu-id="422d7-106">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="422d7-107">Dal riquadro sinistro fare clic con il pulsante destro del mouse su Local CDC Services e selezionare New Service.</span><span class="sxs-lookup"><span data-stu-id="422d7-107">From the left pane, right click Local CDC Services and select New Service</span></span>  
  
     <span data-ttu-id="422d7-108">È inoltre possibile fare clic su **New Service** nel riquadro **Actions** .</span><span class="sxs-lookup"><span data-stu-id="422d7-108">You can also click **New Service** from the **Actions** pane.</span></span>  
  
3.  <span data-ttu-id="422d7-109">Digitare o immettere le informazioni richieste nella finestra di dialogo New Oracle CDC Service.</span><span class="sxs-lookup"><span data-stu-id="422d7-109">Type or enter the required information in the New Oracle CDC Service dialog box.</span></span> <span data-ttu-id="422d7-110">Per informazioni sull'immissione di informazioni nella finestra di dialogo New Oracle CDC Service, vedere [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) .</span><span class="sxs-lookup"><span data-stu-id="422d7-110">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the New Oracle CDC Service dialog box.</span></span>  
  
     <span data-ttu-id="422d7-111">L'account di accesso [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornito nella finestra di dialogo New Oracle CDC Service viene utilizzato dal servizio Oracle CDC per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="422d7-111">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login provided in the New Oracle CDC Service dialog box is used by the Oracle CDC Service when the service runs.</span></span> <span data-ttu-id="422d7-112">È sufficiente che l'account di accesso sia membro del ruolo predefinito del server pubblico, non sono necessari altri privilegi.</span><span class="sxs-lookup"><span data-stu-id="422d7-112">This login only needs to be a member of the public fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="422d7-113">Una volta aggiunte nuove istanze di Oracle CDC, l'account di accesso riceve l'accesso **db_owner** ai database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC associati.</span><span class="sxs-lookup"><span data-stu-id="422d7-113">Once new Oracle CDC Instances are added, that login receives **db_owner** access to the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC databases.</span></span>  
  
4.  <span data-ttu-id="422d7-114">Al termine dell'immissione delle informazioni necessarie, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="422d7-114">When you finish entering the required information, click **OK**.</span></span>  
  
     <span data-ttu-id="422d7-115">Per creare la definizione del servizio Windows di Oracle CDC, è necessario aggiornare l'accesso al database MSXDBCDC nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associata.</span><span class="sxs-lookup"><span data-stu-id="422d7-115">To create the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="422d7-116">Quando si fa clic su **OK**, una finestra di dialogo richiede all'utente di immettere un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con un accesso aggiornato al database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="422d7-116">When you click **OK**, a dialog box prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
     <span data-ttu-id="422d7-117">Per informazioni sui dati da digitare nella finestra di dialogo Connect to SQL Server, vedere [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="422d7-117">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="422d7-118">Scegliere **OK** per chiudere la finestra di dialogo New Oracle CDC Service.</span><span class="sxs-lookup"><span data-stu-id="422d7-118">Click **OK** to close the New Oracle CDC Service dialog box.</span></span>  
  
### <a name="to-edit-a-cdc-service"></a><span data-ttu-id="422d7-119">Per modificare un servizio CDC</span><span class="sxs-lookup"><span data-stu-id="422d7-119">To edit a CDC service</span></span>  
  
1.  <span data-ttu-id="422d7-120">Dal menu **Start** , selezionare **CDC Service Configuration for Oracle**.</span><span class="sxs-lookup"><span data-stu-id="422d7-120">From the **Start** menu, select **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="422d7-121">Dal riquadro sinistro selezionare **Local CDC Services** (Servizi CDC locali) e quindi fare clic con il pulsante destro del mouse sul servizio locale da modificare e selezionare **Properties**(Proprietà).</span><span class="sxs-lookup"><span data-stu-id="422d7-121">From the left pane, select **Local CDC Services** then right-click the local service you want to edit and select **Properties**.</span></span>  
  
     <span data-ttu-id="422d7-122">È inoltre possibile selezionare il servizio utilizzato al centro, quindi nel riquadro **Actions** fare clic su **Properties**.</span><span class="sxs-lookup"><span data-stu-id="422d7-122">You can also select the service you are working with in the middle and then from the **Actions** pane, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="422d7-123">Digitare o immettere le informazioni richieste nella finestra di dialogo CDC Service Properties.</span><span class="sxs-lookup"><span data-stu-id="422d7-123">Type or enter the required information in the CDC Service Properties dialog box.</span></span> <span data-ttu-id="422d7-124">Per informazioni sull'immissione di informazioni nella finestra di dialogo CDC Service Properties, vedere [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) .</span><span class="sxs-lookup"><span data-stu-id="422d7-124">See [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) for information on how to enter information in the CDC Service Properties dialog box.</span></span>  
  
4.  <span data-ttu-id="422d7-125">Al termine dell'immissione delle informazioni richieste, fare clic su **OK**. Verrà visualizzata la finestra di dialogo Connect to SQL Server.</span><span class="sxs-lookup"><span data-stu-id="422d7-125">When you finish entering the required information, Click **OK**, the Connect to SQL Server dialog box opens.</span></span>  
  
     <span data-ttu-id="422d7-126">Quando si tenta di creare una nuova istanza di Oracle CDC da un account di accesso senza autorizzazione di scrittura per il database MSXDBDCDC, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="422d7-126">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="422d7-127">Fare clic su **OK** nella finestra di dialogo per visualizzare la finestra di dialogo Connect to SQL Server.</span><span class="sxs-lookup"><span data-stu-id="422d7-127">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span> <span data-ttu-id="422d7-128">In questa finestra di dialogo è necessario immettere le credenziali per un account di accesso con autorizzazione di scrittura per il database MSXDBCDC, ad esempio il ruolo del database **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="422d7-128">In this dialog box you must enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role.</span></span>  
  
     <span data-ttu-id="422d7-129">Per informazioni sui dati da digitare nella finestra di dialogo Connect to SQL Server, vedere [Connection to SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="422d7-129">For information about the data you must type into the Connect to SQL Server dialog box, see [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="422d7-130">Fare clic su **OK** nella finestra di dialogo Connect to Oracle.</span><span class="sxs-lookup"><span data-stu-id="422d7-130">Click **OK** in the Connect to Oracle dialog box.</span></span> <span data-ttu-id="422d7-131">Verranno chiuse entrambe le finestre di dialogo e il servizio verrà aggiornato e registrato.</span><span class="sxs-lookup"><span data-stu-id="422d7-131">Both dialog boxes close and the service is updated and registered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="422d7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="422d7-132">See Also</span></span>  
 <span data-ttu-id="422d7-133">[Progettazione Change Data Capture per Oracle di Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="422d7-133">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="422d7-134">Creare e modificare un servizio Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="422d7-134">Create and Edit an Oracle CDC Service</span></span>](create-and-edit-an-oracle-cdc-service.md)  
  
  
