---
title: Editor trasformazione Conversione dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontransformation.f1
helpviewer_keywords:
- Data Conversion Transformation Editor
ms.assetid: 7b4e4873-e8fe-4549-a965-65bebdb270bc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4b893f04dcca2dd2a1a5874b55c1c1c608aaeb12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726155"
---
# <a name="data-conversion-transformation-editor"></a><span data-ttu-id="548f1-102">Editor trasformazione Conversione dati</span><span class="sxs-lookup"><span data-stu-id="548f1-102">Data Conversion Transformation Editor</span></span>
  <span data-ttu-id="548f1-103">Usare la finestra di dialogo **Editor trasformazione Conversione dati** per selezionare le colonne da convertire e i tipi di dati in cui convertire la colonna e impostare gli attributi di conversione.</span><span class="sxs-lookup"><span data-stu-id="548f1-103">Use the **Data Conversion Transformation Editor** dialog box to select the columns to convert, select the data type to which the column is converted, and set conversion attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="548f1-104">La `FastParse` proprietà delle colonne di output della trasformazione Conversione dati non è disponibile nell' **Editor trasformazione Conversione dati**, ma può essere impostata tramite il **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="548f1-104">The `FastParse` property of the output columns of the Data Conversion transformation is not available in the **Data Conversion Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="548f1-105">Per altre informazioni su questa proprietà, vedere la sezione relativa alla trasformazione Conversione dati in [Proprietà personalizzate delle trasformazioni](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="548f1-105">For more information on this property, see the Data Conversion Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="548f1-106">Per sapere di più sulla trasformazione conversione dati, vedere [Trasformazione Conversione dati](data-flow/transformations/data-conversion-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="548f1-106">To learn more about the Data Conversion transformation, see [Data Conversion Transformation](data-flow/transformations/data-conversion-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="548f1-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="548f1-107">Options</span></span>  
 <span data-ttu-id="548f1-108">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="548f1-108">**Available Input Columns**</span></span>  
 <span data-ttu-id="548f1-109">Consente di selezionare le colonne da convertire utilizzando le caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="548f1-109">Select columns to convert by using the check boxes.</span></span> <span data-ttu-id="548f1-110">Le selezioni effettuate determinano l'aggiunta delle colonne di input nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="548f1-110">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="548f1-111">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="548f1-111">**Input Column**</span></span>  
 <span data-ttu-id="548f1-112">Consente di selezionare le colonne da convertire nell'elenco delle colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="548f1-112">Select columns to convert from the list of available input columns.</span></span> <span data-ttu-id="548f1-113">Le selezioni effettuate vengono riflesse nelle selezioni delle caselle di controllo descritte in precedenza.</span><span class="sxs-lookup"><span data-stu-id="548f1-113">Your selections are reflected in the check box selections above.</span></span>  
  
 <span data-ttu-id="548f1-114">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="548f1-114">**Output Alias**</span></span>  
 <span data-ttu-id="548f1-115">Consente di digitare un alias per ogni nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="548f1-115">Type an alias for each new column.</span></span> <span data-ttu-id="548f1-116">L'impostazione predefinita è `Copy of` seguita dal nome della colonna di input. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="548f1-116">The default is `Copy of` followed by the input column name; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="548f1-117">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="548f1-117">**Data Type**</span></span>  
 <span data-ttu-id="548f1-118">Consente di selezionare un tipo di dati disponibile nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="548f1-118">Select an available data type from the list.</span></span> <span data-ttu-id="548f1-119">Per altre informazioni, vedere [Tipi di dati di Integration Services](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="548f1-119">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="548f1-120">**Lunghezza**</span><span class="sxs-lookup"><span data-stu-id="548f1-120">**Length**</span></span>  
 <span data-ttu-id="548f1-121">Consente di selezionare la lunghezza della colonna per dati di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="548f1-121">Set the column length for string data.</span></span>  
  
 <span data-ttu-id="548f1-122">**Precisione**</span><span class="sxs-lookup"><span data-stu-id="548f1-122">**Precision**</span></span>  
 <span data-ttu-id="548f1-123">Consente di impostare la precisione per dati numerici.</span><span class="sxs-lookup"><span data-stu-id="548f1-123">Set the precision for numeric data.</span></span>  
  
 <span data-ttu-id="548f1-124">**Ridimensionamento**</span><span class="sxs-lookup"><span data-stu-id="548f1-124">**Scale**</span></span>  
 <span data-ttu-id="548f1-125">Consente di impostare la scala per dati numerici.</span><span class="sxs-lookup"><span data-stu-id="548f1-125">Set the scale for numeric data.</span></span>  
  
 <span data-ttu-id="548f1-126">**Tabella codici**</span><span class="sxs-lookup"><span data-stu-id="548f1-126">**Code page**</span></span>  
 <span data-ttu-id="548f1-127">Consente di selezionare la tabella codici appropriata per le colonne di tipo DT_STR.</span><span class="sxs-lookup"><span data-stu-id="548f1-127">Select the appropriate code page for columns of type DT_STR.</span></span>  
  
 <span data-ttu-id="548f1-128">**Configurare l'output degli errori**</span><span class="sxs-lookup"><span data-stu-id="548f1-128">**Configure error output**</span></span>  
 <span data-ttu-id="548f1-129">Consente di indicare come gestire gli errori tramite la finestra di dialogo [Configura output errori](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="548f1-129">Specify how to handle row-level errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548f1-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="548f1-130">See Also</span></span>  
 <span data-ttu-id="548f1-131">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="548f1-131">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="548f1-132">Conversione di dati in un tipo di dati diverso utilizzando la trasformazione Conversione dati</span><span class="sxs-lookup"><span data-stu-id="548f1-132">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>](data-flow/transformations/convert-data-type-by-using-data-conversion-transformation.md)  
  
  
