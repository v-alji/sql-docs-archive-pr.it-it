---
title: Gestire un servizio Oracle CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- createSrv
ms.assetid: 5972cee3-b1a9-4c56-aed6-bdddf84af283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f5fbe769980297a06b7958ecad04bfed85b9b714
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712272"
---
# <a name="manage-an-oracle-cdc-service"></a><span data-ttu-id="b2714-102">Manage an Oracle CDC Service</span><span class="sxs-lookup"><span data-stu-id="b2714-102">Manage an Oracle CDC Service</span></span>
  <span data-ttu-id="b2714-103">È possibile utilizzare CDC Service Configuration Console per gestire un servizio CDC specifico.</span><span class="sxs-lookup"><span data-stu-id="b2714-103">You can use the CDC Service Configuration Console to manage a specific CDC Service.</span></span>  
  
 <span data-ttu-id="b2714-104">**Per selezionare il servizio CDC che si desidera utilizzare**</span><span class="sxs-lookup"><span data-stu-id="b2714-104">**To select the CDC service you want to work with**</span></span>  
  
1.  <span data-ttu-id="b2714-105">Dal riquadro sinistro di CDC Service Configuration Console, espandere **Local CDC Services**.</span><span class="sxs-lookup"><span data-stu-id="b2714-105">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
2.  <span data-ttu-id="b2714-106">Selezionare il servizio CDC che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b2714-106">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="b2714-107">È inoltre possibile fare clic con il pulsante destro del mouse sul servizio CDC da utilizzare e selezionare l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="b2714-107">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="b2714-108">Visualizzare [cosa puoi fare con un servizio CDC](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="b2714-108">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
 <span data-ttu-id="b2714-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="b2714-109">**OR**</span></span>  
  
1.  <span data-ttu-id="b2714-110">Selezionare **Local CDC Services** nel riquadro sinistro in CDC Service Configuration Console.</span><span class="sxs-lookup"><span data-stu-id="b2714-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console.</span></span>  
  
2.  <span data-ttu-id="b2714-111">Dalla sezione centrale di CDC Service Configuration Console selezionare il servizio che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b2714-111">From the middle section of the CDC Service Configuration Console, select the service you want to work with.</span></span>  
  
     <span data-ttu-id="b2714-112">È inoltre possibile fare clic con il pulsante destro del mouse sul servizio CDC da utilizzare e selezionare l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="b2714-112">You can also right-click the CDC service you want to work with and select the desired action.</span></span> <span data-ttu-id="b2714-113">Visualizzare [cosa puoi fare con un servizio CDC](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span><span class="sxs-lookup"><span data-stu-id="b2714-113">See [What can you do with a CDC Service](manage-an-oracle-cdc-service.md#BKMK_WhatcandowithCDCService).</span></span>  
  
##  <a name="what-can-you-do-with-a-cdc-service"></a><a name="BKMK_WhatcandowithCDCService"></a> <span data-ttu-id="b2714-114">Cosa può fare con un servizio CDC</span><span class="sxs-lookup"><span data-stu-id="b2714-114">What can you do with a CDC Service</span></span>  
 <span data-ttu-id="b2714-115">Quando si utilizza un servizio CDC è possibile eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2714-115">You can carry out the following actions when working with a CDC service.</span></span>  
  
### <a name="delete-the-service"></a><span data-ttu-id="b2714-116">Eliminare il servizio</span><span class="sxs-lookup"><span data-stu-id="b2714-116">Delete the service</span></span>  
 <span data-ttu-id="b2714-117">Dal riquadro **Actions** sul lato destro di CDC Service Configuration Console, fare clic su **Delete** per eliminare il servizio.</span><span class="sxs-lookup"><span data-stu-id="b2714-117">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
 <span data-ttu-id="b2714-118">È inoltre possibile fare clic con il pulsante destro del mouse sul servizio CDC da eliminare e scegliere **Delete**.</span><span class="sxs-lookup"><span data-stu-id="b2714-118">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
 <span data-ttu-id="b2714-119">**Nota**: se il servizio è in esecuzione al momento dell'eliminazione, il servizio viene arrestato prima di essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="b2714-119">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
 <span data-ttu-id="b2714-120">Per eliminare la definizione del servizio Windows di Oracle CDC, è necessario aggiornare l'accesso al database MSXDBCDC nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associata.</span><span class="sxs-lookup"><span data-stu-id="b2714-120">To delete the Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="b2714-121">Quando si fa clic su OK per eliminare il servizio, viene effettuato un tentativo di eliminare la registrazione del servizio Oracle CDC nel database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="b2714-121">When you click OK to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="b2714-122">Se non è possibile eliminare la registrazione del servizio Oracle CDC tramite il programma perché non sono disponibili le autorizzazioni appropriate, viene richiesto all'utente di immettere un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con autorizzazioni di aggiornamento per il database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="b2714-122">If the program cannot delete the Oracle CDC Service registration because it does not have the proper permissions, it prompts the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with update permissions to the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="b2714-123">Per informazioni sui dati da immettere nella finestra di dialogo Connect to SQL Server, vedere [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="b2714-123">For information about the data you must enter in the Connect to SQL Server dialog box, see [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
### <a name="edit-the-cdc-service-properties"></a><span data-ttu-id="b2714-124">Modificare le proprietà del servizio CDC</span><span class="sxs-lookup"><span data-stu-id="b2714-124">Edit the CDC Service Properties</span></span>  
 <span data-ttu-id="b2714-125">Dal riquadro **Actions** sul lato destro di CDC Service Configuration Console, fare clic su **Properties**.</span><span class="sxs-lookup"><span data-stu-id="b2714-125">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
 <span data-ttu-id="b2714-126">È inoltre possibile fare clic con il pulsante destro del mouse sul servizio CDC in cui si desidera modificare le proprietà e scegliere **Properties**.</span><span class="sxs-lookup"><span data-stu-id="b2714-126">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2714-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2714-127">See Also</span></span>  
 [<span data-ttu-id="b2714-128">Procedura di gestione di un servizio CDC locale</span><span class="sxs-lookup"><span data-stu-id="b2714-128">How to Manage a Local CDC Service</span></span>](how-to-manage-a-local-cdc-service.md)  
