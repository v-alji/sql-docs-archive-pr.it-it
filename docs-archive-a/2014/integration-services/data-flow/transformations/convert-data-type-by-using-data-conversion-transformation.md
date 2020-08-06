---
title: Conversione di dati in un tipo di dati diverso tramite la trasformazione Conversione dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: 4aabbe4f-7666-4672-865a-9627bd25fbfd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 878741717c36c18e9a069c62e86be0148272239f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629946"
---
# <a name="convert-data-to-a-different-data-type-by-using-the-data-conversion-transformation"></a><span data-ttu-id="798a6-102">Conversione di dati in un tipo di dati diverso utilizzando la trasformazione Conversione dati</span><span class="sxs-lookup"><span data-stu-id="798a6-102">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>
  <span data-ttu-id="798a6-103">È possibile aggiungere e configurare una trasformazione Conversione dati solo se il pacchetto include già almeno un'attività Flusso di dati e un'origine.</span><span class="sxs-lookup"><span data-stu-id="798a6-103">To add and configure a Data Conversion transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-convert-data-to-a-different-data-type"></a><span data-ttu-id="798a6-104">Per convertire i dati in un tipo di dati diverso</span><span class="sxs-lookup"><span data-stu-id="798a6-104">To convert data to a different data type</span></span>  
  
1.  <span data-ttu-id="798a6-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="798a6-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="798a6-106">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="798a6-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="798a6-107">Fare clic sulla scheda **Flusso di dati** e quindi, dalla **casella degli strumenti**, trascinare la trasformazione Conversione dati sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="798a6-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Data Conversion transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="798a6-108">Connettere la trasformazione Conversione dati al flusso di dati trascinando un connettore dall'origine o dalla trasformazione precedente alla trasformazione Conversione dati.</span><span class="sxs-lookup"><span data-stu-id="798a6-108">Connect the Data Conversion transformation to the data flow by dragging a connector from the source or the previous transformation to the Data Conversion transformation.</span></span>  
  
5.  <span data-ttu-id="798a6-109">Fare doppio clic sulla trasformazione Conversione dati.</span><span class="sxs-lookup"><span data-stu-id="798a6-109">Double-click the Data Conversion transformation.</span></span>  
  
6.  <span data-ttu-id="798a6-110">Nella tabella **Colonne di input disponibili** della finestra di dialogo **Editor trasformazione Conversione dati** selezionare le caselle di controllo accanto alle colonne di cui si vuole convertire il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="798a6-110">In the **Data ConversionTransformation Editor** dialog box, in the **Available Input Columns** table, select the check box next to the columns whose data type you want to convert.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="798a6-111">È possibile applicare più conversioni di dati a una singola colonna di input.</span><span class="sxs-lookup"><span data-stu-id="798a6-111">You can apply multiple data conversions to an input column.</span></span>  
  
7.  <span data-ttu-id="798a6-112">Facoltativamente, modificare i valori predefiniti nella colonna **Alias di output** .</span><span class="sxs-lookup"><span data-stu-id="798a6-112">Optionally, modify the default values in the **Output Alias** column.</span></span>  
  
8.  <span data-ttu-id="798a6-113">Nell'elenco **Tipo di dati** selezionare il nuovo tipo di dati per la colonna.</span><span class="sxs-lookup"><span data-stu-id="798a6-113">In the **Data Type** list, select the new data type for the column.</span></span> <span data-ttu-id="798a6-114">Il tipo di dati predefinito è quello della colonna di input.</span><span class="sxs-lookup"><span data-stu-id="798a6-114">The default data type is the data type of the input column.</span></span>  
  
9. <span data-ttu-id="798a6-115">A seconda del tipo di dati selezionato, aggiornare facoltativamente i valori nelle colonne **Lunghezza**, **Precisione**, **Scala**e **Tabella codici** .</span><span class="sxs-lookup"><span data-stu-id="798a6-115">Optionally, depending on the selected data type, update the values in the **Length**, the **Precision**, the **Scale**, and the **Code Page** columns.</span></span>  
  
10. <span data-ttu-id="798a6-116">Per configurare l'output degli errori, fare clic su **Configura output errori**.</span><span class="sxs-lookup"><span data-stu-id="798a6-116">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="798a6-117">Per altre informazioni, vedere [Configurazione di un output degli errori in un componente del flusso di dati](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="798a6-117">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="798a6-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="798a6-118">Click **OK**.</span></span>  
  
12. <span data-ttu-id="798a6-119">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="798a6-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="798a6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="798a6-120">See Also</span></span>  
 <span data-ttu-id="798a6-121">[Data Conversion Transformation](data-conversion-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="798a6-121">[Data Conversion Transformation](data-conversion-transformation.md) </span></span>  
 <span data-ttu-id="798a6-122">[Trasformazioni di Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="798a6-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="798a6-123">[Percorsi in Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="798a6-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="798a6-124">[Tipi di dati di Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="798a6-124">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 [<span data-ttu-id="798a6-125">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="798a6-125">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
