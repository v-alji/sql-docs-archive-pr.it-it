---
title: 'Attività 2 (facoltativo): creazione di una vista sottoscrizioni MDS con Gestione dati master | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f3da8219-e0cb-4848-95ca-285a76ec1ba9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 998436734ba5c3cf09cfe88f266a0908c0550abc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720435"
---
# <a name="task-2-optional-creating-a-mds-subscription-view-using-master-data-manager"></a><span data-ttu-id="7bc09-102">Attività 2 (facoltativa): Creazione di viste sottoscrizioni MDS tramite Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="7bc09-102">Task 2 (Optional): Creating a MDS Subscription View using Master Data Manager</span></span>
  <span data-ttu-id="7bc09-103">In questa attività viene creata una vista sottoscrizioni per esporre l'entità **Supplier** nel modello **Suppliers** ad altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7bc09-103">In this task, you create a subscription view to expose the **Supplier** entity in the **Suppliers** model to other applications.</span></span> <span data-ttu-id="7bc09-104">Questa vista non viene utilizzata nella versione corrente dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="7bc09-104">You do not consume this view in the current version of the tutorial.</span></span>  
  
1.  <span data-ttu-id="7bc09-105">Passare alla pagina principale di **Gestione dati master** ( `http://localhost/MDS` ) facendo clic **SQL Server Master Data Services 2012** nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="7bc09-105">Switch to the main page of **Master Data Manager** (`http://localhost/MDS`) by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
2.  <span data-ttu-id="7bc09-106">Fare clic su **Gestione integrazione**.</span><span class="sxs-lookup"><span data-stu-id="7bc09-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="7bc09-107">Fare clic su **Crea viste** sulla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="7bc09-107">Click **Create Views** on the menu bar.</span></span>  
  
     <span data-ttu-id="7bc09-108">![Pulsante Aggiungi nuova vista sottoscrizione](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Pulsante Aggiungi nuova vista sottoscrizione")</span><span class="sxs-lookup"><span data-stu-id="7bc09-108">![Add a New Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Add a New Subscription View Button")</span></span>  
  
4.  <span data-ttu-id="7bc09-109">Fare clic sull'icona **+ (segno più)** sulla barra degli strumenti per creare una vista sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="7bc09-109">Click **+ (Plus)** icon on the toolbar to create a subscription view.</span></span>  
  
5.  <span data-ttu-id="7bc09-110">Nel riquadro **Crea vista sottoscrizioni** digitare **Suppliers** per **nome vista**sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="7bc09-110">In the **Create Subscription View** pane, type **Suppliers** for **Subscription view name**.</span></span>  
  
6.  <span data-ttu-id="7bc09-111">Selezionare **Suppliers** per **modello**.</span><span class="sxs-lookup"><span data-stu-id="7bc09-111">Select **Suppliers** for **Model**.</span></span>  
  
7.  <span data-ttu-id="7bc09-112">Selezionare **VERSION_1** per **versione**.</span><span class="sxs-lookup"><span data-stu-id="7bc09-112">Select **VERSION_1** for **Version**.</span></span>  
  
8.  <span data-ttu-id="7bc09-113">Selezionare **Supplier** per **Entity**.</span><span class="sxs-lookup"><span data-stu-id="7bc09-113">Select **Supplier** for **Entity**.</span></span>  
  
9. <span data-ttu-id="7bc09-114">Selezionare **membri foglia** per **formato**.</span><span class="sxs-lookup"><span data-stu-id="7bc09-114">Select **Leaf members** for **Format**.</span></span>  
  
     <span data-ttu-id="7bc09-115">![Pulsante Salva vista sottoscrizione](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Pulsante Salva vista sottoscrizione")</span><span class="sxs-lookup"><span data-stu-id="7bc09-115">![Save Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Save Subscription View Button")</span></span>  
  
10. <span data-ttu-id="7bc09-116">Fare clic su **Salva** sulla barra degli strumenti per salvare la vista sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="7bc09-116">Click **Save** on the toolbar to save the subscription view.</span></span> <span data-ttu-id="7bc09-117">Questa azione consente di creare una vista in SQL Server **Suppliers**.</span><span class="sxs-lookup"><span data-stu-id="7bc09-117">This action creates a view in SQL Server named **Suppliers**.</span></span> <span data-ttu-id="7bc09-118">Per verificarla, utilizzare SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="7bc09-118">You can verify this using SQL Server Management Studio (SSMS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="7bc09-119">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="7bc09-119">Next Step</span></span>  
 [<span data-ttu-id="7bc09-120">Attività 3 &#40;&#41; facoltativo: Revisione delle viste sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="7bc09-120">Task 3 &#40;Optional&#41;: Reviewing the Subscription Views</span></span>](task-3-optional-reviewing-the-subscription-views.md)  
  
  
