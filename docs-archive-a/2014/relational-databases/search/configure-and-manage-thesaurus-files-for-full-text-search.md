---
title: Configurare e gestire i file del thesaurus per la ricerca full-text | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], thesaurus files
- thesaurus [full-text search], configuring
- thesaurus [full-text search]
ms.assetid: 3ef96a63-8a52-45be-9a1f-265bff400e54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67f0a5af7be4f41ce33692e5f28ad5adf676980c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726863"
---
# <a name="configure-and-manage-thesaurus-files-for-full-text-search"></a><span data-ttu-id="1c43a-102">Configurare e gestire i file del thesaurus per la ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="1c43a-102">Configure and Manage Thesaurus Files for Full-Text Search</span></span>
  <span data-ttu-id="1c43a-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]le query full-text consentono di eseguire una ricerca di sinonimi dei termini specificati dall'utente tramite l'utilizzo di un thesaurus.</span><span class="sxs-lookup"><span data-stu-id="1c43a-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], full-text queries can search for synonyms of user-specified terms through the use of a thesaurus.</span></span> <span data-ttu-id="1c43a-104">In un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *di* viene definito un set di sinonimi per una lingua specifica.</span><span class="sxs-lookup"><span data-stu-id="1c43a-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *thesaurus* defines a set of synonyms for a specific language.</span></span> <span data-ttu-id="1c43a-105">Gli amministratori di sistema possono definire due forme di sinonimi, i set di espansione e i set di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="1c43a-105">System administrators can define two forms of synonyms: expansion sets and replacement sets.</span></span> <span data-ttu-id="1c43a-106">Sviluppando un thesaurus basato sui dati full-text in uso, è possibile ampliare in modo efficace l'ambito delle query full-text su tali dati.</span><span class="sxs-lookup"><span data-stu-id="1c43a-106">By developing a thesaurus tailored to your full-text data, you can effectively broaden the scope of full-text queries on that data.</span></span> <span data-ttu-id="1c43a-107">La corrispondenza con il thesaurus si verifica per tutte le query [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) e [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) e per tutte le query [CONTAINS](/sql/t-sql/queries/contains-transact-sql) e [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) che specificano la clausola FORMSOF THESAURUS.</span><span class="sxs-lookup"><span data-stu-id="1c43a-107">Thesaurus matching occurs for all [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) and [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) queries and for any [CONTAINS](/sql/t-sql/queries/contains-transact-sql) and [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) queries that specify the FORMSOF THESAURUS clause.</span></span>  
  
##  <a name="basic-tasks-for-setting-up-a-thesaurus-file"></a><a name="tasks"></a><span data-ttu-id="1c43a-108">Attività di base per la configurazione di un file del thesaurus</span><span class="sxs-lookup"><span data-stu-id="1c43a-108">Basic Tasks for Setting Up a Thesaurus File</span></span>  
 <span data-ttu-id="1c43a-109">Prima che le query di ricerca full-text nell'istanza del server siano in grado di eseguire la ricerca di sinonimi in una determinata lingua, è necessario definire mapping del thesaurus (sinonimi) per tale lingua.</span><span class="sxs-lookup"><span data-stu-id="1c43a-109">Before full-text search queries on your server instance can look for synonyms in a given language, you must define thesaurus mappings (synonyms) for that language.</span></span> <span data-ttu-id="1c43a-110">È necessario configurare manualmente ogni thesaurus per definire gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c43a-110">Each thesaurus must be manually configured to define the following:</span></span>  
  
-   <span data-ttu-id="1c43a-111">Impostazione dei segni diacritici</span><span class="sxs-lookup"><span data-stu-id="1c43a-111">Diacritics setting</span></span>  
  
     <span data-ttu-id="1c43a-112">Per un determinato thesaurus, tutti i criteri di ricerca sono sensibili o insensibili ai segni diacritici, ad esempio una tilde ( **~** ), un segno di accento acuto (**??**) o una diereszione (**??**) (ovvero, *distinzione tra caratteri accentati* o senza distinzione tra *caratteri*accentati).</span><span class="sxs-lookup"><span data-stu-id="1c43a-112">For a given thesaurus, all search patterns are either sensitive or insensitive to diacritical marks such as a tilde (**~**), acute accent mark (**??**), or umlaut (**??**) (that is, *accent sensitive* or *accent insensitive*).</span></span> <span data-ttu-id="1c43a-113">Si supponga, ad esempio, di specificare il modello "CAF??"</span><span class="sxs-lookup"><span data-stu-id="1c43a-113">For example, suppose you specify the pattern "caf??"</span></span> <span data-ttu-id="1c43a-114">con altri criteri in una query di ricerca full-text.</span><span class="sxs-lookup"><span data-stu-id="1c43a-114">to be replaced by other patterns in a full-text query.</span></span> <span data-ttu-id="1c43a-115">Se il thesaurus è senza distinzione tra caratteri accentati, la ricerca full-text sostituisce i modelli "CAF??"</span><span class="sxs-lookup"><span data-stu-id="1c43a-115">If the thesaurus is accent-insensitive, full-text search replaces the patterns "caf??"</span></span> <span data-ttu-id="1c43a-116">e "cafe".</span><span class="sxs-lookup"><span data-stu-id="1c43a-116">and "cafe".</span></span> <span data-ttu-id="1c43a-117">Se il thesaurus è con distinzione tra caratteri accentati, la ricerca full-text sostituisce solo il modello "CAF??".</span><span class="sxs-lookup"><span data-stu-id="1c43a-117">If the thesaurus is accent-sensitive, full-text search replaces only the pattern "caf??".</span></span> <span data-ttu-id="1c43a-118">Per impostazione predefinita, un thesaurus non supporta la distinzione tra caratteri accentati e non accentati.</span><span class="sxs-lookup"><span data-stu-id="1c43a-118">By default, a thesaurus is accent-insensitive.</span></span>  
  
