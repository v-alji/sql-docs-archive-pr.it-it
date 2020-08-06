---
title: Concedere le autorizzazioni per un oggetto origine dati (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.roledesignerdialog.datasources.f1
helpviewer_keywords:
- read/write permissions
- user access rights [Analysis Services], data sources
- security [Analysis Services], data sources
- connection strings [Analysis Services]
- data sources [Analysis Services], security
ms.assetid: b4e302d3-c93b-4383-aa4a-37d15c129830
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0a7de676f5863187c2c137e056392a605af474f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718804"
---
# <a name="grant-permissions-on-a-data-source-object-analysis-services"></a><span data-ttu-id="0a261-102">Concedere le autorizzazioni per un oggetto origine dati (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="0a261-102">Grant permissions on a data source object (Analysis Services)</span></span>
  <span data-ttu-id="0a261-103">In genere la maggior parte degli utenti di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] non necessita dell'accesso alle origini dati sottostanti di un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a261-103">Typically, most users of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not require access to the data sources that underlie an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="0a261-104">Gli utenti in genere eseguono query solo sui dati inclusi in un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a261-104">Users ordinarily just query the data within an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="0a261-105">In un contesto di data mining, tuttavia, ad esempio per l'esecuzione di stime basate su un modello di data mining, un utente deve unire in join i dati risultanti di un modello di data mining e i dati specificati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0a261-105">However, in the context of data mining, such as performing predictions based on a mining model, a user has to join the learned data of a mining model with user-provided data.</span></span> <span data-ttu-id="0a261-106">Per connettersi all'origine dati contenente i dati specificati dall'utente, l'utente usa una query DMX (Data Mining Extensions) che include le clausole [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery) e [OPENROWSET &#40;DMX&#41;](/sql/dmx/source-data-query-openrowset).</span><span class="sxs-lookup"><span data-stu-id="0a261-106">To connect to the data source that contains the user-provided data, the user uses a Data Mining Extensions (DMX) query that contains either the [OPENQUERY &#40;DMX&#41;](/sql/dmx/source-data-query-openquery) and [OPENROWSET &#40;DMX&#41;](/sql/dmx/source-data-query-openrowset) clause.</span></span>  
  
 <span data-ttu-id="0a261-107">Per eseguire una query DMX per la connessione a un'origine dei dati, l'utente deve poter accedere all'oggetto origine dei dati nel database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0a261-107">To execute a DMX query that connects to a data source, the user must have access to the data source object within the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="0a261-108">Per impostazione predefinita, solo gli amministratori del server o del database possono accedere agli oggetti origine dati.</span><span class="sxs-lookup"><span data-stu-id="0a261-108">By default, only Server Administrators or Database Administrators have access to data source objects.</span></span> <span data-ttu-id="0a261-109">Ciò significa che un utente non può accedere a un oggetto origine dati a meno che un amministratore non conceda le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0a261-109">This means that a user cannot access a data source object unless an administrator grants permissions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0a261-110">Per motivi di sicurezza, l'invio di query DMX tramite una stringa di connessione aperta nella clausola OPENROWSET è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="0a261-110">For security reasons, the submission of DMX queries by using an open connection string in the OPENROWSET clause is disabled.</span></span>  
  
## <a name="set-read-permissions-to-a-data-source"></a><span data-ttu-id="0a261-111">Impostare le autorizzazioni di Lettura per un'origine dati</span><span class="sxs-lookup"><span data-stu-id="0a261-111">Set Read permissions to a data source</span></span>  
 <span data-ttu-id="0a261-112">A un ruolo del database è possibile non concedere alcuna autorizzazione di accesso per un oggetto origine dei dati oppure concedere autorizzazioni di lettura.</span><span class="sxs-lookup"><span data-stu-id="0a261-112">A database role can be granted either no access permissions on a data source object or read permissions.</span></span>  
  
1.  <span data-ttu-id="0a261-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi all'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], espandere il nodo **Ruoli** relativo al database appropriato in Esplora oggetti, quindi fare clic su un ruolo del database o creare un nuovo ruolo del database.</span><span class="sxs-lookup"><span data-stu-id="0a261-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], expand **Roles** for the appropriate database in Object explorer, and then click a database role (or create a new database role).</span></span>  
  
2.  <span data-ttu-id="0a261-114">Nel riquadro **Accesso all'origine dati** individuare l'oggetto origine dati nell'elenco **Origine dati** , quindi selezionare **Lettura** nell'elenco **Accesso** relativo all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0a261-114">In the **Data Source Access** pane, locate the data source object in the **Data Source** list, and then select the **Read** in the **Access** list for the data source.</span></span> <span data-ttu-id="0a261-115">Se questa opzione non è disponibile, verificare se nel riquadro **Generale** è selezionato Controllo completo.</span><span class="sxs-lookup"><span data-stu-id="0a261-115">If this option is unavailable, check the **General** pane to see if Full Control is selected.</span></span> <span data-ttu-id="0a261-116">Il Controllo completo fornisce già l'autorizzazione e nell'origine dati non è possibile sostituire le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0a261-116">Full Control is already providing permission, you cannot override permissions on the data source.</span></span>  
  
