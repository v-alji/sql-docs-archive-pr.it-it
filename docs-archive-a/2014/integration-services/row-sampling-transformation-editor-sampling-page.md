---
title: Editor trasformazione Campionamento righe (pagina campionamento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.ROWSAMPLINGTRANSFORMATION.COLUMNS.F1
- sql12.dts.designer.rowsamplingtransformation.f1
helpviewer_keywords:
- Row Sampling Transformation Editor
ms.assetid: 544c7709-6de0-4c08-bda3-759985be9a05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 26d0c0439e548172225f02220d8f6814a1168ea9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713260"
---
# <a name="row-sampling-transformation-editor-sampling-page"></a><span data-ttu-id="c6800-102">Editor trasformazione Campionamento righe (pagina Campionamento)</span><span class="sxs-lookup"><span data-stu-id="c6800-102">Row Sampling Transformation Editor (Sampling Page)</span></span>
  <span data-ttu-id="c6800-103">Utilizzare la finestra di dialogo **Editor trasformazione Campionamento righe** per dividere parte di un input in un campione utilizzando il numero di righe specificato.</span><span class="sxs-lookup"><span data-stu-id="c6800-103">Use the **Row Sampling Transformation Editor** dialog box to split a portion of an input into a sample using a specified number of rows.</span></span> <span data-ttu-id="c6800-104">La trasformazione divide l'input in due output separati.</span><span class="sxs-lookup"><span data-stu-id="c6800-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="c6800-105">Per ulteriori informazioni sulla trasformazione Campionamento righe, vedere [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c6800-105">To learn more about the Row Sampling transformation, see [Row Sampling Transformation](data-flow/transformations/row-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c6800-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c6800-106">Options</span></span>  
 <span data-ttu-id="c6800-107">**Numero di righe**</span><span class="sxs-lookup"><span data-stu-id="c6800-107">**Number of rows**</span></span>  
 <span data-ttu-id="c6800-108">Consente di specificare il numero di righe dell'input da utilizzare come campione.</span><span class="sxs-lookup"><span data-stu-id="c6800-108">Specify the number of rows from the input to use as a sample.</span></span>  
  
 <span data-ttu-id="c6800-109">È possibile specificare il valore di questa proprietà tramite un'espressione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="c6800-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="c6800-110">**Nome output campione**</span><span class="sxs-lookup"><span data-stu-id="c6800-110">**Sample output name**</span></span>  
 <span data-ttu-id="c6800-111">Consente di specificare un nome univoco per l'output che includerà le righe campionate.</span><span class="sxs-lookup"><span data-stu-id="c6800-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="c6800-112">Il nome specificato verrà visualizzato in Progettazione SSIS.</span><span class="sxs-lookup"><span data-stu-id="c6800-112">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="c6800-113">**Nome output non selezionato**</span><span class="sxs-lookup"><span data-stu-id="c6800-113">**Unselected output name**</span></span>  
 <span data-ttu-id="c6800-114">Consente di specificare un nome univoco per l'output che conterrà le righe escluse dal campionamento.</span><span class="sxs-lookup"><span data-stu-id="c6800-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="c6800-115">Il nome specificato verrà visualizzato in Progettazione SSIS.</span><span class="sxs-lookup"><span data-stu-id="c6800-115">The name provided will be displayed within SSIS Designer.</span></span>  
  
 <span data-ttu-id="c6800-116">**Usa il valore di inizializzazione casuale seguente**</span><span class="sxs-lookup"><span data-stu-id="c6800-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="c6800-117">Consente di specificare il valore di inizializzazione del campionamento per il generatore di numeri casuali utilizzato dalla trasformazione per creare un campione.</span><span class="sxs-lookup"><span data-stu-id="c6800-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="c6800-118">È consigliato solo a scopo di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="c6800-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="c6800-119">Se non viene specificato alcun valore di inizializzazione casuale, la trasformazione utilizza il conteggio tick di Microsoft Windows come valore di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="c6800-119">The transformation uses the Microsoft Windows tick count as a seed if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6800-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6800-120">See Also</span></span>  
 <span data-ttu-id="c6800-121">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c6800-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="c6800-122">Trasformazione Campionamento percentuale</span><span class="sxs-lookup"><span data-stu-id="c6800-122">Percentage Sampling Transformation</span></span>](data-flow/transformations/percentage-sampling-transformation.md)  
  
  
