---
title: MSSQLSERVER_208 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 208 (Database Engine error)
ms.assetid: 4b1895f5-3197-4da1-af86-954c93507956
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 97ab3eb220c03c3de0c95251861f3b947890b090
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624236"
---
# <a name="mssqlserver_208"></a><span data-ttu-id="dfdab-102">MSSQLSERVER_208</span><span class="sxs-lookup"><span data-stu-id="dfdab-102">MSSQLSERVER_208</span></span>
    
## <a name="details"></a><span data-ttu-id="dfdab-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dfdab-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dfdab-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="dfdab-104">Product Name</span></span>|<span data-ttu-id="dfdab-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dfdab-105">SQL Server</span></span>|  
|<span data-ttu-id="dfdab-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="dfdab-106">Event ID</span></span>|<span data-ttu-id="dfdab-107">208</span><span class="sxs-lookup"><span data-stu-id="dfdab-107">208</span></span>|  
|<span data-ttu-id="dfdab-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="dfdab-108">Event Source</span></span>|<span data-ttu-id="dfdab-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dfdab-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dfdab-110">Componente</span><span class="sxs-lookup"><span data-stu-id="dfdab-110">Component</span></span>|<span data-ttu-id="dfdab-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dfdab-111">SQLEngine</span></span>|  
|<span data-ttu-id="dfdab-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="dfdab-112">Symbolic Name</span></span>|<span data-ttu-id="dfdab-113">SQ_BADOBJECT</span><span class="sxs-lookup"><span data-stu-id="dfdab-113">SQ_BADOBJECT</span></span>|  
|<span data-ttu-id="dfdab-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="dfdab-114">Message Text</span></span>|<span data-ttu-id="dfdab-115">Il nome di oggetto '%.\*ls' non è valido.</span><span class="sxs-lookup"><span data-stu-id="dfdab-115">Invalid object name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dfdab-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="dfdab-116">Explanation</span></span>  
 <span data-ttu-id="dfdab-117">Non è possibile individuare l'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="dfdab-117">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="dfdab-118">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="dfdab-118">Possible Causes</span></span>  
 <span data-ttu-id="dfdab-119">L'errore può essere causato da uno dei problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dfdab-119">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="dfdab-120">L'oggetto non è stato specificato correttamente.</span><span class="sxs-lookup"><span data-stu-id="dfdab-120">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="dfdab-121">L'oggetto non esiste nel database corrente oppure in quello specificato.</span><span class="sxs-lookup"><span data-stu-id="dfdab-121">The object does not exist in the current database or in the specified database.</span></span>  
  
-   <span data-ttu-id="dfdab-122">L'oggetto esiste, ma potrebbe non essere esposto all'utente.</span><span class="sxs-lookup"><span data-stu-id="dfdab-122">The object exists, but could not be exposed to the user.</span></span> <span data-ttu-id="dfdab-123">È possibile ad esempio che l'utente non disponga di autorizzazioni sull'oggetto oppure l'oggetto è stato creato all'interno di un'istruzione EXECUTE, ma l'accesso è stato eseguito al di fuori dell'ambito dell'istruzione EXECUTE.</span><span class="sxs-lookup"><span data-stu-id="dfdab-123">For example, the user might not have permissions on the object or the object is created within an EXECUTE statement but accessed outside the scope of the EXECUTE statement.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dfdab-124">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="dfdab-124">User Action</span></span>  
 <span data-ttu-id="dfdab-125">Verificare le informazioni seguenti e correggere l'istruzione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="dfdab-125">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="dfdab-126">Correttezza dell'ortografia dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="dfdab-126">The object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="dfdab-127">Correttezza del contesto di database corrente.</span><span class="sxs-lookup"><span data-stu-id="dfdab-127">The current database context is correct.</span></span> <span data-ttu-id="dfdab-128">Se per l'oggetto non è specificato un nome di database, l'oggetto deve esistere nel database corrente.</span><span class="sxs-lookup"><span data-stu-id="dfdab-128">If a database name for the object is not specified, the object must exist in the current database.</span></span> <span data-ttu-id="dfdab-129">Per altre informazioni sull'impostazione del contesto di database, vedere [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfdab-129">For more information about setting the database context, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="dfdab-130">Esistenza dell'oggetto nelle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="dfdab-130">The object exists in the system tables.</span></span> <span data-ttu-id="dfdab-131">Per verificare l'esistenza di una tabella o un altro oggetto con ambito schema, eseguire una query nella vista del catalogo **sys.objects**.</span><span class="sxs-lookup"><span data-stu-id="dfdab-131">To verify whether a table or other schema-scoped object exists, query the **sys.objects** catalog view.</span></span> <span data-ttu-id="dfdab-132">Se l'oggetto non è presente nelle tabelle di sistema, significa che è stato eliminato o l'utente non dispone delle autorizzazioni necessarie per visualizzare i metadati dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="dfdab-132">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="dfdab-133">Per altre informazioni sulle autorizzazioni per visualizzare i metadati degli oggetti, vedere [Configurazione della visibilità dei metadati](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="dfdab-133">For more information about permissions to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
