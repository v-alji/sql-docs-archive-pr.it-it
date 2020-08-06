---
title: Impostazione informazioni origine (creazione guidata dimensione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionmaintable.f1
ms.assetid: 0538b490-5185-49e1-a783-4ce3539a0de5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 99bbaac0bdf24a18dcde455e779f056b98106dc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635759"
---
# <a name="specify-source-information-dimension-wizard"></a><span data-ttu-id="15266-102">Impostazione informazioni origine (Creazione guidata dimensione)</span><span class="sxs-lookup"><span data-stu-id="15266-102">Specify Source Information (Dimension Wizard)</span></span>
  <span data-ttu-id="15266-103">Utilizzare la pagina **Selezione tabella principale della dimensione** per selezionare la vista origine dati, la tabella principale della dimensione, le colonne chiave e le colonne nome membro per la dimensione da creare.</span><span class="sxs-lookup"><span data-stu-id="15266-103">Use the **Select the Main Dimension Table** page to select the data source view, main dimension table, key columns, and member name column for the dimension to be created.</span></span>  
  
 <span data-ttu-id="15266-104">**Per aprire la Creazione guidata dimensione.**</span><span class="sxs-lookup"><span data-stu-id="15266-104">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="15266-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]fare clic con il pulsante destro del mouse sulla cartella **Dimensioni**in **Esplora soluzioni** per scegliere un progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , quindi fare clic su **Nuova dimensione**.</span><span class="sxs-lookup"><span data-stu-id="15266-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="15266-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="15266-106">Options</span></span>  
 <span data-ttu-id="15266-107">**Vista origine dati**</span><span class="sxs-lookup"><span data-stu-id="15266-107">**Data source view**</span></span>  
 <span data-ttu-id="15266-108">Seleziona una vista origine dati</span><span class="sxs-lookup"><span data-stu-id="15266-108">Select a data source view.</span></span>  
  
 <span data-ttu-id="15266-109">**Tabella principale**</span><span class="sxs-lookup"><span data-stu-id="15266-109">**Main table**</span></span>  
 <span data-ttu-id="15266-110">Consente di selezionare una tabella da utilizzare come tabella principale della dimensione nella vista origine dati specificata.</span><span class="sxs-lookup"><span data-stu-id="15266-110">Select a table from the selected data source view to use as the main table for the dimension.</span></span>  
  
 <span data-ttu-id="15266-111">**Colonne chiave**</span><span class="sxs-lookup"><span data-stu-id="15266-111">**Key columns**</span></span>  
 <span data-ttu-id="15266-112">Consente di selezionare le colonne chiave della tabella specificata nell'opzione **Tabella principale** per l'attributo chiave della dimensione.</span><span class="sxs-lookup"><span data-stu-id="15266-112">Select the key columns from the table specified in **Main table** for the key attribute of the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15266-113">È possibile selezionare più colonne.</span><span class="sxs-lookup"><span data-stu-id="15266-113">More than one column can be selected.</span></span> <span data-ttu-id="15266-114">Se la tabella contiene una chiave primaria composta, selezionare tutte le colonne incluse in essa.</span><span class="sxs-lookup"><span data-stu-id="15266-114">If the table contains a composite primary key, select all the columns included in the composite primary key.</span></span> <span data-ttu-id="15266-115">L'ordine delle colonne chiave è importante.</span><span class="sxs-lookup"><span data-stu-id="15266-115">The order of the key columns is important.</span></span>  
  
 <span data-ttu-id="15266-116">**Colonna nome**</span><span class="sxs-lookup"><span data-stu-id="15266-116">**Name column**</span></span>  
 <span data-ttu-id="15266-117">Consente di selezionare la colonna contenente i nomi membro per la dimensione nella tabella specificata nell'opzione **Tabella principale** .</span><span class="sxs-lookup"><span data-stu-id="15266-117">Select the column from the table specified in **Main table** that provides the member names for the dimension.</span></span> <span data-ttu-id="15266-118">È necessario specificare una colonna nome quando si utilizza una chiave composta.</span><span class="sxs-lookup"><span data-stu-id="15266-118">A name column must be specified when a composite key is used.</span></span> <span data-ttu-id="15266-119">Per creare una colonna nome per una chiave composta, si consiglia di creare un calcolo denominato nella vista origine dati che concatena le colonne chiave specificate.</span><span class="sxs-lookup"><span data-stu-id="15266-119">To create a name column for a composite key, we recommend that you create a named calculation in the data source view that concatenates the specified key columns.</span></span> <span data-ttu-id="15266-120">Quando si utilizza una chiave singola, la colonna nome è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="15266-120">When a single key is used, the name column is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15266-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15266-121">See Also</span></span>  
 <span data-ttu-id="15266-122">[Guida sensibile al contesto della creazione guidata dimensione](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="15266-122">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="15266-123">[Dimensioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="15266-123">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="15266-124">Dimensioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="15266-124">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
