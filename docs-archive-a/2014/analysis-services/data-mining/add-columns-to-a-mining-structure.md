---
title: Aggiungere colonne a una struttura di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- columns [data mining], mining structure columns
- adding columns
ms.assetid: 3f879344-9f66-4178-851a-e8c5ccccf4cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 093d78b36ab3aae6600b890a8137025c9dc9134e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635272"
---
# <a name="add-columns-to-a-mining-structure"></a><span data-ttu-id="79a63-102">Aggiungere colonne a una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="79a63-102">Add Columns to a Mining Structure</span></span>
  <span data-ttu-id="79a63-103">È possibile utilizzare Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] per aggiungere colonne a una struttura di data mining dopo averla definita tramite la Creazione guidata modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="79a63-103">Use Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to add columns to a mining structure after you have defined it in the Data Mining Wizard.</span></span> <span data-ttu-id="79a63-104">È possibile aggiungere qualsiasi colonna presente nella vista origine dati utilizzata per definire la struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="79a63-104">You can add any column that exists in the data source view that was used to define the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79a63-105">È possibile aggiungere più copie di colonne in una struttura di data mining; tuttavia, è consigliabile evitare di utilizzare più di un'istanza della colonna all'interno dello stesso modello, in modo da evitare false correlazioni tra la colonna di origine e quella derivata.</span><span class="sxs-lookup"><span data-stu-id="79a63-105">You can add multiple copies of columns to a mining structure; however, you should avoid using more than one instance of the column within the same model, to avoid false correlations between the source and the derived column.</span></span>  
  
### <a name="to-add-a-column-to-a-mining-structure"></a><span data-ttu-id="79a63-106">Per aggiungere una colonna a una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="79a63-106">To add a column to a mining structure</span></span>  
  
1.  <span data-ttu-id="79a63-107">Selezionare la scheda **Struttura di data mining** in Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="79a63-107">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="79a63-108">Fare clic con il pulsante destro del mouse sulla struttura di data mining e scegliere **Aggiungi colonna**.</span><span class="sxs-lookup"><span data-stu-id="79a63-108">Right-click the mining structure and select **Add a Column**.</span></span>  
  
     <span data-ttu-id="79a63-109">Verrà visualizzata la finestra di dialogo **Seleziona colonna** .</span><span class="sxs-lookup"><span data-stu-id="79a63-109">The **Select a Column** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="79a63-110">In **Tabella di origine**selezionare la tabella della vista origine dati in cui si trova la colonna.</span><span class="sxs-lookup"><span data-stu-id="79a63-110">Under **Source table**, select the table in the data source view where the column resides.</span></span>  
  
4.  <span data-ttu-id="79a63-111">In **Colonna di origine**selezionare la colonna che si desidera aggiungere alla struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="79a63-111">Under **Source column**, select the column that you want to add to the mining structure.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="79a63-112">Se si aggiunge una colonna già esistente, nella struttura verrà inclusa una copia e al nome verrà aggiunto "1".</span><span class="sxs-lookup"><span data-stu-id="79a63-112">If you add a column that already exists, a copy will be included in the structure, and the name appended with a "1".</span></span> <span data-ttu-id="79a63-113">È possibile specificare un nome più descrittivo per la colonna copiata digitandolo nella proprietà **Nome** della colonna della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="79a63-113">You can change the name of the copied column to something more descriptive by typing a new name in the **Name** property of the mining structure column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a63-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79a63-114">See Also</span></span>  
 [<span data-ttu-id="79a63-115">Attività e procedure relative alla struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="79a63-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
