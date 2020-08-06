---
title: Procedura per l'uso dei servizi CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: db5c718a-6e7f-48ec-82a3-9d5b131716e5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7cfb5a0ed0e9ded8e0be118deb3c819626448896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627343"
---
# <a name="how-to-work-with-cdc-services"></a><span data-ttu-id="b574a-102">Procedura di utilizzo dei servizi CDC</span><span class="sxs-lookup"><span data-stu-id="b574a-102">How to Work with CDC Services</span></span>
  <span data-ttu-id="b574a-103">In questa procedura viene descritto come utilizzare CDC Service Configuration Console per preparare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare con i servizi Oracle CDC e creare un nuovo servizio CDC.</span><span class="sxs-lookup"><span data-stu-id="b574a-103">This procedure describes how to use the CDC Service Configuration Console to prepare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to work with Oracle CDC Services and to create a new CDC service.</span></span>  
  
### <a name="to-work-with-cdc-services"></a><span data-ttu-id="b574a-104">Per utilizzare i servizi CDC</span><span class="sxs-lookup"><span data-stu-id="b574a-104">To work with CDC services</span></span>  
  
1.  <span data-ttu-id="b574a-105">Dal menu **Start** , selezionare **CDC Service Configuration for Oracle**.</span><span class="sxs-lookup"><span data-stu-id="b574a-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="b574a-106">Dal riquadro sinistro selezionare **Local CDC Services** (livello radice).</span><span class="sxs-lookup"><span data-stu-id="b574a-106">From the left pane, select **Local CDC Services** (the root level).</span></span>  
  