-   <span data-ttu-id="1c43a-119">Set di espansione</span><span class="sxs-lookup"><span data-stu-id="1c43a-119">Expansion set</span></span>  
  
     <span data-ttu-id="1c43a-120">Un set di espansione contiene un gruppo di sinonimi, ad esempio "writer", "author" e "journalist", che vengono sostituiti gli uni con gli altri da una query full-text.</span><span class="sxs-lookup"><span data-stu-id="1c43a-120">An expansion set contains a group of synonyms such as "writer", "author", and "journalist" that are substituted for one another by a full-text query.</span></span> <span data-ttu-id="1c43a-121">Le query che contengono una corrispondenza per uno dei sinonimi in un set di espansione vengono espanse per includere ogni altro sinonimo nel set di espansione stesso.</span><span class="sxs-lookup"><span data-stu-id="1c43a-121">Queries that contain a match for any synonym in an expansion set are expanded to include every other synonym in the expansion set.</span></span>  
  
     <span data-ttu-id="1c43a-122">Per altre informazioni, vedere "Struttura XML di un set di espansione" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1c43a-122">For more information, see "XML Structure of an Expansion Set," later in this topic.</span></span>  
  
-   <span data-ttu-id="1c43a-123">Set di sostituzione</span><span class="sxs-lookup"><span data-stu-id="1c43a-123">Replacement set</span></span>  
  
     <span data-ttu-id="1c43a-124">Un set di sostituzione include un criterio di testo da sostituire con parole specifiche.</span><span class="sxs-lookup"><span data-stu-id="1c43a-124">A replacement set contains a text pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="1c43a-125">Vedere, ad esempio, la sezione "Struttura XML di un set di sostituzione" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1c43a-125">For an example, see the section "XML Structure of a Replacement Set" later in this topic.</span></span>  
  
  
##  <a name="initial-content-of-the-thesaurus-files"></a><a name="initial_thesaurus_files"></a><span data-ttu-id="1c43a-126">Contenuto iniziale dei file del thesaurus</span><span class="sxs-lookup"><span data-stu-id="1c43a-126">Initial Content of the Thesaurus Files</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1c43a-127">offre un set di file XML del thesaurus, uno per ogni lingua supportata.</span><span class="sxs-lookup"><span data-stu-id="1c43a-127">provides a set of XML thesaurus files, one for each supported language.</span></span> <span data-ttu-id="1c43a-128">Tali file sono essenzialmente vuoti</span><span class="sxs-lookup"><span data-stu-id="1c43a-128">These files are essentially empty.</span></span> <span data-ttu-id="1c43a-129">e contengono solo la struttura XML di livello principale comune a tutti i thesaurus di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e un thesaurus di esempio costituito da commenti.</span><span class="sxs-lookup"><span data-stu-id="1c43a-129">They contain only the top-level XML structure that is common to all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] thesauruses and a commented-out sample thesaurus.</span></span>  
  
 <span data-ttu-id="1c43a-130">Tutti i file del thesaurus disponibili in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contengono il codice XML seguente:</span><span class="sxs-lookup"><span data-stu-id="1c43a-130">The thesaurus files that are released with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all contain the following XML code:</span></span>  
  
