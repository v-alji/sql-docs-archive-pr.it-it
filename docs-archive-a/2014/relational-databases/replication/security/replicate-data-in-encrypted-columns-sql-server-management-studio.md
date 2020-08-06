---
title: Replicare dati in colonne crittografate (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], replicating data
- encryption [SQL Server replication]
- publishing [SQL Server replication], encrypted columns
ms.assetid: d1f8f586-e5a3-4a71-9391-11198d42bfa3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e1528d81faa352fdcdf37abe9ad93fda190445c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716247"
---
# <a name="replicate-data-in-encrypted-columns-sql-server-management-studio"></a><span data-ttu-id="92bbd-102">Replicare dati in colonne crittografate (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="92bbd-102">Replicate Data in Encrypted Columns (SQL Server Management Studio)</span></span>
  <span data-ttu-id="92bbd-103">La replica consente di pubblicare dati di colonna crittografati.</span><span class="sxs-lookup"><span data-stu-id="92bbd-103">Replication enables you to publish encrypted column data.</span></span> <span data-ttu-id="92bbd-104">Per decrittografare e utilizzare tali dati nel Sottoscrittore, la chiave utilizzata per crittografare i dati nel server di pubblicazione deve essere presente anche nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="92bbd-104">To decrypt and use this data at the Subscriber, the key that was used to encrypt the data at the Publisher must also be present on the Subscriber.</span></span> <span data-ttu-id="92bbd-105">La replica non rappresenta un meccanismo protetto per il trasporto di chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="92bbd-105">Replication does not provide a secure mechanism to transport encryption keys.</span></span> <span data-ttu-id="92bbd-106">La chiave di crittografia deve essere ricreata manualmente nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="92bbd-106">You must manually re-create the encryption key at the Subscriber.</span></span> <span data-ttu-id="92bbd-107">In questo argomento verrà illustrato come crittografare una colonna nel server di pubblicazione e garantire che la chiave di crittografia sia disponibile nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="92bbd-107">This topic shows you how to encrypt a column at the Publisher and make sure that the encryption key is available at the Subscriber.</span></span>  
  
 <span data-ttu-id="92bbd-108">I passaggi di base sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="92bbd-108">The basic steps are as follows:</span></span>  
  
1.  <span data-ttu-id="92bbd-109">Creare la chiave simmetrica nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="92bbd-109">Create the symmetric key at the Publisher.</span></span>  
  
2.  <span data-ttu-id="92bbd-110">Crittografare i dati della colonna con la chiave simmetrica.</span><span class="sxs-lookup"><span data-stu-id="92bbd-110">Encrypt column data with the symmetric key.</span></span>  
  
3.  <span data-ttu-id="92bbd-111">Pubblicare la tabella con la colonna crittografata.</span><span class="sxs-lookup"><span data-stu-id="92bbd-111">Publish the table with the encrypted column.</span></span>  
  
4.  <span data-ttu-id="92bbd-112">Sottoscrivere la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="92bbd-112">Subscribe to the publication.</span></span>  
  
5.  <span data-ttu-id="92bbd-113">Inizializzare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="92bbd-113">Initialize the subscription.</span></span>  
  
6.  <span data-ttu-id="92bbd-114">Ricreare la chiave simmetrica nel Sottoscrittore utilizzando i valori del passaggio 1 per ALGORITHM, KEY_SOURCE e IDENTITY_VALUE.</span><span class="sxs-lookup"><span data-stu-id="92bbd-114">Recreate the symmetric key at the Subscriber using same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span>  
  
7.  <span data-ttu-id="92bbd-115">Accedere ai dati della colonna crittografata.</span><span class="sxs-lookup"><span data-stu-id="92bbd-115">Access the encrypted column data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92bbd-116">Per crittografare i dati della colonna è consigliabile utilizzare una chiave simmetrica.</span><span class="sxs-lookup"><span data-stu-id="92bbd-116">You should use a symmetric key to encrypt column data.</span></span> <span data-ttu-id="92bbd-117">La chiave simmetrica può essere protetta in modi diversi nel server di pubblicazione e nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="92bbd-117">The symmetric key itself can be secured by different means at the Publisher and Subscriber.</span></span>  
  
### <a name="to-create-and-replicate-encrypted-column-data"></a><span data-ttu-id="92bbd-118">Per creare e replicare dati di colonne crittografate</span><span class="sxs-lookup"><span data-stu-id="92bbd-118">To create and replicate encrypted column data</span></span>  
  
