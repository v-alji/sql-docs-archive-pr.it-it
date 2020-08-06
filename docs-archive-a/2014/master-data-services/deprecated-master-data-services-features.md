---
title: Funzionalità di Master Data Services deprecate in SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d8506bda-66dd-45a4-bfc9-3a10fa665acc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce532e9f407ec475f7e59c0d79659265a9e0bf3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712088"
---
# <a name="deprecated-master-data-services-features-in-sql-server-2014"></a><span data-ttu-id="a9b95-102">Funzionalità deprecate di Master Data Services in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a9b95-102">Deprecated Master Data Services Features in SQL Server 2014</span></span>
  <span data-ttu-id="a9b95-103">In questo argomento verranno descritte le funzionalità deprecate di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] ancora disponibili in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9b95-103">This topic describes the deprecated [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] features that are still available in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a9b95-104">Tali funzionalità verranno rimosse a partire da una delle prossime versioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9b95-104">These features are scheduled to be removed in a future release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a9b95-105">È consigliabile non usare le funzionalità deprecate nelle nuove applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a9b95-105">Deprecated features should not be used in new applications.</span></span>  
  
## <a name="staging-process"></a><span data-ttu-id="a9b95-106">Processo di gestione temporanea</span><span class="sxs-lookup"><span data-stu-id="a9b95-106">Staging Process</span></span>  
 <span data-ttu-id="a9b95-107">Il processo di gestione temporanea utilizzato in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] non è più disponibile nell'applicazione Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] ; tuttavia è ancora disponibile in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9b95-107">The staging process that was used in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] is no longer available in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application; however it is still available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="a9b95-108">Gli errori di gestione temporanea dal processo di gestione temporanea [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] non sono più visualizzati nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="a9b95-108">Staging errors from the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] staging process are no longer displayed in the UI.</span></span> <span data-ttu-id="a9b95-109">I codici di errore popolati durante il processo di gestione temporanea sono ancora disponibili nelle tabelle di staging ed è possibile trovarli qui: [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx) .</span><span class="sxs-lookup"><span data-stu-id="a9b95-109">Error codes that are populated during the staging process are still available in the staging tables, and can be found here: [https://msdn.microsoft.com/library/ff487022.aspx](https://msdn.microsoft.com/library/ff487022.aspx).</span></span>  
  
 <span data-ttu-id="a9b95-110">Le tabelle di staging (tblStgMember, tblStgMemberAttribute e tblStgRelationship) ancora sono disponibili nel database.</span><span class="sxs-lookup"><span data-stu-id="a9b95-110">The staging tables (tblStgMember, tblStgMemberAttribute, and tblStgRelationship) are still available in the database.</span></span> <span data-ttu-id="a9b95-111">La stored procedure utilizzata per iniziare il processo di gestione temporanea (mdm.udpStagingSweep) è ancora disponibile nel database.</span><span class="sxs-lookup"><span data-stu-id="a9b95-111">The stored procedure used to initiate the staging process (mdm.udpStagingSweep) is still available in the database.</span></span>  
  
 <span data-ttu-id="a9b95-112">Sono ancora disponibili i metodi del servizio Web che richiamano il processo di gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="a9b95-112">The web service methods that call the staging process are still available.</span></span>  
  
 <span data-ttu-id="a9b95-113">Il set dell'intervallo di gestione temporanea in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] si applica al processo di gestione temporanea in [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] e in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9b95-113">The staging interval set in [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] applies to the staging process in both [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] and [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="a9b95-114">Un nuovo, più elevato processo di gestione temporanea delle prestazioni è stato implementato in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9b95-114">A new, higher performance staging process has been implemented in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="a9b95-115">Per altre informazioni, vedere [Importazione dati &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a9b95-115">For more information, see [Data Import &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
## <a name="metadata"></a><span data-ttu-id="a9b95-116">Metadati</span><span class="sxs-lookup"><span data-stu-id="a9b95-116">Metadata</span></span>  
 <span data-ttu-id="a9b95-117">Sebbene il modello di metadati è ancora visualizzato nell'applicazione Web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , non deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="a9b95-117">Though the Metadata model is still displayed in the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application, it should not be used.</span></span> <span data-ttu-id="a9b95-118">Verrà rimosso in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="a9b95-118">It will be removed in a future release.</span></span> <span data-ttu-id="a9b95-119">Gli Utenti possono visualizzare anche più metadati nell'area funzionale **Esplora** ed è possibile creare più versioni del modello di metadati.</span><span class="sxs-lookup"><span data-stu-id="a9b95-119">Users can also no longer view metadata in the **Explorer** functional area, and you can no longer create versions of the Metadata model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b95-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9b95-120">See Also</span></span>  
 [<span data-ttu-id="a9b95-121">Funzionalità di Master Data Services non più supportate in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="a9b95-121">Discontinued Master Data Services Features in SQL Server 2014</span></span>](discontinued-master-data-services-features.md)  
  
  
