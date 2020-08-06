---
title: Cercare la corrispondenza tra dati simili (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: f6fd6fc1-3569-42a5-b6cb-87a921c88f3b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 70dea36de557c6fda909d06ee19ff8fa2ed6908d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715475"
---
# <a name="match-similar-data-mds-add-in-for-excel"></a><span data-ttu-id="8a34a-102">Cercare la corrispondenza tra dati simili (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="8a34a-102">Match Similar Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="8a34a-103">Nel [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]usare la funzionalità Data Quality Services (DQS) per trovare analogie nei dati.</span><span class="sxs-lookup"><span data-stu-id="8a34a-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use Data Quality Services (DQS) functionality to find similarities in your data.</span></span>  
  
 <span data-ttu-id="8a34a-104">Per eseguire questa procedura, è possibile:</span><span class="sxs-lookup"><span data-stu-id="8a34a-104">To perform this procedure, you can:</span></span>  
  
-   <span data-ttu-id="8a34a-105">Utilizzare la Knowledge Base predefinita di Data Quality Services o</span><span class="sxs-lookup"><span data-stu-id="8a34a-105">Use the default Data Quality Services knowledge base, or</span></span>  
  
-   <span data-ttu-id="8a34a-106">Creare una Knowledge Base DQS e criteri di corrispondenza personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8a34a-106">Create your own custom DQS knowledge base and matching policy.</span></span> <span data-ttu-id="8a34a-107">Per altre informazioni, vedere [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="8a34a-107">For more information, see [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8a34a-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8a34a-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="8a34a-109">È necessario disporre di un foglio di lavoro contenente dati gestiti da MDS.</span><span class="sxs-lookup"><span data-stu-id="8a34a-109">You must have a worksheet that contains MDS-managed data.</span></span> <span data-ttu-id="8a34a-110">Per altre informazioni, vedere [caricare i dati da MDS in Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8a34a-110">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="8a34a-111">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8a34a-111">Optional.</span></span> <span data-ttu-id="8a34a-112">È possibile combinare altri dati con i dati gestiti da MDS prima di verificare le analogie.</span><span class="sxs-lookup"><span data-stu-id="8a34a-112">You can combine other data with the MDS-managed data before checking for similarities.</span></span> <span data-ttu-id="8a34a-113">Per altre informazioni, vedere [Combinare i dati &#40;componente aggiuntivo MDS per Excel&#41;](combine-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8a34a-113">For more information, see [Combine Data &#40;MDS Add-in for Excel&#41;](combine-data-mds-add-in-for-excel.md).</span></span>  
  
### <a name="to-find-similarities-by-using-the-default-knowledge-base"></a><span data-ttu-id="8a34a-114">Per trovare analogie utilizzando la Knowledge Base predefinita</span><span class="sxs-lookup"><span data-stu-id="8a34a-114">To find similarities by using the default knowledge base</span></span>  
  
1.  <span data-ttu-id="8a34a-115">Dal foglio di lavoro contenente i dati gestiti da MDS fare clic su **Abbina dati** nel gruppo **Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="8a34a-115">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="8a34a-116">Nella finestra di dialogo **Abbina dati** selezionare **Dati DQS (predefinito)** nell'elenco **Knowledge Base DQS**.</span><span class="sxs-lookup"><span data-stu-id="8a34a-116">In the **Match Data** dialog box, from the **DQS Knowledge Base** list, select **DQS Data (default)**.</span></span>  
  
3.  <span data-ttu-id="8a34a-117">Per ogni colonna contenente i dati per cui si desidera verificare la corrispondenza, aggiungere una riga nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8a34a-117">For each column that contains data you want to match, add a row in the dialog box.</span></span> <span data-ttu-id="8a34a-118">Per informazioni sui campi di questa finestra di dialogo, vedere [Modalità di impostazione dei parametri relativi alle regole di corrispondenza](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span><span class="sxs-lookup"><span data-stu-id="8a34a-118">For information about the fields in this dialog box, see [How to Set Matching Rule Parameters](../../data-quality-services/create-a-matching-policy.md#MatchingRules).</span></span>  
  
4.  <span data-ttu-id="8a34a-119">Quando il totale di tutti i valori di peso è uguale al 100%, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a34a-119">When the total of all weight values equals 100 percent, click **OK**.</span></span>  
  
### <a name="to-find-similarities-by-using-a-custom-knowledge-base"></a><span data-ttu-id="8a34a-120">Per trovare analogie utilizzando una Knowledge Base personalizzata</span><span class="sxs-lookup"><span data-stu-id="8a34a-120">To find similarities by using a custom knowledge base</span></span>  
  
1.  <span data-ttu-id="8a34a-121">Dal foglio di lavoro contenente i dati gestiti da MDS fare clic su **Abbina dati** nel gruppo **Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="8a34a-121">From the worksheet that contains MDS-managed data, in the **Data Quality** group, click **Match Data**.</span></span>  
  
2.  <span data-ttu-id="8a34a-122">Nell'elenco **Knowledge Base DQS** selezionare il nome della Knowledge Base personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8a34a-122">From the **DQS Knowledge Base** list, select the name of your custom knowledge base.</span></span>  
  
3.  <span data-ttu-id="8a34a-123">Per ogni colonna nel foglio di lavoro, selezionare un dominio DQS.</span><span class="sxs-lookup"><span data-stu-id="8a34a-123">For each column in the worksheet, select a DQS domain.</span></span>  
  
4.  <span data-ttu-id="8a34a-124">Dopo aver eseguito il mapping di tutti i domini DQS alle colonne nel foglio di lavoro, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a34a-124">When all DQS domains are mapped to columns in the worksheet, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8a34a-125">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8a34a-125">Next Steps</span></span>  
  
-   <span data-ttu-id="8a34a-126">Visualizzare informazioni aggiuntive per determinare quali dati sono simili.</span><span class="sxs-lookup"><span data-stu-id="8a34a-126">View additional information to determine which data is similar.</span></span> <span data-ttu-id="8a34a-127">Per altre informazioni, vedere [Colonne corrispondenti Data Quality &#40;componente aggiuntivo MDS per Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8a34a-127">For more information, see [Data Quality Matching Columns &#40;MDS Add-in for Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a34a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a34a-128">See Also</span></span>  
 <span data-ttu-id="8a34a-129">[Corrispondenza Data Quality nel Componente aggiuntivo MDS per Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="8a34a-129">[Data Quality Matching in the MDS Add-in for Excel](data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="8a34a-130">Corrispondenza di dati</span><span class="sxs-lookup"><span data-stu-id="8a34a-130">Data Matching</span></span>](../../data-quality-services/data-matching.md)  
  
  
