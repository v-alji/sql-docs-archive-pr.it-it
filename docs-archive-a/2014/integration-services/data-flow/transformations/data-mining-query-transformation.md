---
title: Trasformazione Query di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquerytrans.f1
helpviewer_keywords:
- Data Mining Query transformation
- prediction queries [Integration Services]
ms.assetid: 7960133b-a3e1-48af-ba43-55ed78c38e71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 278fdc3b1abd38b63f01e967e28d11983a09e682
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624276"
---
# <a name="data-mining-query-transformation"></a><span data-ttu-id="70610-102">Query di data mining - trasformazione</span><span class="sxs-lookup"><span data-stu-id="70610-102">Data Mining Query Transformation</span></span>
  <span data-ttu-id="70610-103">La trasformazione Query di data mining esegue query di stima basate su modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="70610-103">The Data Mining Query transformation performs prediction queries against data mining models.</span></span> <span data-ttu-id="70610-104">Questa trasformazione contiene un generatore di query per la creazione di query DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="70610-104">This transformation contains a query builder for creating Data Mining Extensions (DMX) queries.</span></span> <span data-ttu-id="70610-105">Il generatore di query consente di creare istruzioni personalizzate per la valutazione dei dati di input della trasformazione in base a un modello di data mining esistente, utilizzando il linguaggio DMX.</span><span class="sxs-lookup"><span data-stu-id="70610-105">The query builder lets you create custom statements for evaluating the transformation input data against an existing mining model using the DMX language.</span></span> <span data-ttu-id="70610-106">Per altre informazioni, vedere [Guida di riferimento a DMX &#40;Data Mining Extensions&#41;](/sql/dmx/data-mining-extensions-dmx-reference).</span><span class="sxs-lookup"><span data-stu-id="70610-106">For more information, see [Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference).</span></span>  
  
 <span data-ttu-id="70610-107">Una singola trasformazione può eseguire più query di stima, se i modelli sono compilati in base alla stessa struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="70610-107">One transformation can execute multiple prediction queries if the models are built on the same data mining structure.</span></span> <span data-ttu-id="70610-108">Per ulteriori informazioni, vedere [interfacce di query di data mining](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span><span class="sxs-lookup"><span data-stu-id="70610-108">For more information, see [Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools).</span></span>  
  
## <a name="configuration-of-the-data-mining-query-transformation"></a><span data-ttu-id="70610-109">Configurazione della trasformazione Query di data mining</span><span class="sxs-lookup"><span data-stu-id="70610-109">Configuration of the Data Mining Query Transformation</span></span>  
 <span data-ttu-id="70610-110">La trasformazione Query di data mining usa una gestione connessione [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] per connettersi al progetto di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] o all'istanza di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] che contiene la struttura e i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="70610-110">The Data Mining Query transformation uses an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] connection manager to connect to the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] project or the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that contains the mining structure and mining models.</span></span> <span data-ttu-id="70610-111">Per altre informazioni, vedere [Gestione connessione Analysis Services](../../connection-manager/analysis-services-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="70610-111">For more information, see [Analysis Services Connection Manager](../../connection-manager/analysis-services-connection-manager.md).</span></span>  
  
 <span data-ttu-id="70610-112">Questa trasformazione include un input e un output.</span><span class="sxs-lookup"><span data-stu-id="70610-112">This transformation has one input and one output.</span></span> <span data-ttu-id="70610-113">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="70610-113">It does not support an error output.</span></span>  
  
 <span data-ttu-id="70610-114">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="70610-114">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="70610-115">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Query di data mining** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="70610-115">For more information about the properties that you can set in the **Data Mining Query Transformation Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="70610-116">Editor trasformazione Query di data mining &#40;scheda Modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="70610-116">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
-   [<span data-ttu-id="70610-117">Editor trasformazione Query di data mining &#40;scheda Modello di data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="70610-117">Data Mining Query Transformation Editor &#40;Mining Model Tab&#41;</span></span>](../../data-mining-query-transformation-editor-mining-model-tab.md)  
  
 <span data-ttu-id="70610-118">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="70610-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="70610-119">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="70610-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="70610-120">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="70610-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="70610-121">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="70610-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="70610-122">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="70610-122">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
