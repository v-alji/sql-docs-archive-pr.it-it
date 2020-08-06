---
title: Procedura di gestione di un servizio CDC locale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f9be649-cd93-40c1-bc48-0480106f207c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 437590d4b91f2fc80d5bb8a90251bf0dc7c8e18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710992"
---
# <a name="how-to-manage-a-local-cdc-service"></a><span data-ttu-id="f75fa-102">Procedura di gestione di un servizio CDC locale</span><span class="sxs-lookup"><span data-stu-id="f75fa-102">How to Manage a Local CDC Service</span></span>
  <span data-ttu-id="f75fa-103">In questa procedura viene illustrato come utilizzare CDC Service Configuration Console per gestire servizi CDC specifici.</span><span class="sxs-lookup"><span data-stu-id="f75fa-103">This procedure describes how to use the CDC Service Configuration Console to manage specific CDC services.</span></span>  
  
### <a name="to-manage-a-specific-cdc-service"></a><span data-ttu-id="f75fa-104">Per gestire un servizio CDC specifico</span><span class="sxs-lookup"><span data-stu-id="f75fa-104">To manage a specific CDC Service</span></span>  
  
1.  <span data-ttu-id="f75fa-105">Dal menu **Start** , selezionare **CDC Service Configuration for Oracle**.</span><span class="sxs-lookup"><span data-stu-id="f75fa-105">From the **Start** menu, select the **CDC Service Configuration for Oracle**.</span></span>  
  
2.  <span data-ttu-id="f75fa-106">Dal riquadro sinistro di CDC Service Configuration Console, espandere **Local CDC Services**.</span><span class="sxs-lookup"><span data-stu-id="f75fa-106">From the left pane in the CDC Service Configuration Console, expand **Local CDC Services**.</span></span>  
  
3.  <span data-ttu-id="f75fa-107">Selezionare il servizio CDC che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f75fa-107">Select the CDC service you want to work with.</span></span>  
  
     <span data-ttu-id="f75fa-108">È inoltre possibile fare clic con il pulsante destro del mouse sul servizio CDC da utilizzare e selezionare l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="f75fa-108">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
     <span data-ttu-id="f75fa-109">**OR**</span><span class="sxs-lookup"><span data-stu-id="f75fa-109">**OR**</span></span>  
  
     <span data-ttu-id="f75fa-110">Selezionare **Local CDC Services** dal riquadro sinistro di CDC Service Configuration Console, quindi selezionare quindi il servizio che si desidera utilizzare dalla sezione centrale della console di configurazione del servizio CDC.</span><span class="sxs-lookup"><span data-stu-id="f75fa-110">Select **Local CDC Services** from the left pane in the CDC Service Configuration Console then select the service you want to work with from the middle section of the CDC Service Configuration Console.</span></span>  
  
     <span data-ttu-id="f75fa-111">È inoltre possibile fare clic con il pulsante destro del mouse sul servizio CDC da utilizzare e selezionare l'azione desiderata.</span><span class="sxs-lookup"><span data-stu-id="f75fa-111">You can also right-click the CDC service you want to work with and select the desired action.</span></span>  
  
4.  <span data-ttu-id="f75fa-112">Quando si utilizza un servizio CDC è possibile eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="f75fa-112">You can carry out the following tasks when working with a CDC service.</span></span>  
  
    -   <span data-ttu-id="f75fa-113">**Eliminare il servizio**</span><span class="sxs-lookup"><span data-stu-id="f75fa-113">**Delete the service**</span></span>  
  
         <span data-ttu-id="f75fa-114">Dal riquadro **Actions** sul lato destro di CDC Service Configuration Console, fare clic su **Delete** per eliminare il servizio.</span><span class="sxs-lookup"><span data-stu-id="f75fa-114">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Delete** to delete the service.</span></span>  
  
         <span data-ttu-id="f75fa-115">È inoltre possibile fare clic con il pulsante destro del mouse sul servizio CDC da eliminare e scegliere **Delete**.</span><span class="sxs-lookup"><span data-stu-id="f75fa-115">You can also right-click the CDC service you want to delete and select **Delete**.</span></span>  
  
         <span data-ttu-id="f75fa-116">**Nota**: se il servizio è in esecuzione al momento dell'eliminazione, il servizio viene arrestato prima di essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="f75fa-116">**Note**: If the service is running when deleting the service, the service is stopped before being deleted.</span></span>  
  
         <span data-ttu-id="f75fa-117">Per eliminare una definizione del servizio Windows di Oracle CDC, è necessario aggiornare l'accesso al database MSXDBCDC nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] associata.</span><span class="sxs-lookup"><span data-stu-id="f75fa-117">To delete an Oracle CDC Windows Service definition, the program needs update access to the MSXDBCDC database in the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="f75fa-118">Quando si fa clic su **OK** per eliminare il servizio, viene effettuato un tentativo di eliminare la registrazione del servizio Oracle CDC nel database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="f75fa-118">When you click **OK** to delete the service, the program attempts to delete the Oracle CDC Service registration in the MSXDBCDC database.</span></span> <span data-ttu-id="f75fa-119">Se l'operazione ha esito negativo a causa della mancanza di autorizzazioni, verrà visualizzata una finestra di dialogo in cui viene richiesto all'utente di immettere un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con un accesso di aggiornamento al database MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="f75fa-119">If it fails due to lack of permissions, a dialog box is displayed to prompt the user to enter a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login with an update access to the MSXDBCDC database.</span></span>  
  
         <span data-ttu-id="f75fa-120">Per informazioni sui dati da immettere nella finestra di dialogo Connect to SQL Server, vedere [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) e [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span><span class="sxs-lookup"><span data-stu-id="f75fa-120">For information about the data you must enter in the Connect to SQL Server dialog box, see [Manage an Oracle CDC Service](manage-an-oracle-cdc-service.md) and [Connection to SQL Server for Delete](connection-to-sql-server-for-delete.md).</span></span>  
  
    -   <span data-ttu-id="f75fa-121">**Modificare le proprietà del servizio CDC**</span><span class="sxs-lookup"><span data-stu-id="f75fa-121">**Edit the CDC Service Properties**</span></span>  
  
         <span data-ttu-id="f75fa-122">Dal riquadro **Actions** sul lato destro di CDC Service Configuration Console, fare clic su **Properties**.</span><span class="sxs-lookup"><span data-stu-id="f75fa-122">From the **Actions** pane on the right side of the CDC Service Configuration Console, click **Properties**.</span></span>  
  
         <span data-ttu-id="f75fa-123">È inoltre possibile fare clic con il pulsante destro del mouse sul servizio CDC in cui si desidera modificare le proprietà e scegliere **Properties**.</span><span class="sxs-lookup"><span data-stu-id="f75fa-123">You can also right-click the CDC service where you want to edit the properties and select **Properties**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75fa-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f75fa-124">See Also</span></span>  
 [<span data-ttu-id="f75fa-125">Gestire un servizio Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="f75fa-125">Manage an Oracle CDC Service</span></span>](manage-an-oracle-cdc-service.md)  
  
  
