---
title: Tipo di connessione Oracle (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9db86dd2-beda-42d8-8af7-2629d58a8e3d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e9bf19953c5d2dc2f818eddcacf445e641972d4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628479"
---
# <a name="oracle-connection-type-ssrs"></a><span data-ttu-id="929db-102">Tipo di connessione Oracle (SSRS)</span><span class="sxs-lookup"><span data-stu-id="929db-102">Oracle Connection Type (SSRS)</span></span>
  <span data-ttu-id="929db-103">Per utilizzare dati di un database Oracle nel report, è necessario disporre di un set di dati basato su un'origine dati del report di tipo Oracle.</span><span class="sxs-lookup"><span data-stu-id="929db-103">To use data from an Oracle database in your report, you must you must have a dataset that is based on a report data source of type Oracle.</span></span> <span data-ttu-id="929db-104">Questo tipo di origine dati predefinita è basata sul provider gestito .NET Framework per Oracle e richiede un componente software client Oracle.</span><span class="sxs-lookup"><span data-stu-id="929db-104">This built-in data source type is based on the .NET Framework Managed Provider for Oracle and requires an Oracle client software component.</span></span>  
  
 <span data-ttu-id="929db-105">Usare le informazioni presenti in questo argomento per compilare un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="929db-105">Use the information in this topic to build a data source.</span></span> <span data-ttu-id="929db-106">Per istruzioni dettagliate, vedere [aggiungere e verificare una connessione dati o un'origine dati &#40;Generatore report e SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="929db-106">For step-by-step instructions, see [Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](add-and-verify-a-data-connection-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="connection-string"></a><a name="Connection"></a><span data-ttu-id="929db-107">Stringa di connessione</span><span class="sxs-lookup"><span data-stu-id="929db-107">Connection String</span></span>  
 <span data-ttu-id="929db-108">Contattare l'amministratore del database per ottenere le informazioni di connessione e le credenziali da utilizzare per connettersi all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="929db-108">Contact your database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="929db-109">Nella stringa di connessione di esempio seguente viene specificato un database Oracle nel server "Oracle9" che utilizza Unicode.</span><span class="sxs-lookup"><span data-stu-id="929db-109">The following connection string example specifies an Oracle database on the server named "Oracle9" using Unicode.</span></span> <span data-ttu-id="929db-110">Il nome del server deve corrispondere a quello definito nel file di configurazione Tnsnames.ora come nome dell'istanza del server Oracle.</span><span class="sxs-lookup"><span data-stu-id="929db-110">The server name must match what is defined in the Tnsnames.ora configuration file as the Oracle server instance name.</span></span>  
  
```  
Data Source="Oracle9"; Unicode="True"  
```  
  
 <span data-ttu-id="929db-111">Per altre informazioni ed esempi di stringhe di connessione, vedere [Connessioni dati, origini dati e stringhe di connessione in Generatore report](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="929db-111">For more information about connection string examples, see [Data Connections, Data Sources, and Connection Strings in Report Builder](../data-connections-data-sources-and-connection-strings-in-report-builder.md).</span></span>  
  
##  <a name="credentials"></a><a name="Credentials"></a><span data-ttu-id="929db-112">Credenziali</span><span class="sxs-lookup"><span data-stu-id="929db-112">Credentials</span></span>  
 <span data-ttu-id="929db-113">Le credenziali sono necessarie per eseguire query, nonché per visualizzare l'anteprima del report in locale e dal server di report.</span><span class="sxs-lookup"><span data-stu-id="929db-113">Credentials are required to run queries, to preview the report locally, and to preview the report from the report server.</span></span>  
  
 <span data-ttu-id="929db-114">Dopo aver pubblicato il report, potrebbe essere necessario modificare le credenziali per l'origine dati affinché quando il report viene eseguito nel server di report, le autorizzazioni per il recupero dei dati risultino valide.</span><span class="sxs-lookup"><span data-stu-id="929db-114">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
 <span data-ttu-id="929db-115">Per ulteriori informazioni, vedere [connessioni dati, origini dati e stringhe di connessione in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) o [specificare le credenziali in Generatore report](../specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="929db-115">For more information, see [Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) or [Specify Credentials in Report Builder](../specify-credentials-in-report-builder.md).</span></span>  
  

  
##  <a name="queries"></a><a name="Query"></a><span data-ttu-id="929db-116">Query</span><span class="sxs-lookup"><span data-stu-id="929db-116">Queries</span></span>  
 <span data-ttu-id="929db-117">Per creare un set di dati, è possibile selezionare una stored procedure in un elenco a discesa oppure creare una query SQL.</span><span class="sxs-lookup"><span data-stu-id="929db-117">To create a dataset, you can either select a stored procedure from a drop-down list or create an SQL query.</span></span> <span data-ttu-id="929db-118">Per compilare una query, è necessario utilizzare la finestra Progettazione query basata su testo.</span><span class="sxs-lookup"><span data-stu-id="929db-118">To build a query, you must use the text-based query designer.</span></span> <span data-ttu-id="929db-119">Per altre informazioni, vedere [Interfaccia utente di Progettazione query basata su testo &#40;Generatore report &#41;](text-based-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="929db-119">For more information, see [Text-based Query Designer User Interface &#40;Report Builder&#41;](text-based-query-designer-user-interface-report-builder.md).</span></span>  
  
 <span data-ttu-id="929db-120">È possibile specificare le stored procedure che restituiscono solo un set di risultati.</span><span class="sxs-lookup"><span data-stu-id="929db-120">You can specify stored procedures that return only one result set.</span></span> <span data-ttu-id="929db-121">Le query basate su cursori non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="929db-121">Using cursor-based queries are not supported.</span></span>  
  
##  <a name="parameters"></a><a name="Parameters"></a> <span data-ttu-id="929db-122">Parametri</span><span class="sxs-lookup"><span data-stu-id="929db-122">Parameters</span></span>  
 <span data-ttu-id="929db-123">Se la query include variabili di query, i parametri di report corrispondenti verranno generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="929db-123">If the query includes query variables, corresponding report parameters are automatically generated.</span></span> <span data-ttu-id="929db-124">I parametri denominati sono supportati da questa estensione.</span><span class="sxs-lookup"><span data-stu-id="929db-124">Named parameters are supported by this extension.</span></span> <span data-ttu-id="929db-125">Per Oracle versione 9 o successive, i parametri multivalore sono supportati.</span><span class="sxs-lookup"><span data-stu-id="929db-125">For Oracle version 9 or later, multivalue parameters are supported.</span></span>  
  
 <span data-ttu-id="929db-126">I parametri di report vengono creati con valori di proprietà predefiniti che all'occorrenza possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="929db-126">Report parameters are created with default property values that you might need to modify.</span></span> <span data-ttu-id="929db-127">Ad esempio, i dati di ogni parametro di report sono di tipo **Text**.</span><span class="sxs-lookup"><span data-stu-id="929db-127">For example, each report parameter is data type **Text**.</span></span> <span data-ttu-id="929db-128">Dopo aver creato i parametri di report, potrebbe essere necessario modificare i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="929db-128">After the report parameters are created, you might have to change default values.</span></span> <span data-ttu-id="929db-129">Per ulteriori informazioni, vedere la pagina relativa al [Parametri report &#40;Generatore report e Progettazione report&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="929db-129">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  

  
##  <a name="remarks"></a><a name="Remarks"></a> <span data-ttu-id="929db-130">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="929db-130">Remarks</span></span>  
 <span data-ttu-id="929db-131">Prima di poter connettere un'origine dati Oracle, l'amministratore di sistema deve installare la versione del provider di dati .NET per Oracle che supporta il recupero di dati dal database Oracle.</span><span class="sxs-lookup"><span data-stu-id="929db-131">Before you can connect an Oracle data source, the system administrator must have installed the version of the .NET Data Provider for Oracle that supports retrieving data from the Oracle database.</span></span> <span data-ttu-id="929db-132">Il provider di dati deve essere installato nello stesso computer di Generatore report e anche nel server di report.</span><span class="sxs-lookup"><span data-stu-id="929db-132">This data provider must be installed on the same computer as Report Builder and also on the report server.</span></span>  
  
 <span data-ttu-id="929db-133">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="929db-133">For more information, see the following:</span></span>  
  
-   <span data-ttu-id="929db-134">[Utilizzo del provider di dati .NET Framework per Oracle](https://go.microsoft.com/fwlink/?LinkId=112314) nel sito msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="929db-134">[Using the .NET Framework Data Provider for Oracle](https://go.microsoft.com/fwlink/?LinkId=112314) on msdn.microsoft.com</span></span>  
  
-   [<span data-ttu-id="929db-135">Come utilizzare Reporting Services per configurare e accedere a un'origine dati Oracle</span><span class="sxs-lookup"><span data-stu-id="929db-135">How to use Reporting Services to configure and to access an Oracle data source</span></span>](https://support.microsoft.com/kb/834305)  
  
-   [<span data-ttu-id="929db-136">Come aggiungere autorizzazioni per l'entità di sicurezza SERVIZIO DI RETE</span><span class="sxs-lookup"><span data-stu-id="929db-136">How to add permissions for the NETWORK SERVICE security principal</span></span>](https://support.microsoft.com/kb/870668)  
  
###### <a name="alternate-data-extensions"></a><span data-ttu-id="929db-137">Estensioni per i dati alternative</span><span class="sxs-lookup"><span data-stu-id="929db-137">Alternate Data Extensions</span></span>  
 <span data-ttu-id="929db-138">È inoltre possibile recuperare dati da un database Oracle tramite un tipo di origine dati OLE DB.</span><span class="sxs-lookup"><span data-stu-id="929db-138">You can also retrieve data from an Oracle database by using an OLE DB data source type.</span></span> <span data-ttu-id="929db-139">Per altre informazioni, vedere [Tipo di connessione OLE DB &#40;SSRS&#41;](ole-db-connection-type-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="929db-139">For more information, see [OLE DB Connection Type &#40;SSRS&#41;](ole-db-connection-type-ssrs.md).</span></span>  
  
###### <a name="report-models"></a><span data-ttu-id="929db-140">Modelli di report</span><span class="sxs-lookup"><span data-stu-id="929db-140">Report Models</span></span>  
 <span data-ttu-id="929db-141">È possibile creare anche modelli basati su un database Oracle.</span><span class="sxs-lookup"><span data-stu-id="929db-141">You can also create models based on an Oracle database.</span></span>  
  
###### <a name="platform-and-version-information"></a><span data-ttu-id="929db-142">Informazioni sulla piattaforma e sulla versione</span><span class="sxs-lookup"><span data-stu-id="929db-142">Platform and Version Information</span></span>  
 <span data-ttu-id="929db-143">Per altre informazioni sul supporto della piattaforma e della versione, vedere [Origini dati supportate da Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) nella documentazione relativa a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] inclusa nella [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [documentazione online](https://go.microsoft.com/fwlink/?linkid=121312) di .</span><span class="sxs-lookup"><span data-stu-id="929db-143">For more information about platform and version support, see [Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  

  
##  <a name="how-to-topics"></a><a name="HowTo"></a><span data-ttu-id="929db-144">Procedure</span><span class="sxs-lookup"><span data-stu-id="929db-144">How-To Topics</span></span>  
 <span data-ttu-id="929db-145">In questa sezione sono contenute istruzioni dettagliate per l'utilizzo di connessioni dati, origini dati e set di dati.</span><span class="sxs-lookup"><span data-stu-id="929db-145">This section contains step-by-step instructions for working with data connections, data sources, and datasets.</span></span>  
  
 [<span data-ttu-id="929db-146">Aggiungere e verificare una connessione dati o un'origine dati &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="929db-146">Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;</span></span>](add-and-verify-a-data-connection-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="929db-147">Creare un set di dati condiviso o un set di dati incorporato &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="929db-147">Create a Shared Dataset or Embedded Dataset &#40;Report Builder and SSRS&#41;</span></span>](create-a-shared-dataset-or-embedded-dataset-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="929db-148">Aggiungere un filtro a un set di dati &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="929db-148">Add a Filter to a Dataset &#40;Report Builder and SSRS&#41;</span></span>](add-a-filter-to-a-dataset-report-builder-and-ssrs.md)  
  
 
  
##  <a name="related-sections"></a><a name="Related"></a><span data-ttu-id="929db-149">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="929db-149">Related Sections</span></span>  
 <span data-ttu-id="929db-150">In queste sezioni della documentazione sono incluse informazioni concettuali approfondite sui dati dei report, nonché le informazioni necessarie sulle procedure per definire, personalizzare e usare parti di un report correlate ai dati.</span><span class="sxs-lookup"><span data-stu-id="929db-150">These sections of the documentation provide in-depth conceptual information about report data, as well as procedural information about how to define, customize, and use parts of a report that are related to data.</span></span>  
  
 [<span data-ttu-id="929db-151">Aggiungere dati a un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="929db-151">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-datasets-ssrs.md)  
 <span data-ttu-id="929db-152">Viene fornita una panoramica sull'accesso ai dati del report.</span><span class="sxs-lookup"><span data-stu-id="929db-152">Provides an overview of accessing data for your report.</span></span>  
  
 [<span data-ttu-id="929db-153">Connessioni dati, origini dati e stringhe di connessione in Generatore report</span><span class="sxs-lookup"><span data-stu-id="929db-153">Data Connections, Data Sources, and Connection Strings in Report Builder</span></span>](../data-connections-data-sources-and-connection-strings-in-report-builder.md)  
 <span data-ttu-id="929db-154">Vengono fornite informazioni sulle connessioni dati e sulle origini dati.</span><span class="sxs-lookup"><span data-stu-id="929db-154">Provides information about data connections and data sources.</span></span>  
  
 [<span data-ttu-id="929db-155">Set di dati condivisi e incorporati del report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="929db-155">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
 <span data-ttu-id="929db-156">Vengono fornite informazioni sui set di dati incorporati e condivisi.</span><span class="sxs-lookup"><span data-stu-id="929db-156">Provides information about embedded and shared datasets.</span></span>  
  
 [<span data-ttu-id="929db-157">Raccolta di campi del set di dati &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="929db-157">Dataset Fields Collection &#40;Report Builder and SSRS&#41;</span></span>](dataset-fields-collection-report-builder-and-ssrs.md)  
 <span data-ttu-id="929db-158">Vengono fornite informazioni sulla raccolta di campi di set di dati generata dalla query.</span><span class="sxs-lookup"><span data-stu-id="929db-158">Provides information about the dataset field collection generated by the query.</span></span>  
  
 <span data-ttu-id="929db-159">[Origini dati supportate da Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) nella documentazione relativa a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] inclusa nella [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [documentazione online](https://go.microsoft.com/fwlink/?linkid=121312) di .</span><span class="sxs-lookup"><span data-stu-id="929db-159">[Data Sources Supported by Reporting Services &#40;SSRS&#41;](../create-deploy-and-manage-mobile-and-paginated-reports.md) in the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
 <span data-ttu-id="929db-160">Vengono fornite informazioni dettagliate sul supporto delle piattaforme e delle versioni per ogni estensione per i dati.</span><span class="sxs-lookup"><span data-stu-id="929db-160">Provides in-depth information about platform and version support for each data extension.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="929db-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="929db-161">See Also</span></span>  
 <span data-ttu-id="929db-162">[Parametri del report &#40;Generatore report e Progettazione report&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="929db-162">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="929db-163">[Filtrare, raggruppare e ordinare i dati &#40;Generatore report e SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="929db-163">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](../report-design/filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="929db-164">Espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="929db-164">Expressions &#40;Report Builder and SSRS&#41;</span></span>](../report-design/expressions-report-builder-and-ssrs.md)  
  
  