3.  <span data-ttu-id="b574a-107">Viene eseguita una delle attività seguenti o entrambe:</span><span class="sxs-lookup"><span data-stu-id="b574a-107">You carry out the one or both of the following tasks:</span></span>  
  
    -   <span data-ttu-id="b574a-108">**Prepare SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b574a-108">**Prepare SQL Server**</span></span>  
  
         <span data-ttu-id="b574a-109">Selezionare questa opzione dal riquadro **Actions** sul lato destro di CDC Service Configuration Console.</span><span class="sxs-lookup"><span data-stu-id="b574a-109">Select this option from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="b574a-110">È anche possibile fare clic con il pulsante destro del mouse su **Local CDC Services** e scegliere **Prepare SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="b574a-110">You can also right-click **Local CDC Services** and select **Prepare SQL Server**.</span></span>  
  
         <span data-ttu-id="b574a-111">Verrà visualizzata la finestra di dialogo Preparing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance for Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="b574a-111">The Preparing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instance for Oracle CDC dialog box opens.</span></span>  
  
         <span data-ttu-id="b574a-112">Per preparare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per i servizi Oracle CDC, l'account di accesso deve disporre di un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con il ruolo predefinito del server `dbcreator` .</span><span class="sxs-lookup"><span data-stu-id="b574a-112">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC services, the login must have a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with the `dbcreator` fixed server role.</span></span> <span data-ttu-id="b574a-113">Questo account di accesso viene utilizzato per creare il database MSXDBCDC obbligatorio per l'aggiunta di servizi Oracle CDC e, successivamente, di istanze di Oracle CDC.</span><span class="sxs-lookup"><span data-stu-id="b574a-113">This login is used to create the MSXDBCDC database that is required for adding Oracle CDC Services and, later on, Oracle CDC Instances.</span></span>  
  
         <span data-ttu-id="b574a-114">Per informazioni su come utilizzare questa finestra di dialogo, vedere [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="b574a-114">For information on how to use this dialog box, see [Prepare SQL Server for CDC](prepare-sql-server-for-cdc.md).</span></span> <span data-ttu-id="b574a-115">Per informazioni su come abilitare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per CDC, vedere [Procedura di preparazione di SQL Server per CDC](how-to-prepare-sql-server-for-cdc.md).</span><span class="sxs-lookup"><span data-stu-id="b574a-115">For information on how to enable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for CDC, see [How to Prepare SQL Server for CDC](how-to-prepare-sql-server-for-cdc.md).</span></span>  
  
    -   <span data-ttu-id="b574a-116">**Creare un nuovo servizio CDC**</span><span class="sxs-lookup"><span data-stu-id="b574a-116">**Create a new CDC service**</span></span>  
  
         <span data-ttu-id="b574a-117">Fare clic su **New Service** dal riquadro **Actions** sul lato destro di CDC Service Configuration Console.</span><span class="sxs-lookup"><span data-stu-id="b574a-117">Click **New Service** from the **Actions** pane on the right side of the CDC Service Configuration Console.</span></span>  
  
         <span data-ttu-id="b574a-118">È anche possibile fare clic con il pulsante destro del mouse su **Local CDC Services** e scegliere **New Service**.</span><span class="sxs-lookup"><span data-stu-id="b574a-118">You can also right-Click **Local CDC Services** and select **New Service**.</span></span>  
  
         <span data-ttu-id="b574a-119">Verrà aperta la finestra di dialogo New Oracle CDC Service.</span><span class="sxs-lookup"><span data-stu-id="b574a-119">The New Oracle CDC Service dialog box opens.</span></span>  
  
         <span data-ttu-id="b574a-120">Per informazioni su come utilizzare questa finestra di dialogo, vedere [Creare e modificare un servizio Oracle CDC](create-and-edit-an-oracle-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="b574a-120">For information on how to use this dialog box, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md).</span></span> <span data-ttu-id="b574a-121">Per informazioni sulla procedura di creazione o modifica di un servizio CDC, vedere [Procedura di creazione e modifica di un servizio CDC](how-to-create-and-edit-a-cdc-service.md).</span><span class="sxs-lookup"><span data-stu-id="b574a-121">For information on how to create or edit a CDC service, see [How to Create and Edit a CDC Service](how-to-create-and-edit-a-cdc-service.md).</span></span>  
  
         <span data-ttu-id="b574a-122">È sufficiente che l'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzato dal servizio Oracle CDC sia membro del ruolo predefinito del server `public` , non sono necessari altri privilegi.</span><span class="sxs-lookup"><span data-stu-id="b574a-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used by the Oracle CDC Service only needs to be a member of the `public` fixed-server role, no other privileges are needed.</span></span> <span data-ttu-id="b574a-123">Tuttavia, per creare il servizio Oracle CDC, l'account di accesso deve avere l'autorizzazione di scrittura per il database MSXDBCDC, ad esempio è necessario che all'account di accesso sia assegnato il ruolo del database **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="b574a-123">However, to create the Oracle CDC Service, the login must have write permission to the MSXDBCDC database, for example the **db_owner** database role must be assigned to the login.</span></span> <span data-ttu-id="b574a-124">Quando si tenta di creare una nuova istanza di Oracle CDC da un account di accesso senza autorizzazione di scrittura per il database MSXDBDCDC, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="b574a-124">When a login without write permission to the MSXDBDCDC database attempts to create a new Oracle CDC instance an error message is displayed.</span></span> <span data-ttu-id="b574a-125">Fare clic su **OK** nella finestra di dialogo per visualizzare la finestra di dialogo Connect to SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b574a-125">Click **OK** in that dialog box to display the Connect to SQL Server dialog box.</span></span>  
  
         <span data-ttu-id="b574a-126">Per informazioni su come immettere le credenziali per un account di accesso che ha l'autorizzazione di scrittura per il database MSXDBCDC, ad esempio il ruolo del database **db_owner** , vedere [Creare e modificare un servizio Oracle CDC](create-and-edit-an-oracle-cdc-service.md) e [Connessione a SQL Server](connection-to-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b574a-126">For information on how to enter the credentials for a login that has write permission to the MSXDBCDC database, such the **db_owner** database role, see [Create and Edit an Oracle CDC Service](create-and-edit-an-oracle-cdc-service.md) and [Connection to SQL Server](connection-to-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b574a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b574a-127">See Also</span></span>  
 [<span data-ttu-id="b574a-128">Usare i servizi CDC</span><span class="sxs-lookup"><span data-stu-id="b574a-128">Work with CDC Services</span></span>](work-with-cdc-services.md)  
  
  