```  
<XML ID="Microsoft Search Thesaurus">  
  
<!--  Commented out  
  
    <thesaurus xmlns="x-schema:tsSchema.xml">  
<diacritics_sensitive>0</diacritics_sensitive>  
        <expansion>  
            <sub>Internet Explorer</sub>  
            <sub>IE</sub>  
            <sub>IE5</sub>  
        </expansion>  
        <replacement>  
            <pat>NT5</pat>  
            <pat>W2K</pat>  
            <sub>Windows 2012</sub>  
        </replacement>  
        <expansion>  
            <sub>run</sub>  
            <sub>jog</sub>  
        </expansion>  
    </thesaurus>  
-->  
</XML>  
```  
  
  
##  <a name="location-of-the-thesaurus-files"></a><a name="location"></a><span data-ttu-id="1c43a-131">Percorso dei file del thesaurus</span><span class="sxs-lookup"><span data-stu-id="1c43a-131">Location of the Thesaurus Files</span></span>  
 <span data-ttu-id="1c43a-132">Il percorso predefinito dei file del thesaurus è il seguente:</span><span class="sxs-lookup"><span data-stu-id="1c43a-132">The default location of the thesaurus files is:</span></span>  
  
 <span data-ttu-id="1c43a-133">*<SQL_Server_data_files_path>* \MSSQL12. MSSQLSERVER\MSSQL\FTDATA</span><span class="sxs-lookup"><span data-stu-id="1c43a-133">*<SQL_Server_data_files_path>* \MSSQL12.MSSQLSERVER\MSSQL\FTDATA</span></span>\  
  
 <span data-ttu-id="1c43a-134">Tale percorso predefinito contiene i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c43a-134">This default location contains the following files:</span></span>  
  
-   <span data-ttu-id="1c43a-135">File del thesaurus specifici della lingua</span><span class="sxs-lookup"><span data-stu-id="1c43a-135">Language-specific thesaurus files</span></span>  
  
     <span data-ttu-id="1c43a-136">Durante l'installazione, nel percorso indicato in precedenza vengono installati file del thesaurus vuoti,</span><span class="sxs-lookup"><span data-stu-id="1c43a-136">During setup, empty thesaurus files are installed in the above location.</span></span> <span data-ttu-id="1c43a-137">uno per ogni lingua supportata.</span><span class="sxs-lookup"><span data-stu-id="1c43a-137">A separate file is provided for each supported language.</span></span> <span data-ttu-id="1c43a-138">Tali file possono essere personalizzati da un amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="1c43a-138">A system administrator can customize these files.</span></span>  
  
     <span data-ttu-id="1c43a-139">Per i nomi predefiniti dei file del thesaurus viene usato il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="1c43a-139">The default file names of the thesaurus files use following format:</span></span>  
  
     <span data-ttu-id="1c43a-140">' ts ' + \<three-letter language-abbreviation> +'. xml '</span><span class="sxs-lookup"><span data-stu-id="1c43a-140">'ts' + \<three-letter language-abbreviation> + '.xml'</span></span>  
  
     <span data-ttu-id="1c43a-141">Il nome del file del thesaurus per una lingua specifica è indicato nel valore del Registro di sistema HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<nome-istanza>\MSSearch\\<abbrev-lingua>.</span><span class="sxs-lookup"><span data-stu-id="1c43a-141">The name of the thesaurus file for a given language is specified in the registry in the following value HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<instance-name>\MSSearch\\<language-abbrev>.</span></span>  
  
-   <span data-ttu-id="1c43a-142">File del thesaurus globale</span><span class="sxs-lookup"><span data-stu-id="1c43a-142">The global thesaurus file</span></span>  
  
     <span data-ttu-id="1c43a-143">File del thesaurus globale vuoto denominato tsGlobal.xml.</span><span class="sxs-lookup"><span data-stu-id="1c43a-143">An empty global thesaurus file, tsGlobal.xml.</span></span>  
  
 <span data-ttu-id="1c43a-144">È possibile modificare il percorso e il nome di un file del thesaurus modificando la relativa chiave del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="1c43a-144">You can change the location and names of a thesaurus file by changing its registry key.</span></span> <span data-ttu-id="1c43a-145">Per ogni lingua, il percorso del file del thesaurus viene specificato nel seguente valore del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="1c43a-145">For each language, the location of the thesaurus file is specified in the following value in the registry:</span></span>  
  
 <span data-ttu-id="1c43a-146">HKLM/SOFTWARE/Microsoft/Microsoft SQL Server/ \<instance name> /MSSearch/Language/ \<language-abbreviation> /TsaurusFile</span><span class="sxs-lookup"><span data-stu-id="1c43a-146">HKLM/SOFTWARE/Microsoft/Microsoft SQL Server/\<instance name>/MSSearch/Language/\<language-abbreviation>/TsaurusFile</span></span>  
  
 <span data-ttu-id="1c43a-147">Il file del thesaurus globale corrisponde alla lingua neutra con LCID 0.</span><span class="sxs-lookup"><span data-stu-id="1c43a-147">The global thesaurus file corresponds to the Neutral language with LCID 0.</span></span> <span data-ttu-id="1c43a-148">Questo valore può essere modificato solo dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="1c43a-148">This value can be changed by administrators only.</span></span>  
  
  
