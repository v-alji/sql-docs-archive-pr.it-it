---
title: Copia colonna - trasformazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copycolumntrans.f1
helpviewer_keywords:
- columns [Integration Services], copying
- copying columns
- Copy Column transformation
ms.assetid: 1c72a313-9026-46bc-a57f-c6b3f47346f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fd2745070a92ab71e89f3bfa9edd8673b676632b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629944"
---
# <a name="copy-column-transformation"></a><span data-ttu-id="cf2ea-102">Copia colonna - trasformazione</span><span class="sxs-lookup"><span data-stu-id="cf2ea-102">Copy Column Transformation</span></span>
  <span data-ttu-id="cf2ea-103">La trasformazione Copia colonna consente di creare nuove colonne copiando le colonne di input e aggiungendo le nuove colonne all'output della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="cf2ea-103">The Copy Column transformation creates new columns by copying input columns and adding the new columns to the transformation output.</span></span> <span data-ttu-id="cf2ea-104">Successivamente nel flusso di dati alle copie delle colonne sarà possibile applicare altre trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="cf2ea-104">Later in the data flow, different transformations can be applied to the column copies.</span></span> <span data-ttu-id="cf2ea-105">È ad esempio possibile utilizzare la trasformazione Copia colonna per creare una copia di una colonna e quindi utilizzare la trasformazione Mappa caratteri per convertire in caratteri maiuscoli i dati copiati oppure utilizzare la trasformazione Aggregazione per applicare aggregazioni alla nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="cf2ea-105">For example, you can use the Copy Column transformation to create a copy of a column and then convert the copied data to uppercase characters by using the Character Map transformation, or apply aggregations to the new column by using the Aggregate transformation.</span></span>  
  
## <a name="configuration-of-the-copy-column-transformation"></a><span data-ttu-id="cf2ea-106">Configurazione della trasformazione Copia colonna</span><span class="sxs-lookup"><span data-stu-id="cf2ea-106">Configuration of the Copy Column Transformation</span></span>  
 <span data-ttu-id="cf2ea-107">Per configurare la trasformazione Copia colonna, è necessario specificare le colonne di input da copiare.</span><span class="sxs-lookup"><span data-stu-id="cf2ea-107">You configure the Copy Column transformation by specifying the input columns to copy.</span></span> <span data-ttu-id="cf2ea-108">È possibile creare più copie di una stessa colonna oppure creare copie di più colonne in una singola operazione.</span><span class="sxs-lookup"><span data-stu-id="cf2ea-108">You can create multiple copies of a column, or create copies of multiple columns in one operation.</span></span>  
  
 <span data-ttu-id="cf2ea-109">Questa trasformazione include un input e un output.</span><span class="sxs-lookup"><span data-stu-id="cf2ea-109">This transformation has one input and one output.</span></span> <span data-ttu-id="cf2ea-110">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="cf2ea-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="cf2ea-111">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="cf2ea-111">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="cf2ea-112">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Copia colonna** , vedere [Editor trasformazione Copia colonna](../../copy-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="cf2ea-112">For more information about the properties that you can set in the **Copy Column Transformation Editor** dialog box, see [Copy Column Transformation Editor](../../copy-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="cf2ea-113">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="cf2ea-113">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="cf2ea-114">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf2ea-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="cf2ea-115">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="cf2ea-115">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="cf2ea-116">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="cf2ea-116">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="cf2ea-117">Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="cf2ea-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf2ea-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf2ea-118">See Also</span></span>  
 <span data-ttu-id="cf2ea-119">[Flusso di dati](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="cf2ea-119">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="cf2ea-120">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="cf2ea-120">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
