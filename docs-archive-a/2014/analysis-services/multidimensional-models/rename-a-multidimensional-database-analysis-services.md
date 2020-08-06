---
title: Rinominare un database multidimensionale (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- renaming databases
ms.assetid: 15fdaec7-f3e4-44d9-9b78-1a1d78c484e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3974e7671aff5d1cba22b10563bbc85a129a1dff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630110"
---
# <a name="rename-a-multidimensional-database-analysis-services"></a><span data-ttu-id="34279-102">Rinominare un database multidimensionale (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="34279-102">Rename a Multidimensional Database (Analysis Services)</span></span>
  <span data-ttu-id="34279-103">Il modo in cui si modifica il nome di un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database dipende dalla modalità di connessione al [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span><span class="sxs-lookup"><span data-stu-id="34279-103">The manner in which you change the name of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database depends upon how you connect to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="34279-104">Per modificare il nome di un database esistente, è necessario connettersi in modalità online.</span><span class="sxs-lookup"><span data-stu-id="34279-104">To change the name of an existing database, you must connect in online mode.</span></span> <span data-ttu-id="34279-105">Per modificare il nome del database in cui verranno create istanze degli oggetti di un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , è necessario connettersi in modalità progetto.</span><span class="sxs-lookup"><span data-stu-id="34279-105">To change the name of the database into which objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project will be instantiated, you must connect in project mode.</span></span>  
  
### <a name="to-change-the-database-name-in-online-mode"></a><span data-ttu-id="34279-106">Per modificare il nome del database in modalità online</span><span class="sxs-lookup"><span data-stu-id="34279-106">To change the database name in online mode</span></span>  
  
1.  <span data-ttu-id="34279-107">Connettersi direttamente al database di [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]utilizzando [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34279-107">Using [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], connect directly to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="34279-108">In Esplora soluzioni fare clic con il pulsante destro del mouse sul database e quindi scegliere **Modifica database**.</span><span class="sxs-lookup"><span data-stu-id="34279-108">In Solution Explorer, right-click the database and then click **Edit Database**.</span></span>  
  
3.  <span data-ttu-id="34279-109">Nella casella di testo **Nome database** modificare il nome del database.</span><span class="sxs-lookup"><span data-stu-id="34279-109">In the **Database name** text box, change the database name.</span></span>  
  
4.  <span data-ttu-id="34279-110">Fare clic su **Salva** o **Salva tutto** sulla barra degli strumenti, scegliere **Salva elementi selezionati** o **Salva tutto** dal menu **File** oppure chiudere **Progettazione database** e quindi fare clic su **Salva** quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="34279-110">Click **Save** or **Save All** on the toolbar, click **Save Selected Items** or **Save All** on the **File** menu, or close the **Database Designer** and then click **Save** when prompted.</span></span>  
  
     <span data-ttu-id="34279-111">Il nome del database verrà aggiornato nell'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e l'oggetto di database verrà aggiornato in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="34279-111">The database name is updated in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and the database object in Solution Explorer is refreshed.</span></span>  
  
### <a name="to-change-the-database-name-in-project-mode"></a><span data-ttu-id="34279-112">Per modificare il nome del database in modalità progetto</span><span class="sxs-lookup"><span data-stu-id="34279-112">To change the database name in project mode</span></span>  
  
1.  <span data-ttu-id="34279-113">Aprire il progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34279-113">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="34279-114">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="34279-114">In Solution Explorer, right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="34279-115">Nella finestra di dialogo **Pagine delle proprietà** fare clic su **Distribuzione** nella sezione **Proprietà di configurazione** .</span><span class="sxs-lookup"><span data-stu-id="34279-115">In the **Property Pages** dialog box, click **Deployment** in the **Configuration Properties** section.</span></span>  
  
4.  <span data-ttu-id="34279-116">Modificare la proprietà **Database** nel nuovo nome del database.</span><span class="sxs-lookup"><span data-stu-id="34279-116">Change the **Database** property to the new database name.</span></span>  
  
     <span data-ttu-id="34279-117">La successiva distribuzione del progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] verrà eseguita per questo nuovo nome di database.</span><span class="sxs-lookup"><span data-stu-id="34279-117">The next time the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project is deployed, it will be deployed to this new database name.</span></span> <span data-ttu-id="34279-118">Se il database esiste già, verrà sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="34279-118">If this database already exists, it will be overwritten.</span></span>  
  
### <a name="to-change-the-database-name-using-sql-server-management-studio"></a><span data-ttu-id="34279-119">Per modificare il nome del database tramite SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34279-119">To change the database name using SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="34279-120">Fare clic con il pulsante destro del mouse sul database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e modificare la proprietà Name.</span><span class="sxs-lookup"><span data-stu-id="34279-120">Right-click the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and edit the Name property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34279-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34279-121">See Also</span></span>  
 <span data-ttu-id="34279-122">[Configurare le proprietà del server in Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="34279-122">[Configure Server Properties in Analysis Services](../server-properties/server-properties-in-analysis-services.md) </span></span>  
 <span data-ttu-id="34279-123">[Impostazione delle proprietà di database multidimensionali &#40;Analysis Services&#41;](set-multidimensional-database-properties-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="34279-123">[Set Multidimensional Database Properties &#40;Analysis Services&#41;](set-multidimensional-database-properties-analysis-services.md) </span></span>  
 <span data-ttu-id="34279-124">[Configurare Analysis Services proprietà del progetto &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="34279-124">[Configure Analysis Services Project Properties &#40;SSDT&#41;](configure-analysis-services-project-properties-ssdt.md) </span></span>  
 [<span data-ttu-id="34279-125">Distribuire progetti di Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="34279-125">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](deploy-analysis-services-projects-ssdt.md)  
  
  