##  <a name="how-queries-use-thesaurus-files"></a><a name="how_queries_use_tf"></a><span data-ttu-id="1c43a-149">Modalità di utilizzo dei file del thesaurus nelle query</span><span class="sxs-lookup"><span data-stu-id="1c43a-149">How Queries Use Thesaurus Files</span></span>  
 <span data-ttu-id="1c43a-150">Una query sul thesaurus usano sia un thesaurus specifico della lingua sia un thesaurus globale.</span><span class="sxs-lookup"><span data-stu-id="1c43a-150">A thesaurus query uses both a language-specific thesaurus and the global thesaurus.</span></span> <span data-ttu-id="1c43a-151">La query esegue innanzitutto la ricerca in un file specifico della lingua e lo carica per l'elaborazione, a meno che non sia già caricato.</span><span class="sxs-lookup"><span data-stu-id="1c43a-151">First, the query looks up the language-specific file and loads it for processing (unless it is already loaded).</span></span> <span data-ttu-id="1c43a-152">La query viene quindi espansa per includere i sinonimi specifici della lingua indicati dalle regole del set di espansione e del set di sostituzione nel file del thesaurus.</span><span class="sxs-lookup"><span data-stu-id="1c43a-152">The query is expanded to include the language-specific synonyms specified by the expansion set and replacement set rules in the thesaurus file.</span></span> <span data-ttu-id="1c43a-153">Questi passaggi vengono quindi ripetuti per il thesaurus globale.</span><span class="sxs-lookup"><span data-stu-id="1c43a-153">These steps are then repeated for the global thesaurus.</span></span> <span data-ttu-id="1c43a-154">Se, tuttavia, nel file del thesaurus specifico della lingua è già stata individuata una corrispondenza per un termine, tale termine non può essere considerato valido per la corrispondenza nel thesaurus globale.</span><span class="sxs-lookup"><span data-stu-id="1c43a-154">However, if a term is already part of a match in the language specific thesaurus file, the term is ineligible for matching in the global thesaurus.</span></span>  
  
  
##  <a name="understanding-the-structure-of-a-thesaurus-file"></a><a name="structure"></a><span data-ttu-id="1c43a-155">Informazioni sulla struttura di un file del thesaurus</span><span class="sxs-lookup"><span data-stu-id="1c43a-155">Understanding the Structure of a Thesaurus File</span></span>  
 <span data-ttu-id="1c43a-156">Ogni file del thesaurus definisce un contenitore XML, il cui ID è `Microsoft Search Thesaurus`, e un commento `<!--` ... `-->` che contiene un thesaurus di esempio.</span><span class="sxs-lookup"><span data-stu-id="1c43a-156">Each thesaurus file defines an XML container whose ID is `Microsoft Search Thesaurus`, and a comment, `<!--` ... `-->`, that contains a sample thesaurus.</span></span> <span data-ttu-id="1c43a-157">Il thesaurus è definito in un \<thesaurus> elemento che contiene esempi degli elementi figlio che definiscono l'impostazione dei segni diacritici, i set di espansione e i set di sostituzione, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1c43a-157">The thesaurus is defined in a \<thesaurus> element that contains samples of the child elements that define the diacritics setting, expansion sets, and replacement sets, as follows:</span></span>  
  
