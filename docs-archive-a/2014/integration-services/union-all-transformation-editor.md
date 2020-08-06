---
title: Editor trasformazione Unione input multipli | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltransformation.f1
helpviewer_keywords:
- Union All Transformation Editor
ms.assetid: 32fbc1c1-da83-4684-9479-31fc3e2df98c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7e84c106767aa897b2e419b51ca5b5c538501cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625447"
---
# <a name="union-all-transformation-editor"></a><span data-ttu-id="c8157-102">Editor trasformazione Unione input multipli</span><span class="sxs-lookup"><span data-stu-id="c8157-102">Union All Transformation Editor</span></span>
  <span data-ttu-id="c8157-103">Utilizzare la finestra di dialogo **Editor trasformazione Unione input multipli** per unire diversi set di righe di input in un unico set di righe di output.</span><span class="sxs-lookup"><span data-stu-id="c8157-103">Use the **Union All Transformation Editor** dialog box to merge several input rowsets into a single output rowset.</span></span> <span data-ttu-id="c8157-104">Includendo la trasformazione Unione input multipli in un flusso di dati è possibile unire dati tratti da più flussi di dati, creare set di dati complessi nidificando più trasformazioni Unione input multipli e unire nuovamente le righe dopo la correzione degli errori nei dati.</span><span class="sxs-lookup"><span data-stu-id="c8157-104">By including the Union All transformation in a data flow, you can merge data from multiple data flows, create complex datasets by nesting Union All transformations, and re-merge rows after you correct errors in the data.</span></span>  
  
 <span data-ttu-id="c8157-105">Per ulteriori informazioni sulla trasformazione Unione input multipli, vedere [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c8157-105">To learn more about the Union All transformation, see [Union All Transformation](data-flow/transformations/union-all-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c8157-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c8157-106">Options</span></span>  
 <span data-ttu-id="c8157-107">**Nome colonna di output**</span><span class="sxs-lookup"><span data-stu-id="c8157-107">**Output Column Name**</span></span>  
 <span data-ttu-id="c8157-108">Consente di digitare un alias per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="c8157-108">Type an alias for each column.</span></span> <span data-ttu-id="c8157-109">Per impostazione predefinita, viene suggerito il nome della colonna del primo input, ovvero l'input di riferimento. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="c8157-109">The default is the name of the input column from the first (reference) input; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="c8157-110">**Input unione input multipli 1**</span><span class="sxs-lookup"><span data-stu-id="c8157-110">**Union All Input 1**</span></span>  
 <span data-ttu-id="c8157-111">Consente di selezionare nell'elenco di colonne di input disponibili nel primo input, ovvero l'input di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c8157-111">Select from the list of available input columns in the first (reference) input.</span></span> <span data-ttu-id="c8157-112">I metadati delle colonne mappate devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="c8157-112">The metadata of mapped columns must match.</span></span>  
  
 <span data-ttu-id="c8157-113">**Input unione input multipli n**</span><span class="sxs-lookup"><span data-stu-id="c8157-113">**Union All Input n**</span></span>  
 <span data-ttu-id="c8157-114">Consente di selezionare nell'elenco di colonne di input disponibili nel secondo input e negli input aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c8157-114">Select from the list of available input columns in the second and additional inputs.</span></span> <span data-ttu-id="c8157-115">I metadati delle colonne mappate devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="c8157-115">The metadata of mapped columns must match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8157-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8157-116">See Also</span></span>  
 <span data-ttu-id="c8157-117">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c8157-117">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c8157-118">[Unione di dati tramite la trasformazione Unione input multipli](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="c8157-118">[Merge Data by Using the Union All Transformation](data-flow/transformations/merge-data-by-using-the-union-all-transformation.md) </span></span>  
 <span data-ttu-id="c8157-119">[Trasformazione Unione](data-flow/transformations/merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="c8157-119">[Merge Transformation](data-flow/transformations/merge-transformation.md) </span></span>  
 [<span data-ttu-id="c8157-120">Trasformazione Merge join</span><span class="sxs-lookup"><span data-stu-id="c8157-120">Merge Join Transformation</span></span>](data-flow/transformations/merge-join-transformation.md)  
  
  
