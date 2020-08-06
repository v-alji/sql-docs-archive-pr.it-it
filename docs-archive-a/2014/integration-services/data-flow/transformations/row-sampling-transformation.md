---
title: Trasformazione Campionamento righe | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rowsamplingtrans.f1
helpviewer_keywords:
- sampling seeds [Integration Services]
- random seeds
- random sampling
- sample data sets [Integration Services]
- Row Sampling transformation
- packages [Integration Services], samples
- datasets [Integration Services], sample
ms.assetid: b6caafd3-30b2-4368-82af-a44611d4cd39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c56f07d9fafa03752ef8c6572a13c6ad7c02a8c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727096"
---
# <a name="row-sampling-transformation"></a><span data-ttu-id="47068-102">Campionamento righe - trasformazione</span><span class="sxs-lookup"><span data-stu-id="47068-102">Row Sampling Transformation</span></span>
  <span data-ttu-id="47068-103">La trasformazione Campionamento righe consente di ottenere un subset di elementi selezionati casualmente da un set di dati di input.</span><span class="sxs-lookup"><span data-stu-id="47068-103">The Row Sampling transformation is used to obtain a randomly selected subset of an input dataset.</span></span> <span data-ttu-id="47068-104">È possibile specificare le dimensioni esatte dell'output campione e un valore di inizializzazione per il generatore di numeri casuali.</span><span class="sxs-lookup"><span data-stu-id="47068-104">You can specify the exact size of the output sample, and specify a seed for the random number generator.</span></span>  
  
 <span data-ttu-id="47068-105">Il campionamento casuale può essere utilizzato in molte circostanze.</span><span class="sxs-lookup"><span data-stu-id="47068-105">There are many applications for random sampling.</span></span> <span data-ttu-id="47068-106">Se ad esempio in una società si desidera selezionare casualmente 50 dipendenti a cui assegnare i premi di una lotteria, sarà possibile utilizzare la trasformazione Campionamento righe sul database dei dipendenti per generare esattamente il numero di vincitori specificato.</span><span class="sxs-lookup"><span data-stu-id="47068-106">For example, a company that wanted to randomly select 50 employees to receive prizes in a lottery could use the Row Sampling transformation on the employee database to generate the exact number of winners.</span></span>  
  
 <span data-ttu-id="47068-107">La trasformazione Campionamento righe risulta utile anche durante lo sviluppo dei pacchetti, per la creazione di un set di dati piccolo ma rappresentativo.</span><span class="sxs-lookup"><span data-stu-id="47068-107">The Row Sampling transformation is also useful during package development for creating a small but representative dataset.</span></span> <span data-ttu-id="47068-108">È possibile testare l'esecuzione del pacchetto e la trasformazione dei dati con dati altamente rappresentativi, ma più rapidamente, perché al posto del set di dati completo viene utilizzato un campione casuale.</span><span class="sxs-lookup"><span data-stu-id="47068-108">You can test package execution and data transformation with richly representative data, but more quickly because a random sample is used instead of the full dataset.</span></span> <span data-ttu-id="47068-109">Poiché le dimensioni del set di dati di esempio utilizzato dal pacchetto di test sono sempre uguali, l'utilizzo del subset campione semplifica inoltre l'identificazione di eventuali problemi di prestazioni nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="47068-109">Because the sample dataset used by the test package is always the same size, using the sample subset also makes it easier to identify performance problems in the package.</span></span>  
  
 <span data-ttu-id="47068-110">Questa trasformazione è simile alla trasformazione Campionamento percentuale, che crea un set di dati campione selezionando una percentuale delle righe di input.</span><span class="sxs-lookup"><span data-stu-id="47068-110">This transformation is similar to the Percentage Sampling transformation, which creates a sample dataset by selecting a percentage of the input rows.</span></span> <span data-ttu-id="47068-111">Vedere [Trasformazione Campionamento percentuale](percentage-sampling-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="47068-111">See [Percentage Sampling Transformation](percentage-sampling-transformation.md).</span></span>  
  
## <a name="configuring-the-row-sampling-transformation"></a><span data-ttu-id="47068-112">Configurazione della trasformazione Campionamento righe</span><span class="sxs-lookup"><span data-stu-id="47068-112">Configuring the Row Sampling Transformation</span></span>  
 <span data-ttu-id="47068-113">La trasformazione Campionamento righe crea un set di dati campione selezionando un numero specificato di righe di input della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="47068-113">The Row Sampling transformation creates a sample dataset by selecting a specified number of the transformation input rows.</span></span> <span data-ttu-id="47068-114">Poiché la selezione delle righe dall'input della trasformazione è casuale, il campione risultante è rappresentativo dell'input.</span><span class="sxs-lookup"><span data-stu-id="47068-114">Because the selection of rows from the transformation input is random, the resultant sample is representative of the input.</span></span> <span data-ttu-id="47068-115">Per determinare la modalità di selezione delle righe da parte della trasformazione, è inoltre possibile specificare il valore di inizializzazione utilizzato dal generatore di numeri casuali.</span><span class="sxs-lookup"><span data-stu-id="47068-115">You can also specify the seed that is used by the random number generator, to affect how the transformation selects rows.</span></span>  
  
 <span data-ttu-id="47068-116">Se si utilizza sempre lo stesso valore di inizializzazione per il generatore di numeri casuali sullo stesso input della trasformazione, si otterrà sempre lo stesso output campione.</span><span class="sxs-lookup"><span data-stu-id="47068-116">Using the same random seed on the same transformation input always creates the same sample output.</span></span> <span data-ttu-id="47068-117">Se non viene specificato alcun valore di inizializzazione, per creare il numero casuale la trasformazione utilizzerà il numero di tick del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="47068-117">If no seed is specified, the transformation uses the tick count of the operating system to create the random number.</span></span> <span data-ttu-id="47068-118">È pertanto possibile utilizzare un valore di inizializzazione costante durante il test per verificare i risultati della trasformazione durante lo sviluppo e il test di un pacchetto e quindi passare all'utilizzo di un valore di inizializzazione casuale quando il pacchetto viene introdotto nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="47068-118">Therefore, you could use the same seed during testing, to verify the transformation results during the development and testing of the package, and then change to a random seed when the package is moved into production.</span></span>  
  
 <span data-ttu-id="47068-119">La trasformazione Campionamento righe include la proprietà personalizzata `SamplingValue`,</span><span class="sxs-lookup"><span data-stu-id="47068-119">The Row Sampling transformation includes the `SamplingValue` custom property.</span></span> <span data-ttu-id="47068-120">che può essere aggiornata da un'espressione di proprietà al caricamento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="47068-120">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="47068-121">Per altre informazioni, vedere [Espressioni di Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Utilizzo delle espressioni di proprietà nei pacchetti](../../expressions/use-property-expressions-in-packages.md) e [Proprietà personalizzate delle trasformazioni](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="47068-121">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="47068-122">Questa trasformazione include un input e due output.</span><span class="sxs-lookup"><span data-stu-id="47068-122">This transformation has one input and two outputs.</span></span> <span data-ttu-id="47068-123">Non include alcun output degli errori.</span><span class="sxs-lookup"><span data-stu-id="47068-123">It has no error output.</span></span>  
  
 <span data-ttu-id="47068-124">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="47068-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="47068-125">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Campionamento righe**, vedere [Editor trasformazione Campionamento righe &#40;pagina Campionamento&#41;](../../row-sampling-transformation-editor-sampling-page.md).</span><span class="sxs-lookup"><span data-stu-id="47068-125">For more information about the properties that you can set in the **Row Sampling Transformation Editor** dialog box, see [Row Sampling Transformation Editor &#40;Sampling Page&#41;](../../row-sampling-transformation-editor-sampling-page.md).</span></span>  
  
 <span data-ttu-id="47068-126">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="47068-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="47068-127">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="47068-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="47068-128">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="47068-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="47068-129">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="47068-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="47068-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="47068-130">Related Tasks</span></span>  
 [<span data-ttu-id="47068-131">Impostazione delle proprietà di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="47068-131">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
  
