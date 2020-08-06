---
title: Associazione di un parametro di query a un parametro di report (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- queries [Reporting Services], parameters
- parameters [Reporting Services], queries
ms.assetid: 6d297e1a-ff71-472a-addc-349e863092b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f65aa36e8910378d68963c8c9990518b661025ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713895"
---
# <a name="associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="bf188-102">Associazione di un parametro di query a un parametro di report (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="bf188-102">Associate a Query Parameter with a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="bf188-103">Quando si definisce una query del set di dati contenente una variabile di query, il comando della query viene analizzato.</span><span class="sxs-lookup"><span data-stu-id="bf188-103">When you define a dataset query that contains a query variable, the query command is parsed.</span></span> <span data-ttu-id="bf188-104">Per ogni variabile di query, vengono creati un parametro del set di dati e un parametro del report corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="bf188-104">For each query variable, a corresponding dataset parameter and report parameter are created.</span></span> <span data-ttu-id="bf188-105">Il parametro del set di dati punta al parametro del report.</span><span class="sxs-lookup"><span data-stu-id="bf188-105">The dataset parameter points to the report parameter.</span></span> <span data-ttu-id="bf188-106">Questo consente di immettere un valore che viene passato direttamente alla query.</span><span class="sxs-lookup"><span data-stu-id="bf188-106">This enables a user to enter a value that passes directly to the query.</span></span> <span data-ttu-id="bf188-107">Ogni volta che si modifica il comando della query, si verifica lo stesso processo.</span><span class="sxs-lookup"><span data-stu-id="bf188-107">Each time you edit the query command, the same process takes place.</span></span>  
  
 <span data-ttu-id="bf188-108">Per rinominare un parametro di report associato a un parametro di query, è necessario collegare manualmente i parametri di query al parametro di report rinominato utilizzando la procedura illustrata in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="bf188-108">If you rename a report parameter that is bound to a query parameter, you need to manually link the query parameters to the renamed report parameter by using the procedure in this topic.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-query-parameter-with-a-report-parameter"></a><span data-ttu-id="bf188-109">Per associare un parametro di query a un parametro di report</span><span class="sxs-lookup"><span data-stu-id="bf188-109">To associate a query parameter with a report parameter</span></span>  
  
1.  <span data-ttu-id="bf188-110">Nel riquadro dei dati del report fare clic con il pulsante destro del mouse sul set di dati, fare clic su **Proprietà set di dati**, quindi scegliere **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="bf188-110">In the Report Data pane, right-click the dataset, click **Dataset Properties**, and then click **Parameters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bf188-111"> Se il riquadro Dati report non è visualizzato, scegliere **Dati report** dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="bf188-111">If the Report Data pane is not visible, click **Report Data** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="bf188-112">Nella colonna **Nome parametro**individuare il nome del parametro di query.</span><span class="sxs-lookup"><span data-stu-id="bf188-112">In the column **Parameter Name**, find the name of the query parameter.</span></span> <span data-ttu-id="bf188-113">I nomi dei parametri vengono popolati automaticamente in base alla query.</span><span class="sxs-lookup"><span data-stu-id="bf188-113">Parameter names are automatically populated based on the query.</span></span> <span data-ttu-id="bf188-114">Ogni volta che si modifica la query, vengono verificati i nuovi parametri della query.</span><span class="sxs-lookup"><span data-stu-id="bf188-114">Every time you change the query, the query is checked for new query parameters.</span></span> <span data-ttu-id="bf188-115">I parametri di query creati manualmente non vengono modificati quando la query cambia.</span><span class="sxs-lookup"><span data-stu-id="bf188-115">Query parameters that you create manually are not changed when the query changes.</span></span>  
  
    -   <span data-ttu-id="bf188-116">In **Nome parametro**individuare il nome del parametro di query così come è riportato nella query.</span><span class="sxs-lookup"><span data-stu-id="bf188-116">In **Parameter Name**, find the query parameter name as it exists in the query.</span></span> <span data-ttu-id="bf188-117">È anche possibile aggiungere manualmente un nuovo parametro di query e specificare un nome.</span><span class="sxs-lookup"><span data-stu-id="bf188-117">You can also manually add a new query parameter and enter a name.</span></span>  
  
    -   <span data-ttu-id="bf188-118">In **Valore parametro**digitare o selezionare un'espressione che restituisca il valore da passare al parametro di query.</span><span class="sxs-lookup"><span data-stu-id="bf188-118">In **Parameter Value**, type or select an expression that evaluates to the value to pass to the query parameter.</span></span> <span data-ttu-id="bf188-119">Si tratta in genere del nome del parametro di report.</span><span class="sxs-lookup"><span data-stu-id="bf188-119">This is typically the name of the report parameter.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="bf188-120">Non è obbligatorio utilizzare i parametri di report come valori per un parametro di query.</span><span class="sxs-lookup"><span data-stu-id="bf188-120">You are not limited to report parameters as values for a query parameter.</span></span> <span data-ttu-id="bf188-121">È infatti possibile utilizzare qualsiasi espressione che restituisca un valore per il parametro.</span><span class="sxs-lookup"><span data-stu-id="bf188-121">You can use any expression that evaluates to a value for the parameter value.</span></span>  
  
3.  <span data-ttu-id="bf188-122">Ripetere il passaggio 2 per gli altri parametri di query.</span><span class="sxs-lookup"><span data-stu-id="bf188-122">Repeat step 2 for additional query parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf188-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf188-123">See Also</span></span>  
 <span data-ttu-id="bf188-124">[Set di set di impostazioni e set di impostazioni di set di report incorporati &#40;Generatore report e SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bf188-124">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bf188-125">Concetto dei parametri di report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="bf188-125">Report Parameters Concept &#40;Report Builder and SSRS&#41;</span></span>](../report-design/report-parameters-concepts-report-builder-and-ssrs.md)  
  
  
