---
title: Finestra di dialogo Seleziona colonna chiave tabella nidificata (visualizzazione struttura di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.structure.addnestedtable.f1
helpviewer_keywords:
- Select a Nested Table Key Column dialog box
ms.assetid: f68b89a7-17df-45f8-ba7f-b458cd9b1ec3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dc524f6913b7be15e87869355515397a3e0b65c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635778"
---
# <a name="select-a-nested-table-key-column-dialog-box-mining-structure-view"></a><span data-ttu-id="fa14f-102">Finestra di dialogo Seleziona colonna chiave tabella nidificata (visualizzazione Struttura di data mining)</span><span class="sxs-lookup"><span data-stu-id="fa14f-102">Select a Nested Table Key Column Dialog Box (Mining Structure View)</span></span>
  <span data-ttu-id="fa14f-103">Utilizzare la finestra di dialogo **Seleziona colonna chiave tabella nidificata** per indicare una colonna che fungerà da chiave per la nuova tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="fa14f-103">Use the **Select a Nested Table Key Column** dialog box to designate a column that will act as the key for the new nested table.</span></span> <span data-ttu-id="fa14f-104">Alla chiusura della finestra di dialogo, una nuova tabella verrà aggiunta alla struttura di data mining contenente la colonna chiave specificata.</span><span class="sxs-lookup"><span data-stu-id="fa14f-104">When you exit the dialog box, a new table is added to the mining structure that contains the designated key column.</span></span> <span data-ttu-id="fa14f-105">È possibile aggiungere altre colonne alla tabella annidata facendo clic con il pulsante destro del mouse sulla struttura e selezionando **Aggiungi colonna**.</span><span class="sxs-lookup"><span data-stu-id="fa14f-105">You can add additional columns to the nested table by right-clicking the structure and selecting **Add a Column**.</span></span> <span data-ttu-id="fa14f-106">Nella finestra di dialogo sono disponibili opzioni diverse a seconda che si utilizzi una modello di data mining OLAP o relazionale.</span><span class="sxs-lookup"><span data-stu-id="fa14f-106">The dialog box contains different options depending on whether you are working with an OLAP mining model or a relational mining model.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa14f-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fa14f-107">Options</span></span>  
 <span data-ttu-id="fa14f-108">**Tabella di origine**</span><span class="sxs-lookup"><span data-stu-id="fa14f-108">**Source table**</span></span>  
 <span data-ttu-id="fa14f-109">Tabella su cui è basato il modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="fa14f-109">The table on which the mining model is based.</span></span>  
  
 <span data-ttu-id="fa14f-110">Questa opzione può essere utilizzata solo per i modelli di dati mining relazionali.</span><span class="sxs-lookup"><span data-stu-id="fa14f-110">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="fa14f-111">**Colonna di origine**</span><span class="sxs-lookup"><span data-stu-id="fa14f-111">**Source column**</span></span>  
 <span data-ttu-id="fa14f-112">Elenco di tutte le colonne disponibili nella tabella di origine utilizzabili come chiave della tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="fa14f-112">A list of all the available columns in the source table that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="fa14f-113">Questa opzione può essere utilizzata solo per i modelli di dati mining relazionali.</span><span class="sxs-lookup"><span data-stu-id="fa14f-113">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="fa14f-114">**Mostra colonne di tipo**</span><span class="sxs-lookup"><span data-stu-id="fa14f-114">**Show column types**</span></span>  
 <span data-ttu-id="fa14f-115">Elenco dei tipi di dati di colonna disponibili.</span><span class="sxs-lookup"><span data-stu-id="fa14f-115">A list of available column data types.</span></span> <span data-ttu-id="fa14f-116">Selezionare o deselezionare i tipi di dati per ridurre l'elenco di colonne in **Colonna di origine**.</span><span class="sxs-lookup"><span data-stu-id="fa14f-116">Select or clear data types to filter the list of columns in **Source column**.</span></span> <span data-ttu-id="fa14f-117">Nell'elenco **Colonna di origine** verranno visualizzate solo le colonne che corrispondono ai tipi di dati selezionati.</span><span class="sxs-lookup"><span data-stu-id="fa14f-117">Only columns that match the checked data types will be shown in the **Source column** list.</span></span>  
  
 <span data-ttu-id="fa14f-118">Questa opzione può essere utilizzata solo per i modelli di dati mining relazionali.</span><span class="sxs-lookup"><span data-stu-id="fa14f-118">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="fa14f-119">**Attributes (Attributi)**</span><span class="sxs-lookup"><span data-stu-id="fa14f-119">**Attributes**</span></span>  
 <span data-ttu-id="fa14f-120">Elenco di attributi utilizzabili come chiave della tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="fa14f-120">A list of attributes that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="fa14f-121">Questa opzione può essere utilizzata solo per i modelli di dati mining OLAP.</span><span class="sxs-lookup"><span data-stu-id="fa14f-121">This is only used for OLAP mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa14f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa14f-122">See Also</span></span>  
 [<span data-ttu-id="fa14f-123">Visualizzazione struttura di data mining &#40;Progettazione modelli di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="fa14f-123">Mining Structure View &#40;Data Mining Model Designer&#41;</span></span>](mining-structure-view-data-mining-model-designer.md)  
  
  
