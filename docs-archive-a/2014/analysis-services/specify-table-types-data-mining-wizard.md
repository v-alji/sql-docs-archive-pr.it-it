---
title: Impostazione tipi di tabella (creazione guidata modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifytabletypes.f1
ms.assetid: 8209a707-faef-4ffc-8991-6c13bb350753
author: minewiskan
ms.author: owend
ms.openlocfilehash: 88c09f26958c37ed0a99efb54a5eb5c08505d16b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635756"
---
# <a name="specify-table-types-data-mining-wizard"></a><span data-ttu-id="80cd5-102">Impostazione tipi di tabelle (Creazione guidata modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="80cd5-102">Specify Table Types (Data Mining Wizard)</span></span>
  <span data-ttu-id="80cd5-103">Usare la pagina **Impostazione tipi di tabelle** per identificare le tabelle da utilizzare per definire la struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="80cd5-103">Use the **Specify Table Types** page to identify the tables to use to define the mining structure.</span></span> <span data-ttu-id="80cd5-104">Le tabelle non selezionate non verranno utilizzate per definire la struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="80cd5-104">If a table is not selected, it will not be used to define the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80cd5-105">È possibile aggiungere tabelle successivamente mediante la scheda **Struttura di data mining** in **Progettazione modelli di data mining**.</span><span class="sxs-lookup"><span data-stu-id="80cd5-105">You can add tables later from the **Mining Structure** tab in **Data Mining Designer**.</span></span>  
  
 <span data-ttu-id="80cd5-106">**Per altre informazioni:** [Tabelle annidate &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), [Creazione guidata modello di data mining &#40;Analysis Services - Data mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Creare una struttura di data mining relazionale](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="80cd5-106">**For More Information:** [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="80cd5-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="80cd5-107">Options</span></span>  
 <span data-ttu-id="80cd5-108">**Tabelle**</span><span class="sxs-lookup"><span data-stu-id="80cd5-108">**Tables**</span></span>  
 <span data-ttu-id="80cd5-109">Visualizza le tabelle incluse nella vista origine dati selezionata nella pagina **Selezione vista origine dati** della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="80cd5-109">Displays the tables in the data source view that you selected on the **Select Data Source View** page of the wizard.</span></span>  
  
 <span data-ttu-id="80cd5-110">**Caso**</span><span class="sxs-lookup"><span data-stu-id="80cd5-110">**Case**</span></span>  
 <span data-ttu-id="80cd5-111">Consente di selezionare una tabella da utilizzare come tabella del case.</span><span class="sxs-lookup"><span data-stu-id="80cd5-111">Select one table to use as the case table.</span></span>  
  
 <span data-ttu-id="80cd5-112">**Annidato**</span><span class="sxs-lookup"><span data-stu-id="80cd5-112">**Nested**</span></span>  
 <span data-ttu-id="80cd5-113">Consente di selezionare le tabelle nidificate.</span><span class="sxs-lookup"><span data-stu-id="80cd5-113">Select the tables to use as nested tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="80cd5-114">A queste tabelle deve essere associata una relazione molti-a-uno e non uno-a-molti con la tabella del case.</span><span class="sxs-lookup"><span data-stu-id="80cd5-114">These tables must have a many-to-one relationship with the case table, not a one-to-many relationship.</span></span> <span data-ttu-id="80cd5-115">Per poter selezionare la tabella nidificata, è necessario impostare tale relazione nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="80cd5-115">You must specify this relationship in the data source view before you can select the table as nested.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cd5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80cd5-116">See Also</span></span>  
 <span data-ttu-id="80cd5-117">[Guida sensibile al contesto della creazione guidata modello di data mining &#40;Analysis Services-&#41;di data mining](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="80cd5-117">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="80cd5-118">[Selezione vista origine dati &#40;creazione guidata modello di data mining&#41;](select-data-source-view-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="80cd5-118">[Select Data Source View &#40;Data Mining Wizard&#41;](select-data-source-view-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="80cd5-119">Specificare i dati di training &#40;creazione guidata modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="80cd5-119">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](specify-the-training-data-data-mining-wizard.md)  
  
  
