---
title: Finestra di dialogo Versioni progetto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.versions.f1
ms.assetid: a48a387c-2e70-45bc-be2e-26e57a9bb2c4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 998dd194c2a056121fd6f7a404e75c7080b85aa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721683"
---
# <a name="project-versions-dialog-box"></a><span data-ttu-id="9f48b-102">Finestra di dialogo Versioni progetto</span><span class="sxs-lookup"><span data-stu-id="9f48b-102">Project Versions Dialog Box</span></span>
  <span data-ttu-id="9f48b-103">Utilizzare la finestra di dialogo **Versioni di progetto** per visualizzare le versioni di un progetto e per ripristinare una versione precedente.</span><span class="sxs-lookup"><span data-stu-id="9f48b-103">Use the **Project Versions** dialog box to view versions of a project and to restore a previous version.</span></span>  
  
 <span data-ttu-id="9f48b-104">È anche possibile visualizzare le versioni precedenti nella vista [catalog.object_versions &#40;database SSISDB&#41;](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) e usare la stored procedure [catalog.restore_project &#40;database SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) per ripristinare le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="9f48b-104">You can also view previous versions in the [catalog.object_versions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-versions-ssisdb-database) view, and use the [catalog.restore_project &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-restore-project-ssisdb-database) stored procedure to restore previous versions.</span></span>  
  
 <span data-ttu-id="9f48b-105">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="9f48b-105">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="9f48b-106">Aprire la finestra di dialogo Versioni di progetto</span><span class="sxs-lookup"><span data-stu-id="9f48b-106">Open the Project Versions dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="9f48b-107">Ripristinare una versione Progetto</span><span class="sxs-lookup"><span data-stu-id="9f48b-107">Restore a Project Version</span></span>](#restore)  
  
##  <a name="open-the-project-versions-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="9f48b-108">Aprire la finestra di dialogo Versioni di progetto</span><span class="sxs-lookup"><span data-stu-id="9f48b-108">Open the Project Versions dialog box</span></span>  
  
1.  <span data-ttu-id="9f48b-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi al server [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9f48b-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="9f48b-110">cioè connettersi all'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in cui è ospitato il database di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9f48b-110">That is, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="9f48b-111">In Esplora oggetti espandere l'albero per visualizzare il nodo dei **cataloghi di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="9f48b-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="9f48b-112">Espandere il nodo **Cataloghi di Integration Services** per visualizzare il nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="9f48b-112">Expand the **Integration Services Catalogs** node to display the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="9f48b-113">Nel nodo **SSISDB** sono contenute una o più cartelle in cui sono inclusi uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="9f48b-113">The **SSISDB** node contains one or more folders that each contain one or more projects.</span></span> <span data-ttu-id="9f48b-114">Espandere la cartella contenente il progetto a cui si è interessati.</span><span class="sxs-lookup"><span data-stu-id="9f48b-114">Expand the folder that contains the project you are interested in.</span></span>  
  
5.  <span data-ttu-id="9f48b-115">Fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Versioni**.</span><span class="sxs-lookup"><span data-stu-id="9f48b-115">Right-click the project, and then click **Versions**.</span></span>  
  
 <span data-ttu-id="9f48b-116">Nella tabella **Versioni** della finestra di dialogo **Versioni progetto** viene visualizzato l'elenco di versioni del progetto che sono state distribuite nel server, con la data e l'ora di distribuzione della versione, la data e l'ora di ripristino della versione (se questa operazione è stata effettuata), la descrizione della versione e un identificatore di versione.</span><span class="sxs-lookup"><span data-stu-id="9f48b-116">In the **Project Versions** dialog box, the **Versions** table displays the list of versions of the project that have been deployed on the server, with the date and time the version was deployed, the date and time the version was restored (if it was restored), the version description, and a version identifier.</span></span> <span data-ttu-id="9f48b-117">La versione attualmente attiva viene indicata con un segno di spunta nella colonna **Corrente** della tabella.</span><span class="sxs-lookup"><span data-stu-id="9f48b-117">The currently active version is indicated with a check mark in the **Current** column of the table.</span></span>  
  
##  <a name="restore-a-project-version"></a><a name="restore"></a> <span data-ttu-id="9f48b-118">Ripristinare una versione Progetto</span><span class="sxs-lookup"><span data-stu-id="9f48b-118">Restore a Project Version</span></span>  
 <span data-ttu-id="9f48b-119">Per ripristinare una versione precedente di un progetto, selezionare la versione nella tabella **Versioni** , quindi fare clic su **Ripristina versione selezionata**.</span><span class="sxs-lookup"><span data-stu-id="9f48b-119">To restore a previous version of a project, select the version in the **Versions** table, and then click **Restore to Selected Version**.</span></span> <span data-ttu-id="9f48b-120">Il progetto viene ripristinato alla versione selezionata e quella versione viene indicata con un segno di spunta nella colonna **Corrente** della tabella **Versioni** .</span><span class="sxs-lookup"><span data-stu-id="9f48b-120">The project is restored to the selected version and that version is indicated with a check mark in the **Current** column of the **Versions** table.</span></span>  
  
  
