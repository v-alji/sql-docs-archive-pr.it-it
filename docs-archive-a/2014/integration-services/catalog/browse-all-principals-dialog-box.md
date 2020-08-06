---
title: Finestra di dialogo Sfoglia tutte le entità | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.browseprincipals.f1
ms.assetid: f11d2c5e-ee05-45f3-8dc2-0feb99b2f76f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c204411a4daace27745e46269cbcfa0ed33f323f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624891"
---
# <a name="browse-all-principals-dialog-box"></a><span data-ttu-id="e315c-102">Finestra di dialogo Sfoglia tutte le entità</span><span class="sxs-lookup"><span data-stu-id="e315c-102">Browse All Principals Dialog Box</span></span>
  <span data-ttu-id="e315c-103">Usare la finestra di dialogo **Sfoglia tutte le entità** per selezionare un'entità di database per modificare le autorizzazioni dell'entità per il progetto selezionato o per tutti i progetti contenuti in una cartella selezionata.</span><span class="sxs-lookup"><span data-stu-id="e315c-103">Use the **Browse All Principals** dialog box to select a database principal to change the principal's permissions on the selected project or on all projects contained in a selected folder.</span></span>  
  
 <span data-ttu-id="e315c-104">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="e315c-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="e315c-105">Aprire la finestra di dialogo Sfoglia tutte le entità</span><span class="sxs-lookup"><span data-stu-id="e315c-105">Open the Browse All Principals dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="e315c-106">Configurare le opzioni</span><span class="sxs-lookup"><span data-stu-id="e315c-106">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-browse-all-principals-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="e315c-107">Aprire la finestra di dialogo Sfoglia tutte le entità</span><span class="sxs-lookup"><span data-stu-id="e315c-107">Open the Browse All Principals dialog box</span></span>  
  
1.  <span data-ttu-id="e315c-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi al server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e315c-108">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="e315c-109">Verrà eseguita la connessione all'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in cui è ospitato il catalogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="e315c-109">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB catalog.</span></span>  
  
2.  <span data-ttu-id="e315c-110">In Esplora oggetti espandere l'albero per visualizzare il nodo dei **cataloghi di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="e315c-110">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="e315c-111">Espandere il nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="e315c-111">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="e315c-112">Per modificare le autorizzazioni dell'entità per tutti i progetti contenuti in una cartella selezionata, fare clic con il pulsante destro del mouse sulla cartella, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e315c-112">To change the principal's permissions on all projects contained in a selected folder, right-click the folder and then click **Properties**.</span></span>  
  
     <span data-ttu-id="e315c-113">Per modificare le autorizzazioni dell'entità per un progetto selezionato, espandere la cartella che contiene il progetto, fare clic con il pulsante destro del mouse sul progetto, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e315c-113">To change the principal's permissions on a selected project, expand the folder that contains the project, right-click the project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="e315c-114">Selezionare la pagina **Autorizzazioni** , quindi fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="e315c-114">Select the **Permissions** page, and then click **Browse**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="e315c-115">Configurare le opzioni</span><span class="sxs-lookup"><span data-stu-id="e315c-115">Configure the Options</span></span>  
 <span data-ttu-id="e315c-116">In questa pagina vengono visualizzate le entità della vista del catalogo sys.database_principals del database SSISDB.</span><span class="sxs-lookup"><span data-stu-id="e315c-116">This page displays the principals from the catalog view, sys.database_principals, of the SSISDB database.</span></span>  
  
 <span data-ttu-id="e315c-117">Tramite la selezione le entità vengono aggiunte all'elenco **Account di accesso o ruoli** nella pagina **Autorizzazioni** della finestra di dialogo padre quando si fa clic su **OK** e si chiude la finestra di dialogo **Sfoglia tutte le entità** .</span><span class="sxs-lookup"><span data-stu-id="e315c-117">Selecting principals adds them to the **Logins or roles** list on the **Permissions** page of the parent dialog box when you click **OK** and close the **Browse All Principals** dialog box.</span></span> <span data-ttu-id="e315c-118">Dopo aver aggiunto le entità all'elenco **Account di accesso o ruoli** , è possibile modificare le autorizzazioni per il progetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="e315c-118">After adding principals to the **Logins or roles** list, you can change their permissions on the selected project.</span></span>  
  
 <span data-ttu-id="e315c-119">**Colonna Selezione**</span><span class="sxs-lookup"><span data-stu-id="e315c-119">**Selection column**</span></span>  
 <span data-ttu-id="e315c-120">Selezionare per aggiungere l'entità all'elenco **Account di accesso o ruoli** nella pagina **Autorizzazioni** della finestra di dialogo padre.</span><span class="sxs-lookup"><span data-stu-id="e315c-120">Select to add the principal to the **Logins or roles** list on the **Permissions** page of the parent dialog box.</span></span>  
  
 <span data-ttu-id="e315c-121">**Colonna Icona**</span><span class="sxs-lookup"><span data-stu-id="e315c-121">**Icon column**</span></span>  
 <span data-ttu-id="e315c-122">Icona che corrisponde al **Tipo** di entità.</span><span class="sxs-lookup"><span data-stu-id="e315c-122">An icon that corresponds to the **Type** of the principal.</span></span>  
  
 <span data-ttu-id="e315c-123">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e315c-123">**Name**</span></span>  
 <span data-ttu-id="e315c-124">Nome dell'entità.</span><span class="sxs-lookup"><span data-stu-id="e315c-124">The name of the principal.</span></span>  
  
 <span data-ttu-id="e315c-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e315c-125">**Type**</span></span>  
 <span data-ttu-id="e315c-126">Tipo dell'entità.</span><span class="sxs-lookup"><span data-stu-id="e315c-126">The type of the principal.</span></span> <span data-ttu-id="e315c-127">I tipi comuni sono:</span><span class="sxs-lookup"><span data-stu-id="e315c-127">The common types are:</span></span>  
  
-   <span data-ttu-id="e315c-128">Utente SQL</span><span class="sxs-lookup"><span data-stu-id="e315c-128">SQL User</span></span>  
  
-   <span data-ttu-id="e315c-129">Utente di Windows</span><span class="sxs-lookup"><span data-stu-id="e315c-129">Windows User</span></span>  
  
-   <span data-ttu-id="e315c-130">Ruolo del database</span><span class="sxs-lookup"><span data-stu-id="e315c-130">Database Role</span></span>  
  
  
