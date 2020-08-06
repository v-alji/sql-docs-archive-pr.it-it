---
title: Trasformazione UnPivot | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unpivottrans.f1
helpviewer_keywords:
- Unpivot transformation
- more normalized data set [Integration Services]
- normalized data [Integration Services]
- datasets [Integration Services], normalized data
ms.assetid: f635c64b-a9c5-4f11-9c40-9cd9d5298c5d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e605dc4827a885b5dc65fbb680cce8a434b89fd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636292"
---
# <a name="unpivot-transformation"></a><span data-ttu-id="acc3b-102">UnPivot - trasformazione</span><span class="sxs-lookup"><span data-stu-id="acc3b-102">Unpivot Transformation</span></span>
  <span data-ttu-id="acc3b-103">La trasformazione tramite UnPivot consente di trasformare un set di dati non normalizzato in una versione più normalizzata, espandendo valori di più colonne contenuti in un singolo record in più record con gli stessi valori in un'unica colonna.</span><span class="sxs-lookup"><span data-stu-id="acc3b-103">The Unpivot transformation makes an unnormalized dataset into a more normalized version by expanding values from multiple columns in a single record into multiple records with the same values in a single column.</span></span> <span data-ttu-id="acc3b-104">Si consideri ad esempio un set di dati che elenca i nomi dei clienti e include una riga per ogni cliente, ognuna contenente colonne in cui sono indicati i prodotti e le quantità acquistati.</span><span class="sxs-lookup"><span data-stu-id="acc3b-104">For example, a dataset that lists customer names has one row for each customer, with the products and the quantity purchased shown in columns in the row.</span></span> <span data-ttu-id="acc3b-105">Dopo la normalizzazione del set di dati tramite la trasformazione UnPivot, il set di dati conterrà una riga per ogni prodotto acquistato dal cliente.</span><span class="sxs-lookup"><span data-stu-id="acc3b-105">After the Unpivot transformation normalizes the data set, the data set contains a different row for each product that the customer purchased.</span></span>  
  
 <span data-ttu-id="acc3b-106">Nella figura seguente viene illustrato un set di dati prima della trasformazione tramite UnPivot in base alla colonna Product.</span><span class="sxs-lookup"><span data-stu-id="acc3b-106">The following diagram shows a data set before the data is unpivoted on the Product column.</span></span>  
  
 <span data-ttu-id="acc3b-107">![Set di dati dopo la trasformazione tramite UnPivot](../../media/mw-dts-18.gif "Set di dati dopo la trasformazione tramite UnPivot")</span><span class="sxs-lookup"><span data-stu-id="acc3b-107">![Dataset after it is unpivoted](../../media/mw-dts-18.gif "Dataset after it is unpivoted")</span></span>  
  
 <span data-ttu-id="acc3b-108">Nella figura seguente viene illustrato un set di dati dopo la trasformazione tramite UnPivot in base alla colonna Product.</span><span class="sxs-lookup"><span data-stu-id="acc3b-108">The following diagram shows a data set after it has been unpivoted on the Product column.</span></span>  
  
 <span data-ttu-id="acc3b-109">![Set di dati prima della trasformazione tramite UnPivot](../../media/mw-dts-17.gif "Set di dati prima della trasformazione tramite UnPivot")</span><span class="sxs-lookup"><span data-stu-id="acc3b-109">![Dataset before it is unpivoted](../../media/mw-dts-17.gif "Dataset before it is unpivoted")</span></span>  
  
 <span data-ttu-id="acc3b-110">In alcuni casi, i risultati della trasformazione tramite UnPivot possono contenere righe con valori imprevisti.</span><span class="sxs-lookup"><span data-stu-id="acc3b-110">Under some circumstances, the unpivot results may contain rows with unexpected values.</span></span> <span data-ttu-id="acc3b-111">Se i dati di esempio da trasformare tramite UnPivot illustrati nel diagramma contenessero valori Null in tutte le colonne Qty per Fred, l'output conterrebbe solo una riga per Fred e non cinque.</span><span class="sxs-lookup"><span data-stu-id="acc3b-111">For example, if the sample data to unpivot shown in the diagram had null values in all the Qty columns for Fred, then the output would include only one row for Fred, not five.</span></span> <span data-ttu-id="acc3b-112">La colonna Qty conterrebbe valori Null oppure zero, in base al tipo di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="acc3b-112">The Qty column would contain either null or zero, depending on the column data type.</span></span>  
  
## <a name="configuration-of-the-unpivot-transformation"></a><span data-ttu-id="acc3b-113">Configurazione della trasformazione UnPivot</span><span class="sxs-lookup"><span data-stu-id="acc3b-113">Configuration of the Unpivot Transformation</span></span>  
 <span data-ttu-id="acc3b-114">La trasformazione UnPivot include la proprietà personalizzata `PivotKeyValue`,</span><span class="sxs-lookup"><span data-stu-id="acc3b-114">The Unpivot transformation includes the `PivotKeyValue` custom property.</span></span> <span data-ttu-id="acc3b-115">che può essere aggiornata da un'espressione di proprietà al caricamento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="acc3b-115">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="acc3b-116">Per altre informazioni, vedere [Espressioni di Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Utilizzo delle espressioni di proprietà nei pacchetti](../../expressions/use-property-expressions-in-packages.md) e [Proprietà personalizzate delle trasformazioni](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="acc3b-116">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="acc3b-117">Questa trasformazione include un input e un output.</span><span class="sxs-lookup"><span data-stu-id="acc3b-117">This transformation has one input and one output.</span></span> <span data-ttu-id="acc3b-118">Non include alcun output degli errori.</span><span class="sxs-lookup"><span data-stu-id="acc3b-118">It has no error output.</span></span>  
  
 <span data-ttu-id="acc3b-119">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="acc3b-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="acc3b-120">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione UnPivot** , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="acc3b-120">For more information about the properties that you can set in the **Unpivot Transformation Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="acc3b-121">Editor trasformazione UnPivot</span><span class="sxs-lookup"><span data-stu-id="acc3b-121">Unpivot Transformation Editor</span></span>](../../unpivot-transformation-editor.md)  
  
 <span data-ttu-id="acc3b-122">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="acc3b-122">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="acc3b-123">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="acc3b-123">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="acc3b-124">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="acc3b-124">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="acc3b-125">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="acc3b-125">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
