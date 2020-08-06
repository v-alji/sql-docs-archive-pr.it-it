---
title: Utilizzo di dati di tabelle nidificate come input per un grafico di accuratezza | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], nested tables
- Mining Accuracy Chart [Analysis Services], input tables
- nested tables
- adding nested tables
ms.assetid: 162e0686-ada3-4dd3-9151-9589926e6613
author: minewiskan
ms.author: owend
ms.openlocfilehash: 97d5bbd75d09b1a9e4276c4723ad6986dbabf9e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623582"
---
# <a name="using-nested-table-data-as-an-input-for-an-accuracy-chart"></a><span data-ttu-id="0fcdc-102">Utilizzo di dati di tabelle nidificate come input per un grafico di accuratezza</span><span class="sxs-lookup"><span data-stu-id="0fcdc-102">Using Nested Table Data as an Input for an Accuracy Chart</span></span>
  <span data-ttu-id="0fcdc-103">Quando si esegue il test dell'accuratezza di un modello di data mining utilizzando dati esterni, se il modello di data mining contiene tabelle nidificate, anche i dati esterni devono contenere una tabella del case e una tabella nidificata associata.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-103">When you test the accuracy of a mining model by using external data, if the mining model contains nested tables, the external data must also contain a case table and an associated nested table.</span></span>  
  
 <span data-ttu-id="0fcdc-104">In questo argomento viene decritto come utilizzare le tabelle nidificate utilizzate per il test del modello, come eseguire il mapping delle tabelle nidificate e del case nel modello e nei dati esterni e come applicare un filtro a una tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-104">This topic describes how to work with nested tables used for model testing, how to map nested and case tables in the mode and in the external data, and how to apply a filter to a nested table.</span></span>  
  
 <span data-ttu-id="0fcdc-105">Quando si utilizzano tabelle annidate, ricordare i suggerimenti riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="0fcdc-105">When working with nested tables, keep in mind these tips:</span></span>  
  
-   <span data-ttu-id="0fcdc-106">Se si seleziona l'opzione **Usa test case del modello di data mining** o **Usa test case della struttura di data mining**, non è necessario specificare una tabella del case o una tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-106">If you select the option **Use mining model test cases** or **Use mining structure test cases**, you do not need to specify a case table or nested table.</span></span> <span data-ttu-id="0fcdc-107">Con queste opzioni, la definizione dei dati di test viene archiviata nella struttura di data mining e i dati di test vengono automaticamente selezionati quando si crea il grafico di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-107">With those options, the definition of the test data is stored in the mining structure and the test data is automatically selected when you create the accuracy chart.</span></span>  
  
-   <span data-ttu-id="0fcdc-108">Se esiste già una relazione tra il case e la tabella nidificata nell'origine dati, viene eseguito il mapping automatico tra le colonne della struttura di data mining e le colonne con lo stesso nome della tabella di input.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-108">If a relationship already exists between the case and nested table in the data source, the columns in the mining structure are automatically mapped to the columns that have the same name in the input table.</span></span>  
  
-   <span data-ttu-id="0fcdc-109">Non è possibile selezionare una tabella nidificata fino a quando non è stata specificata la tabella del case.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-109">You cannot select a nested table until you have specified the case table.</span></span> <span data-ttu-id="0fcdc-110">Inoltre, non è possibile specificare una tabella nidificata come input a meno che anche il modello di data mining non utilizzi una tabella del case e una struttura della tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-110">Also, you cannot specify a nested table as an input unless the mining model also uses a case table and nested table structure.</span></span>  
  
### <a name="use-a-nested-table-as-input-to-an-accuracy-chart"></a><span data-ttu-id="0fcdc-111">Utilizzare una tabella nidificata come input per un grafico di accuratezza</span><span class="sxs-lookup"><span data-stu-id="0fcdc-111">Use a nested table as input to an accuracy chart</span></span>  
  
1.  <span data-ttu-id="0fcdc-112">Fare doppio clic sulla struttura di data mining per aprirla in Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-112">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="0fcdc-113">Selezionare la scheda **Grafico di accuratezza modello di data mining** , quindi selezionare la scheda **Selezione input** .</span><span class="sxs-lookup"><span data-stu-id="0fcdc-113">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="0fcdc-114">In **Seleziona set di dati da utilizzare per il grafico di accuratezza**selezionare l'opzione **Specifica un set di dati diverso**.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-114">In **Select data set to be used for accuracy chart**, select the option **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="0fcdc-115">Fare clic sul pulsante Sfoglia **(...)** per scegliere il set di dati esterno da un elenco di viste origine dati nel server corrente.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-115">Click the browse button **(...)** to choose the external data set from a list of data source views on the current server.</span></span>  
  
5.  <span data-ttu-id="0fcdc-116">Fare clic su **Seleziona tabella del case**.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-116">Click **Select Case Table**.</span></span> <span data-ttu-id="0fcdc-117">Nella finestra di dialogo **Seleziona tabella** scegliere una tabella dalla vista origine dati che contiene i dati del case e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-117">In the **Select Table** dialog box, choose the table from the data source view that contains the case data, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="0fcdc-118">Fare clic su **Seleziona tabella nidificata**.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-118">Click **Select Nested Table**.</span></span> <span data-ttu-id="0fcdc-119">Nella finestra di dialogo **Seleziona tabella** selezionare la tabella che contiene i dati nidificati e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0fcdc-119">In the **Select Table** dialog box, select the table that contains the nested data, and then click **OK**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="0fcdc-120">Se è necessario modificare la relazione tra la tabella nidificata e la tabella del case, fare clic su **Modifica join** per aprire la finestra di dialogo **Crea relazione** .</span><span class="sxs-lookup"><span data-stu-id="0fcdc-120">If you need to modify the relationship between the nested table and the case table, click **Modify Join** to open the **Create Relationship** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fcdc-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fcdc-121">See Also</span></span>  
 <span data-ttu-id="0fcdc-122">[Scegliere ed eseguire il mapping dei dati di test del modello](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="0fcdc-122">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="0fcdc-123">Applicare filtri ai dati di test del modello</span><span class="sxs-lookup"><span data-stu-id="0fcdc-123">Apply Filters to Model Testing Data</span></span>](apply-filters-to-model-testing-data.md)  
  
  
