---
title: Progettare la query | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptwizard.designquery.f1
ms.assetid: 2dad800f-10a1-453c-8761-2935b9826d84
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9b56d99ec11b50ce53ef223a01eb5fc2766238ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719679"
---
# <a name="design-the-query"></a><span data-ttu-id="eeabc-102">Progettazione query</span><span class="sxs-lookup"><span data-stu-id="eeabc-102">Design the Query</span></span>
  <span data-ttu-id="eeabc-103">Utilizzare questa pagina della Creazione guidata report per creare una query immettendola manualmente, utilizzando Generatore query per compilare una query in modo interattivo o importando la query da un altro report.</span><span class="sxs-lookup"><span data-stu-id="eeabc-103">Use this page of the Report Wizard to create a query by typing the query manually, by using Query Builder to interactively build a query, or by importing a query from another report.</span></span>  
  
 <span data-ttu-id="eeabc-104">Il tipo di origine dati selezionato nella pagina Selezione origine dati, una pagina precedente della Creazione guidata report, determina la query che è possibile immettere in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="eeabc-104">The data source type you chose on the Select the Data Source page, a previous page in the Report Wizard, determines the query you can enter on this page.</span></span> <span data-ttu-id="eeabc-105">Se, ad esempio, il tipo di origine dati è [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , è possibile immettere [!INCLUDE[tsql](../includes/tsql-md.md)] istruzioni o nomi di stored procedure.</span><span class="sxs-lookup"><span data-stu-id="eeabc-105">For example, if the data source type is [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you can enter [!INCLUDE[tsql](../includes/tsql-md.md)] statements or stored procedure names.</span></span> <span data-ttu-id="eeabc-106">Se il tipo di origine dati è [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , il riquadro query è disabilitato e non è possibile immettere una query direttamente.</span><span class="sxs-lookup"><span data-stu-id="eeabc-106">If the data source type is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], the Query pane is disabled and you cannot enter a query directly.</span></span> <span data-ttu-id="eeabc-107">È possibile specificare la query utilizzando Generatore di query.</span><span class="sxs-lookup"><span data-stu-id="eeabc-107">You can specify the query by using Query Builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="eeabc-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="eeabc-108">Options</span></span>  
 <span data-ttu-id="eeabc-109">**Stringa di query**</span><span class="sxs-lookup"><span data-stu-id="eeabc-109">**Query string**</span></span>  
 <span data-ttu-id="eeabc-110">Consente di digitare una query che recupera i dati da utilizzare nel report.</span><span class="sxs-lookup"><span data-stu-id="eeabc-110">Type a query that retrieves the data you want to use in your report.</span></span>  
  
 <span data-ttu-id="eeabc-111">**Generatore di query**</span><span class="sxs-lookup"><span data-stu-id="eeabc-111">**Query Builder**</span></span>  
 <span data-ttu-id="eeabc-112">Fare clic su **Generatore di query** per aprire una finestra Progettazione query per l'origine dati o importare una query da un altro report.</span><span class="sxs-lookup"><span data-stu-id="eeabc-112">Click **Query Builder** to open a query designer for the data source, or to import a query from another report.</span></span>  
  
 <span data-ttu-id="eeabc-113">Per ulteriori informazioni sugli strumenti di progettazione query, vedere [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span><span class="sxs-lookup"><span data-stu-id="eeabc-113">For more information about query designers, see [Reporting Services Query Designers](../../2014/reporting-services/reporting-services-query-designers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeabc-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="eeabc-114">Example</span></span>  
 <span data-ttu-id="eeabc-115">Per il tipo di origine dati **Microsoft SQL Server**, la query seguente recupera un elenco di cognomi dalla [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] tabella di database `Person` .</span><span class="sxs-lookup"><span data-stu-id="eeabc-115">For the data source type **Microsoft SQL Server**, the following query retrieves a list of last names from the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database `Person` table.</span></span>  
  
```  
SELECT LastName FROM Person.Person;  
```  
  
 <span data-ttu-id="eeabc-116">Per il tipo di origine dati **Microsoft SQL Server**, la query seguente esegue il [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] stored procedure `uspGetEmployeeManagers` per il dipendente con numero di identificazione 1:</span><span class="sxs-lookup"><span data-stu-id="eeabc-116">For the data source type **Microsoft SQL Server**, the following query runs the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] stored procedure `uspGetEmployeeManagers` for the employee with identification number 1:</span></span>  
  
```  
EXEC uspgetEmployeeManagers '1';  
```  
  
## <a name="see-also"></a><span data-ttu-id="eeabc-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eeabc-117">See Also</span></span>  
 <span data-ttu-id="eeabc-118">[Guida della creazione guidata report](../../2014/reporting-services/report-wizard-help.md) </span><span class="sxs-lookup"><span data-stu-id="eeabc-118">[Report Wizard Help](../../2014/reporting-services/report-wizard-help.md) </span></span>  
 <span data-ttu-id="eeabc-119">[Set di set di impostazioni e set di impostazioni di set di report incorporati &#40;Generatore report e SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="eeabc-119">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="eeabc-120">Aggiungere dati a un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="eeabc-120">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