## <a name="working-with-the-connection-string-used-by-a-data-source-object"></a><span data-ttu-id="0a261-117">Stringa di connessione usata da un oggetto origine dei dati</span><span class="sxs-lookup"><span data-stu-id="0a261-117">Working With the Connection String Used by a Data Source Object</span></span>  
 <span data-ttu-id="0a261-118">L'oggetto origine dei dati include la stringa di connessione usata per eseguire la connessione all'origine dei dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="0a261-118">The data source object contains the connection string that is used to connect to the underlying data source.</span></span> <span data-ttu-id="0a261-119">Tale stringa di connessione consente di specificare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a261-119">This connection string can specify one of the following:</span></span>  
  
-   <span data-ttu-id="0a261-120">**Specificare un nome utente e una password**</span><span class="sxs-lookup"><span data-stu-id="0a261-120">**Specify a user name and password**</span></span>  
  
     <span data-ttu-id="0a261-121">Se tramite la stringa di connessione usata da un oggetto origine dei dati vengono specificati un nome utente e una password, è possibile creare più oggetti origine dei dati, ognuno dei quali con account utente diversi.</span><span class="sxs-lookup"><span data-stu-id="0a261-121">If the connection string that a data source object uses specifies a user name and password, you may want to create multiple data source objects, each with different user accounts.</span></span> <span data-ttu-id="0a261-122">La creazione di più oggetti origine dei dati consente agli utenti di accedere a oggetti origine dei dati specifici impedendo l'accesso ad altri oggetti origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="0a261-122">Creating multiple data source objects lets users access certain data source objects and prevents those users from accessing other data source objects.</span></span> <span data-ttu-id="0a261-123">Questi altri oggetti origine dei dati possono essere usati da [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] stesso per elaborare oggetti, ad esempio cubi e modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="0a261-123">These other data source objects can be used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] itself for processing objects, such as cubes and mining models.</span></span>  
  
-   <span data-ttu-id="0a261-124">**Specificare l'autenticazione Windows**</span><span class="sxs-lookup"><span data-stu-id="0a261-124">**Specify Windows Authentication**</span></span>  
  
     <span data-ttu-id="0a261-125">Se tramite la stringa di connessione usata da un oggetto origine dei dati viene specificata l'autenticazione di Windows, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deve essere in grado di rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="0a261-125">If the connection string that a data source object uses specifies Windows Authentication, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] must be able to impersonate the client.</span></span> <span data-ttu-id="0a261-126">Se l'origine dei dati è presente in un computer remoto, i due computer devono essere ritenuti attendibili per la rappresentazione tramite l'autenticazione Kerberos, altrimenti la query ha in genere esito negativo.</span><span class="sxs-lookup"><span data-stu-id="0a261-126">If the data source is on a remote computer, the two computers must be trusted for impersonation by using Kerberos authentication, or the query will typically fail.</span></span> <span data-ttu-id="0a261-127">Per altre informazioni, vedere [Configurare Analysis Services per la delega vincolata Kerberos](../instances/configure-analysis-services-for-kerberos-constrained-delegation.md) .</span><span class="sxs-lookup"><span data-stu-id="0a261-127">See [Configure Analysis Services for Kerberos constrained delegation](../instances/configure-analysis-services-for-kerberos-constrained-delegation.md) for more information.</span></span>  
  
     <span data-ttu-id="0a261-128">Se il client non consente la rappresentazione, tramite la proprietà Impersonation Level in OLE DB e altri componenti client, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] proverà a stabilire una connessione anonima all'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="0a261-128">If the client does not allow for impersonation (through the Impersonation Level property in OLE DB and other client components), [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will try to make an anonymous connection to the underlying data source.</span></span> <span data-ttu-id="0a261-129">Le connessioni anonime alle origini dati remote raramente riescono poiché la maggior parte delle origini dati non accetta connessioni anonime.</span><span class="sxs-lookup"><span data-stu-id="0a261-129">Anonymous connections to remote data sources rarely succeed, as most data sources do not accept anonymous connections).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a261-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a261-130">See Also</span></span>  
 <span data-ttu-id="0a261-131">[Origini dati nei modelli multidimensionali](data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="0a261-131">[Data Sources in Multidimensional Models](data-sources-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="0a261-132">[Proprietà della stringa di connessione &#40;Analysis Services&#41;](../instances/connection-string-properties-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="0a261-132">[Connection String Properties &#40;Analysis Services&#41;](../instances/connection-string-properties-analysis-services.md) </span></span>  
 <span data-ttu-id="0a261-133">[Metodologie di autenticazione supportate da Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="0a261-133">[Authentication methodologies supported by Analysis Services](../instances/authentication-methodologies-supported-by-analysis-services.md) </span></span>  
 <span data-ttu-id="0a261-134">[Concessione dell'accesso personalizzato ai dati della dimensione &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="0a261-134">[Grant custom access to dimension data &#40;Analysis Services&#41;](grant-custom-access-to-dimension-data-analysis-services.md) </span></span>  
 <span data-ttu-id="0a261-135">[Concedere le autorizzazioni per il cubo o il modello &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="0a261-135">[Grant cube or model permissions &#40;Analysis Services&#41;](grant-cube-or-model-permissions-analysis-services.md) </span></span>  
 [<span data-ttu-id="0a261-136">Concedere l'accesso personalizzato ai dati delle celle &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0a261-136">Grant custom access to cell data &#40;Analysis Services&#41;</span></span>](grant-custom-access-to-cell-data-analysis-services.md)  
  
  