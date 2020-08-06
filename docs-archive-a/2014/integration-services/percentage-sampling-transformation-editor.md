---
title: Editor trasformazione Campionamento percentuale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.percentagesamplingtransformation.f1
helpviewer_keywords:
- Percentage Sampling Transformation Editor
ms.assetid: 2c40d804-26a3-4d35-809b-bc923d83d451
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c4dbd96ab952b6c88bdaa7bf56a0a2f1b3585c57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624798"
---
# <a name="percentage-sampling-transformation-editor"></a><span data-ttu-id="47df1-102">Editor trasformazione Campionamento percentuale</span><span class="sxs-lookup"><span data-stu-id="47df1-102">Percentage Sampling Transformation Editor</span></span>
  <span data-ttu-id="47df1-103">Utilizzare la finestra di dialogo **Editor trasformazione Campionamento percentuale** per dividere parte di un input in un campione utilizzando la percentuale di righe specificata.</span><span class="sxs-lookup"><span data-stu-id="47df1-103">Use the **Percentage Sampling Transformation Editor** dialog box to split part of an input into a sample using a specified percentage of rows.</span></span> <span data-ttu-id="47df1-104">La trasformazione divide l'input in due output separati.</span><span class="sxs-lookup"><span data-stu-id="47df1-104">This transformation divides the input into two separate outputs.</span></span>  
  
 <span data-ttu-id="47df1-105">Per ulteriori informazioni sulla trasformazione Campionamento percentuale, vedere [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="47df1-105">To learn more about the percentage sampling transformation, see [Percentage Sampling Transformation](data-flow/transformations/percentage-sampling-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="47df1-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="47df1-106">Options</span></span>  
 <span data-ttu-id="47df1-107">**Percentuale di righe**</span><span class="sxs-lookup"><span data-stu-id="47df1-107">**Percentage of rows**</span></span>  
 <span data-ttu-id="47df1-108">Consente di specificare la percentuale di righe dell'input da utilizzare come campione.</span><span class="sxs-lookup"><span data-stu-id="47df1-108">Specify the percentage of rows in the input to use as a sample.</span></span>  
  
 <span data-ttu-id="47df1-109">È possibile specificare il valore di questa proprietà tramite un'espressione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="47df1-109">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="47df1-110">**Nome output campione**</span><span class="sxs-lookup"><span data-stu-id="47df1-110">**Sample output name**</span></span>  
 <span data-ttu-id="47df1-111">Consente di specificare un nome univoco per l'output che includerà le righe campionate.</span><span class="sxs-lookup"><span data-stu-id="47df1-111">Provide a unique name for the output that will include the sampled rows.</span></span> <span data-ttu-id="47df1-112">Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="47df1-112">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="47df1-113">**Nome output non selezionato**</span><span class="sxs-lookup"><span data-stu-id="47df1-113">**Unselected output name**</span></span>  
 <span data-ttu-id="47df1-114">Consente di specificare un nome univoco per l'output che conterrà le righe escluse dal campionamento.</span><span class="sxs-lookup"><span data-stu-id="47df1-114">Provide a unique name for the output that will contain the rows excluded from the sampling.</span></span> <span data-ttu-id="47df1-115">Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="47df1-115">The name provided will be displayed within the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="47df1-116">**Usa il valore di inizializzazione casuale seguente**</span><span class="sxs-lookup"><span data-stu-id="47df1-116">**Use the following random seed**</span></span>  
 <span data-ttu-id="47df1-117">Consente di specificare il valore di inizializzazione del campionamento per il generatore di numeri casuali utilizzato dalla trasformazione per creare un campione.</span><span class="sxs-lookup"><span data-stu-id="47df1-117">Specify the sampling seed for the random number generator that the transformation uses to create a sample.</span></span> <span data-ttu-id="47df1-118">È consigliato solo a scopo di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="47df1-118">This is only recommended for development and testing.</span></span> <span data-ttu-id="47df1-119">Se non viene specificato alcun valore di inizializzazione casuale, la trasformazione utilizza il conteggio tick di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="47df1-119">The transformation uses the Microsoft Windows tick count if a random seed is not specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47df1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47df1-120">See Also</span></span>  
 <span data-ttu-id="47df1-121">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="47df1-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="47df1-122">Trasformazione Campionamento righe</span><span class="sxs-lookup"><span data-stu-id="47df1-122">Row Sampling Transformation</span></span>](data-flow/transformations/row-sampling-transformation.md)  
  
  