-   <span data-ttu-id="dfdab-134">Presenza dell'oggetto nello schema predefinito dell'utente.</span><span class="sxs-lookup"><span data-stu-id="dfdab-134">The object is contained in the default schema of the user.</span></span> <span data-ttu-id="dfdab-135">Se questa condizione non si verifica, l'oggetto deve essere specificato nel formato in due parti *schema_name.object_name*.</span><span class="sxs-lookup"><span data-stu-id="dfdab-135">If it is not, the object must be specified using the two-part format *schema_name.object_name*.</span></span> <span data-ttu-id="dfdab-136">Si noti che è sempre necessario richiamare funzioni a valori scalari utilizzando almeno un nome in due parti.</span><span class="sxs-lookup"><span data-stu-id="dfdab-136">Note that scalar-valued functions must always be invoked by using at least a two-part name.</span></span>  
  
-   <span data-ttu-id="dfdab-137">Distinzione tra maiuscole e minuscole delle regole di confronto del database.</span><span class="sxs-lookup"><span data-stu-id="dfdab-137">The case sensitivity of the database collation.</span></span>  
  
     <span data-ttu-id="dfdab-138">Quando in un database vengono utilizzate regole di confronto con distinzione tra maiuscole e minuscole, il nome dell'oggetto deve corrispondere alla combinazione di maiuscole e minuscole dell'oggetto nel database.</span><span class="sxs-lookup"><span data-stu-id="dfdab-138">When a database uses a case-sensitive collation, the object name must match the case of the object in the database.</span></span> <span data-ttu-id="dfdab-139">Ad esempio, se un oggetto è specificato come **MiaTabella** in un database con regole di confronto che rispettano la distinzione tra maiuscole e minuscole, le query che si riferiscono all'oggetto come **miatabella** o **Miatabella** restituiranno l'errore 208 poiché i nomi degli oggetti non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="dfdab-139">For example, when an object is specified as **MyTable** in a database with a case sensitive collation, queries that refer to the object as **mytable** or **Mytable** will cause error 208 to return because the object names do not match.</span></span>  
  
     <span data-ttu-id="dfdab-140">Per verificare le regole di confronto del database, eseguire l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="dfdab-140">You can verify the database collation by running the following statement.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="dfdab-141">L'abbreviazione CS nel nome delle regole di confronto indica che le regole di confronto rispettano la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="dfdab-141">The abbreviation CS in the collation name indicates the collation is case sensitive.</span></span> <span data-ttu-id="dfdab-142">Ad esempio, Latin1_General_CS_AS è una regola di confronto con distinzione tra maiuscole e minuscole e distinzione tra caratteri accentati e non accentati,</span><span class="sxs-lookup"><span data-stu-id="dfdab-142">For example, Latin1_General_CS_AS is a case sensitive, accent sensitive collation.</span></span> <span data-ttu-id="dfdab-143">mentre CI indica una regola di confronto senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="dfdab-143">CI indicates a case insensitive collation.</span></span>  
  
-   <span data-ttu-id="dfdab-144">Autorizzazioni di accesso all'oggetto concesse all'utente.</span><span class="sxs-lookup"><span data-stu-id="dfdab-144">The user has permission to access the object.</span></span> <span data-ttu-id="dfdab-145">Per verificare le autorizzazioni di cui l'utente dispone sull'oggetto, usare la funzione di sistema **Has_Perms_By_Name**.</span><span class="sxs-lookup"><span data-stu-id="dfdab-145">To verify the permissions the user has on the object, use the **Has_Perms_By_Name** system function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfdab-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfdab-146">See Also</span></span>  
 <span data-ttu-id="dfdab-147">[USARE &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/use-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dfdab-147">[USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql) </span></span>  
 <span data-ttu-id="dfdab-148">[Configurazione della visibilità dei metadati](../security/metadata-visibility-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="dfdab-148">[Metadata Visibility Configuration](../security/metadata-visibility-configuration.md) </span></span>  
 [<span data-ttu-id="dfdab-149">HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dfdab-149">HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/has-perms-by-name-transact-sql)  
  
  
