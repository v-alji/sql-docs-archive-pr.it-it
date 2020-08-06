---
title: 'Attività 16: verifica con Gestione dati master | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 57ad9d3e-8f95-4df6-af01-c291ccf49164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d1649582f97e9e08691726745e4ba14b2f8226bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715895"
---
# <a name="task-16-verifying-with-master-data-manager"></a><span data-ttu-id="37411-102">Attività 16: Verifica con Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="37411-102">Task 16: Verifying with Master Data Manager</span></span>
  <span data-ttu-id="37411-103">In questa attività viene verificato lo stato del processo batch inviato dal pacchetto SSIS e viene controllato che i dati siano stati caricati nel server MDS tramite Gestione dati master.</span><span class="sxs-lookup"><span data-stu-id="37411-103">In this task, you check the status of the batch job submitted by the SSIS package and verify that the data was uploaded to MDS server by using Master Data Manager.</span></span>  
  
1.  <span data-ttu-id="37411-104">Avviare **Gestione dati master** ( `http://localhost/MDS` ).</span><span class="sxs-lookup"><span data-stu-id="37411-104">Launch **Master Data Manager** (`http://localhost/MDS`).</span></span> <span data-ttu-id="37411-105">Se è già aperto, fare clic su **Microsoft SQL Server Master Data Services** nella parte superiore per passare al **Home page**.</span><span class="sxs-lookup"><span data-stu-id="37411-105">If it is already open, click **Microsoft SQL Server Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="37411-106">Fare clic su **Gestione integrazione**.</span><span class="sxs-lookup"><span data-stu-id="37411-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="37411-107">Si noti che è presente un batch con il nome **EIMBatch** inviato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="37411-107">Notice that there is a batch with named **EIMBatch** that you submitted in the list.</span></span> <span data-ttu-id="37411-108">Se non viene visualizzata la schermata seguente, fare clic su **Importa dati** nella barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="37411-108">Click **Import Data** on the menu bar if you do not see the following screen.</span></span>  
  
     <span data-ttu-id="37411-109">![Batch EIM](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "Batch EIM")</span><span class="sxs-lookup"><span data-stu-id="37411-109">![EIM Batch](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "EIM Batch")</span></span>  
  
4.  <span data-ttu-id="37411-110">Tornare al home page facendo clic **SQL Server Master Data Services 2012** nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="37411-110">Switch back to the home page by click **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
5.  <span data-ttu-id="37411-111">Verificare che il **modello Suppliers** sia selezionato **per modello** e **VERSION_1** sia selezionato per **versione**, quindi fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="37411-111">Make sure that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**, and click **Explorer**.</span></span>  
  
6.  <span data-ttu-id="37411-112">È possibile visualizzare il pacchetto di dati SSIS importato in MDS.</span><span class="sxs-lookup"><span data-stu-id="37411-112">You can see the data SSIS package imported into MDS.</span></span> <span data-ttu-id="37411-113">I dati devono essere puliti e non contengono valori di **codice** duplicati (Nota: la colonna **SupplierID** in Excel corrisponde all'attributo **Code** dell'entità Supplier in MDS).</span><span class="sxs-lookup"><span data-stu-id="37411-113">The data should be cleansed and have no duplicates **Code** values (Note: **SupplierID** column in Excel corresponds to **Code** attribute of Supplier entity in MDS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="37411-114">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="37411-114">Next Step</span></span>  
 [<span data-ttu-id="37411-115">Attività 17: Verifica del progetto DQS Cleansing creato dal pacchetto SSIS</span><span class="sxs-lookup"><span data-stu-id="37411-115">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>](../../2014/tutorials/task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package.md)  
  
  
