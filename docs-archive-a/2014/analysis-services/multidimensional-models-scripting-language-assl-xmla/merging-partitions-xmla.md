---
title: Unione di partizioni (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- merging partitions [XMLA]
- XMLA, partitions
- partitions [Analysis Services], XML for Analysis
- XML for Analysis, partitions
ms.assetid: 657e1d4d-6d50-40f8-a771-7b20c9d865f8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 65840066d3e95571db511a2015a1bee64aa8d922
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627468"
---
# <a name="merging-partitions-xmla"></a><span data-ttu-id="7a0ea-102">Unione di partizioni (XMLA)</span><span class="sxs-lookup"><span data-stu-id="7a0ea-102">Merging Partitions (XMLA)</span></span>
  <span data-ttu-id="7a0ea-103">Se le partizioni hanno la stessa struttura e progettazione delle aggregazioni, è possibile unire la partizione usando il comando [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) in XML for Analysis (XMLA).</span><span class="sxs-lookup"><span data-stu-id="7a0ea-103">If partitions have the same aggregation design and structure, you can merge the partition by using the [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) command in XML for Analysis (XMLA).</span></span> <span data-ttu-id="7a0ea-104">L'unione è un'azione particolarmente importante da eseguire quando si gestiscono partizioni, soprattutto per le partizioni che contengono dati cronologici partizionati in base alla data.</span><span class="sxs-lookup"><span data-stu-id="7a0ea-104">Merging partitions is an important action to perform when you manage partitions, especially those partitions that contain historical data partitioned by date.</span></span>  
  
 <span data-ttu-id="7a0ea-105">Un cubo finanziario può utilizzare ad esempio due partizioni:</span><span class="sxs-lookup"><span data-stu-id="7a0ea-105">For example, a financial cube may use two partitions:</span></span>  
  
-   <span data-ttu-id="7a0ea-106">Una partizione rappresenta i dati finanziari per l'anno corrente utilizzando impostazioni di archiviazione OLAP relazionale (ROLAP) in tempo reale per motivi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7a0ea-106">One partition represents financial data for the current year, using real-time relational OLAP (ROLAP) storage settings for performance.</span></span>  
  
-   <span data-ttu-id="7a0ea-107">Un'altra partizione contiene dati finanziari per gli anni precedenti utilizzando impostazioni di archiviazione OLAP multidimensionale (MOLAP) per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="7a0ea-107">Another partition contains financial data for previous years, using multidimensional OLAP (MOLAP) storage settings for storage.</span></span>  
  
 <span data-ttu-id="7a0ea-108">Entrambe le partizioni utilizzano impostazioni di archiviazione diverse, ma la stessa progettazione delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="7a0ea-108">Both partitions use different storage settings, but use the same aggregation design.</span></span> <span data-ttu-id="7a0ea-109">Anziché elaborare il cubo attraverso anni di dati cronologici al termine dell'anno, è possibile utilizzare il comando `MergePartitions` per unire la partizione relativa all'anno corrente con quella relativa agli anni precedenti.</span><span class="sxs-lookup"><span data-stu-id="7a0ea-109">Instead of processing the cube across years of historical data at the end of the year, you can instead use the `MergePartitions` command to merge the partition for the current year into the partition for previous years.</span></span> <span data-ttu-id="7a0ea-110">In questo modo è possibile mantenere i dati aggregati senza che sia necessaria un'elaborazione completa del cubo che potrebbe richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="7a0ea-110">This preserves the aggregation data without requiring a potentially time-consuming full processing of the cube.</span></span>  
  
## <a name="specifying-partitions-to-merge"></a><span data-ttu-id="7a0ea-111">Specifica di partizioni da unire</span><span class="sxs-lookup"><span data-stu-id="7a0ea-111">Specifying Partitions to Merge</span></span>  
 <span data-ttu-id="7a0ea-112">Quando `MergePartitions` si esegue il comando, i dati di aggregazione archiviati nelle partizioni di origine specificate nella proprietà di [origine](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) vengono aggiunti alla partizione di destinazione specificata nella proprietà di [destinazione](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="7a0ea-112">When the `MergePartitions` command runs, the aggregation data stored in the source partitions specified in the [Source](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/source-element-xmla) property is added to the target partition specified in the [Target](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/target-element-xmla) property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a0ea-113">La proprietà `Source` può contenere più di un riferimento all'oggetto partizione,</span><span class="sxs-lookup"><span data-stu-id="7a0ea-113">The `Source` property can contain more than one partition object reference.</span></span> <span data-ttu-id="7a0ea-114">a differenza della proprietà `Target`.</span><span class="sxs-lookup"><span data-stu-id="7a0ea-114">However, the `Target` property cannot.</span></span>  
  
 <span data-ttu-id="7a0ea-115">Per essere unite, le partizioni specificate nelle proprietà `Source` e `Target` devono essere contenute dallo stesso gruppo di misure e devono utilizzare la stessa progettazione delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="7a0ea-115">To be successfully merged, the partitions specified in both the `Source` and `Target` must be contained by the same measure group and use the same aggregation design.</span></span> <span data-ttu-id="7a0ea-116">In caso contrario si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="7a0ea-116">Otherwise, an error occurs.</span></span>  
  
 <span data-ttu-id="7a0ea-117">Le partizioni specificate in `Source` vengono eliminate dopo che il comando `MergePartitions` è stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7a0ea-117">The partitions specified in the `Source` are deleted after the `MergePartitions` command is successfully completed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7a0ea-118">Esempi</span><span class="sxs-lookup"><span data-stu-id="7a0ea-118">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="7a0ea-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a0ea-119">Description</span></span>  
 <span data-ttu-id="7a0ea-120">Nell'esempio seguente vengono unite tutte le partizioni del gruppo di misure **Customer Counts** del cubo **Adventure Works** nel database di esempio **Adventure Works DW** nella [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] partizione **Customers_2004** .</span><span class="sxs-lookup"><span data-stu-id="7a0ea-120">The following example merges all the partitions in the **Customer Counts** measure group of the **Adventure Works** cube in the **Adventure Works DW** sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database into the **Customers_2004** partition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7a0ea-121">Codice</span><span class="sxs-lookup"><span data-stu-id="7a0ea-121">Code</span></span>  
  
```  
<MergePartitions xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  <Sources>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2001</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2002</PartitionID>  
    </Source>  
    <Source>  
      <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
      <CubeID>Adventure Works DW</CubeID>  
      <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
      <PartitionID>Internet_Sales_2003</PartitionID>  
    </Source>  
  </Sources>  
  <Target>  
    <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    <CubeID>Adventure Works DW</CubeID>  
    <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
    <PartitionID>Internet_Sales_2004</PartitionID>  
  </Target>  
</MergePartitions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a0ea-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a0ea-122">See Also</span></span>  
 [<span data-ttu-id="7a0ea-123">Sviluppo con XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7a0ea-123">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
