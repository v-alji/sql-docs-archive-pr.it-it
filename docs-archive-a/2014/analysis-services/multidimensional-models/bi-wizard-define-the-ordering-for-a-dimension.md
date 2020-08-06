---
title: Definire l'ordinamento per una dimensione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OrderBy property
- dimensions [Analysis Services], ordering
- Business Intelligence enhancements [Analysis Services], ordering
- dimensions [Analysis Services], Business Intelligence enhancements
- ordering dimensions [Analysis Services]
- OrderByAttributeID property
ms.assetid: c42fbd58-244d-4e0a-b715-6f919cbc3ad9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8cd5ea148e374c18c530ba0a15c80dbb23983020
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626369"
---
# <a name="define-the-ordering-for-a-dimension"></a><span data-ttu-id="f9fd5-102">Definire l'ordinamento di una dimensione</span><span class="sxs-lookup"><span data-stu-id="f9fd5-102">Define the Ordering for a Dimension</span></span>
  <span data-ttu-id="f9fd5-103">L'aggiunta della funzionalità avanzata di ordinamento degli attributi a un cubo o una dimensione consente di specificare come verranno ordinati i membri di un attributo.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-103">Add the attribute ordering enhancement to a cube or dimension to specify how the members of an attribute are ordered.</span></span> <span data-ttu-id="f9fd5-104">I membri possono essere ordinati in base al nome o alla chiave dell'attributo oppure in base al nome o alla chiave di un altro attributo (tramite una relazione tra attributi).</span><span class="sxs-lookup"><span data-stu-id="f9fd5-104">Members can be ordered by the name or the key of the attribute, or by the name or the key of another attribute (based on an attribute relationship).</span></span> <span data-ttu-id="f9fd5-105">Per impostazione predefinita, i membri vengono ordinati in base al nome.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-105">By default, members are ordered by the name.</span></span> <span data-ttu-id="f9fd5-106">Questa funzionalità avanzata modifica l'impostazione delle proprietà `OrderBy` e `OrderByAttributeID` degli attributi in una dimensione.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-106">This enhancement changes the `OrderBy` and `OrderByAttributeID` property settings for attributes in a dimension.</span></span>  
  
 <span data-ttu-id="f9fd5-107">Per aggiungere la funzionalità di ordinamento degli attributi, usare Configurazione guidata funzionalità di Business Intelligence e quindi selezionare l'opzione **Impostazione ordinamento attributi** nella pagina **Scelta funzionalità avanzata** .</span><span class="sxs-lookup"><span data-stu-id="f9fd5-107">To add attribute ordering, you use the Business Intelligence Wizard, and select the **Specify attribute ordering** option on the **Choose Enhancement** page.</span></span> <span data-ttu-id="f9fd5-108">Questa procedura guidata consente di eseguire in modo semplificato i passaggi relativi alla selezione di una dimensione alla quale si desidera applicare l'ordinamento degli attributi e all'impostazione della modalità di ordinamento degli attributi per la dimensione selezionata.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-108">This wizard then guides you through the steps of selecting a dimension to which you want to apply attribute ordering and specifying how to order the attributes for the selected dimension.</span></span>  
  
## <a name="selecting-a-dimension"></a><span data-ttu-id="f9fd5-109">Selezione di una dimensione</span><span class="sxs-lookup"><span data-stu-id="f9fd5-109">Selecting a Dimension</span></span>  
 <span data-ttu-id="f9fd5-110">Nella prima pagina **Impostazione ordinamento attributi** della procedura guidata specificare la dimensione alla quale si desidera applicare l'ordinamento degli attributi.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-110">On the first **Specify Attribute Ordering** page of the wizard, you specify the dimension to which you want to apply attribute ordering.</span></span> <span data-ttu-id="f9fd5-111">L'aggiunta della funzionalità avanzata dell'ordinamento degli attributi alla dimensione selezionata implica modifiche alla dimensione.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-111">The attribute ordering enhancement added to this selected dimension will result in changes to the dimension.</span></span> <span data-ttu-id="f9fd5-112">Tali modifiche verranno ereditate da tutti i cubi che includono la dimensione selezionata.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-112">These changes will be inherited by all cubes that include the selected dimension.</span></span>  
  
## <a name="specifying-ordering"></a><span data-ttu-id="f9fd5-113">Impostazione dell'ordinamento</span><span class="sxs-lookup"><span data-stu-id="f9fd5-113">Specifying Ordering</span></span>  
 <span data-ttu-id="f9fd5-114">Nella seconda pagina **Impostazione ordinamento attributi** della procedura guidata specificare la modalità di ordinamento di tutti gli attributi nella dimensione.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-114">On the second **Specify Attribute Ordering** page of the wizard, you specify how all the attributes in the dimension will be ordered.</span></span>  
  
 <span data-ttu-id="f9fd5-115">Nella colonna **Attributo di ordinamento** è possibile modificare l'attributo usato per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-115">In the **Ordering Attribute** column, you can change the attribute used to do the ordering.</span></span> <span data-ttu-id="f9fd5-116">Se l'attributo che si desidera utilizzare per ordinare i membri non è presente nell'elenco, scorrere l'elenco verso il basso e quindi selezionare **\<New attribute...>** per aprire la finestra di dialogo **Seleziona colonna** , in cui è possibile selezionare una colonna in una tabella delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-116">If the attribute that you want to use to order members is not in the list, scroll down the list, and then select **\<New attribute...>** to open the **Select a Column** dialog box, where you can select a column in a dimension table.</span></span> <span data-ttu-id="f9fd5-117">La selezione di una colonna tramite la finestra di dialogo **Seleziona colonna** consente di creare un attributo aggiuntivo in base al quale ordinare i membri di un attributo.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-117">Selecting a column by using the **Select a Column** dialog box creates an additional attribute with which to order members of an attribute.</span></span>  
  
 <span data-ttu-id="f9fd5-118">Nella colonna **Criteri** è quindi possibile selezionare se ordinare i membri dell'attributo in base alla **chiave** oppure al **nome**.</span><span class="sxs-lookup"><span data-stu-id="f9fd5-118">In the **Criteria** column, you can then select whether to order the members of the attribute by either **Key** or **Name**.</span></span>  
  
  
