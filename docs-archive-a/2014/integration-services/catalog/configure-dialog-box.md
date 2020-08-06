---
title: Finestra di dialogo Configura | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.SSIS.SSMS.ISPROJECTPROP.PARAMETERS.F1
- SQL12.SSIS.SSMS.ISPROJECTPROP.REFERENCES.F1
- sql12.dts.designer.configure.f1
ms.assetid: 10183c8d-b1be-420f-972a-96ea97d4f4d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857baf3421f2744144e10b0df0b770538f533192
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629995"
---
# <a name="configure-dialog-box"></a><span data-ttu-id="a1af5-102">Finestra di dialogo Configura</span><span class="sxs-lookup"><span data-stu-id="a1af5-102">Configure Dialog Box</span></span>
  <span data-ttu-id="a1af5-103">Utilizzare la finestra di dialogo **Configura** per configurare i parametri, le gestioni connessioni e i riferimenti agli ambienti per pacchetti e progetti.</span><span class="sxs-lookup"><span data-stu-id="a1af5-103">Use the **Configure** dialog box to configure parameters, connection managers, and references to environments, for packages and projects.</span></span>  
  
 <span data-ttu-id="a1af5-104">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="a1af5-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="a1af5-105">Aprire la finestra di dialogo Configura</span><span class="sxs-lookup"><span data-stu-id="a1af5-105">Open the Configure Dialog Box</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="a1af5-106">Impostare le opzioni nella pagina Parametri</span><span class="sxs-lookup"><span data-stu-id="a1af5-106">Set the options on the Parameters page</span></span>](#parameter)  
  
