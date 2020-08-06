---
title: Importare un progetto Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3301c328-b0f5-4517-915c-93713413e453
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6a98219f3a04d11e086957d64a62e7c64cd51418
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624837"
---
# <a name="import-an-integration-services-project"></a><span data-ttu-id="23c76-102">Importare un progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="23c76-102">Import an Integration Services Project</span></span>
  <span data-ttu-id="23c76-103">Utilizzare l'**Importazione guidata progetto** di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per creare un progetto da un file di distribuzione esistente (ispac) o da un progetto distribuito nel catalogo di Integration Services.</span><span class="sxs-lookup"><span data-stu-id="23c76-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]**Import Project Wizard** to create a project from an existing deployment file (.ispac) or from a project deployed to Integration services catalog.</span></span> <span data-ttu-id="23c76-104">Questa caratteristica è utile soprattutto quando non si dispone della copia originale del progetto, ma si desidera crearne uno da un file ispac o dal catalogo di SSISDB.</span><span class="sxs-lookup"><span data-stu-id="23c76-104">This feature is especially useful when you do not have the original copy of the project but you want to create one from an .ispac file or SSISDB catalog.</span></span>  
  
### <a name="to-import-a-project"></a><span data-ttu-id="23c76-105">Per importare un progetto</span><span class="sxs-lookup"><span data-stu-id="23c76-105">To Import a Project</span></span>  
  
1.  <span data-ttu-id="23c76-106">In [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] scegliere **nuovo**  >  **progetto** dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="23c76-106">In [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], click **New** > **Project** on the **File** menu.</span></span>  
  
2.  <span data-ttu-id="23c76-107">Nell'area **Modelli installati** della finestra **Nuovo progetto** espandere **Business Intelligence**, quindi scegliere **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="23c76-107">In the **Installed Templates** area of the **New Project** window, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="23c76-108">Selezionare **Importazione guidata progetto di Integration Services** dall'elenco dei tipi di progetto.</span><span class="sxs-lookup"><span data-stu-id="23c76-108">Select **Integration Services Import Project Wizard** from the project types list.</span></span>  
  
4.  <span data-ttu-id="23c76-109">Digitare un nome per il nuovo progetto da creare nella casella di testo **Nome** .</span><span class="sxs-lookup"><span data-stu-id="23c76-109">Type a name for the new project to be created in the **Name** text box.</span></span>  
  
5.  <span data-ttu-id="23c76-110">Digitare il percorso del progetto nella casella di testo **Percorso** oppure fare clic su **Sfoglia** per selezionarne uno.</span><span class="sxs-lookup"><span data-stu-id="23c76-110">Type the path or location for the project in the **Location** text box, or click **Browse** to select one.</span></span>  
  
6.  <span data-ttu-id="23c76-111">Digitare un nome per la soluzione nella casella di testo **Nome soluzione** .</span><span class="sxs-lookup"><span data-stu-id="23c76-111">Type a name for the solution in the **Solution name** text box.</span></span>  
  
7.  <span data-ttu-id="23c76-112">Fare clic su **OK** per avviare la finestra di dialogo **Importazione guidata progetto di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="23c76-112">Click **OK** to launch the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
8.  <span data-ttu-id="23c76-113">Fare clic su **Avanti** per passare alla pagina **Seleziona origine** .</span><span class="sxs-lookup"><span data-stu-id="23c76-113">Click **Next** to switch to the **Select Source** page.</span></span>  
  
9. <span data-ttu-id="23c76-114">Se si importa da un file **ispac** , digitare il percorso comprendente il nome file nella casella di testo **Percorso** .</span><span class="sxs-lookup"><span data-stu-id="23c76-114">If you are importing from an **.ispac** file, type the path including file name in the **Path** text box.</span></span> <span data-ttu-id="23c76-115">Fare clic su **Sfoglia** per passare alla cartella in cui si desidera archiviare la soluzione e digitare il nome file nella casella di testo **Nome file** e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="23c76-115">Click **Browse** to navigate to the folder where you want the solution to be stored and type file name in the **File name** text box, and click **Open**.</span></span>  
  
     <span data-ttu-id="23c76-116">Se si importa da un **Catalogo di Integration Services**, digitare il nome dell'istanza di database nella casella di testo **Nome server** oppure fare clic su **Sfoglia** e selezionare l'istanza di database che contiene il catalogo.</span><span class="sxs-lookup"><span data-stu-id="23c76-116">If you are importing from an **Integration Services Catalog**, type the database instance name in the **Server name** text box or click **Browse** and select the database instance that contains the catalog.</span></span>  
  
     <span data-ttu-id="23c76-117">Fare clic su **Sfoglia** accanto alla casella di testo **Percorso** , espandere cartella nel catalogo, selezionare il progetto che si desidera importare e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="23c76-117">Click **Browse** next to **Path** text box, expand folder in the catalog, select the project you want to import, and click **OK**.</span></span>  
  
     <span data-ttu-id="23c76-118">Fare clic su **Avanti** per passare alla pagina **Verifica** .</span><span class="sxs-lookup"><span data-stu-id="23c76-118">Click **Next** to switch to the **Review** page.</span></span>  
  
10. <span data-ttu-id="23c76-119">Rivedere le informazioni e fare clic su **Importa** per creare un progetto basato sul progetto esistente selezionato.</span><span class="sxs-lookup"><span data-stu-id="23c76-119">Review the information and click **Import** to create a project based on the existing project you selected.</span></span>  
  
11. <span data-ttu-id="23c76-120">Facoltativo: fare clic su **Salva report** per salvare i risultati in un file</span><span class="sxs-lookup"><span data-stu-id="23c76-120">Optional: click **Save Report** to save the results to a file</span></span>  
  
12. <span data-ttu-id="23c76-121">Fare clic su **Chiudi** per chiudere la finestra di dialogo **Importazione guidata progetto di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="23c76-121">Click **Close** to close the **Integration Services Import Project Wizard** dialog box.</span></span>  
  
  
