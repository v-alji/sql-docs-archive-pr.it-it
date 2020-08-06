---
title: Finestra di dialogo Proprietà progetto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isprojectprop.general.f1
- sql12.ssis.ssms.isprojectprop.permissions.f1
ms.assetid: d5cf52f5-1fe2-438a-98a3-fe117360acf8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 259ad48f2b1f33356243635bbaa5426a5199eccf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715648"
---
# <a name="project-properties-dialog-box"></a><span data-ttu-id="6dab9-102">Finestra di dialogo Proprietà progetto</span><span class="sxs-lookup"><span data-stu-id="6dab9-102">Project Properties Dialog Box</span></span>
  <span data-ttu-id="6dab9-103">Un progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] è un'unità di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6dab9-103">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project is a unit of deployment.</span></span> <span data-ttu-id="6dab9-104">In ogni progetto possono essere inclusi pacchetti, parametri e riferimenti all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="6dab9-104">Each project can contain packages, parameters, and environment references.</span></span> <span data-ttu-id="6dab9-105">Un progetto è un oggetto a protezione diretta in cui è possibile definire autorizzazioni per le entità di database.</span><span class="sxs-lookup"><span data-stu-id="6dab9-105">A project is a securable object and can define permissions for database principals.</span></span> <span data-ttu-id="6dab9-106">Quando un progetto viene ridistribuito, la versione precedente può essere archiviata nel catalogo di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6dab9-106">When a project is re-deployed, the previous version of the project can be stored in the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span>  
  
 <span data-ttu-id="6dab9-107">I parametri del progetto e quelli del pacchetto possono essere utilizzati per assegnare valori alle proprietà dei pacchetti durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6dab9-107">Project parameters and package parameters can be used to assign values to properties within packages at the time of execution.</span></span> <span data-ttu-id="6dab9-108">In alcuni parametri devono essere presenti valori prima che il pacchetto possa essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="6dab9-108">Some parameters require values before the package can be executed.</span></span> <span data-ttu-id="6dab9-109">Per i valori di parametri che fanno riferimento alle variabili di ambiente è necessario che il progetto disponga del riferimento all'ambiente corrispondente prima dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6dab9-109">Parameter values that reference environment variables require that the project has the corresponding environment reference prior to execution.</span></span>  
  
 <span data-ttu-id="6dab9-110">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="6dab9-110">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="6dab9-111">Aprire la finestra di dialogo Proprietà progetto</span><span class="sxs-lookup"><span data-stu-id="6dab9-111">Open the Project Properties dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="6dab9-112">Impostare le opzioni nella pagina Generale</span><span class="sxs-lookup"><span data-stu-id="6dab9-112">Set the options on the General page</span></span>](#general)  
  
-   [<span data-ttu-id="6dab9-113">Impostare le opzioni nella pagina Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6dab9-113">Set the options on the Permissions page</span></span>](#permissions)  
  
##  <a name="open-the-project-properties-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="6dab9-114">Aprire la finestra di dialogo Proprietà progetto</span><span class="sxs-lookup"><span data-stu-id="6dab9-114">Open the Project Properties dialog box</span></span>  
  
1.  <span data-ttu-id="6dab9-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi al server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6dab9-115">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="6dab9-116">Verrà eseguita la connessione all'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in cui è ospitato il database SSISDB.</span><span class="sxs-lookup"><span data-stu-id="6dab9-116">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="6dab9-117">In Esplora oggetti espandere l'albero per visualizzare il nodo dei **cataloghi di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="6dab9-117">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="6dab9-118">Espandere il nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="6dab9-118">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="6dab9-119">Espandere la cartella contenente il progetto per cui si desidera impostare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="6dab9-119">Expand the folder that contains the project that you want to set properties for.</span></span>  
  
5.  <span data-ttu-id="6dab9-120">Fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6dab9-120">Right-click the project, and then click **Properties**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="6dab9-121">Impostare le opzioni nella pagina Generale</span><span class="sxs-lookup"><span data-stu-id="6dab9-121">Set the options on the General page</span></span>  
 <span data-ttu-id="6dab9-122">Utilizzare la pagina Generale per visualizzare le proprietà del progetto.</span><span class="sxs-lookup"><span data-stu-id="6dab9-122">Use the General page to view project properties.</span></span>  
  
 <span data-ttu-id="6dab9-123">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6dab9-123">**Name**</span></span>  
 <span data-ttu-id="6dab9-124">Viene elencato il nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="6dab9-124">Lists the project name.</span></span>  
  
 <span data-ttu-id="6dab9-125">**Identificatore**</span><span class="sxs-lookup"><span data-stu-id="6dab9-125">**Identifier**</span></span>  
 <span data-ttu-id="6dab9-126">Viene elencato l'ID del progetto.</span><span class="sxs-lookup"><span data-stu-id="6dab9-126">Lists the project ID.</span></span>  
  
 <span data-ttu-id="6dab9-127">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6dab9-127">**Description**</span></span>  
 <span data-ttu-id="6dab9-128">Viene visualizzata la descrizione facoltativa del progetto.</span><span class="sxs-lookup"><span data-stu-id="6dab9-128">Displays the optional description of the project.</span></span>  
  
 <span data-ttu-id="6dab9-129">**Versione progetto**</span><span class="sxs-lookup"><span data-stu-id="6dab9-129">**Project Version**</span></span>  
 <span data-ttu-id="6dab9-130">Viene elencata la versione del progetto.</span><span class="sxs-lookup"><span data-stu-id="6dab9-130">Lists the project version.</span></span>  
  
 <span data-ttu-id="6dab9-131">**Data di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="6dab9-131">**Deployment Date**</span></span>  
 <span data-ttu-id="6dab9-132">Vengono elencate la data e l'ora di distribuzione o ridistribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="6dab9-132">Lists the date and time the project was deployed or redeployed.</span></span>  
  
##  <a name="set-the-options-on-the-permissions-page"></a><a name="permissions"></a> <span data-ttu-id="6dab9-133">Impostare le opzioni nella pagina Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6dab9-133">Set the options on the Permissions page</span></span>  
 <span data-ttu-id="6dab9-134">Utilizzare la pagina **Autorizzazioni** per visualizzare e impostare le autorizzazioni esplicite per il progetto.</span><span class="sxs-lookup"><span data-stu-id="6dab9-134">Use the **Permissions** page to view and set explicit permissions for the project.</span></span>  
  
 <span data-ttu-id="6dab9-135">Sfoglia</span><span class="sxs-lookup"><span data-stu-id="6dab9-135">Browse</span></span>  
 <span data-ttu-id="6dab9-136">Fare clic su **Sfoglia** per selezionare gli utenti e i ruoli per cui si vuole impostare le autorizzazioni, usando la finestra di dialogo **Sfoglia tutte le entità** .</span><span class="sxs-lookup"><span data-stu-id="6dab9-136">Click **Browse** to select users and roles that you want to set permissions for, by using the **Browse All Principals** dialog box.</span></span>  
  
 <span data-ttu-id="6dab9-137">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6dab9-137">**Name**</span></span>  
 <span data-ttu-id="6dab9-138">Viene elencato il nome dell'utente o del ruolo.</span><span class="sxs-lookup"><span data-stu-id="6dab9-138">Lists the name of the user or role.</span></span>  
  
 <span data-ttu-id="6dab9-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6dab9-139">**Type**</span></span>  
 <span data-ttu-id="6dab9-140">Viene elencato il tipo di utente o ruolo.</span><span class="sxs-lookup"><span data-stu-id="6dab9-140">Lists the type of user or role.</span></span>  
  
 <span data-ttu-id="6dab9-141">**Autorizzazione**</span><span class="sxs-lookup"><span data-stu-id="6dab9-141">**Permission**</span></span>  
 <span data-ttu-id="6dab9-142">Vengono elencare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="6dab9-142">Lists the permissions.</span></span>  
  
 <span data-ttu-id="6dab9-143">**Utente che concede le autorizzazioni**</span><span class="sxs-lookup"><span data-stu-id="6dab9-143">**Grantor**</span></span>  
 <span data-ttu-id="6dab9-144">Viene elencato l'utente o il ruolo tramite cui viene concessa l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="6dab9-144">Lists the user or role that grants the permission.</span></span>  
  
 <span data-ttu-id="6dab9-145">**Concedi**</span><span class="sxs-lookup"><span data-stu-id="6dab9-145">**Grant**</span></span>  
 <span data-ttu-id="6dab9-146">Se l'opzione **Concedi** è selezionata, l'autorizzazione viene concessa per l'utente o il ruolo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6dab9-146">When **Grant** is selected, the permission is granted for the selected user or role.</span></span>  
  
 <span data-ttu-id="6dab9-147">**Nega**</span><span class="sxs-lookup"><span data-stu-id="6dab9-147">**Deny**</span></span>  
 <span data-ttu-id="6dab9-148">Se l'opzione **Nega** è selezionata, l'autorizzazione viene negata all'utente o al ruolo selezionato.</span><span class="sxs-lookup"><span data-stu-id="6dab9-148">When **Deny** is selected, the permission is denied for the selected user or role.</span></span>  
  
  
