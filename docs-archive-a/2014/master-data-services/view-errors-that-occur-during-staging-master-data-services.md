---
title: Visualizzare gli errori che si verificano durante il processo di gestione temporanea (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- staging process [Master Data Services], viewing errors
ms.assetid: 6d2bff84-624b-47fc-a4a5-d9ea01d13412
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3b39d039b29090f3021c764126ebb782ce25cbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715472"
---
# <a name="view-errors-that-occur-during-the-staging-process-master-data-services"></a><span data-ttu-id="352f9-102">Visualizzare errori che si verificano durante il processo di gestione temporanea (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="352f9-102">View Errors that Occur During the Staging Process (Master Data Services)</span></span>
  <span data-ttu-id="352f9-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], è possibile visualizzare errori che si verificano durante il processo di gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="352f9-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can view errors that occur during the staging process.</span></span> <span data-ttu-id="352f9-104">Nel database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , sono disponibili due viste che mostrano errori:</span><span class="sxs-lookup"><span data-stu-id="352f9-104">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, there are two views that show errors:</span></span>  
  
-   <span data-ttu-id="352f9-105">stg.viw_name_MemberErrorDetails per foglia o aggiornamenti dei membri consolidati.</span><span class="sxs-lookup"><span data-stu-id="352f9-105">stg.viw_name_MemberErrorDetails for leaf or consolidated member updates.</span></span>  
  
-   <span data-ttu-id="352f9-106">stg.viw_name_RelationshipErrorDetails per aggiornamenti delle relazioni di gerarchia.</span><span class="sxs-lookup"><span data-stu-id="352f9-106">stg.viw_name_RelationshipErrorDetails for hierarchy relationship updates.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="352f9-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="352f9-107">Prerequisites</span></span>  
 <span data-ttu-id="352f9-108">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="352f9-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="352f9-109">Nel database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , è necessario disporre delle autorizzazioni SELECT per la vista stg.viw_name_MemberErrorDetails o stg.viw_name_RelationshipErrorDetails.</span><span class="sxs-lookup"><span data-stu-id="352f9-109">In the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database, you must have SELECT permissions to either the stg.viw_name_MemberErrorDetails or stg.viw_name_RelationshipErrorDetails view.</span></span>  
  
-   <span data-ttu-id="352f9-110">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="352f9-110">You must be a model administrator.</span></span> <span data-ttu-id="352f9-111">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="352f9-111">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-view-staging-errors"></a><span data-ttu-id="352f9-112">Per visualizzare gli errori di gestione temporanea</span><span class="sxs-lookup"><span data-stu-id="352f9-112">To view staging errors</span></span>  
  
1.  <span data-ttu-id="352f9-113">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e connettersi all'istanza [!INCLUDE[ssDE](../includes/ssde-md.md)] per il database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="352f9-113">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="352f9-114">Aprire una nuova query.</span><span class="sxs-lookup"><span data-stu-id="352f9-114">Open a new query.</span></span>  
  
3.  <span data-ttu-id="352f9-115">Digitare il testo seguente, sostituendo il nome con quello della tabella di staging, ad esempio, viw_Product_MemberErrorDetails.</span><span class="sxs-lookup"><span data-stu-id="352f9-115">Type the following text, replacing name with the name of your staging table, for example, viw_Product_MemberErrorDetails.</span></span>  
  
     `SELECT * FROM stg.viw_name_MemberErrorDetails`  
  
4.  <span data-ttu-id="352f9-116">Eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="352f9-116">Excecute the query.</span></span> <span data-ttu-id="352f9-117">I dettagli dell'errore vengono visualizzati nel campo **ErrorDescription** .</span><span class="sxs-lookup"><span data-stu-id="352f9-117">Error details are displayed in the **ErrorDescription** field.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="352f9-118">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="352f9-118">Next Steps</span></span>  
 <span data-ttu-id="352f9-119">Per informazioni dettagliate sui messaggi di errore, vedere [Errori del processo di gestione temporanea &#40;Master Data Services&#41;](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="352f9-119">For more details on error messages, see [Staging Process Errors &#40;Master Data Services&#41;](../../2014/master-data-services/staging-process-errors-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="352f9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="352f9-120">See Also</span></span>  
 <span data-ttu-id="352f9-121">[Importazione dati &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="352f9-121">[Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md) </span></span>  
 [<span data-ttu-id="352f9-122">Risoluzione dei problemi relativi al processo di gestione temporanea (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="352f9-122">Troubleshooting the Staging Process (Master Data Services)</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/troubleshooting-the-staging-process-master-data-services.aspx)  
  
  
