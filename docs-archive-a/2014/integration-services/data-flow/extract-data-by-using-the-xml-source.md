---
title: Estrarre i dati tramite l'origine XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], XML
- XML source [Integration Services]
ms.assetid: 5d5be54c-2b7e-4957-9193-c5ea5c5d6d15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57758353c476badfba4cb12a1ef6b5101f16735d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726108"
---
# <a name="extract-data-by-using-the-xml-source"></a><span data-ttu-id="c8487-102">Estrazione dei dati tramite l'origine XML</span><span class="sxs-lookup"><span data-stu-id="c8487-102">Extract Data by Using the XML Source</span></span>
  <span data-ttu-id="c8487-103">È possibile aggiungere e configurare un'origine XML solo se il pacchetto include già almeno un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="c8487-103">To add and configure an XML source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-xml-source"></a><span data-ttu-id="c8487-104">Per estrarre dati tramite un'origine XML</span><span class="sxs-lookup"><span data-stu-id="c8487-104">To extract data using an XML source</span></span>  
  
1.  <span data-ttu-id="c8487-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="c8487-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="c8487-106">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="c8487-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="c8487-107">Fare clic sulla scheda **Flusso di dati** e quindi, dalla **casella degli strumenti**, trascinare l'origine XML sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="c8487-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the XML source to the design surface.</span></span>  
  
4.  <span data-ttu-id="c8487-108">Fare doppio clic sull'origine XML.</span><span class="sxs-lookup"><span data-stu-id="c8487-108">Double-click the XML source.</span></span>  
  
5.  <span data-ttu-id="c8487-109">Nella pagina **Gestione connessione**della finestra di dialogo **Editor origine XML** selezionare una modalità di accesso ai dati:</span><span class="sxs-lookup"><span data-stu-id="c8487-109">In the **XML Source Editor**, on the **Connection Manager** page, select a data access mode:</span></span>  
  
    -   <span data-ttu-id="c8487-110">Per la modalità di accesso **Percorso file XML** , fare clic su **Sfoglia** e individuare la cartella che contiene il file XML.</span><span class="sxs-lookup"><span data-stu-id="c8487-110">For the **XML file location** access mode, click **Browse** and locate the folder that contains the XML file.</span></span>  
  
    -   <span data-ttu-id="c8487-111">Per la modalità di accesso **File XML da variabile** , selezionare la variabile definita dall'utente che contiene il percorso del file XML.</span><span class="sxs-lookup"><span data-stu-id="c8487-111">For the **XML file from variable** access mode, select the user-defined variable that contains the path of the XML file.</span></span>  
  
    -   <span data-ttu-id="c8487-112">Per la modalità di accesso **Dati XML da variabile** , selezionare la variabile definita dall'utente che contiene i dati XML.</span><span class="sxs-lookup"><span data-stu-id="c8487-112">For the **XML data from variable** access mode, select the user-defined variable that contains the XML data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c8487-113">La variabile deve essere definita nell'ambito dell'attività Flusso di dati che contiene l'origine XML, oppure nell'ambito del pacchetto, e deve avere un tipo di dati string.</span><span class="sxs-lookup"><span data-stu-id="c8487-113">The variables must be defined in the scope of the Data Flow task that contains the XML source, or in the scope of the package; additionally, the variable must have a string data type.</span></span>  
  
6.  <span data-ttu-id="c8487-114">Facoltativamente, selezionare **Usa schema inline** per indicare che il documento XML include informazioni sullo schema.</span><span class="sxs-lookup"><span data-stu-id="c8487-114">Optionally, select **Use inline schema** to indicate that the XML document includes schema information.</span></span>  
  
7.  <span data-ttu-id="c8487-115">Per specificare uno schema XSD (XML Schema Definition Language) esterno per il file XML, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8487-115">To specify an external XML Schema definition language (XSD) schema for the XML file, do one of the following:</span></span>  
  
    -   <span data-ttu-id="c8487-116">Fare clic su **Sfoglia** per individuare un file XSD esistente.</span><span class="sxs-lookup"><span data-stu-id="c8487-116">Click **Browse** to locate an existing XSD file.</span></span>  
  
    -   <span data-ttu-id="c8487-117">Fare clic su **Genera XSD** per creare un file XSD dal file XML.</span><span class="sxs-lookup"><span data-stu-id="c8487-117">Click **Generate XSD** to create an XSD from the XML file.</span></span>  
  
8.  <span data-ttu-id="c8487-118">Per aggiornare i nomi delle colonne di output, fare clic su **Colonne** e modificare i valori nell'elenco **Colonna di output** .</span><span class="sxs-lookup"><span data-stu-id="c8487-118">To update the names of output columns, click **Columns** and edit the values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="c8487-119">Per configurare l'output degli errori, fare clic su **Output errori**.</span><span class="sxs-lookup"><span data-stu-id="c8487-119">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="c8487-120">Per altre informazioni, vedere [Configurazione di un output degli errori in un componente del flusso di dati](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="c8487-120">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="c8487-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8487-121">Click **OK**.</span></span>  
  
11. <span data-ttu-id="c8487-122">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="c8487-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8487-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8487-123">See Also</span></span>  
 <span data-ttu-id="c8487-124">[Origine XML](xml-source.md) </span><span class="sxs-lookup"><span data-stu-id="c8487-124">[XML Source](xml-source.md) </span></span>  
 <span data-ttu-id="c8487-125">[Trasformazioni di Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="c8487-125">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="c8487-126">[Percorsi in Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="c8487-126">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="c8487-127">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="c8487-127">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