-   <span data-ttu-id="1c43a-158">Struttura XML dell'impostazione dei segni diacritici</span><span class="sxs-lookup"><span data-stu-id="1c43a-158">XML Structure of the Diacritical Setting</span></span>  
  
     <span data-ttu-id="1c43a-159">L'impostazione dei segni diacritici di un thesaurus è specificata in un singolo elemento <diacritics_sensitive>,</span><span class="sxs-lookup"><span data-stu-id="1c43a-159">The diacritics setting of a thesaurus is specified in a single <diacritics_sensitive> element.</span></span> <span data-ttu-id="1c43a-160">che contiene un valore intero che determina il supporto della distinzione tra caratteri accentati e non accentati, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1c43a-160">This element contains an integer value that controls accent sensitivity, as follows:</span></span>  
  
    |<span data-ttu-id="1c43a-161">Impostazione dei segni diacritici</span><span class="sxs-lookup"><span data-stu-id="1c43a-161">Diacritics Setting</span></span>|<span data-ttu-id="1c43a-162">Valore</span><span class="sxs-lookup"><span data-stu-id="1c43a-162">Value</span></span>|<span data-ttu-id="1c43a-163">XML</span><span class="sxs-lookup"><span data-stu-id="1c43a-163">XML</span></span>|  
    |------------------------|-----------|---------|  
    |<span data-ttu-id="1c43a-164">non supportano la distinzione tra caratteri accentati e non accentati</span><span class="sxs-lookup"><span data-stu-id="1c43a-164">Accent insensitive</span></span>|<span data-ttu-id="1c43a-165">0</span><span class="sxs-lookup"><span data-stu-id="1c43a-165">0</span></span>|`<diacritics_sensitive>0</diacritics_sensitive>`|  
    |<span data-ttu-id="1c43a-166">supportano la distinzione tra caratteri accentati e non accentati</span><span class="sxs-lookup"><span data-stu-id="1c43a-166">Accent sensitive</span></span>|<span data-ttu-id="1c43a-167">1</span><span class="sxs-lookup"><span data-stu-id="1c43a-167">1</span></span>|`<diacritics_sensitive>1</diacritics_sensitive>`|  
  
    > [!NOTE]  
    >  <span data-ttu-id="1c43a-168">Questa impostazione può essere applicata solo una volta nel file e si applica a tutti i criteri di ricerca nel file.</span><span class="sxs-lookup"><span data-stu-id="1c43a-168">This setting can only be applied one time in the file, and it applies to all search patterns in the file.</span></span> <span data-ttu-id="1c43a-169">L'impostazione non può essere specificata per singoli criteri.</span><span class="sxs-lookup"><span data-stu-id="1c43a-169">This setting cannot be specified for individual patterns.</span></span>  
  
-   <span data-ttu-id="1c43a-170">Struttura XML di un set di espansione</span><span class="sxs-lookup"><span data-stu-id="1c43a-170">XML Structure of an Expansion Set</span></span>  
  
     <span data-ttu-id="1c43a-171">Ogni set di espansione è racchiuso in un elemento \<expansion>.</span><span class="sxs-lookup"><span data-stu-id="1c43a-171">Each expansion set is enclosed within an \<expansion> element.</span></span> <span data-ttu-id="1c43a-172">All'interno di questo elemento è possibile specificare una o più sostituzioni in un elemento \<sub>.</span><span class="sxs-lookup"><span data-stu-id="1c43a-172">Within this element, you specify one or more substitutions in a \<sub> element.</span></span> <span data-ttu-id="1c43a-173">Nel set di espansione è possibile specificare un gruppo di sostituzioni che sono sinonimi una dell'altra.</span><span class="sxs-lookup"><span data-stu-id="1c43a-173">In the expansion set, you can specify a group of substitutions that are synonyms of each other.</span></span>  
  
     <span data-ttu-id="1c43a-174">Ad esempio, è possibile modificare la sezione di espansione per considerare le sostituzioni "writer", "author" e "journalist" come sinonimi.</span><span class="sxs-lookup"><span data-stu-id="1c43a-174">For example, you can edit the expansion section to treat the substitutions "writer", "author", and "journalist" as synonyms.</span></span> <span data-ttu-id="1c43a-175">per includere tutte le altre sostituzioni specificate nel set di espansione, vengono espanse le query di ricerca full-text che contengono corrispondenze in una sostituzione.</span><span class="sxs-lookup"><span data-stu-id="1c43a-175">full-text search queries that contain matches in one substitution are expanded to include all other substitutions specified in the expansion set.</span></span> <span data-ttu-id="1c43a-176">Di conseguenza, quando nell'esempio precedente si esegue una query FORMS OF THESAURUS o FREETEXT per la parola "author", vengono restituiti anche i risultati di ricerca contenenti le parole "writer" e "journalist".</span><span class="sxs-lookup"><span data-stu-id="1c43a-176">Therefore, in the preceding example, when you issue a FORMS OF THESAURUS or a FREETEXT query for the word "author", full-text search also returns search results containing the words "writer" and "journalist".</span></span>  
  
     <span data-ttu-id="1c43a-177">La sezione del set di espansione dell'esempio precedente sarà la seguente:</span><span class="sxs-lookup"><span data-stu-id="1c43a-177">This is what the expansion set section would look like for the above example:</span></span>  
  
    ```  
    <expansion>  
            <sub>writer</sub>  
            <sub>author</sub>  
            <sub>journalist</sub>  
    </expansion>  
    ```  
  
