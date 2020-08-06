---
title: Importazione guidata progetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.importprojectwizard.f1
ms.assetid: 9247ad6c-4bd1-43ab-b347-583181cb9917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 81a990995d7e98c21b61f484372d31c9a1773102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628899"
---
# <a name="import-project-wizard"></a><span data-ttu-id="b049f-102">Importazione guidata progetto</span><span class="sxs-lookup"><span data-stu-id="b049f-102">Import Project Wizard</span></span>
  <span data-ttu-id="b049f-103">Utilizzare l'importazione guidata progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per creare un nuovo progetto di Integration Services basato su uno esistente.</span><span class="sxs-lookup"><span data-stu-id="b049f-103">Use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Import Project Wizard create a new Integration Services project based on an existing one.</span></span> <span data-ttu-id="b049f-104">Importare i progetti che sono già stati distribuiti nel catalogo di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o importare i progetti da un file di distribuzione del progetto (con estensione ispac).</span><span class="sxs-lookup"><span data-stu-id="b049f-104">Import projects that have already been deployed to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] catalog or import projects from a project deployment file (.ispac extension).</span></span>  
  
### <a name="to-create-a-project-based-on-a-project-in-ispac-file-or-in-catalog"></a><span data-ttu-id="b049f-105">Per creare un progetto basato su un progetto nel file .ispac o nel catalogo</span><span class="sxs-lookup"><span data-stu-id="b049f-105">To create a project based on a project in .ispac file or in catalog</span></span>  
  
1.  <span data-ttu-id="b049f-106">Fare clic su **file**, scegliere **nuovo**e fare clic su progetto.</span><span class="sxs-lookup"><span data-stu-id="b049f-106">Click **File**, point to **New**, and click Project.</span></span>  
  
2.  <span data-ttu-id="b049f-107">Espandere **Business Intelligence**e fare clic su **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="b049f-107">Expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="b049f-108">Selezionare **Importazione guidata di Integration Services** nel riquadro centrale, digitare un **nome** per la soluzione, il progetto e specificare la **cartella** per il progetto, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="b049f-108">Select **Integration Services Import Wizard** in the middle pane, type a **name** for the solution, project, and specify the **folder** for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b049f-109">Vedere l' **Importazione guidata progetto di Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="b049f-109">You should see the **Integration Services Import Project Wizard**.</span></span> <span data-ttu-id="b049f-110">Questa procedura guidata crea un nuovo progetto di Integration Services basato su uno esistente</span><span class="sxs-lookup"><span data-stu-id="b049f-110">This wizard creates a new Integration Services project based on an existing one</span></span>  
  
4.  <span data-ttu-id="b049f-111">Fare clic su **Avanti** sulla pagina **Introduzione** per vedere la pagina **Seleziona origine** .</span><span class="sxs-lookup"><span data-stu-id="b049f-111">Click **Next** on the **Introduction** page to see the **Select Source** page.</span></span>  
  
5.  <span data-ttu-id="b049f-112">Specificare se si desidera importare il progetto da un file con estensione ispac o da un catalogo.</span><span class="sxs-lookup"><span data-stu-id="b049f-112">Specify whether you want to import project from an .ispac file or from a catalog.</span></span>  
  
    -   <span data-ttu-id="b049f-113">Se si seleziona l'opzione **File distribuzione progetto** , specificare il percorso del file con estensione ispac.</span><span class="sxs-lookup"><span data-stu-id="b049f-113">If you select **Project deployment file** option, specify the path to the .ispac file.</span></span>  
  
    -   <span data-ttu-id="b049f-114">Se si seleziona l'opzione **Catalogo di Integration Services** , specificare il nome dell'istanza del server di database nel quale esiste il catalogo e il percorso al progetto nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="b049f-114">If you select **Integration Services Catalog** option, specify the name of database server instance on which the catalog exists, and the path to the project in the catalog.</span></span>  
  
6.  <span data-ttu-id="b049f-115">Fare clic su **Avanti** sulla pagina **Seleziona origine** per vedere la pagina **Esame funzionalità** .</span><span class="sxs-lookup"><span data-stu-id="b049f-115">Click **Next** on the **Select Source** page to see the **Review** page.</span></span> <span data-ttu-id="b049f-116">Rivedere le informazioni visualizzate sulla pagina sull'operazione di importazione che la procedura guidata eseguirà.</span><span class="sxs-lookup"><span data-stu-id="b049f-116">Review the information displayed on the page about the import operation the wizard is going to perform.</span></span>  
  
7.  <span data-ttu-id="b049f-117">Fare clic su **Importa** per creare un nuovo progetto di Integration Services basato su quello selezionato.</span><span class="sxs-lookup"><span data-stu-id="b049f-117">Click **Import** to create a new Integration Services project based on the one you selected.</span></span>  
  
8.  <span data-ttu-id="b049f-118">La pagina **Risultati** deve visualizzare i risultati dall'operazione di importazione che la procedura guidata ha eseguito.</span><span class="sxs-lookup"><span data-stu-id="b049f-118">The **Results** page should display the results from import operation the wizard performed.</span></span> <span data-ttu-id="b049f-119">Fare clic su **Salva report** per salvare il report in un file XML.</span><span class="sxs-lookup"><span data-stu-id="b049f-119">Click **Save Report** to save the report to an XML file.</span></span>  
  
9. <span data-ttu-id="b049f-120">Fare clic su **Chiudi** per uscire dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b049f-120">Click **Close** to close the wizard.</span></span>  
  
  
