---
title: Eliminare un'origine dati in Esplora soluzioni (SSAS multidimensionale) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.deleteobjects.f1
helpviewer_keywords:
- data sources [Analysis Services], deleting
- deleting data sources
- removing data sources
ms.assetid: b45441ef-f909-4736-98b9-cc80d0acac99
author: minewiskan
ms.author: owend
ms.openlocfilehash: d6101c8704579894590994d88e0286197148b694
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637464"
---
# <a name="delete-a-data-source-in-solution-explorer-ssas-multidimensional"></a><span data-ttu-id="9ea56-102">Eliminare un'origine dati in Esplora soluzioni (SSAS multidimensionale)</span><span class="sxs-lookup"><span data-stu-id="9ea56-102">Delete a Data Source in Solution Explorer (SSAS Multidimensional)</span></span>
  <span data-ttu-id="9ea56-103">È possibile eliminare un oggetto origine dati per rimuoverlo definitivamente da un progetto di modello multidimensionale di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="9ea56-103">You can delete a data source object to permanently remove it from an Analysis Services multidimensional model project.</span></span>  
  
 <span data-ttu-id="9ea56-104">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]le origini dati costituiscono la base sulla quale vengono costruite le viste origine dati e queste ultime vengono a propria volta utilizzate per definire dimensioni, cubi e strutture di data mining in un database o un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ea56-104">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], data sources provide the basis on which data source views are constructed, and data source views are in turn used to define dimensions, cubes, and mining structures in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span> <span data-ttu-id="9ea56-105">Di conseguenza, l'eliminazione di un'origine dei dati può invalidare altri oggetti di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ea56-105">Therefore, deleting a data source may invalidate other [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="9ea56-106">Prima di eliminare l'oggetto, si consiglia di verificare sempre l'elenco degli oggetti dipendenti fornito.</span><span class="sxs-lookup"><span data-stu-id="9ea56-106">You should always review the list of dependent objects that is provided before deleting the object.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9ea56-107">Non è possibile eliminare origini dati da cui dipendono altri oggetti da un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] aperto da [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in modalità online.</span><span class="sxs-lookup"><span data-stu-id="9ea56-107">Data sources on which other objects depend cannot be deleted from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database opened by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span> <span data-ttu-id="9ea56-108">Prima di eliminare l'origine dati, è necessario eliminare tutti gli oggetti del database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] che dipendono da tale origine dati.</span><span class="sxs-lookup"><span data-stu-id="9ea56-108">You must delete all objects in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that depend on that data source before deleting the data source.</span></span> <span data-ttu-id="9ea56-109">Per altre informazioni sulla modalità online, vedere [Connect in Online Mode to an Analysis Services Database](connect-in-online-mode-to-an-analysis-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="9ea56-109">For more information about online mode, see [Connect in Online Mode to an Analysis Services Database](connect-in-online-mode-to-an-analysis-services-database.md).</span></span>  
  
### <a name="to-delete-a-data-source"></a><span data-ttu-id="9ea56-110">Per eliminare un'origine dati</span><span class="sxs-lookup"><span data-stu-id="9ea56-110">To delete a data source</span></span>  
  
1.  <span data-ttu-id="9ea56-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto o connettersi al database da cui si desidera eliminare un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9ea56-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database from which you want to delete a data source.</span></span>  
  
2.  <span data-ttu-id="9ea56-112">In **Esplora soluzioni**espandere la cartella **Origini dati** .</span><span class="sxs-lookup"><span data-stu-id="9ea56-112">In **Solution Explorer**, expand the **Data Sources** folder.</span></span>  
  
3.  <span data-ttu-id="9ea56-113">Fare clic con il pulsante destro del mouse sull'origine dati, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="9ea56-113">Right-click the data source, and then click **Delete**.</span></span> <span data-ttu-id="9ea56-114">Viene visualizzata la finestra di dialogo **Elimina oggetti**  in cui sono riportati gli oggetti che saranno invalidati in caso di eliminazione dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9ea56-114">The **Delete Objects**  dialog box appears, showing the objects that will be invalidated if you delete the data source.</span></span> <span data-ttu-id="9ea56-115">Esaminare attentamente l'elenco prima di fare clic su **OK** per eliminare l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9ea56-115">Review this list carefully before clicking **OK** to delete the data source.</span></span>  
  
4.  <span data-ttu-id="9ea56-116">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="9ea56-116">Save the project.</span></span>  
  
     <span data-ttu-id="9ea56-117">Dopo l'eliminazione di un'origine dati da un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , è necessario salvare il progetto modificato. In caso contrario, alla successiva apertura del progetto verrà visualizzato un errore poiché il file XML sottostante per l'origine dati eliminata risulta mancante quando il progetto tenta di caricare tale origine dati.</span><span class="sxs-lookup"><span data-stu-id="9ea56-117">After deleting a data source from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you must save the modified project or you will receive an error the next time you open the project because the underlying XML file for the deleted data source will be missing when the project attempts to load the deleted data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea56-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ea56-118">See Also</span></span>  
 <span data-ttu-id="9ea56-119">[Origini dati nei modelli multidimensionali](data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="9ea56-119">[Data Sources in Multidimensional Models](data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="9ea56-120">Origini dati supportate &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="9ea56-120">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)  
  
  
