---
title: MSSQLSERVER_2501 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2501 (Database Engine error)
ms.assetid: 895aafe3-a4e7-4ed8-acc5-93be76ef3664
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 200997dcfe7bf8a5933b9fce492daabd5baffd04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718185"
---
# <a name="mssqlserver_2501"></a><span data-ttu-id="0956d-102">MSSQLSERVER_2501</span><span class="sxs-lookup"><span data-stu-id="0956d-102">MSSQLSERVER_2501</span></span>
    
## <a name="details"></a><span data-ttu-id="0956d-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0956d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0956d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0956d-104">Product Name</span></span>|<span data-ttu-id="0956d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0956d-105">SQL Server</span></span>|  
|<span data-ttu-id="0956d-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="0956d-106">Event ID</span></span>|<span data-ttu-id="0956d-107">2501</span><span class="sxs-lookup"><span data-stu-id="0956d-107">2501</span></span>|  
|<span data-ttu-id="0956d-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0956d-108">Event Source</span></span>|<span data-ttu-id="0956d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0956d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0956d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0956d-110">Component</span></span>|<span data-ttu-id="0956d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0956d-111">SQLEngine</span></span>|  
|<span data-ttu-id="0956d-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0956d-112">Symbolic Name</span></span>|<span data-ttu-id="0956d-113">DBCC_NO_SUCH_TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="0956d-113">DBCC_NO_SUCH_TABLE_NAME</span></span>|  
|<span data-ttu-id="0956d-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0956d-114">Message Text</span></span>|<span data-ttu-id="0956d-115">Impossibile trovare un oggetto o una tabella con il nome 'NAME'.</span><span class="sxs-lookup"><span data-stu-id="0956d-115">Cannot find a table or object with the name 'NAME'.</span></span> <span data-ttu-id="0956d-116">Controllare il catalogo di sistema.</span><span class="sxs-lookup"><span data-stu-id="0956d-116">Check the system catalog.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0956d-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0956d-117">Explanation</span></span>  
 <span data-ttu-id="0956d-118">Non è possibile individuare l'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="0956d-118">The specified object cannot be found.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="0956d-119">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="0956d-119">Possible Causes</span></span>  
 <span data-ttu-id="0956d-120">L'errore può essere causato da uno dei problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0956d-120">This error can be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="0956d-121">L'oggetto non è stato specificato correttamente.</span><span class="sxs-lookup"><span data-stu-id="0956d-121">The object is not specified correctly.</span></span>  
  
-   <span data-ttu-id="0956d-122">L'oggetto non esiste o è stato rimosso prima di essere utilizzato in un'istruzione.</span><span class="sxs-lookup"><span data-stu-id="0956d-122">The object does not exist, or the object was dropped before a statement tried to use it.</span></span>  
  
-   <span data-ttu-id="0956d-123">È possibile che l'oggetto esista ma non possa essere esposto all'utente.</span><span class="sxs-lookup"><span data-stu-id="0956d-123">The object might exist, but could not be exposed to the user.</span></span> <span data-ttu-id="0956d-124">Ad esempio, l'utente potrebbe non disporre di autorizzazioni sufficienti per visualizzare l'oggetto oppure l'oggetto è costituito da una tabella interna che non può essere visualizzata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0956d-124">For example, the user might not have permissions on the object, or the object is an internal table that could not be seen by a user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0956d-125">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0956d-125">User Action</span></span>  
  
-   <span data-ttu-id="0956d-126">Verificare la correttezza del contesto di database corrente.</span><span class="sxs-lookup"><span data-stu-id="0956d-126">Verify the current database context is correct.</span></span> <span data-ttu-id="0956d-127">Per altre informazioni, vedere [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0956d-127">For more information, see [USE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/use-transact-sql).</span></span>  
  
-   <span data-ttu-id="0956d-128">Verificare che il nome della tabella o dell'oggetto sia stato specificato correttamente.</span><span class="sxs-lookup"><span data-stu-id="0956d-128">Verify that the table or object name is spelled correctly.</span></span>  
  
-   <span data-ttu-id="0956d-129">Verificare il nome dello schema contenente l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0956d-129">Verify the schema name that contains the object.</span></span> <span data-ttu-id="0956d-130">Se l'oggetto appartiene a uno schema diverso da quello predefinito, ovvero **dbo**, è necessario specificare il nome della tabella o dell'oggetto usando il formato in due parti *schema_name.object_name*.</span><span class="sxs-lookup"><span data-stu-id="0956d-130">If the object belongs to a schema other than the default (**dbo**) schema, you must specify the table or object name by using the two-part format *schema_name.object_name*.</span></span>  
  
-   <span data-ttu-id="0956d-131">Verificare l'esistenza dell'oggetto nelle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="0956d-131">Verify that the object exists in the system tables.</span></span> <span data-ttu-id="0956d-132">Per verificare l'esistenza di una tabella o un altro oggetto con ambito schema, eseguire una query nella vista del catalogo [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0956d-132">To verify whether a table or other schema-scoped object exists, query the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view.</span></span> <span data-ttu-id="0956d-133">Se l'oggetto non è presente nelle tabelle di sistema, significa che è stato eliminato o l'utente non dispone delle autorizzazioni necessarie per visualizzare i metadati dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="0956d-133">If the object is not in the system tables, the object has been deleted, or the user does not have permissions to view the object metadata.</span></span> <span data-ttu-id="0956d-134">Per altre informazioni su come visualizzare i metadati degli oggetti, vedere [Configurazione della visibilità dei metadati](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="0956d-134">For more information about how to view object metadata, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0956d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0956d-135">See Also</span></span>  
 [<span data-ttu-id="0956d-136">Viste del catalogo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0956d-136">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
  
