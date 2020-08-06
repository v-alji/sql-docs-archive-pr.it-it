---
title: Impostazione chiave e tipo della dimensione (creazione guidata dimensione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionkeyandtype.f1
ms.assetid: d7d5db55-36c3-45f6-ade3-29aa516589c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc08584ed12de8597b8289fd223cc47945d7d087
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635774"
---
# <a name="specify-dimension-key-and-type-dimension-wizard"></a><span data-ttu-id="f752e-102">Impostazione chiave e tipo della dimensione (Creazione guidata dimensione)</span><span class="sxs-lookup"><span data-stu-id="f752e-102">Specify Dimension Key and Type (Dimension Wizard)</span></span>
  <span data-ttu-id="f752e-103">La pagina **Impostazione chiave e tipo della dimensione** consente di definire l'attributo chiave della dimensione e di indicare se si tratta di una dimensione a modifica lenta.</span><span class="sxs-lookup"><span data-stu-id="f752e-103">Use the **Specify Dimension Key and Type** page to define the key attribute of the dimension and to indicate whether the dimension is a slowly changing dimension (SCD).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f752e-104">Questa pagina viene visualizzata solo se si seleziona **Build the dimension without using a data source** (Compila dimensione senza usare un'origine dei dati) nella pagina **Select Build Method** (Selezione metodo di compilazione) e **Dimensione standard** nella pagina **Selezione tipo di dimensione** .</span><span class="sxs-lookup"><span data-stu-id="f752e-104">This page is displayed only if you selected **Build the dimension without using a data source** on the **Select Build Method** page and if you selected **Standard dimension** on the **Select the Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f752e-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f752e-105">Options</span></span>  
 <span data-ttu-id="f752e-106">**Attributo chiave**</span><span class="sxs-lookup"><span data-stu-id="f752e-106">**Key attribute**</span></span>  
 <span data-ttu-id="f752e-107">Consente di selezionare l'attributo che costituirà l'attributo chiave per la dimensione.</span><span class="sxs-lookup"><span data-stu-id="f752e-107">Select the attribute that will be the key attribute for the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f752e-108">Se non sono stati definiti attributi per la dimensione, l'unico valore disponibile per questa opzione sarà **Creare automaticamente l'attributo chiave**.</span><span class="sxs-lookup"><span data-stu-id="f752e-108">If no attributes have been defined for the dimension, the only value available for this option is **Create key attribute automatically.**</span></span> <span data-ttu-id="f752e-109">Questo valore non è disponibile se sono stati definiti attributi per la dimensione.</span><span class="sxs-lookup"><span data-stu-id="f752e-109">This value is not available if any attributes are defined for the dimension.</span></span>  
  
 <span data-ttu-id="f752e-110">**Dimensione modificabile**</span><span class="sxs-lookup"><span data-stu-id="f752e-110">**This is a changing dimension**</span></span>  
 <span data-ttu-id="f752e-111">Selezionare questa opzione per indicare che si tratta di una dimensione a modifica lenta.</span><span class="sxs-lookup"><span data-stu-id="f752e-111">Select to indicate that the dimension is a slowly changing dimension.</span></span> <span data-ttu-id="f752e-112">Selezionando questa opzione vengono create colonne e attributi aggiuntivi che possono essere utilizzati per tenere traccia di tutti gli spostamenti dei membri tra le gerarchie della dimensione.</span><span class="sxs-lookup"><span data-stu-id="f752e-112">Selecting this option will create additional columns and attributes that can be used to track the movement of members within the hierarchies of the dimension over time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f752e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f752e-113">See Also</span></span>  
 <span data-ttu-id="f752e-114">[Guida sensibile al contesto della creazione guidata dimensione](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="f752e-114">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="f752e-115">[Dimensioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="f752e-115">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="f752e-116">Dimensioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="f752e-116">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