-   [<span data-ttu-id="a1af5-107">Impostare le opzioni nella pagina Riferimenti</span><span class="sxs-lookup"><span data-stu-id="a1af5-107">Set the options on the References page</span></span>](#references)  
  
##  <a name="open-the-configure-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="a1af5-108">Aprire la finestra di dialogo Configura</span><span class="sxs-lookup"><span data-stu-id="a1af5-108">Open the Configure Dialog Box</span></span>  
  
1.  <span data-ttu-id="a1af5-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi al server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1af5-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
     <span data-ttu-id="a1af5-110">Verrà eseguita la connessione all'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in cui è ospitato il database SSISDB.</span><span class="sxs-lookup"><span data-stu-id="a1af5-110">You're connecting to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the SSISDB database.</span></span>  
  
2.  <span data-ttu-id="a1af5-111">In Esplora oggetti espandere l'albero per visualizzare il nodo dei **cataloghi di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="a1af5-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="a1af5-112">Espandere il nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="a1af5-112">Expand the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="a1af5-113">Espandere la cartella contenente il pacchetto o il progetto che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="a1af5-113">Expand the folder that contains the package or project that you want to configure.</span></span>  
  
5.  <span data-ttu-id="a1af5-114">Fare clic con il pulsante destro del mouse sul pacchetto o sul progetto, quindi scegliere **Configura**.</span><span class="sxs-lookup"><span data-stu-id="a1af5-114">Right-click the package or project, and then click **Configure**.</span></span>  
  
##  <a name="set-the-options-on-the-parameters-page"></a><a name="parameter"></a> <span data-ttu-id="a1af5-115">Impostare le opzioni nella pagina Parametri</span><span class="sxs-lookup"><span data-stu-id="a1af5-115">Set the options on the Parameters page</span></span>  
 <span data-ttu-id="a1af5-116">Utilizzare la pagina **Parametri** per visualizzare i nomi dei parametri e i valori e per modificare i valori.</span><span class="sxs-lookup"><span data-stu-id="a1af5-116">Use the **Parameters** page to view parameter names and values, and to modify the values.</span></span>  
  
 <span data-ttu-id="a1af5-117">Selezionare l'ambito dei parametri visualizzato nelle schede **Parametri** e **Gestioni connessioni** nell'elenco a discesa **Ambito** .</span><span class="sxs-lookup"><span data-stu-id="a1af5-117">Select the scope of the parameters displayed in the **Parameters** and **Connection Managers** tabs, in the **Scope** drop-down list.</span></span>  
  
 <span data-ttu-id="a1af5-118">Di seguito sono riportate le opzioni della scheda **Parametri** .</span><span class="sxs-lookup"><span data-stu-id="a1af5-118">The following is a list of the options in the **Parameters** tab.</span></span>  
  
 <span data-ttu-id="a1af5-119">**Contenitore**</span><span class="sxs-lookup"><span data-stu-id="a1af5-119">**Container**</span></span>  
 <span data-ttu-id="a1af5-120">Viene elencato l'oggetto contenente il parametro.</span><span class="sxs-lookup"><span data-stu-id="a1af5-120">Lists the object that contains the parameter.</span></span>  
  
 <span data-ttu-id="a1af5-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a1af5-121">**Name**</span></span>  
 <span data-ttu-id="a1af5-122">Viene elencato il nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="a1af5-122">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="a1af5-123">**Valore**</span><span class="sxs-lookup"><span data-stu-id="a1af5-123">**Value**</span></span>  
 <span data-ttu-id="a1af5-124">Viene elencato il valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="a1af5-124">Lists the parameter value.</span></span> <span data-ttu-id="a1af5-125">Fare clic sul pulsante con i puntini di sospensione per modificare il valore nella finestra di dialogo **Imposta valore parametro** .</span><span class="sxs-lookup"><span data-stu-id="a1af5-125">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span>  
  
 <span data-ttu-id="a1af5-126">Di seguito sono riportate le opzioni della scheda **Gestioni connessioni** . Utilizzare questa scheda per modificare i valori per le proprietà di gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="a1af5-126">The following is a list of the options in the **Connection Managers** tab. You use this tab to change values for connection manager properties.</span></span> <span data-ttu-id="a1af5-127">I parametri vengono automaticamente generati nel server SSIS per le proprietà.</span><span class="sxs-lookup"><span data-stu-id="a1af5-127">Parameters are automatically generated on the SSIS server for the properties.</span></span>  
  
 <span data-ttu-id="a1af5-128">**Contenitore**</span><span class="sxs-lookup"><span data-stu-id="a1af5-128">**Container**</span></span>  
 <span data-ttu-id="a1af5-129">Viene elencato l'oggetto contenente la gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="a1af5-129">Lists the object that contains the connection manager.</span></span>  
  
 <span data-ttu-id="a1af5-130">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a1af5-130">**Name**</span></span>  
 <span data-ttu-id="a1af5-131">Viene elencato il nome della gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="a1af5-131">Lists the connection manager name.</span></span>  
  
 <span data-ttu-id="a1af5-132">**Nome proprietà**</span><span class="sxs-lookup"><span data-stu-id="a1af5-132">**Property name**</span></span>  
 <span data-ttu-id="a1af5-133">Viene elencato il nome della proprietà della gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="a1af5-133">Lists the name of the connection manager property.</span></span>  
  
 <span data-ttu-id="a1af5-134">**Valore**</span><span class="sxs-lookup"><span data-stu-id="a1af5-134">**Value**</span></span>  
 <span data-ttu-id="a1af5-135">Viene elencato il valore assegnato alla proprietà della gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="a1af5-135">Lists the value assigned to the connection manager property.</span></span> <span data-ttu-id="a1af5-136">Fare clic sul pulsante con i puntini di sospensione per modificare il valore nella finestra di dialogo **Imposta valore parametro** .</span><span class="sxs-lookup"><span data-stu-id="a1af5-136">Click the ellipsis button to change the value in the **Set Parameter Value** dialog box.</span></span> <span data-ttu-id="a1af5-137">È possibile immettere un valore letterale, eseguire il mapping di una variabile di ambiente contenente il valore da utilizzare oppure utilizzare il valore predefinito dal pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a1af5-137">You can enter a literal value, map an environment variable that contains the value you want to use, or use the default value from the package.</span></span>  
  
##  <a name="set-the-options-on-the-references-page"></a><a name="references"></a> <span data-ttu-id="a1af5-138">Impostare le opzioni nella pagina Riferimenti</span><span class="sxs-lookup"><span data-stu-id="a1af5-138">Set the options on the References page</span></span>  
 <span data-ttu-id="a1af5-139">Utilizzare la pagina **Riferimenti** per aggiungere e rimuovere i riferimenti agli ambienti e accedere alle proprietà dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1af5-139">Use the **References** page to add and remove references to environments, and to access environment properties.</span></span>  
  
 <span data-ttu-id="a1af5-140">Un ambiente specifica i valori di runtime per i pacchetti contenuti nei progetti distribuiti nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1af5-140">An environment specifies runtime values for packages contained in the projects you've deployed to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span>  
  
 <span data-ttu-id="a1af5-141">**Environment**</span><span class="sxs-lookup"><span data-stu-id="a1af5-141">**Environment**</span></span>  
 <span data-ttu-id="a1af5-142">Elenca l'ambiente</span><span class="sxs-lookup"><span data-stu-id="a1af5-142">Lists the environment.</span></span>  
  
 <span data-ttu-id="a1af5-143">**Cartella ambiente**</span><span class="sxs-lookup"><span data-stu-id="a1af5-143">**Environment Folder**</span></span>  
 <span data-ttu-id="a1af5-144">Elenca la cartella in cui è contenuto l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1af5-144">Lists the folder that contains the environment.</span></span>  
  
 <span data-ttu-id="a1af5-145">**Apri**</span><span class="sxs-lookup"><span data-stu-id="a1af5-145">**Open**</span></span>  
 <span data-ttu-id="a1af5-146">Fare clic per aprire la finestra di dialogo **Proprietà ambiente** .</span><span class="sxs-lookup"><span data-stu-id="a1af5-146">Click to open the **Environment Properties** dialog box.</span></span>  
  
 <span data-ttu-id="a1af5-147">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="a1af5-147">**Add**</span></span>  
 <span data-ttu-id="a1af5-148">Fare clic per aggiungere un riferimento a un ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1af5-148">Click to add a reference to an environment.</span></span> <span data-ttu-id="a1af5-149">Nella finestra di dialogo **Sfoglia ambienti** fare clic su un ambiente, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1af5-149">In the **Browse Environments** dialog box click an environment and then click **OK**.</span></span>  
  
 <span data-ttu-id="a1af5-150">È possibile selezionare un ambiente contenuto in qualsiasi cartella del progetto nel nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="a1af5-150">You can select an environment contained in any project folder under the **SSISDB** node.</span></span>  
  
 <span data-ttu-id="a1af5-151">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="a1af5-151">**Remove**</span></span>  
 <span data-ttu-id="a1af5-152">Fare clic su un ambiente elencato nell'area **Riferimenti** e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="a1af5-152">Click an environment listed in the **References** area, and then click **Remove**.</span></span>  
  
  
