---
title: Importare da un'origine dati multidimensionale (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7f0793ea-a4c7-42e9-b722-2164a454ebca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b26cc8ed7237f87fa5e23c6a2fd47e18de2c165
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637485"
---
# <a name="import-from-a-multidimensional-data-source-ssas-tabular"></a><span data-ttu-id="c0067-102">Importare da un'origine dati multidimensionale (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="c0067-102">Import from a Multidimensional Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="c0067-103">Un database del cubo di Analysis Services può essere utilizzato come origine dati per un modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="c0067-103">You can use an Analysis Services cube database as a data source for a tabular model.</span></span> <span data-ttu-id="c0067-104">Per importare dati da un cubo di Analysis Services, è necessario definire una query MDX per selezionare i dati da importare.</span><span class="sxs-lookup"><span data-stu-id="c0067-104">In order to import data from an Analysis Services cube, you must define an MDX Query to select data to import.</span></span>  
  
 <span data-ttu-id="c0067-105">È possibile importare in un modello qualsiasi tipo di dati contenuto in un database di SQL Server Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c0067-105">Any data that is contained in a SQL Server Analysis Services database can be imported into a model.</span></span> <span data-ttu-id="c0067-106">È possibile estrarre tutta o parte di una dimensione oppure ottenere sezioni e funzioni di aggregazione dal cubo, ad esempio la somma mensile delle vendite per l'anno corrente, e così via. È tuttavia necessario tenere presente che tutti i dati importati da un cubo sono bidimensionali.</span><span class="sxs-lookup"><span data-stu-id="c0067-106">You can extract all or part of a dimension, or get slices and aggregates from the cube, such as the sum of sales, month by month, for the current year, etc. However, you should keep in mind all data that you import from a cube is flattened.</span></span> <span data-ttu-id="c0067-107">Se pertanto si definisce una query che consente di recuperare misure in base a più dimensioni, ogni dimensione dei dati verrà importata in una colonna separata.</span><span class="sxs-lookup"><span data-stu-id="c0067-107">Therefore, if you define a query that retrieves measures along multiple dimensions, the data will be imported with each dimension in a separate column.</span></span>  
  
 <span data-ttu-id="c0067-108">La versione dei cubi di Analysis Services deve essere SQL Server 2005, SQL Server 2008, SQL Server 2008 R2 [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]o [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0067-108">Analysis Services cubes must be version SQL Server 2005, SQL Server 2008, SQL Server 2008 R2, [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], or [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].</span></span>  
  
### <a name="to-import-data-from-an-analysis-services-cube"></a><span data-ttu-id="c0067-109">Per importare dati da un cubo di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c0067-109">To import data from an Analysis Services cube</span></span>  
  
1.  <span data-ttu-id="c0067-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]fare clic sul menu **Modello** , quindi selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="c0067-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="c0067-111">Selezionare **Microsoft Analysis Services** nella pagina **Connessione a un'origine dati**, quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c0067-111">On the **Connect to a Data Source** page, select **Microsoft Analysis Services**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="c0067-112">Seguire i passaggi nell'Importazione guidata tabella.</span><span class="sxs-lookup"><span data-stu-id="c0067-112">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="c0067-113">Sarà possibile specificare una query MDX nella pagina **Specifica di una query MDX** .</span><span class="sxs-lookup"><span data-stu-id="c0067-113">You will be able to specify an MDX query on the **Specify a MDX Query** page.</span></span> <span data-ttu-id="c0067-114">Per utilizzare Progettazione query MDX, nella pagina Specifica di una query MDX fare clic su **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="c0067-114">To use the MDX Query Designer, on the Specify a MDX Query page, click **Design**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0067-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0067-115">See Also</span></span>  
 <span data-ttu-id="c0067-116">[Importare dati &#40;SSAS tabulare&#41;](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c0067-116">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="c0067-117">Origini dati supportate &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="c0067-117">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
