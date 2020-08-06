---
title: Definire una relazione di riferimento e le proprietà delle relazioni a cui si fa riferimento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- referenced dimension relationship
- relationships [Analysis Services], referenced dimensions
ms.assetid: 5bb44b41-635b-4398-8fe9-0bfbb142553e
author: minewiskan
ms.author: owend
ms.openlocfilehash: a84cf2ed95ab3660c5a6b3c039dc58351dc43264
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715808"
---
# <a name="define-a-referenced-relationship-and-referenced-relationship-properties"></a><span data-ttu-id="46dcf-102">Definire una relazione di tipo Riferimento e le relative proprietà</span><span class="sxs-lookup"><span data-stu-id="46dcf-102">Define a Referenced Relationship and Referenced Relationship Properties</span></span>
  <span data-ttu-id="46dcf-103">È possibile definire una relazione di tipo Riferimento per la dimensione tramite la scheda **Utilizzo dimensioni** di Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="46dcf-103">A reference dimension relationship is defined on the **Dimension Usage** tab of Cube Designer.</span></span> <span data-ttu-id="46dcf-104">La relazione di tipo Riferimento viene definita specificando gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="46dcf-104">The reference dimension relationship is defined by specifying the following:</span></span>  
  
-   <span data-ttu-id="46dcf-105">La dimensione intermedia con cui eseguire l'unione in join.</span><span class="sxs-lookup"><span data-stu-id="46dcf-105">The intermediate dimension to which to join.</span></span> <span data-ttu-id="46dcf-106">A tale scopo, è possibile specificare una dimensione regolare o un'altra dimensione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="46dcf-106">This can be a regular dimension or another reference dimension.</span></span>  
  
-   <span data-ttu-id="46dcf-107">Un attributo della dimensione di riferimento che definisce il livello più basso in cui la dimensione è disponibile per l'aggregazione in relazione al gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="46dcf-107">A reference dimension attribute that defines the lowest level that the dimension is available for aggregation with regard to the measure group.</span></span>  
  
-   <span data-ttu-id="46dcf-108">L'attributo (chiave esterna) nella dimensione intermedia corrispondente all'attributo della dimensione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="46dcf-108">The (foreign key) attribute in the intermediate dimension that corresponds to the reference dimension attribute.</span></span>  
  
 <span data-ttu-id="46dcf-109">Si noti che la colonna che collega la dimensione di riferimento alla tabella dei fatti, che corrisponde in genere all'attributo chiave nella dimensione di riferimento, deve essere inoltre definita come attributo nella dimensione intermedia.</span><span class="sxs-lookup"><span data-stu-id="46dcf-109">Notice that the column that links the reference dimension to the fact table, which is generally the key attribute in the reference dimension, must also be defined as an attribute in the intermediate dimension.</span></span> <span data-ttu-id="46dcf-110">Quando si crea una catena di dimensioni di riferimento, creare innanzitutto la relazione di tipo Regolare tra la prima dimensione nella catena e il gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="46dcf-110">When you create a chain of reference dimensions, start by creating the regular relationship between the first dimension in the chain and the measure group.</span></span> <span data-ttu-id="46dcf-111">Creare quindi ogni ulteriore relazione di tipo Riferimento nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="46dcf-111">Then create each additional referenced relationship in order.</span></span> <span data-ttu-id="46dcf-112">È possibile creare una relazione di tipo Riferimento solo con una dimensione per la quale esiste una relazione con il gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="46dcf-112">A referenced relationship can only be made to a dimension that has an existing relationship to the measure group.</span></span>  
  
 <span data-ttu-id="46dcf-113">Quando si crea una relazione di tipo Riferimento, il collegamento dell'attributo della dimensione viene materializzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="46dcf-113">When you create a reference dimension relationship, the dimension attribute link is materialized by default.</span></span> <span data-ttu-id="46dcf-114">La materializzazione di un collegamento dell'attributo della dimensione determina la materializzazione o l'archiviazione del valore del collegamento tra la tabella dei fatti e la dimensione di riferimento per ogni riga nella struttura MOLAP della dimensione durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="46dcf-114">Materializing a dimension attribute link causes the value of the link between the fact table and the reference dimension for each row to be materialized, or stored, in the MOLAP structure for the dimension during processing.</span></span> <span data-ttu-id="46dcf-115">Ciò influisce in modo poco significativo sulle prestazioni di elaborazione e sui requisiti di archiviazione, ma determina un miglioramento delle prestazioni di esecuzione delle query.</span><span class="sxs-lookup"><span data-stu-id="46dcf-115">This will have a minor effect on processing performance and storage requirements, but will improve query performance.</span></span>  
  
 <span data-ttu-id="46dcf-116">In una dimensione di riferimento, la granularità viene specificata identificando l'attributo che definisce la relazione tra una dimensione di riferimento e il gruppo di misure corrispondente alla tabella principale della dimensione.</span><span class="sxs-lookup"><span data-stu-id="46dcf-116">In a reference dimension, granularity is specified by identifying the attribute that defines the relationship between a reference dimension and the measure group corresponding to the main table of the dimension.</span></span> <span data-ttu-id="46dcf-117">Quando più dimensioni di riferimento sono concatenate, i riferimenti definiscono la relazione dalla dimensione più esterna al gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="46dcf-117">When multiple reference dimensions are chained together, the references define the relationship from the outermost dimension to the measure group.</span></span>  
  
  
