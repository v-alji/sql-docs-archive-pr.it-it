---
title: Operazioni del servizio Web per categoria (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: e3f346b5-7e26-481d-9821-1846e2e91289
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0f7dd682f55c16c6dcbff9f0f669593a10486da6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635707"
---
# <a name="categorized-web-service-operations-master-data-services"></a><span data-ttu-id="ceb3d-102">Operazioni del servizio Web per categoria (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ceb3d-102">Categorized Web Service Operations (Master Data Services)</span></span>
  <span data-ttu-id="ceb3d-103">Il servizio Web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] contiene un set completo di operazioni che consentono di scrivere il codice per controllare tutte le caratteristiche implementate da [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-103">The [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service contains a complete set of operations that let you write code to control all of the features that [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] does through its user interface.</span></span> <span data-ttu-id="ceb3d-104">Le operazioni del servizio Web sono definite dall'interfaccia <xref:Microsoft.MasterDataServices.IService> e vengono implementate come metodi nella classe <xref:Microsoft.MasterDataServices.ServiceClient>.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-104">The web service operations are defined by the <xref:Microsoft.MasterDataServices.IService> interface and are implemented as methods in the <xref:Microsoft.MasterDataServices.ServiceClient> class.</span></span> <span data-ttu-id="ceb3d-105">In questo argomento le operazioni del servizio Web vengono raggruppate in categorie concettuali per consentire all'utente di capire come utilizzare l'API del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-105">This topic groups the web service operations into conceptual categories to help you understand how to use the web service API.</span></span>  
  
## <a name="model-operations"></a><span data-ttu-id="ceb3d-106">Operazioni di modelli</span><span class="sxs-lookup"><span data-stu-id="ceb3d-106">Model Operations</span></span>  
 <span data-ttu-id="ceb3d-107">Queste operazioni vengono utilizzate per creare, aggiornare ed eliminare i modelli, nonché per gestire tutto il contenuto di un modello, ad esempio entità, gerarchie e versioni.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-107">These operations are used to create, update, and delete models, as well as to operate on all the contents of a model, such as entities, hierarchies, and versions.</span></span> <span data-ttu-id="ceb3d-108">Per altre informazioni, vedere [Modelli &#40;Master Data Services&#41;](../models-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3d-108">For more information, see [Models &#40;Master Data Services&#41;](../models-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>|  
  
## <a name="entity-operations"></a><span data-ttu-id="ceb3d-109">Operazioni di entità</span><span class="sxs-lookup"><span data-stu-id="ceb3d-109">Entity Operations</span></span>  
 <span data-ttu-id="ceb3d-110">Queste operazioni vengono utilizzate per creare, aggiornare ed eliminare i membri di una singola entità.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-110">These operations are used to create, update, and delete the members of a single entity.</span></span> <span data-ttu-id="ceb3d-111">Per altre informazioni, vedere [Entità &#40;Master Data Services&#41;](../entities-master-data-services.md) e [Membri &#40;Master Data Services&#41;](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3d-111">For more information, see [Entities &#40;Master Data Services&#41;](../entities-master-data-services.md) and [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberKeyLookup%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMembersUpdate%2A>|  
  
## <a name="member-operations"></a><span data-ttu-id="ceb3d-112">Operazioni di membri</span><span class="sxs-lookup"><span data-stu-id="ceb3d-112">Member Operations</span></span>  
 <span data-ttu-id="ceb3d-113">Queste operazioni vengono utilizzate per ottenere, aggiornare ed eliminare i membri.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-113">These operations are used to get, update, and delete members.</span></span> <span data-ttu-id="ceb3d-114">Il set di membri utilizzato può contenere membri di più entità.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-114">The set of members operated on can contain members from multiple entities.</span></span> <span data-ttu-id="ceb3d-115">Per altre informazioni, vedere [Membri &#40;Master Data Services&#41;](../members-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3d-115">For more information, see [Members &#40;Master Data Services&#41;](../members-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkMerge%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersBulkUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ModelMembersGet%2A>|  
  
## <a name="attribute-and-hierarchy-operations"></a><span data-ttu-id="ceb3d-116">Operazioni di attributi e gerarchie</span><span class="sxs-lookup"><span data-stu-id="ceb3d-116">Attribute and Hierarchy Operations</span></span>  
 <span data-ttu-id="ceb3d-117">Queste operazioni vengono utilizzate per ottenere informazioni su attributi e gerarchie.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-117">These operations are used to get attribute and hierarchy information.</span></span> <span data-ttu-id="ceb3d-118">Gli attributi e le gerarchie possono essere modificati anche mediante le operazioni di modelli, ad esempio <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-118">Attributes and hierarchies can also be modified by using the model operations, such as <xref:Microsoft.MasterDataServices.ServiceClient.MetadataUpdate%2A>.</span></span> <span data-ttu-id="ceb3d-119">Per altre informazioni, vedere [Attributi &#40;Master Data Services&#41;](../attributes-master-data-services.md) e [Gerarchie &#40;Master Data Services&#41;](../hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3d-119">For more information, see [Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) and [Hierarchies &#40;Master Data Services&#41;](../hierarchies-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAttributesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.HierarchyMembersGet%2A>|  
  
## <a name="business-rule-operations"></a><span data-ttu-id="ceb3d-120">Operazioni di regole business</span><span class="sxs-lookup"><span data-stu-id="ceb3d-120">Business Rule Operations</span></span>  
 <span data-ttu-id="ceb3d-121">Queste operazioni vengono utilizzate per creare, aggiornare, eliminare e pubblicare le regole business.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-121">These operations are used to create, update, delete, and publish business rules.</span></span> <span data-ttu-id="ceb3d-122">Per altre informazioni, vedere [Regole di business &#40;Master Data Services&#41;](../business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3d-122">For more information, see [Business Rules &#40;Master Data Services&#41;](../business-rules-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPaletteGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesPublish%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.BusinessRulesUpdate%2A>|  
  
## <a name="annotation-operations"></a><span data-ttu-id="ceb3d-123">Operazioni di annotazioni</span><span class="sxs-lookup"><span data-stu-id="ceb3d-123">Annotation Operations</span></span>  
 <span data-ttu-id="ceb3d-124">Queste operazioni vengono utilizzate per creare, aggiornare ed eliminare le annotazioni.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-124">These operations are used to create, update, and delete annotations.</span></span> <span data-ttu-id="ceb3d-125">Per altre informazioni, vedere [Annotazioni &#40;Master Data Services&#41;](../annotations-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3d-125">For more information, see [Annotations &#40;Master Data Services&#41;](../annotations-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.AnnotationsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityMemberAnnotationsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionAnnotationsGet%2A>|  
  
## <a name="transaction-operations"></a><span data-ttu-id="ceb3d-126">Operazioni di transazioni</span><span class="sxs-lookup"><span data-stu-id="ceb3d-126">Transaction Operations</span></span>  
 <span data-ttu-id="ceb3d-127">Queste operazioni vengono utilizzate per ottenere e invertire le transazioni.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-127">These operations are used to get and reverse transactions.</span></span> <span data-ttu-id="ceb3d-128">Per altre informazioni, vedere [Transazioni &#40;Master Data Services&#41;](../transactions-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3d-128">For more information, see [Transactions &#40;Master Data Services&#41;](../transactions-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.TransactionsReverse%2A>|  
  
## <a name="version-and-validation-operations"></a><span data-ttu-id="ceb3d-129">Operazioni di versioni e convalida</span><span class="sxs-lookup"><span data-stu-id="ceb3d-129">Version and Validation Operations</span></span>  
 <span data-ttu-id="ceb3d-130">Queste operazioni vengono utilizzate per copiare e convalidare le versioni.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-130">These operations are used to copy and validate versions.</span></span> <span data-ttu-id="ceb3d-131">Per altre informazioni, vedere [Versioni &#40;Master Data Services&#41;](../versions-master-data-services.md) e [Convalida &#40;Master Data Services&#41;](../validation-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3d-131">For more information, see [Versions &#40;Master Data Services&#41;](../versions-master-data-services.md) and [Validation &#40;Master Data Services&#41;](../validation-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.VersionCopy%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ValidationProcess%2A>|  
  
## <a name="data-quality-operations"></a><span data-ttu-id="ceb3d-132">Operazioni di qualità dei dati</span><span class="sxs-lookup"><span data-stu-id="ceb3d-132">Data Quality Operations</span></span>  
 <span data-ttu-id="ceb3d-133">Queste operazioni vengono utilizzate per eseguire le attività relative alla qualità dei dati e per esaminarne i risultati.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-133">These operations are used to perform data quality tasks and to examine their results.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityCleansingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityMatchingOperationCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStart%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityInstalledState%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityKnowledgeBasesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationResultsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.DataQualityOperationStatus%2A>|  
  
## <a name="data-import-operations"></a><span data-ttu-id="ceb3d-134">Operazioni di importazione dei dati</span><span class="sxs-lookup"><span data-stu-id="ceb3d-134">Data Import Operations</span></span>  
 <span data-ttu-id="ceb3d-135">Queste operazioni vengono utilizzate per importare i dati in un database di [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ceb3d-135">These operations are used to import data into a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="ceb3d-136">Per altre informazioni, vedere [Importazione dati &#40;Master Data Services&#41;](../overview-importing-data-from-tables-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3d-136">For more information, see [Data Import &#40;Master Data Services&#41;](../overview-importing-data-from-tables-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingLoad%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.EntityStagingProcess%2A>|  
  
 <span data-ttu-id="ceb3d-137">Le operazioni seguenti vengono utilizzate per importare i dati mediante il processo di gestione temporanea incluso in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ceb3d-137">The following operations are used to import data by using the staging process included in [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)].</span></span> <span data-ttu-id="ceb3d-138">Queste operazioni devono essere utilizzate solo per supportare i database esistenti.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-138">These operations should be used only to support existing databases.</span></span> <span data-ttu-id="ceb3d-139">Per un nuovo progetto di sviluppo utilizzare le operazioni elencate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-139">For new development, use the previously listed operations.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingClear%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingNameCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.StagingProcess%2A>|  
  
## <a name="data-export-operations"></a><span data-ttu-id="ceb3d-140">Operazioni di esportazione dei dati</span><span class="sxs-lookup"><span data-stu-id="ceb3d-140">Data Export Operations</span></span>  
 <span data-ttu-id="ceb3d-141">Queste operazioni vengono utilizzate per esportare i dati tramite l'utilizzo di viste sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-141">These operations are used to export data through the use of subscription views.</span></span> <span data-ttu-id="ceb3d-142">Per ulteriori informazioni, vedere [esportazione di dati &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3d-142">For more information, see [Exporting Data &#40;Master Data Services&#41;](../overview-exporting-data-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ExportViewUpdate%2A>|  
  
## <a name="security-operations"></a><span data-ttu-id="ceb3d-143">Operazioni per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="ceb3d-143">Security Operations</span></span>  
 <span data-ttu-id="ceb3d-144">Queste operazioni vengono utilizzate per modificare le impostazioni di sicurezza che controllano l'accesso al database di [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ceb3d-144">These operations are used to modify the security settings that control access to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="ceb3d-145">Per altre informazioni, vedere [Sicurezza &#40;Master Data Services&#41;](../security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ceb3d-145">For more information, see [Security &#40;Master Data Services&#41;](../security-master-data-services.md).</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrincipalsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesClone%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesCreate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SecurityPrivilegesUpdate%2A>|  
  
## <a name="system-operations"></a><span data-ttu-id="ceb3d-146">Operazioni di sistema</span><span class="sxs-lookup"><span data-stu-id="ceb3d-146">System Operations</span></span>  
 <span data-ttu-id="ceb3d-147">Queste operazioni vengono utilizzate per ottenere e aggiornare le impostazioni di sistema e le preferenze dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ceb3d-147">These operations are used to get and update system settings and user preferences.</span></span>  
  
||  
|-|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceCheck%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.ServiceVersionGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemDomainListGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemPropertiesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.SystemSettingsUpdate%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesDelete%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesGet%2A>|  
|<xref:Microsoft.MasterDataServices.ServiceClient.UserPreferencesUpdate%2A>|  
  
  
