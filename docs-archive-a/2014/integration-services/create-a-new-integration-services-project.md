---
title: Creare un nuovo progetto Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Integration Services], creating
- Integration Services projects, creating
- SQL Server Integration Services projects, creating
- SSIS projects, creating
ms.assetid: 1e23f259-0401-4333-ab4f-89809aae63b1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f62d3ac2d33bb51a0ccc3b77d9f8b5ec0f52b345
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627326"
---
# <a name="create-a-new-integration-services-project"></a><span data-ttu-id="c559b-102">Creazione di un nuovo progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="c559b-102">Create a New Integration Services Project</span></span>
  <span data-ttu-id="c559b-103">Questa procedura consente di creare un nuovo progetto e una nuova soluzione di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c559b-103">This procedure creates a new project and a new [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] solution.</span></span>  
  
### <a name="to-create-a-new-integration-services-project"></a><span data-ttu-id="c559b-104">Per creare un nuovo progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="c559b-104">To create a new Integration Services project</span></span>  
  
1.  <span data-ttu-id="c559b-105">Aprire [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c559b-105">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="c559b-106">Scegliere **Nuovo** dal menu **File**e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="c559b-106">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="c559b-107">Nel riquadro **Modelli** della finestra di dialogo **Nuovo progetto** selezionare il modello **Progetto di Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="c559b-107">In the **New Project** dialog box, in the **Templates** pane, select the **Integration Services Project** template.</span></span>  
  
     <span data-ttu-id="c559b-108">Con il modello **Progetto di Integration Services** è possibile creare un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente un unico pacchetto vuoto.</span><span class="sxs-lookup"><span data-stu-id="c559b-108">The **Integration Services Project** template creates an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains a single, empty package.</span></span>  
  
4.  <span data-ttu-id="c559b-109">Facoltativamente, modificare il nome e il percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="c559b-109">(Optional) Edit the project name and the location.</span></span>  
  
     <span data-ttu-id="c559b-110">Il nome della soluzione viene aggiornato automaticamente in moda da corrispondere al nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="c559b-110">The solution name is automatically updated to match the project name.</span></span>  
  
5.  <span data-ttu-id="c559b-111">Per creare una cartella distinta per il file della soluzione, selezionare **Crea directory per soluzione**.</span><span class="sxs-lookup"><span data-stu-id="c559b-111">To create a separate folder for the solution file, select **Create directory for solution**.</span></span> <span data-ttu-id="c559b-112">Questa è l'opzione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c559b-112">This is the default option.</span></span>  
  
6.  <span data-ttu-id="c559b-113">Se nel computer è installato software per il controllo del codice sorgente, selezionare **Aggiungi al controllo del codice sorgente** per associare il progetto al controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="c559b-113">If source control software is installed on the computer, select **Add to source control**  to associate the project with source control.</span></span>  
  
7.  <span data-ttu-id="c559b-114">Se il software per il controllo del codice sorgente è [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, verrà visualizzata la finestra di dialogo **Accesso a Visual SourceSafe**.</span><span class="sxs-lookup"><span data-stu-id="c559b-114">If the source control software is [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, the **Visual SourceSafe Login** dialog box opens.</span></span> <span data-ttu-id="c559b-115">In **Accesso a Visual SourceSafe** specificare un nome utente, una password e il nome del database di [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="c559b-115">In **Visual SourceSafe Login**, provide a user name, a password, and the name of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe database.</span></span> <span data-ttu-id="c559b-116">Fare clic su **Sfoglia** per individuare il database.</span><span class="sxs-lookup"><span data-stu-id="c559b-116">Click **Browse** to locate the database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c559b-117">Per visualizzare e modificare il plug-in per il controllo del codice sorgente selezionato e configurare l'ambiente di controllo del codice sorgente, scegliere **Opzioni** dal menu **Strumenti** e quindi espandere il nodo **Controllo del codice sorgente**.</span><span class="sxs-lookup"><span data-stu-id="c559b-117">To view and change the selected source control plug-in and to configure the source control environment, click **Options** on the **Tools** menu, and then expand the **Source Control** node.</span></span>  
  
8.  <span data-ttu-id="c559b-118">Fare clic su **OK** per aggiungere la soluzione alla **soluzione Esplora**r e aggiungere il progetto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="c559b-118">Click **OK** to add the solution to **Solution Explore**r and add the project to the solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c559b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c559b-119">See Also</span></span>  
 <span data-ttu-id="c559b-120">[Integration Services &#40;progetti SSIS&#41;](integration-services-ssis-projects-and-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="c559b-120">[Integration Services &#40;SSIS&#41; Projects](integration-services-ssis-projects-and-solutions.md) </span></span>  
 [<span data-ttu-id="c559b-121">Aggiunta o rimozione di un progetto di Integration Services da una soluzione</span><span class="sxs-lookup"><span data-stu-id="c559b-121">Add or Remove an Integration Services Project in a Solution</span></span>](../../2014/integration-services/add-or-remove-an-integration-services-project-in-a-solution.md)  
  
  
