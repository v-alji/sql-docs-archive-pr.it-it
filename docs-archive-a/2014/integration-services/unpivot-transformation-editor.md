---
title: Editor trasformazione UnPivot | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unpivottransformation.f1
helpviewer_keywords:
- Unpivot Transformation Editor
ms.assetid: 72a36ef0-4070-4f6c-9c74-0720109617dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c3b93370b34440b73b4c9c78dc7d19fa4095275
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625446"
---
# <a name="unpivot-transformation-editor"></a><span data-ttu-id="67f86-102">Editor trasformazione UnPivot</span><span class="sxs-lookup"><span data-stu-id="67f86-102">Unpivot Transformation Editor</span></span>
  <span data-ttu-id="67f86-103">Utilizzare la finestra di dialogo **Editor trasformazione UnPivot** per selezionare le colonne da trasformare in righe tramite Pivot e specificare la colonna di dati e la nuova colonna di output per il valore pivot.</span><span class="sxs-lookup"><span data-stu-id="67f86-103">Use the **Unpivot Transformation Editor** dialog box to select the columns to pivot into rows, and to specify the data column and the new pivot value output column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67f86-104"> Per illustrare l'utilizzo delle opzioni, questo argomento si basa sullo scenario UnPivot descritto in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md) .</span><span class="sxs-lookup"><span data-stu-id="67f86-104">This topic relies on the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md) to illustrate the use of the options.</span></span>  
  
 <span data-ttu-id="67f86-105">Per ulteriori informazioni sulla trasformazione tramite UnPivot, vedere [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="67f86-105">To learn more about the Unpivot transformation, see [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="67f86-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="67f86-106">Options</span></span>  
 <span data-ttu-id="67f86-107">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="67f86-107">**Available Input Columns**</span></span>  
 <span data-ttu-id="67f86-108">Consente di specificare le colonne da trasformare in righe tramite Pivot utilizzando le caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="67f86-108">Using the check boxes, specify the columns to pivot into rows.</span></span>  
  
 <span data-ttu-id="67f86-109">**Nome**</span><span class="sxs-lookup"><span data-stu-id="67f86-109">**Name**</span></span>  
 <span data-ttu-id="67f86-110">Consente di visualizzare il nome della colonna di input disponibile.</span><span class="sxs-lookup"><span data-stu-id="67f86-110">View the name of the available input column.</span></span>  
  
 <span data-ttu-id="67f86-111">**Pass-through**</span><span class="sxs-lookup"><span data-stu-id="67f86-111">**Pass Through**</span></span>  
 <span data-ttu-id="67f86-112">Indica se includere la colonna nell'output trasformato tramite UnPivot.</span><span class="sxs-lookup"><span data-stu-id="67f86-112">Indicate whether to include the column in the unpivoted output.</span></span>  
  
 <span data-ttu-id="67f86-113">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="67f86-113">**Input Column**</span></span>  
 <span data-ttu-id="67f86-114">Consente di selezionare una colonna di input nell'elenco delle colonne di input disponibili per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="67f86-114">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="67f86-115">Le selezioni effettuate vengono riflesse nelle selezioni delle caselle di controllo nella tabella **Colonne di input disponibili** .</span><span class="sxs-lookup"><span data-stu-id="67f86-115">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="67f86-116">Nello scenario UnPivot descritto in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), le colonne di input sono le colonne **Ham**, **Soda**, **Milk**, **Beer**e **Chips** .</span><span class="sxs-lookup"><span data-stu-id="67f86-116">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Input Columns are the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns.</span></span>  
  
 <span data-ttu-id="67f86-117">**Colonna di destinazione**</span><span class="sxs-lookup"><span data-stu-id="67f86-117">**Destination Column**</span></span>  
 <span data-ttu-id="67f86-118">Consente di specificare un nome per la colonna di dati.</span><span class="sxs-lookup"><span data-stu-id="67f86-118">Provide a name for the data column.</span></span>  
  
 <span data-ttu-id="67f86-119">Nello scenario UnPivot descritto in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), la colonna di destinazione è la colonna delle quantità, ovvero**Qty**.</span><span class="sxs-lookup"><span data-stu-id="67f86-119">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Destination Column is the quantity (**Qty**) column.</span></span>  
  
 <span data-ttu-id="67f86-120">**Valore chiave pivot**</span><span class="sxs-lookup"><span data-stu-id="67f86-120">**Pivot Key Value**</span></span>  
 <span data-ttu-id="67f86-121">Consente di specificare un nome per il valore pivot.</span><span class="sxs-lookup"><span data-stu-id="67f86-121">Provide a name for the pivot value.</span></span> <span data-ttu-id="67f86-122">Per impostazione predefinita viene suggerito il nome della colonna di input. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="67f86-122">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="67f86-123">È possibile specificare il valore di questa proprietà tramite un'espressione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="67f86-123">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="67f86-124">Nello scenario UnPivot descritto in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), i valori pivot verranno visualizzati nella nuova colonna Product designata dall'opzione **Nome colonna valore chiave pivot** allo stesso modo dei valori di testo **Ham**, **Soda**, **Milk**, **Beer**e **Chips**.</span><span class="sxs-lookup"><span data-stu-id="67f86-124">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Values will appear in the new Product column designated by the **Pivot Key Value Column Name** option, as the text values **Ham**, **Soda**, **Milk**, **Beer**, and **Chips**.</span></span>  
  
 <span data-ttu-id="67f86-125">**Nome colonna valore chiave pivot**</span><span class="sxs-lookup"><span data-stu-id="67f86-125">**Pivot Key Value Column Name**</span></span>  
 <span data-ttu-id="67f86-126">Consente di specificare il nome per la colonna del valore pivot.</span><span class="sxs-lookup"><span data-stu-id="67f86-126">Provide a name for the pivot value column.</span></span> <span data-ttu-id="67f86-127">L'impostazione predefinita è "Valore chiave pivot". È comunque possibile scegliere un nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="67f86-127">The default is "Pivot Key Value"; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="67f86-128">Nello scenario UnPivot descritto in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), il Nome colonna valore chiave pivot è **Product** e designa la nuova colonna **Product** come la colonna in cui viene applicata la trasformazione tramite UnPivot alle colonne **Ham**, **Soda**, **Milk**, **Beer**e **Chips** .</span><span class="sxs-lookup"><span data-stu-id="67f86-128">In the Unpivot scenario described in [Unpivot Transformation](data-flow/transformations/unpivot-transformation.md), the Pivot Key Value Column Name is **Product** and designates the new **Product** column into which the **Ham**, **Soda**, **Milk**, **Beer**, and **Chips** columns are unpivoted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f86-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67f86-129">See Also</span></span>  
 <span data-ttu-id="67f86-130">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="67f86-130">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="67f86-131">Trasformazione pivot</span><span class="sxs-lookup"><span data-stu-id="67f86-131">Pivot Transformation</span></span>](data-flow/transformations/pivot-transformation.md)  
  
  
