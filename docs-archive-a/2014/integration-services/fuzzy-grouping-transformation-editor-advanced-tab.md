---
title: Editor trasformazione Raggruppamento fuzzy (scheda Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: dd820d75-b8a7-4515-aea4-3553ba5b442e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2f5dd05eda56b4818914f659734eb3cdfb20c4d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626146"
---
# <a name="fuzzy-grouping-transformation-editor-advanced-tab"></a><span data-ttu-id="6d5e9-102">Editor trasformazione Raggruppamento fuzzy (scheda Avanzate)</span><span class="sxs-lookup"><span data-stu-id="6d5e9-102">Fuzzy Grouping Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="6d5e9-103">La scheda **Avanzate** della finestra di dialogo **Editor trasformazione Raggruppamento fuzzy** consente di specificare le colonne di input e output, impostare le soglie di somiglianza e definire i delimitatori.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-103">Use the **Advanced** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify input and output columns, set similarity thresholds, and define delimiters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6d5e9-104">Le `Exhaustive` proprietà e `MaxMemoryUsage` della trasformazione Raggruppamento fuzzy non sono disponibili nell' **Editor trasformazione Raggruppamento fuzzy**, ma possono essere impostate tramite il **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-104">The `Exhaustive` and the `MaxMemoryUsage` properties of the Fuzzy Grouping transformation are not available in the **Fuzzy Grouping Transformation Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="6d5e9-105">Per ulteriori informazioni su queste proprietà, vedere la sezione relativa alla trasformazione Raggruppamento fuzzy in [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6d5e9-105">For more information on these properties, see the Fuzzy Grouping Transformation section of [Transformation Custom Properties](data-flow/transformations/transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="6d5e9-106">Per ulteriori informazioni sulla trasformazione Raggruppamento fuzzy, vedere [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="6d5e9-106">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="6d5e9-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6d5e9-107">Options</span></span>  
 <span data-ttu-id="6d5e9-108">**Nome colonna chiave di input**</span><span class="sxs-lookup"><span data-stu-id="6d5e9-108">**Input key column name**</span></span>  
 <span data-ttu-id="6d5e9-109">Consente di specificare il nome di una colonna di output contenente l'identificatore univoco per ogni riga di input.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-109">Specify the name of an output column that contains the unique identifier for each input row.</span></span> <span data-ttu-id="6d5e9-110">La colonna `_key_in` contiene un valore che identifica in modo univoco ogni riga.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-110">The `_key_in` column has a value that uniquely identifies each row.</span></span>  
  
 <span data-ttu-id="6d5e9-111">**Nome colonna chiave di output**</span><span class="sxs-lookup"><span data-stu-id="6d5e9-111">**Output key column name**</span></span>  
 <span data-ttu-id="6d5e9-112">Consente di specificare il nome di una colonna di output contenente l'identificatore univoco per la riga canonica di un gruppo di righe duplicate.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-112">Specify the name of an output column that contains the unique identifier for the canonical row of a group of duplicate rows.</span></span> <span data-ttu-id="6d5e9-113">La colonna `_key_out` corrisponde al valore `_key_in` della riga di dati canonica.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-113">The `_key_out` column corresponds to the `_key_in` value of the canonical data row.</span></span>  
  
 <span data-ttu-id="6d5e9-114">**Nome colonna punteggio somiglianza**</span><span class="sxs-lookup"><span data-stu-id="6d5e9-114">**Similarity score column name**</span></span>  
 <span data-ttu-id="6d5e9-115">Consente di specificare un nome per la colonna contenente il punteggio di somiglianza.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-115">Specify a name for the column that contains the similarity score.</span></span> <span data-ttu-id="6d5e9-116">Il punteggio di somiglianza è un valore compreso tra 0 e 1 che indica la somiglianza della riga di input alla riga canonica.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-116">The similarity score is a value between 0 and 1 that indicates the similarity of the input row to the canonical row.</span></span> <span data-ttu-id="6d5e9-117">I punteggi più prossimi a 1 indicano una corrispondenza maggiore.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-117">The closer the score is to 1, the more closely the row matches the canonical row.</span></span>  
  
 <span data-ttu-id="6d5e9-118">**Soglia di somiglianza**</span><span class="sxs-lookup"><span data-stu-id="6d5e9-118">**Similarity threshold**</span></span>  
 <span data-ttu-id="6d5e9-119">Consente di impostare la soglia di somiglianza mediante il dispositivo di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-119">Set the similarity threshold by using the slider.</span></span> <span data-ttu-id="6d5e9-120">Le soglie vicine a 1 indicano che le righe devono avere una somiglianza maggiore per poter essere considerate duplicati.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-120">The closer the threshold is to 1, the more the rows must resemble each other to qualify as duplicates.</span></span> <span data-ttu-id="6d5e9-121">L'aumento della soglia può incrementare la velocità di ricerca della corrispondenza in quanto viene considerato un minor numero di record candidati.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-121">Increasing the threshold can improve the speed of matching because fewer candidate records have to be considered.</span></span>  
  
 <span data-ttu-id="6d5e9-122">**Delimitatori token**</span><span class="sxs-lookup"><span data-stu-id="6d5e9-122">**Token delimiters**</span></span>  
 <span data-ttu-id="6d5e9-123">La trasformazione genera un set predefinito di delimitatori per la suddivisione in token dei dati. È tuttavia possibile aggiungere o rimuovere i delimitatori in base alle esigenze modificando l'elenco.</span><span class="sxs-lookup"><span data-stu-id="6d5e9-123">The transformation provides a default set of delimiters for tokenizing data, but you can add or remove delimiters as needed by editing the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d5e9-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d5e9-124">See Also</span></span>  
 <span data-ttu-id="6d5e9-125">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6d5e9-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="6d5e9-126">Identificazione di righe di dati simili tramite la trasformazione Raggruppamento fuzzy</span><span class="sxs-lookup"><span data-stu-id="6d5e9-126">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
