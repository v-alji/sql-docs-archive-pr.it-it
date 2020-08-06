---
title: Eliminare un articolo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- articles [SQL Server replication], dropping
- sp_droparticle
- sp_dropmergearticle
- deleting articles
- removing articles
- dropping articles
ms.assetid: 185b58fc-38c0-4abe-822e-6ec20066c863
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 082f90d33c2b8dedfae34dcada9b3935bed134ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625320"
---
# <a name="delete-an-article"></a><span data-ttu-id="0529c-102">Eliminazione di un articolo</span><span class="sxs-lookup"><span data-stu-id="0529c-102">Delete an Article</span></span>
  <span data-ttu-id="0529c-103">In questo argomento viene descritto come eliminare un articolo in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[tsql](../../../includes/tsql-md.md)] o RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="0529c-103">This topic describes how to delete an article in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)] or Replication Management Objects (RMO).</span></span> <span data-ttu-id="0529c-104">Per informazioni sulle condizioni per l'eliminazione degli articoli e sulla necessità di creare un nuovo snapshot o reinizializzare le sottoscrizioni in seguito all'eliminazione di un articolo, vedere [Aggiungere ed eliminare articoli in pubblicazioni esistenti](add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="0529c-104">For information about the conditions under which articles can be dropped and whether dropping an article requires a new snapshot or the reinitialization of subscriptions, see [Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0529c-105">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0529c-105">Using Transact-SQL</span></span>  
 <span data-ttu-id="0529c-106">È possibile eliminare gli articoli a livello di programmazione tramite le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="0529c-106">Articles can be deleted programmatically using replication stored procedures.</span></span> <span data-ttu-id="0529c-107">Le stored procedure utilizzate dipenderanno dal tipo di pubblicazione a cui appartiene l'articolo.</span><span class="sxs-lookup"><span data-stu-id="0529c-107">The stored procedures that you use depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-from-a-snapshot-or-transactional-publication"></a><span data-ttu-id="0529c-108">Per eliminare un articolo da una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="0529c-108">To delete an article from a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="0529c-109">Eseguire [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql) per eliminare un articolo, specificato da **\@article**, da una pubblicazione, specificata da **\@publication**.</span><span class="sxs-lookup"><span data-stu-id="0529c-109">Execute [sp_droparticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-droparticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="0529c-110">Specificare il valore **1** per \*\* \@ force_invalidate_snapshot\*\*.</span><span class="sxs-lookup"><span data-stu-id="0529c-110">Specify a value of **1** for **\@force_invalidate_snapshot**.</span></span>  
  
2.  <span data-ttu-id="0529c-111">(Facoltativo) Per rimuovere completamente l'oggetto pubblicato dal database, eseguire il comando `DROP <objectname>` nel database di pubblicazione del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0529c-111">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
#### <a name="to-delete-an-article-from-a-merge-publication"></a><span data-ttu-id="0529c-112">Per eliminare un articolo da una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="0529c-112">To delete an article from a merge publication</span></span>  
  
1.  <span data-ttu-id="0529c-113">Eseguire [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql) per eliminare un articolo, specificato da **\@article**, da una pubblicazione, specificata da **\@publication**.</span><span class="sxs-lookup"><span data-stu-id="0529c-113">Execute [sp_dropmergearticle &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropmergearticle-transact-sql) to delete an article, specified by **\@article**, from a publication, specified by **\@publication**.</span></span> <span data-ttu-id="0529c-114">Se necessario, specificare il valore **1** per \*\* \@ force_invalidate_snapshot\*\* e il valore **1** per \*\* \@ force_reinit_subscription\*\*.</span><span class="sxs-lookup"><span data-stu-id="0529c-114">If necessary, specify a value of **1** for **\@force_invalidate_snapshot** and a value of **1** for **\@force_reinit_subscription**.</span></span>  
  
2.  <span data-ttu-id="0529c-115">(Facoltativo) Per rimuovere completamente l'oggetto pubblicato dal database, eseguire il comando `DROP <objectname>` nel database di pubblicazione del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0529c-115">(Optional) To remove the published object from the database entirely, execute the `DROP <objectname>` command at the Publisher on the publication database.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="0529c-116">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0529c-116">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="0529c-117">Nell'esempio seguente un articolo viene eliminato da una pubblicazione transazionale.</span><span class="sxs-lookup"><span data-stu-id="0529c-117">The following example deletes an article from a transactional publication.</span></span> <span data-ttu-id="0529c-118">Poiché questa modifica invalida lo snapshot esistente, viene specificato il valore **1** per il parametro \*\* \@ force_invalidate_snapshot\*\* .</span><span class="sxs-lookup"><span data-stu-id="0529c-118">Because this change invalidates the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_droparticle](../../../snippets/tsql/SQL15/replication/howto/tsql/droptranpub.sql#sp_droparticle)]  
  
 <span data-ttu-id="0529c-119">Nell'esempio seguente due articoli vengono eliminati da una pubblicazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="0529c-119">The following example deletes two articles from a merge publication.</span></span> <span data-ttu-id="0529c-120">Poiché queste modifiche invalidano lo snapshot esistente, viene specificato il valore **1** per il parametro \*\* \@ force_invalidate_snapshot\*\* .</span><span class="sxs-lookup"><span data-stu-id="0529c-120">Because these changes invalidate the existing snapshot, a value of **1** is specified for the **\@force_invalidate_snapshot** parameter.</span></span>  
  
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergepub.sql#sp_dropmergearticle)]
 [!code-sql[HowTo#sp_dropmergearticle](../../../snippets/tsql/SQL15/replication/howto/tsql/dropmergearticles.sql#sp_dropmergearticle)]  
  
##  <a name="using-replication-management-objects-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="0529c-121">Utilizzo di RMO (Replication Management Objects)</span><span class="sxs-lookup"><span data-stu-id="0529c-121">Using Replication Management Objects (RMO)</span></span>  
 <span data-ttu-id="0529c-122">È possibile eliminare articoli a livello di programmazione tramite gli oggetti RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="0529c-122">You can delete articles programmatically by using Replication Management Objects (RMO).</span></span> <span data-ttu-id="0529c-123">Le classi RMO utilizzate per l'eliminazione di un articolo dipendono dal tipo di pubblicazione cui appartiene l'articolo.</span><span class="sxs-lookup"><span data-stu-id="0529c-123">The RMO classes you use to delete an article depend on the type of publication to which the article belongs.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-snapshot-or-transactional-publication"></a><span data-ttu-id="0529c-124">Per eliminare un articolo che appartiene a una pubblicazione snapshot o transazionale</span><span class="sxs-lookup"><span data-stu-id="0529c-124">To delete an article that belongs to a snapshot or transactional publication</span></span>  
  
1.  <span data-ttu-id="0529c-125">Creare una connessione al server di pubblicazione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="0529c-125">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="0529c-126">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.TransArticle>.</span><span class="sxs-lookup"><span data-stu-id="0529c-126">Create an instance of the <xref:Microsoft.SqlServer.Replication.TransArticle> class.</span></span>  
  
3.  <span data-ttu-id="0529c-127">Impostare le proprietà <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>e <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="0529c-127">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="0529c-128">Impostare la connessione del passaggio 1 per la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="0529c-128">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="0529c-129">Controllare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> per verificare che l'articolo esista.</span><span class="sxs-lookup"><span data-stu-id="0529c-129">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="0529c-130">Se il valore di questa proprietà è `false`, le proprietà dell'articolo sono state definite in modo non corretto nel passaggio 3 oppure l'articolo non esiste.</span><span class="sxs-lookup"><span data-stu-id="0529c-130">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="0529c-131">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="0529c-131">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="0529c-132">Chiudere tutte le connessioni.</span><span class="sxs-lookup"><span data-stu-id="0529c-132">Close all connections.</span></span>  
  
#### <a name="to-delete-an-article-that-belongs-to-a-merge-publication"></a><span data-ttu-id="0529c-133">Per eliminare un articolo che appartiene a una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="0529c-133">To delete an article that belongs to a merge publication</span></span>  
  
1.  <span data-ttu-id="0529c-134">Creare una connessione al server di pubblicazione tramite la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="0529c-134">Create a connection to the Publisher by using the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="0529c-135">Creare un'istanza della classe <xref:Microsoft.SqlServer.Replication.MergeArticle>.</span><span class="sxs-lookup"><span data-stu-id="0529c-135">Create an instance of the <xref:Microsoft.SqlServer.Replication.MergeArticle> class.</span></span>  
  
3.  <span data-ttu-id="0529c-136">Impostare le proprietà <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>e <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> .</span><span class="sxs-lookup"><span data-stu-id="0529c-136">Set the <xref:Microsoft.SqlServer.Replication.Article.Name%2A>, <xref:Microsoft.SqlServer.Replication.Article.PublicationName%2A>, and <xref:Microsoft.SqlServer.Replication.Article.DatabaseName%2A> properties.</span></span>  
  
4.  <span data-ttu-id="0529c-137">Impostare la connessione del passaggio 1 per la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> .</span><span class="sxs-lookup"><span data-stu-id="0529c-137">Set the connection from step 1 for the <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> property.</span></span>  
  
5.  <span data-ttu-id="0529c-138">Controllare la proprietà <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> per verificare che l'articolo esista.</span><span class="sxs-lookup"><span data-stu-id="0529c-138">Check the <xref:Microsoft.SqlServer.Replication.ReplicationObject.IsExistingObject%2A> property to verify that the article exists.</span></span> <span data-ttu-id="0529c-139">Se il valore di questa proprietà è `false`, le proprietà dell'articolo sono state definite in modo non corretto nel passaggio 3 oppure l'articolo non esiste.</span><span class="sxs-lookup"><span data-stu-id="0529c-139">If the value of this property is `false`, either the article properties in step 3 were defined incorrectly or the article does not exist.</span></span>  
  
6.  <span data-ttu-id="0529c-140">Chiamare il metodo <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> .</span><span class="sxs-lookup"><span data-stu-id="0529c-140">Call the <xref:Microsoft.SqlServer.Replication.Article.Remove%2A> method.</span></span>  
  
7.  <span data-ttu-id="0529c-141">Chiudere tutte le connessioni.</span><span class="sxs-lookup"><span data-stu-id="0529c-141">Close all connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0529c-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0529c-142">See Also</span></span>  
 <span data-ttu-id="0529c-143">[Aggiungere ed eliminare articoli in pubblicazioni esistenti](add-articles-to-and-drop-articles-from-existing-publications.md) </span><span class="sxs-lookup"><span data-stu-id="0529c-143">[Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md) </span></span>  
 [<span data-ttu-id="0529c-144">Replication System Stored Procedures Concepts</span><span class="sxs-lookup"><span data-stu-id="0529c-144">Replication System Stored Procedures Concepts</span></span>](../concepts/replication-system-stored-procedures-concepts.md)  
  
  
