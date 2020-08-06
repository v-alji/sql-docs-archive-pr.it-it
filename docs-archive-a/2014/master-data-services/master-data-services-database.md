---
title: Database Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- database [Master Data Services], about the database
- database [Master Data Services]
ms.assetid: 5f590cc1-6ec2-4b8c-a598-03de0f6051a0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7e4bae180dfb7c9051d5445a689c44978ef73bfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629879"
---
# <a name="master-data-services-database"></a><span data-ttu-id="ccbc4-102">Database Master Data Services</span><span class="sxs-lookup"><span data-stu-id="ccbc4-102">Master Data Services Database</span></span>
  <span data-ttu-id="ccbc4-103">Nel database sono contenute tutte le informazioni per il sistema [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ccbc4-103">The database contains all of the information for the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span> <span data-ttu-id="ccbc4-104">È l'elemento centrale di una distribuzione di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ccbc4-104">It is central to a [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] deployment.</span></span> <span data-ttu-id="ccbc4-105">Il database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ccbc4-105">The [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database:</span></span>  
  
-   <span data-ttu-id="ccbc4-106">Archivia le impostazioni, gli oggetti di database e i dati necessari per il sistema [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ccbc4-106">Stores the settings, database objects, and data required by the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system.</span></span>  
  
-   <span data-ttu-id="ccbc4-107">Contiene le tabelle di staging utilizzate per elaborare i dati provenienti dai sistemi di origine.</span><span class="sxs-lookup"><span data-stu-id="ccbc4-107">Contains staging tables that are used to process data from source systems.</span></span>  
  
-   <span data-ttu-id="ccbc4-108">Fornisce oggetti dello schema e di database per l'archiviazione dei dati master provenienti dai sistemi di origine.</span><span class="sxs-lookup"><span data-stu-id="ccbc4-108">Provides a schema and database objects to store master data from source systems.</span></span>  
  
-   <span data-ttu-id="ccbc4-109">Supporta le funzionalità di controllo delle versioni, incluse la convalida delle regole business e le notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ccbc4-109">Supports versioning functionality, including business rule validation and e-mail notifications.</span></span>  
  
-   <span data-ttu-id="ccbc4-110">Fornisce le viste per i sistemi di sottoscrizione per il quali è necessario il recupero di dati dal database.</span><span class="sxs-lookup"><span data-stu-id="ccbc4-110">Provides views for subscribing systems that need to retrieve data from the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ccbc4-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="ccbc4-111">In This Section</span></span>  
  
-   [<span data-ttu-id="ccbc4-112">Tabella di gestione temporanea dei membri foglia &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ccbc4-112">Leaf Member Staging Table &#40;Master Data Services&#41;</span></span>](leaf-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="ccbc4-113">Tabella di gestione temporanea di membri consolidati &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ccbc4-113">Consolidated Member Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-member-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="ccbc4-114">Tabella di gestione temporanea delle relazioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ccbc4-114">Relationship Staging Table &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/relationship-staging-table-master-data-services.md)  
  
-   [<span data-ttu-id="ccbc4-115">Errori del processo di gestione temporanea &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ccbc4-115">Staging Process Errors &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/staging-process-errors-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="ccbc4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccbc4-116">See Also</span></span>  
 <span data-ttu-id="ccbc4-117">[Creazione di un database di Master Data Services](install-windows/create-a-master-data-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="ccbc4-117">[Create a Master Data Services Database](install-windows/create-a-master-data-services-database.md) </span></span>  
 <span data-ttu-id="ccbc4-118">[&#40;di sicurezza degli oggetti di database Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ccbc4-118">[Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md) </span></span>  
 [<span data-ttu-id="ccbc4-119">Account di accesso, utenti e ruoli di database &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ccbc4-119">Database Logins, Users, and Roles &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/database-logins-users-and-roles-master-data-services.md)  
  
  