1.  <span data-ttu-id="92bbd-119">Nel server di pubblicazione eseguire [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="92bbd-119">At the Publisher, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="92bbd-120">Il valore di KEY_SOURCE è rappresentato da dati importanti, utilizzabili per ricreare la chiave simmetrica e decrittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="92bbd-120">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="92bbd-121">KEY_SOURCE deve pertanto essere sempre archiviato e trasportato in modo protetto.</span><span class="sxs-lookup"><span data-stu-id="92bbd-121">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
2.  <span data-ttu-id="92bbd-122">Eseguire [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) per aprire la nuova chiave.</span><span class="sxs-lookup"><span data-stu-id="92bbd-122">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
3.  <span data-ttu-id="92bbd-123">Utilizzare la funzione [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) per crittografare i dati della colonna nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="92bbd-123">Use the [EncryptByKey](/sql/t-sql/functions/encryptbykey-transact-sql) function to encrypt column data at the Publisher.</span></span>  
  
4.  <span data-ttu-id="92bbd-124">Eseguire [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) per chiudere la chiave.</span><span class="sxs-lookup"><span data-stu-id="92bbd-124">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
5.  <span data-ttu-id="92bbd-125">Pubblicare la tabella contenente la colonna crittografata.</span><span class="sxs-lookup"><span data-stu-id="92bbd-125">Publish the table that contains the encrypted column.</span></span> <span data-ttu-id="92bbd-126">Per altre informazioni, vedere [Create a Publication](../publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="92bbd-126">For more information, see [Create a Publication](../publish/create-a-publication.md).</span></span>  
  
6.  <span data-ttu-id="92bbd-127">Sottoscrivere la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="92bbd-127">Subscribe to the publication.</span></span> <span data-ttu-id="92bbd-128">Per altre informazioni, vedere [Creare una sottoscrizione pull](../create-a-pull-subscription.md) o [Creare una sottoscrizione push](../create-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="92bbd-128">For more information, see [Create a Pull Subscription](../create-a-pull-subscription.md) or [Create a Push Subscription](../create-a-push-subscription.md).</span></span>  
  
7.  <span data-ttu-id="92bbd-129">Inizializzare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="92bbd-129">Initialize the subscription.</span></span> <span data-ttu-id="92bbd-130">Per altre informazioni, vedere [Creazione e applicazione dello snapshot iniziale](../create-and-apply-the-initial-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="92bbd-130">For more information, see [Create and Apply the Initial Snapshot](../create-and-apply-the-initial-snapshot.md).</span></span>  
  
8.  <span data-ttu-id="92bbd-131">Nel Sottoscrittore eseguire [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) utilizzando i valori del passaggio 1 per ALGORITHM, KEY_SOURCE e IDENTITY_VALUE.</span><span class="sxs-lookup"><span data-stu-id="92bbd-131">At the Subscriber, execute [CREATE SYMMETRIC KEY](/sql/t-sql/statements/create-symmetric-key-transact-sql) using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE as in step 1.</span></span> <span data-ttu-id="92bbd-132">È possibile specificare un valore diverso per ENCRYPTION BY.</span><span class="sxs-lookup"><span data-stu-id="92bbd-132">You can specify a different value for ENCRYPTION BY.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="92bbd-133">Il valore di KEY_SOURCE è rappresentato da dati importanti, utilizzabili per ricreare la chiave simmetrica e decrittografare i dati.</span><span class="sxs-lookup"><span data-stu-id="92bbd-133">The value of KEY_SOURCE is valuable data that can be used to re-create the symmetric key and decrypt data.</span></span> <span data-ttu-id="92bbd-134">KEY_SOURCE deve pertanto essere sempre archiviato e trasportato in modo protetto.</span><span class="sxs-lookup"><span data-stu-id="92bbd-134">KEY_SOURCE must always be stored and transported securely.</span></span>  
  
9. <span data-ttu-id="92bbd-135">Eseguire [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) per aprire la nuova chiave.</span><span class="sxs-lookup"><span data-stu-id="92bbd-135">Execute [OPEN SYMMETRIC KEY](/sql/t-sql/statements/open-symmetric-key-transact-sql) to open the new key.</span></span>  
  
10. <span data-ttu-id="92bbd-136">Utilizzare la funzione [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) per decrittografare i dati replicati nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="92bbd-136">Use the [DecryptByKey](/sql/t-sql/functions/decryptbykey-transact-sql) function to decrypt replicated data at the Subscriber.</span></span>  
  
11. <span data-ttu-id="92bbd-137">Eseguire [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) per chiudere la chiave.</span><span class="sxs-lookup"><span data-stu-id="92bbd-137">Execute [CLOSE SYMMETRIC KEY](/sql/t-sql/statements/close-symmetric-key-transact-sql) to close the key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92bbd-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="92bbd-138">Example</span></span>  
 <span data-ttu-id="92bbd-139">In questo esempio verranno creati una chiave simmetrica, un certificato utilizzato per proteggere la chiave simmetrica e una chiave master.</span><span class="sxs-lookup"><span data-stu-id="92bbd-139">This example creates a symmetric key, a certificate that is used to help secure the symmetric key, and a master key.</span></span> <span data-ttu-id="92bbd-140">Le chiavi verranno create nel database di pubblicazione e</span><span class="sxs-lookup"><span data-stu-id="92bbd-140">These keys are created in the publication database.</span></span> <span data-ttu-id="92bbd-141">verranno utilizzate per creare una colonna crittografata (EncryptedCreditCardApprovalCode) nella tabella `SalesOrderHeader` .</span><span class="sxs-lookup"><span data-stu-id="92bbd-141">They are then used to create an encrypted column (EncryptedCreditCardApprovalCode) in the `SalesOrderHeader` table.</span></span> <span data-ttu-id="92bbd-142">Questa colonna verrà pubblicata nella pubblicazione AdvWorksSalesOrdersMerge al posto della colonna non crittografata CreditCardApprovalCode.</span><span class="sxs-lookup"><span data-stu-id="92bbd-142">This column is published in the AdvWorksSalesOrdersMerge publication instead of the unencrypted CreditCardApprovalCode column.</span></span> <span data-ttu-id="92bbd-143">Se possibile, richiedere agli utenti di immettere le credenziali di sicurezza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="92bbd-143">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="92bbd-144">Se è necessario archiviare le credenziali in un file script, è fondamentale proteggere il file per evitare accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="92bbd-144">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_PublishEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/publishencryptedcolumn.sql#sp_publishencryptedcolumn)]  
  
 [!code-sql[HowTo#sp_AddMergeArticle](../../../snippets/tsql/SQL15/replication/howto/tsql/createmergepub.sql#sp_addmergearticle)]  
  
## <a name="example"></a><span data-ttu-id="92bbd-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="92bbd-145">Example</span></span>  
 <span data-ttu-id="92bbd-146">In questo esempio verrà ricreata la stessa chiave simmetrica nel database di sottoscrizione utilizzando i valori di ALGORITHM, KEY_SOURCE e IDENTITY_VALUE del primo esempio.</span><span class="sxs-lookup"><span data-stu-id="92bbd-146">This example recreates the same symmetric key in the subscription database using the same values for ALGORITHM, KEY_SOURCE, and IDENTITY_VALUE from the first example.</span></span> <span data-ttu-id="92bbd-147">Si presume che sia già stata inizializzata una sottoscrizione alla pubblicazione AdvWorksSalesOrdersMerge per la replica della colonna crittografata.</span><span class="sxs-lookup"><span data-stu-id="92bbd-147">This example assumes that you have already initialized a subscription to the AdvWorksSalesOrdersMerge publication to replicate the encrypted column.</span></span> <span data-ttu-id="92bbd-148">Se possibile, richiedere agli utenti di immettere le credenziali di sicurezza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="92bbd-148">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="92bbd-149">Se è necessario archiviare le credenziali in un file script, è fondamentale proteggere il file durante l'archiviazione e il trasporto per evitare accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="92bbd-149">If you must store credentials in a script file, you must secure the file during storage and transport to prevent unauthorized access.</span></span>  
  
 [!code-sql[HowTo#sp_SubscriberEncryptedColumn](../../../snippets/tsql/SQL15/replication/howto/tsql/subscriberencryptedcolumn.sql#sp_subscriberencryptedcolumn)]  
  
## <a name="see-also"></a><span data-ttu-id="92bbd-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92bbd-150">See Also</span></span>  
 <span data-ttu-id="92bbd-151">[Sicurezza replica di SQL Server](view-and-modify-replication-security-settings.md) </span><span class="sxs-lookup"><span data-stu-id="92bbd-151">[SQL Server Replication Security](view-and-modify-replication-security-settings.md) </span></span>  
 [<span data-ttu-id="92bbd-152">Creare chiavi simmetriche identiche su due server</span><span class="sxs-lookup"><span data-stu-id="92bbd-152">Create Identical Symmetric Keys on Two Servers</span></span>](../../security/encryption/create-identical-symmetric-keys-on-two-servers.md)  
  
  
