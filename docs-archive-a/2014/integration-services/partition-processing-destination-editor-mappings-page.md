---
title: Editor destinazione elaborazione partizione (pagina mapping) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.partprocessingtransformation.mapping.f1
helpviewer_keywords:
- Partition Processing Destination Editor
ms.assetid: e75b766c-85ba-453e-9576-4a1a34f91ecc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3855b15c7ebf1f6fa95c941931869064d552680e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636786"
---
# <a name="partition-processing-destination-editor-mappings-page"></a><span data-ttu-id="a76d6-102">Editor destinazione elaborazione partizione (pagina Mapping)</span><span class="sxs-lookup"><span data-stu-id="a76d6-102">Partition Processing Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="a76d6-103">Utilizzare la pagina **Mapping** della finestra di dialogo **Editor destinazione elaborazione partizione** per eseguire il mapping tra le colonne di input e le colonne di partizione.</span><span class="sxs-lookup"><span data-stu-id="a76d6-103">Use the **Mappings** page of the **Partition Processing Destination Editor** dialog box to map input columns to partition columns.</span></span>  
  
 <span data-ttu-id="a76d6-104">Per ulteriori informazioni sulla destinazione elaborazione partizione, vedere [Partition Processing Destination](data-flow/partition-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a76d6-104">To learn more abou the Partition Processing destination, see [Partition Processing Destination](data-flow/partition-processing-destination.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a76d6-105">Le attività qui descritte non si applicano ai modelli tabulari di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="a76d6-105">Tasks described here do not apply to Analysis Services tabular models.</span></span>  <span data-ttu-id="a76d6-106">Non è possibile eseguire il mapping di colonne di input a colonne di partizione per i modelli tabulari.</span><span class="sxs-lookup"><span data-stu-id="a76d6-106">You cannot map input columns to partition columns for tabular models.</span></span> <span data-ttu-id="a76d6-107">È possibile utilizzare invece l'attività Esegui DDL Analysis Services [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) per elaborare la partizione.</span><span class="sxs-lookup"><span data-stu-id="a76d6-107">You can instead use the Analysis Services Execute DDL task [Analysis Services Execute DDL Task](control-flow/analysis-services-execute-ddl-task.md) to process the partition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a76d6-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a76d6-108">Options</span></span>  
 <span data-ttu-id="a76d6-109">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="a76d6-109">**Available Input Columns**</span></span>  
 <span data-ttu-id="a76d6-110">Consente di visualizzare l'elenco delle colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="a76d6-110">View the list of available input columns.</span></span> <span data-ttu-id="a76d6-111">Eseguire un'operazione di trascinamento della selezione per impostare il mapping tra le colonne di input disponibili nella tabella e le colonne di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a76d6-111">Use a drag-and-drop operation to map available input columns in the table to destination columns.</span></span>  
  
 <span data-ttu-id="a76d6-112">**Colonne di destinazione disponibili**</span><span class="sxs-lookup"><span data-stu-id="a76d6-112">**Available Destination Columns**</span></span>  
 <span data-ttu-id="a76d6-113">Consente di visualizzare l'elenco delle colonne di destinazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="a76d6-113">View the list of available destination columns.</span></span> <span data-ttu-id="a76d6-114">Eseguire un'operazione di trascinamento della selezione per impostare il mapping tra le colonne di destinazione disponibili nella tabella e le colonne di input.</span><span class="sxs-lookup"><span data-stu-id="a76d6-114">Use a drag-and-drop operation to map available destination columns in the table to input columns.</span></span>  
  
 <span data-ttu-id="a76d6-115">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="a76d6-115">**Input Column**</span></span>  
 <span data-ttu-id="a76d6-116">Consente di visualizzare le colonne di input selezionate nella tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="a76d6-116">View input columns selected from the table above.</span></span> <span data-ttu-id="a76d6-117">È possibile modificare i mapping utilizzando l'elenco **Colonne di input disponibili**.</span><span class="sxs-lookup"><span data-stu-id="a76d6-117">You can change the mappings by using the list of **Available Input Columns**.</span></span>  
  
 <span data-ttu-id="a76d6-118">**Colonna di destinazione**</span><span class="sxs-lookup"><span data-stu-id="a76d6-118">**Destination Column**</span></span>  
 <span data-ttu-id="a76d6-119">Consente di visualizzare tutte le colonne di destinazione disponibili, indipendentemente dal fatto che siano mappate o meno.</span><span class="sxs-lookup"><span data-stu-id="a76d6-119">View each available destination column, whether it is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76d6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a76d6-120">See Also</span></span>  
 <span data-ttu-id="a76d6-121">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a76d6-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a76d6-122">[Editor destinazione elaborazione partizione &#40;pagina Gestione connessione&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a76d6-122">[Partition Processing Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/partition-processing-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="a76d6-123">Editor destinazione elaborazione partizione &#40;pagina Avanzate&#41;</span><span class="sxs-lookup"><span data-stu-id="a76d6-123">Partition Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/partition-processing-destination-editor-advanced-page.md)  
  
  
