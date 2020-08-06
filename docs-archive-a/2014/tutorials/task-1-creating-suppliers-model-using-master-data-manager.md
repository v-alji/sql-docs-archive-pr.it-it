---
title: 'Attività 1: creazione del modello Suppliers mediante Gestione dati master | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6bbbcbff-1ecd-456c-947f-c445c8da673c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f6823c96acb7db77a3daafa895f3353b70af44dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714911"
---
# <a name="task-1-creating-suppliers-model-using-master-data-manager"></a><span data-ttu-id="6bce5-102">Attività 1: Creazione del modello Supplier tramite Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="6bce5-102">Task 1: Creating Suppliers Model using Master Data Manager</span></span>
  <span data-ttu-id="6bce5-103">In questa attività viene creato un modello denominato **Suppliers** in MDS utilizzando **Gestione dati master**.</span><span class="sxs-lookup"><span data-stu-id="6bce5-103">In this task, you create a model named **Suppliers** in MDS using **Master Data Manager**.</span></span>  
  
1.  <span data-ttu-id="6bce5-104">Passare a `http://localhost/MDS` per avviare **Gestione dati master**.</span><span class="sxs-lookup"><span data-stu-id="6bce5-104">Navigate to `http://localhost/MDS` to launch **Master Data Manager**.</span></span> <span data-ttu-id="6bce5-105">Se un'applicazione Web è stata configurata con un nome diverso o in un sito Web differente, sostituire l'URL.</span><span class="sxs-lookup"><span data-stu-id="6bce5-105">Replace the URL if you have configured Web Application with a different name or on a different a web site.</span></span>  
  
     <span data-ttu-id="6bce5-106">![Gestione dati master - Amministrazione sistema](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-01.jpg "Gestione dati master - Amministrazione sistema")</span><span class="sxs-lookup"><span data-stu-id="6bce5-106">![Master Data Manager - System Administation](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-01.jpg "Master Data Manager - System Administation")</span></span>  
  
2.  <span data-ttu-id="6bce5-107">Fare clic su **Amministrazione sistema** nella sezione **attività amministrative** .</span><span class="sxs-lookup"><span data-stu-id="6bce5-107">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="6bce5-108">Se non viene visualizzata la pagina **Aggiungi modello** , passare il mouse su **Gestisci** sulla barra dei menu, fare clic su **modelli**e quindi fare clic sul pulsante della barra degli strumenti **Aggiungi modello (+)** per creare un modello.</span><span class="sxs-lookup"><span data-stu-id="6bce5-108">If you do not see the **Add Model** page, hover mouse over **Manage** on the menu bar, click **Models**, and then click **Add Model (+)** toolbar button to create a model.</span></span>  
  
     <span data-ttu-id="6bce5-109">![Gestione - Menu Modelli](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-02.jpg "Gestione - Menu Modelli")</span><span class="sxs-lookup"><span data-stu-id="6bce5-109">![Manage - Models Menu](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-02.jpg "Manage - Models Menu")</span></span>  
  
     <span data-ttu-id="6bce5-110">![Pulsante della barra degli strumenti Aggiungi modello](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-03.jpg "Pulsante della barra degli strumenti Aggiungi modello")</span><span class="sxs-lookup"><span data-stu-id="6bce5-110">![Add Model Toolbat Button](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-03.jpg "Add Model Toolbat Button")</span></span>  
  
4.  <span data-ttu-id="6bce5-111">Immettere **Suppliers** per **nome modello**.</span><span class="sxs-lookup"><span data-stu-id="6bce5-111">Enter **Suppliers** for **Model name**.</span></span>  
  
5.  <span data-ttu-id="6bce5-112">Deselezionare l'opzione **Crea entità con lo stesso nome del modello** .</span><span class="sxs-lookup"><span data-stu-id="6bce5-112">Clear **Create entity with same name as model** option.</span></span> <span data-ttu-id="6bce5-113">Si creerà un'entità in un secondo momento usando il **componente aggiuntivo MDS per Excel**.</span><span class="sxs-lookup"><span data-stu-id="6bce5-113">You will create an entity later using the **MDS Add-in for Excel**.</span></span>  
  
     <span data-ttu-id="6bce5-114">![Pagina Aggiungi modello](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-04.jpg "Pagina Aggiungi modello")</span><span class="sxs-lookup"><span data-stu-id="6bce5-114">![Add Model Page](../../2014/tutorials/media/et-creatingsuppliersmodelusingmdm-04.jpg "Add Model Page")</span></span>  
  
6.  <span data-ttu-id="6bce5-115">Fare clic sul pulsante **Salva modello** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="6bce5-115">Click **Save Model** button on the toolbar.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="6bce5-116">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6bce5-116">Next Step</span></span>  
 [<span data-ttu-id="6bce5-117">Attività 2: Caricamento dei dati fornitore in MDS tramite il componente aggiuntivo MDS per Excel</span><span class="sxs-lookup"><span data-stu-id="6bce5-117">Task 2: Uploading Supplier Data to MDS using MDS Add-in for Excel</span></span>](../../2014/tutorials/task-2-uploading-supplier-data-to-mds-using-mds-add-in-for-excel.md)  
  
  
