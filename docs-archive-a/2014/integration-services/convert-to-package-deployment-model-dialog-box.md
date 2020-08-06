---
title: Finestra di dialogo Converti in modello di distribuzione del pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.bids.converttolegacydeployment.f1
ms.assetid: 9e60a34a-10f7-48d1-966f-b3ff236ab4b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b52932ad26f8cebd2e67b0025f4b881241119f6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629545"
---
# <a name="convert-to-package-deployment-model-dialog-box"></a><span data-ttu-id="6d700-102">Finestra di dialogo Converti in modello di distribuzione di pacchetti</span><span class="sxs-lookup"><span data-stu-id="6d700-102">Convert to Package Deployment Model Dialog Box</span></span>
  <span data-ttu-id="6d700-103">Con il comando **Converti nel modello di distribuzione del pacchetto** è possibile convertire un pacchetto nel modello di distribuzione del pacchetto dopo aver verificato la compatibilità del progetto e di ogni relativo pacchetto con questo modello.</span><span class="sxs-lookup"><span data-stu-id="6d700-103">The **Convert to Package Deployment Model** command allows you to convert a package to the package deployment model after checking the project and each package in the project for compatibility with that model.</span></span> <span data-ttu-id="6d700-104">Se in un pacchetto vengono utilizzate funzionalità univoche per il modello di distribuzione del progetto, ad esempio parametri, il pacchetto non può essere convertito.</span><span class="sxs-lookup"><span data-stu-id="6d700-104">If a package uses features unique to the project deployment model, such as parameters, then the package cannot be converted.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="6d700-105">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="6d700-105">Task List</span></span>  
 <span data-ttu-id="6d700-106">Per la conversione di un pacchetto nel modello di distribuzione del pacchetto sono necessari due passaggi.</span><span class="sxs-lookup"><span data-stu-id="6d700-106">Converting a package to the package deployment model requires two steps.</span></span>  
  
1.  <span data-ttu-id="6d700-107">Quando si seleziona il comando **Converti nel modello di distribuzione del pacchetto** dal menu **Progetto** viene verificata la compatibilità del progetto e di ogni relativo pacchetto con questo modello.</span><span class="sxs-lookup"><span data-stu-id="6d700-107">When you select the **Convert to Package Deployment Model** command from the **Project** menu, the project and each package are checked for compatibility with this model.</span></span> <span data-ttu-id="6d700-108">I risultati vengono visualizzati nella tabella **Risultati** .</span><span class="sxs-lookup"><span data-stu-id="6d700-108">The results are displayed in the **Results** table.</span></span>  
  
     <span data-ttu-id="6d700-109">Se la verifica di compatibilità del progetto o di un pacchetto non viene completata correttamente, per ottenere ulteriori informazioni fare clic su **Non riuscito** nella colonna **Risultato** .</span><span class="sxs-lookup"><span data-stu-id="6d700-109">If the project or a package fails the compatibility test, click **Failed** in the **Result** column for more information.</span></span> <span data-ttu-id="6d700-110">Fare clic su **Salva report** per salvare una copia di queste informazioni in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="6d700-110">Click **Save Report** to save a copy of this information to a text file.</span></span>  
  
2.  <span data-ttu-id="6d700-111">Se il progetto e tutti i pacchetti superano la verifica di compatibilità, fare clic su **OK** per convertire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6d700-111">If the project and all packages pass the compatibility test, then click **OK** to convert the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d700-112">Per convertire un progetto nel modello di distribuzione del progetto usare la **Conversione guidata progetto di Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="6d700-112">To convert a project to the project deployment model, use the **Integration Services Project Conversion Wizard**.</span></span> <span data-ttu-id="6d700-113">Per altre informazioni, vedere [Integration Services Project Conversion Wizard](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="6d700-113">For more information, see [Integration Services Project Conversion Wizard](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d700-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d700-114">See Also</span></span>  
 <span data-ttu-id="6d700-115">[Distribuzione di progetti e pacchetti](packages/deploy-integration-services-ssis-projects-and-packages.md) </span><span class="sxs-lookup"><span data-stu-id="6d700-115">[Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md) </span></span>  
 <span data-ttu-id="6d700-116">[Distribuzione di pacchetti &#40;&#41;SSIS](packages/legacy-package-deployment-ssis.md) </span><span class="sxs-lookup"><span data-stu-id="6d700-116">[Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span></span>  
 [<span data-ttu-id="6d700-117">Conversione guidata progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="6d700-117">Integration Services Project Conversion Wizard</span></span>](../../2014/integration-services/integration-services-project-conversion-wizard.md)  
  
  
