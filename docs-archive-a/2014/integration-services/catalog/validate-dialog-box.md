---
title: Finestra di dialogo Convalida | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.ispackagevalidate.f1
- sql12.ssis.ssms.isprojectvalidate.f1
ms.assetid: 134e14ce-4f8d-4a20-889a-918014c841d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 69e29d106dc9f4f100bf191911c5c34e0250be8f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624879"
---
# <a name="validate-dialog-box"></a><span data-ttu-id="3e116-102">Finestra di dialogo Convalida</span><span class="sxs-lookup"><span data-stu-id="3e116-102">Validate Dialog Box</span></span>
  <span data-ttu-id="3e116-103">Utilizzare la finestra di dialogo **Convalida** per verificare i problemi comuni in un progetto o pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e116-103">Use the **Validate** dialog box to check for common problems in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a project or package.</span></span>  
  
 <span data-ttu-id="3e116-104">Se si è verificato un problema, viene visualizzato un messaggio nella parte superiore della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3e116-104">If there is a problem, a message is displayed at the top of the dialog box.</span></span> <span data-ttu-id="3e116-105">In caso contrario, viene visualizzato il termine Pronto.</span><span class="sxs-lookup"><span data-stu-id="3e116-105">Otherwise, the term Ready displays at the top.</span></span>  
  
 <span data-ttu-id="3e116-106">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="3e116-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="3e116-107">Aprire la finestra di dialogo Convalida</span><span class="sxs-lookup"><span data-stu-id="3e116-107">Open the Validate dialog box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="3e116-108">Impostare le opzioni nella pagina Generale</span><span class="sxs-lookup"><span data-stu-id="3e116-108">Set the options on the General page</span></span>](#general)  
  
##  <a name="open-the-validate-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="3e116-109">Aprire la finestra di dialogo Convalida</span><span class="sxs-lookup"><span data-stu-id="3e116-109">Open the Validate dialog box</span></span>  
  
1.  <span data-ttu-id="3e116-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi al server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e116-110">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="3e116-111">Verrà eseguita la connessione all'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in cui è ospitato il database SSISDB.</span><span class="sxs-lookup"><span data-stu-id="3e116-111">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="3e116-112">In Esplora oggetti espandere l'albero per visualizzare il nodo dei **cataloghi di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="3e116-112">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="3e116-113">Espandere il nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="3e116-113">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="3e116-114">Espandere la cartella contenente il progetto o pacchetto che si desidera convalidare.</span><span class="sxs-lookup"><span data-stu-id="3e116-114">Expand the folder that contains the project or package you want to validate.</span></span>  
  
5.  <span data-ttu-id="3e116-115">Fare clic con il pulsante destro del mouse sul pacchetto o sul progetto, quindi selezionare **Convalida**.</span><span class="sxs-lookup"><span data-stu-id="3e116-115">Right-click the package or package, and then click **Validate**.</span></span>  
  
##  <a name="set-the-options-on-the-general-page"></a><a name="general"></a> <span data-ttu-id="3e116-116">Impostare le opzioni nella pagina Generale</span><span class="sxs-lookup"><span data-stu-id="3e116-116">Set the options on the General page</span></span>  
 <span data-ttu-id="3e116-117">**Environment**</span><span class="sxs-lookup"><span data-stu-id="3e116-117">**Environment**</span></span>  
 <span data-ttu-id="3e116-118">Selezionare l'ambiente da utilizzare per convalidare il progetto o pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3e116-118">Select the environment that you want to use to validate the project or package.</span></span>  
  
 <span data-ttu-id="3e116-119">**Runtime a 32 bit**</span><span class="sxs-lookup"><span data-stu-id="3e116-119">**32-bit runtime**</span></span>  
 <span data-ttu-id="3e116-120">Scegliere di utilizzare un runtime a 32 bit per eseguire un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3e116-120">Select to use a 32-bit runtime to execute a package.</span></span>  
  
 <span data-ttu-id="3e116-121">Nella scheda **Parametri** sono elencati i valori dei parametri utilizzati per convalidare il progetto o pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3e116-121">The **Parameters** tab lists the parameter values that you use to validate the project or package.</span></span> <span data-ttu-id="3e116-122">Di seguito sono riportate le opzioni della scheda Parametri.</span><span class="sxs-lookup"><span data-stu-id="3e116-122">The following are the options on the Parameters tab.</span></span>  
  
 <span data-ttu-id="3e116-123">**Contenitore**</span><span class="sxs-lookup"><span data-stu-id="3e116-123">**Container**</span></span>  
 <span data-ttu-id="3e116-124">Viene elencato l'oggetto contenente il parametro.</span><span class="sxs-lookup"><span data-stu-id="3e116-124">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="3e116-125">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="3e116-125">**Parameter**</span></span>  
 <span data-ttu-id="3e116-126">Viene elencato il nome dei parametri.</span><span class="sxs-lookup"><span data-stu-id="3e116-126">Lists the name of the parameters</span></span>  
  
 <span data-ttu-id="3e116-127">**Valore**</span><span class="sxs-lookup"><span data-stu-id="3e116-127">**Value**</span></span>  
 <span data-ttu-id="3e116-128">Viene elencato il valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="3e116-128">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="3e116-129">Nella scheda **Gestioni connessioni** sono elencati i valori delle proprietà delle gestioni connessioni utilizzati per convalidare il progetto o pacchetto.</span><span class="sxs-lookup"><span data-stu-id="3e116-129">The **Connection Managers** tab lists the connection manager property values that you use to validate the project or package.</span></span>  
  
 <span data-ttu-id="3e116-130">Di seguito sono riportate le opzioni della scheda **Gestioni connessioni** .</span><span class="sxs-lookup"><span data-stu-id="3e116-130">The following are the options on the **Connection Managers** tab.</span></span>  
  
 <span data-ttu-id="3e116-131">**Contenitore**</span><span class="sxs-lookup"><span data-stu-id="3e116-131">**Container**</span></span>  
 <span data-ttu-id="3e116-132">Viene elencato l'oggetto contenente la gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="3e116-132">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="3e116-133">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3e116-133">**Name**</span></span>  
 <span data-ttu-id="3e116-134">Viene elencato il nome della gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="3e116-134">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="3e116-135">**Nome proprietà**</span><span class="sxs-lookup"><span data-stu-id="3e116-135">**Property name**</span></span>  
 <span data-ttu-id="3e116-136">Viene elencato il nome della proprietà della gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="3e116-136">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="3e116-137">**Valore**</span><span class="sxs-lookup"><span data-stu-id="3e116-137">**Value**</span></span>  
 <span data-ttu-id="3e116-138">Viene elencato il valore assegnato alla proprietà della gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="3e116-138">Lists the value assigned to the connection manager property.</span></span>  
  
  
