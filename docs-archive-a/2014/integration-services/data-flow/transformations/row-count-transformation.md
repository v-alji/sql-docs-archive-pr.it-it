---
title: Trasformazione Conteggio righe | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rowcounttrans.f1
helpviewer_keywords:
- updating variables
- Row Count transformation
- number of rows
- variables [Integration Services], updating
- counting rows
ms.assetid: b68293b9-a68c-40be-9d81-77342da1be29
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b0940d608aeaa96b7ec43fa4486944ce0f887e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727092"
---
# <a name="row-count-transformation"></a><span data-ttu-id="4ce4d-102">Conteggio righe - trasformazione</span><span class="sxs-lookup"><span data-stu-id="4ce4d-102">Row Count Transformation</span></span>
  <span data-ttu-id="4ce4d-103">La trasformazione Conteggio righe consente di contare le righe che passano attraverso un flusso di dati e di memorizzare il totale in una variabile.</span><span class="sxs-lookup"><span data-stu-id="4ce4d-103">The Row Count transformation counts rows as they pass through a data flow and stores the final count in a variable.</span></span>  
  
 <span data-ttu-id="4ce4d-104">Un pacchetto di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] può usare i conteggi delle righe per aggiornare le variabili usate in script, espressioni ed espressioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="4ce4d-104">A [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package can use row counts to update the variables used in scripts, expressions, and property expressions.</span></span> <span data-ttu-id="4ce4d-105">È ad esempio possibile utilizzare la variabile che contiene il numero delle righe per aggiornare il testo di un messaggio di posta elettronica in modo che includa il numero delle righe. La variabile utilizzata dalla trasformazione Conteggio righe deve esistere e trovarsi nell'ambito dell'attività Flusso di dati a cui appartiene il flusso di dati con la trasformazione Conteggio righe.</span><span class="sxs-lookup"><span data-stu-id="4ce4d-105">(For example, the variable that stores the row count can update the message text in an e-mail message to include the number of rows.) The variable that the Row Count transformation uses must already exist, and it must be in the scope of the Data Flow task to which the data flow with the Row Count transformation belongs.</span></span>  
  
 <span data-ttu-id="4ce4d-106">La trasformazione archivia nella variabile il valore relativo al numero delle righe solo dopo il passaggio dell'ultima riga attraverso la trasformazione.</span><span class="sxs-lookup"><span data-stu-id="4ce4d-106">The transformation stores the row count value in the variable only after the last row has passed through the transformation.</span></span> <span data-ttu-id="4ce4d-107">Il valore della variabile non viene pertanto aggiornato in tempo per essere utilizzato nel flusso di dati che contiene la trasformazione Conteggio righe.</span><span class="sxs-lookup"><span data-stu-id="4ce4d-107">Therefore, the value of the variable is not updated in time to use the updated value in the data flow that contains the Row Count transformation.</span></span> <span data-ttu-id="4ce4d-108">È possibile utilizzare la variabile aggiornata in un flusso di dati separato.</span><span class="sxs-lookup"><span data-stu-id="4ce4d-108">You can use the updated variable in a separate data flow.</span></span>  
  
 <span data-ttu-id="4ce4d-109">Questa trasformazione include un input e un output.</span><span class="sxs-lookup"><span data-stu-id="4ce4d-109">This transformation has one input and one output.</span></span> <span data-ttu-id="4ce4d-110">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="4ce4d-110">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-row-count-transformation"></a><span data-ttu-id="4ce4d-111">Configurazione della trasformazione Conteggio righe</span><span class="sxs-lookup"><span data-stu-id="4ce4d-111">Configuration of the Row Count Transformation</span></span>  
 <span data-ttu-id="4ce4d-112">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="4ce4d-112">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4ce4d-113">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="4ce4d-113">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="4ce4d-114">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ce4d-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="4ce4d-115">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="4ce4d-115">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="4ce4d-116">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="4ce4d-116">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="4ce4d-117">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="4ce4d-117">Related Tasks</span></span>  
 <span data-ttu-id="4ce4d-118">Per informazioni su come impostare le proprietà del componente, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="4ce4d-118">For information about how to set the properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ce4d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ce4d-119">See Also</span></span>  
 <span data-ttu-id="4ce4d-120">[Variabili di Integration Services &#40;SSIS&#41;](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="4ce4d-120">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="4ce4d-121">[Flusso di dati](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="4ce4d-121">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="4ce4d-122">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="4ce4d-122">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
