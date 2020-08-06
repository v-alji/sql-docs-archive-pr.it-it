---
title: Trasformazione Multicast | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multicasttrans.f1
helpviewer_keywords:
- multiple outputs
- Multicast transformation
- datasets [Integration Services], multiple outputs
- multiple transformations
ms.assetid: 32194784-1684-40cd-9f91-1aba4d8360d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7b5c0a38c966c89f426a213f302b45c390b77cfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727107"
---
# <a name="multicast-transformation"></a><span data-ttu-id="0c47e-102">Multicast - trasformazione</span><span class="sxs-lookup"><span data-stu-id="0c47e-102">Multicast Transformation</span></span>
  <span data-ttu-id="0c47e-103">La trasformazione Multicast distribuisce il proprio input a uno o più output.</span><span class="sxs-lookup"><span data-stu-id="0c47e-103">The Multicast transformation distributes its input to one or more outputs.</span></span> <span data-ttu-id="0c47e-104">Questa trasformazione è simile alla trasformazione Suddivisione condizionale.</span><span class="sxs-lookup"><span data-stu-id="0c47e-104">This transformation is similar to the Conditional Split transformation.</span></span> <span data-ttu-id="0c47e-105">Entrambe le trasformazioni dirigono uno stesso input verso più output,</span><span class="sxs-lookup"><span data-stu-id="0c47e-105">Both transformations direct an input to multiple outputs.</span></span> <span data-ttu-id="0c47e-106">ma la trasformazione Multicast dirige tutte le righe verso tutti gli output, mentre la trasformazione Suddivisione condizionale dirige una riga a un singolo output.</span><span class="sxs-lookup"><span data-stu-id="0c47e-106">The difference between the two is that the Multicast transformation directs every row to every output, and the Conditional Split directs a row to a single output.</span></span> <span data-ttu-id="0c47e-107">Per altre informazioni, vedere [Trasformazione Suddivisione condizionale](conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="0c47e-107">For more information, see [Conditional Split Transformation](conditional-split-transformation.md).</span></span>  
  
 <span data-ttu-id="0c47e-108">Per configurare la trasformazione Multicast, è necessario aggiungere gli output.</span><span class="sxs-lookup"><span data-stu-id="0c47e-108">You configure the Multicast transformation by adding outputs.</span></span>  
  
 <span data-ttu-id="0c47e-109">Tramite la trasformazione Multicast un pacchetto può creare copie logiche dei dati.</span><span class="sxs-lookup"><span data-stu-id="0c47e-109">Using the Multicast transformation, a package can create logical copies of data.</span></span> <span data-ttu-id="0c47e-110">Questa funzionalità è utile quando il pacchetto deve applicare più set di trasformazioni agli stessi dati.</span><span class="sxs-lookup"><span data-stu-id="0c47e-110">This capability is useful when the package needs to apply multiple sets of transformations to the same data.</span></span> <span data-ttu-id="0c47e-111">È ad esempio possibile aggregare una copia dei dati e caricare nella relativa destinazione solo le informazioni di riepilogo, mentre un'altra copia dei dati viene estesa con valori di ricerca e colonne derivate prima di caricarla nella relativa destinazione.</span><span class="sxs-lookup"><span data-stu-id="0c47e-111">For example, one copy of the data is aggregated and only the summary information is loaded into its destination, while another copy of the data is extended with lookup values and derived columns before it is loaded into its destination.</span></span>  
  
 <span data-ttu-id="0c47e-112">Questa trasformazione include un input e più output.</span><span class="sxs-lookup"><span data-stu-id="0c47e-112">This transformation has one input and multiple outputs.</span></span> <span data-ttu-id="0c47e-113">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="0c47e-113">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-multicast-transformation"></a><span data-ttu-id="0c47e-114">Configurazione della trasformazione Multicast</span><span class="sxs-lookup"><span data-stu-id="0c47e-114">Configuration of the Multicast Transformation</span></span>  
 <span data-ttu-id="0c47e-115">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="0c47e-115">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="0c47e-116">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Multicast** , vedere [Editor trasformazione Multicast](../../multicast-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="0c47e-116">For information about the properties that you can set in the **Multicast Transformation Editor** dialog box, see [Multicast Transformation Editor](../../multicast-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="0c47e-117">Per informazioni sulle proprietà che è possibile impostare a livello di codice, vedere [Proprietà comuni](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0c47e-117">For information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="0c47e-118">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="0c47e-118">Related Tasks</span></span>  
 <span data-ttu-id="0c47e-119">Per informazioni su come impostare le proprietà del componente, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="0c47e-119">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c47e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c47e-120">See Also</span></span>  
 <span data-ttu-id="0c47e-121">[Flusso di dati](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="0c47e-121">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="0c47e-122">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="0c47e-122">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
