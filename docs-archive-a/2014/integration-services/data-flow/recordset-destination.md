---
title: Destinazione recordset | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.recordsetdest.f1
helpviewer_keywords:
- Recordset destination
- ADO recordsets [Integration Services]
- destinations [Integration Services], Recordset
- in-memory ADO recordsets [Integration Services]
ms.assetid: be973cf1-c4ff-49f8-987e-314c08ef98e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1acc29c904e9020721e8ac62dff09a8ec29a392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626162"
---
# <a name="recordset-destination"></a><span data-ttu-id="a5be4-102">recordset - destinazione</span><span class="sxs-lookup"><span data-stu-id="a5be4-102">Recordset Destination</span></span>
  <span data-ttu-id="a5be4-103">La destinazione recordset crea e popola un recordset ADO in memoria.</span><span class="sxs-lookup"><span data-stu-id="a5be4-103">The Recordset destination creates and populates an in-memory ADO recordset.</span></span> <span data-ttu-id="a5be4-104">La forma del recordset è definita dall'input della destinazione recordset in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a5be4-104">The shape of the recordset is defined by the input to the Recordset destination at design time.</span></span>  
  
## <a name="configuration-of-the-recordset-destination"></a><span data-ttu-id="a5be4-105">Configurazione della destinazione recordset</span><span class="sxs-lookup"><span data-stu-id="a5be4-105">Configuration of the Recordset Destination</span></span>  
 <span data-ttu-id="a5be4-106">Per configurare la destinazione recordset, è necessario specificare la variabile in cui è memorizzato il recordset ADO.</span><span class="sxs-lookup"><span data-stu-id="a5be4-106">You configure the Recordset destination by specifying the variable that stores the ADO recordset.</span></span>  
  
 <span data-ttu-id="a5be4-107">In fase di esecuzione, nella variabile di tipo Oggetto, specificata nella proprietà VariableName della destinazione recordset, viene scritto un recordset ADO.</span><span class="sxs-lookup"><span data-stu-id="a5be4-107">At run time, an ADO recordset is written to the variable of type, Object, that is specified in the VariableName property of the Recordset destination.</span></span> <span data-ttu-id="a5be4-108">La variabile rende quindi disponibile il recordset all'esterno del flusso di dati, dove può essere utilizzato da script e altri elementi del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a5be4-108">The variable then makes the Recordset available outside the data flow, where it can be used by scripts and other package elements.</span></span>  
  
 <span data-ttu-id="a5be4-109">Questa origine include un solo input.</span><span class="sxs-lookup"><span data-stu-id="a5be4-109">This source has one input.</span></span> <span data-ttu-id="a5be4-110">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="a5be4-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="a5be4-111">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="a5be4-111">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="a5be4-112">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="a5be4-112">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="a5be4-113">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a5be4-113">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a5be4-114">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="a5be4-114">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="a5be4-115">Proprietà personalizzate della destinazione recordset</span><span class="sxs-lookup"><span data-stu-id="a5be4-115">Recordset Destination Custom Properties</span></span>](recordset-destination-custom-properties.md)  
  
 <span data-ttu-id="a5be4-116">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a5be4-116">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a5be4-117">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="a5be4-117">Related Tasks</span></span>  
 [<span data-ttu-id="a5be4-118">Usare una destinazione recordset</span><span class="sxs-lookup"><span data-stu-id="a5be4-118">Use a Recordset Destination</span></span>](recordset-destination.md)  
  
  