-   <span data-ttu-id="1c43a-178">Struttura XML di un set di sostituzione</span><span class="sxs-lookup"><span data-stu-id="1c43a-178">XML Structure of a Replacement Set</span></span>  
  
     <span data-ttu-id="1c43a-179">Ogni set di sostituzione è racchiuso in un elemento \<replacement>.</span><span class="sxs-lookup"><span data-stu-id="1c43a-179">Each replacement set is enclosed within a \<replacement> element.</span></span> <span data-ttu-id="1c43a-180">All'interno di questo elemento è possibile specificare uno o più criteri in un elemento \<pat> e zero o più sostituzioni in elementi \<sub>, uno per sinonimo.</span><span class="sxs-lookup"><span data-stu-id="1c43a-180">Within this element you can specify one or more patterns in a \<pat> element and zero or more substitutions in \<sub> elements, one per synonym.</span></span> <span data-ttu-id="1c43a-181">È possibile specificare un criterio da sostituire con un set di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="1c43a-181">You can specify a pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="1c43a-182">I criteri e le sostituzioni possono contenere una parola o una sequenza di parole.</span><span class="sxs-lookup"><span data-stu-id="1c43a-182">Patterns and substitutions can contain a word, or a sequence of words.</span></span> <span data-ttu-id="1c43a-183">Se non viene specificata alcuna sostituzione per un criterio, questo verrà rimosso dalla query dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1c43a-183">If there is no substitution specified for a pattern, it has the effect of removing the pattern from the user query.</span></span>  
  
     <span data-ttu-id="1c43a-184">Si supponga, ad esempio, di voler eseguire query per sostituire il criterio "Win8" con "Windows Server 2012" o "Windows 8.0".</span><span class="sxs-lookup"><span data-stu-id="1c43a-184">For example, suppose you want queries for "Win8", the pattern, to be replaced by "Windows Server 2012" or "Windows 8.0", the substitutions.</span></span> <span data-ttu-id="1c43a-185">Se si esegue una query full-text per "Win8", verranno restituiti solo i risultati di ricerca full-text contenenti le sostituzioni "Windows Server 2012" o "Windows 8.0".</span><span class="sxs-lookup"><span data-stu-id="1c43a-185">If you run a full-text query for "Win8", full-text search only returns search results containing "Windows Server 2012" or "Windows 8.0".</span></span> <span data-ttu-id="1c43a-186">ma non quelli contenenti "Win8".</span><span class="sxs-lookup"><span data-stu-id="1c43a-186">It does not return results containing "Win8".</span></span> <span data-ttu-id="1c43a-187">Questo accade perché "Win8" è stato "sostituito" con "Windows Server 2012" e "Windows 8.0".</span><span class="sxs-lookup"><span data-stu-id="1c43a-187">This is because the pattern "Win8" has been "replaced" by the patterns "Windows Server 2012" and "Windows 8.0".</span></span>  
  
     <span data-ttu-id="1c43a-188">La sezione del set di sostituzione dell'esempio sopra descritto sarebbe:</span><span class="sxs-lookup"><span data-stu-id="1c43a-188">This is what the replacement set section would look like for the above example:</span></span>  
  
    ```  
    <replacement>  
            <pat>Win8</pat>  
            <sub>Windows Server 2012</sub>  
            <sub>Windows 8.0</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="1c43a-189">Se sono presenti due set di sostituzione con criteri di testo simili da associare, il più lungo dei due ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="1c43a-189">If you have two replacement sets with similar patterns being matched, the longer of the two takes precedence.</span></span> <span data-ttu-id="1c43a-190">Se, ad esempio, si esegue una query FORMS OF THESAURUS per "Internet Explorer online community" e sono presenti i set di sostituzione indicati di seguito, "Internet Explorer" ha la precedenza su "Internet".</span><span class="sxs-lookup"><span data-stu-id="1c43a-190">For example, if you run a FORMS OF THESAURUS query for "Internet Explorer online community" and you have the following replacement sets, the "Internet Explorer" replacement set takes precedence over the "Internet" replacement set.</span></span> <span data-ttu-id="1c43a-191">La query verrà pertanto elaborata come "IE online community" o "IE 9 online community".</span><span class="sxs-lookup"><span data-stu-id="1c43a-191">The query will therefore be processed as "IE online community" or "IE 9 online community".</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet</pat>  
             <sub>intranet</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="1c43a-192">e</span><span class="sxs-lookup"><span data-stu-id="1c43a-192">and</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet Explorer</pat>  
             <sub>IE</sub>  
             <sub>IE 9</sub>  
    </replacement>  
    ```  
  
  
##  <a name="working-with-thesaurus-files"></a><a name="working_with_thesaurus_files"></a><span data-ttu-id="1c43a-193">Utilizzo dei file del thesaurus</span><span class="sxs-lookup"><span data-stu-id="1c43a-193">Working with Thesaurus Files</span></span>  
 <span data-ttu-id="1c43a-194">**Per modificare un file del thesaurus**</span><span class="sxs-lookup"><span data-stu-id="1c43a-194">**To edit a thesaurus file**</span></span>  
  
-   [<span data-ttu-id="1c43a-195">Modifica di un file del thesaurus</span><span class="sxs-lookup"><span data-stu-id="1c43a-195">Editing a Thesaurus File</span></span>](#editing)  
  
 <span data-ttu-id="1c43a-196">**Per caricare un file del thesaurus aggiornato**</span><span class="sxs-lookup"><span data-stu-id="1c43a-196">**To load an updated thesaurus file**</span></span>  
  
-   [<span data-ttu-id="1c43a-197">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1c43a-197">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql)  
  
 <span data-ttu-id="1c43a-198">**Per visualizzare il risultato della suddivisione in token di una combinazione di word breaker, thesaurus ed elenchi di parole non significative**</span><span class="sxs-lookup"><span data-stu-id="1c43a-198">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="1c43a-199">sys. dm_fts_parser &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1c43a-199">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="editing-a-thesaurus-file"></a><a name="editing"></a><span data-ttu-id="1c43a-200">Modifica di un file del thesaurus</span><span class="sxs-lookup"><span data-stu-id="1c43a-200">Editing a Thesaurus File</span></span>  
 <span data-ttu-id="1c43a-201">È possibile configurare il thesaurus per una lingua specifica modificando il relativo file XML.</span><span class="sxs-lookup"><span data-stu-id="1c43a-201">The thesaurus for a given language can be configured by editing its thesaurus file (an XML file).</span></span> <span data-ttu-id="1c43a-202">Durante l'installazione, vengono installati file del thesaurus vuoti che contengono solo il \<xml> contenitore e un elemento di esempio commentato \<thesaurus> .</span><span class="sxs-lookup"><span data-stu-id="1c43a-202">During setup, empty thesaurus files that contain only the \<xml> container and a commented-out sample \<thesaurus> element are installed.</span></span> <span data-ttu-id="1c43a-203">Per consentire il corretto funzionamento delle query di ricerca full-text che cercano sinonimi, è necessario creare un \<thesaurus> elemento effettivo che definisce un set di sinonimi.</span><span class="sxs-lookup"><span data-stu-id="1c43a-203">In order for full-text search queries that look for synonyms to work properly, you must create an actual \<thesaurus> element that defines a set of synonyms.</span></span> <span data-ttu-id="1c43a-204">È possibile definire due forme di sinonimi, i set di espansione e i set di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="1c43a-204">You can define two forms of synonyms, expansion sets and replacement sets.</span></span>  
  
 <span data-ttu-id="1c43a-205">**Restrizioni relative ai file del thesaurus**</span><span class="sxs-lookup"><span data-stu-id="1c43a-205">**Restrictions for thesaurus files**</span></span>  
  
 <span data-ttu-id="1c43a-206">Alla modifica di un file del thesaurus si applicano le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c43a-206">The following restrictions apply to editing a thesaurus file:</span></span>  
  
-   <span data-ttu-id="1c43a-207">Solo gli amministratori di sistema possono aggiornare, modificare o eliminare i file del thesaurus.</span><span class="sxs-lookup"><span data-stu-id="1c43a-207">Only system administrators can update, modify, or delete thesaurus files.</span></span>  
  
-   <span data-ttu-id="1c43a-208">Quando si usano editor di testo per modificare i file del thesaurus, è necessario salvare i file in formato Unicode e specificare gli indicatori per l'ordine dei byte (BOM).</span><span class="sxs-lookup"><span data-stu-id="1c43a-208">When editing thesaurus files using text editor tools, the files must be saved in Unicode format, and Byte Order Marks must be specified.</span></span>  
  
-   <span data-ttu-id="1c43a-209">Le voci del thesaurus non possono essere vuote e non è possibile eseguirne il word breaking in una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="1c43a-209">Thesaurus entries cannot be empty or word break to an empty string.</span></span>  
  
-   <span data-ttu-id="1c43a-210">Le frasi nel file del thesaurus non devono essere costituite da più di 512 caratteri.</span><span class="sxs-lookup"><span data-stu-id="1c43a-210">Phrases in the thesaurus file must be no longer than 512 characters.</span></span>  
  
-   <span data-ttu-id="1c43a-211">Un thesaurus non deve contenere alcuna voce duplicata fra le voci \<sub> dei set di espansione e gli elementi \<pat> dei set di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="1c43a-211">A thesaurus must not contain any duplicate entries among the \<sub> entries of expansion sets and the \<pat> elements of replacement sets.</span></span>  
  
 <span data-ttu-id="1c43a-212">**Indicazioni per i file del thesaurus**</span><span class="sxs-lookup"><span data-stu-id="1c43a-212">**Recommendations for thesaurus files**</span></span>  
  
 <span data-ttu-id="1c43a-213">È consigliabile che le voci del file del thesaurus non contengano caratteri speciali,</span><span class="sxs-lookup"><span data-stu-id="1c43a-213">We recommend that entries in the thesaurus file contain no special characters.</span></span> <span data-ttu-id="1c43a-214">in quanto i word breaker rivelano comportamenti imprevedibili in presenza di tale tipo di caratteri.</span><span class="sxs-lookup"><span data-stu-id="1c43a-214">This is because word breakers have subtle behaviors with respect to special characters.</span></span> <span data-ttu-id="1c43a-215">Se una voce del thesaurus contiene un carattere speciale, i word breaker usati in combinazione con la voce possono avere un comportamento imprevisto con implicazioni su una query full-text.</span><span class="sxs-lookup"><span data-stu-id="1c43a-215">If a thesaurus entry contains any special characters, word breakers used in combination with that entry can have subtle behavioral implications for a full-text query.</span></span>  
  
 <span data-ttu-id="1c43a-216">È consigliabile che le voci \<sub> non contengano parole non significative, in quanto tali parole vengono omesse dall'indice full-text.</span><span class="sxs-lookup"><span data-stu-id="1c43a-216">We recommend that \<sub> entries contain no stopwords since stopwords are omitted from the full-text index.</span></span> <span data-ttu-id="1c43a-217">Le query vengono espanse per includere le voci \<sub> da un file del thesaurus e se una voce \<sub> contiene parole non significative, le dimensioni della query aumentano inutilmente.</span><span class="sxs-lookup"><span data-stu-id="1c43a-217">Queries are expanded to include the \<sub> entries from a thesaurus file, and if a \<sub> entry contains stopwords, query size increases unnecessarily.</span></span>  
  
#### <a name="to-edit-a-thesaurus-file"></a><span data-ttu-id="1c43a-218">Per modificare un file del thesaurus</span><span class="sxs-lookup"><span data-stu-id="1c43a-218">To edit a thesaurus file</span></span>  
  
1.  <span data-ttu-id="1c43a-219">Aprire il file del thesaurus nel Blocco note.</span><span class="sxs-lookup"><span data-stu-id="1c43a-219">Open the thesaurus file in Notepad.</span></span>  
  
2.  <span data-ttu-id="1c43a-220">Se si modifica un file del thesaurus per la prima volta, rimuovere le righe di commento seguenti all'inizio e alla fine del file, rispettivamente:</span><span class="sxs-lookup"><span data-stu-id="1c43a-220">If you are editing the thesaurus file for the first time, remove the following comment lines at the beginning and end of the file, respectively:</span></span>  
  
    ```  
    <!--Commented out  
    -->  
    ```  
  
3.  <span data-ttu-id="1c43a-221">Aggiungere, modificare o eliminare un set di sostituzione o set di espansione.</span><span class="sxs-lookup"><span data-stu-id="1c43a-221">Add, modify, or delete a replacement set, or expansion set.</span></span>  
  
4.  <span data-ttu-id="1c43a-222">Salvare il file e chiudere il Blocco note.</span><span class="sxs-lookup"><span data-stu-id="1c43a-222">Save the file and close Notepad.</span></span>  
  
5.  <span data-ttu-id="1c43a-223">Utilizzare [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) per caricare il contenuto del file del thesaurus in tempdb, specificando l'identificatore LCID corrispondente alla lingua del file del thesaurus.</span><span class="sxs-lookup"><span data-stu-id="1c43a-223">Use [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) to load the content of the thesaurus file into tempdb, specifying the local identifier (LCID) that corresponds to the language of the thesaurus file.</span></span> <span data-ttu-id="1c43a-224">Per il file del thesaurus per la lingua inglese, denominato tsenu.xml, l'identificatore LCID corrispondente è 1033.</span><span class="sxs-lookup"><span data-stu-id="1c43a-224">For example, for the English thesaurus file, tsenu.xml, the corresponding LCID is 1033.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    EXEC sys.sp_fulltext_load_thesaurus_file 1033;  
    GO  
    ```  
  
  
## <a name="see-also"></a><span data-ttu-id="1c43a-225">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c43a-225">See Also</span></span>  
 <span data-ttu-id="1c43a-226">[CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c43a-226">[CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql) </span></span>  
 <span data-ttu-id="1c43a-227">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c43a-227">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="1c43a-228">[FREETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/freetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c43a-228">[FREETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/freetext-transact-sql) </span></span>  
 <span data-ttu-id="1c43a-229">[FREETEXTTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1c43a-229">[FREETEXTTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span></span>  
 [<span data-ttu-id="1c43a-230">Ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="1c43a-230">Full-Text Search</span></span>](full-text-search.md)  
  
  
