---
title: Ripristinare la chiave master di un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], importing
ms.assetid: 16897cc5-db8f-43bb-a38e-6855c82647cf
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 614ba8bdc494ae7e7e5b3ed7b62390721ef642a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726844"
---
# <a name="restore-a-database-master-key"></a><span data-ttu-id="2f942-102">Ripristino di una chiave master del database</span><span class="sxs-lookup"><span data-stu-id="2f942-102">Restore a Database Master Key</span></span>
  <span data-ttu-id="2f942-103">In questo argomento viene descritto come ripristinare una chiave master del database in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f942-103">This topic describes how to restore the database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2f942-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="2f942-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2f942-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="2f942-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2f942-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="2f942-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="2f942-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2f942-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="2f942-108">Per ripristinare la chiave master del database tramite Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2f942-108">To restore the database master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2f942-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2f942-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="2f942-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="2f942-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="2f942-111">Quando si ripristina la chiave master, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vengono decrittografate tutte le chiavi crittografate con la chiave master attiva corrente. Tali elementi venogno poi crittografati nuovamente con la chiave master ripristinata.</span><span class="sxs-lookup"><span data-stu-id="2f942-111">When the master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys that are encrypted with the currently active master key, and then encrypts these keys with the restored master key.</span></span> <span data-ttu-id="2f942-112">Si tratta di un'operazione che utilizza molte risorse e pertanto dovrebbe essere pianificata in periodi di carico ridotto.</span><span class="sxs-lookup"><span data-stu-id="2f942-112">This resource-intensive operation should be scheduled during a period of low demand.</span></span> <span data-ttu-id="2f942-113">L'operazione di ripristino avrà esito negativo se la chiave master del database corrente non è aperta e non è possibile aprirla, oppure se non è possibile decrittografare le eventuali chiavi crittografate con tale chiave master.</span><span class="sxs-lookup"><span data-stu-id="2f942-113">If the current database master key is not open or cannot be opened, or if any of the keys that are encrypted by it cannot be decrypted, the restore operation fails.</span></span>  
  
-   <span data-ttu-id="2f942-114">In caso di esito negativo di una qualsiasi delle operazioni di decrittografia, il ripristino avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2f942-114">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="2f942-115">È possibile utilizzare l'opzione FORCE per ignorare eventuali errori, ma in questo caso andranno perduti tutti i dati che non possono essere decrittografati.</span><span class="sxs-lookup"><span data-stu-id="2f942-115">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="2f942-116">Se la chiave master è stata crittografata con la chiave master del servizio, anche la chiave master ripristinata verrà crittografata con la chiave master del servizio.</span><span class="sxs-lookup"><span data-stu-id="2f942-116">If the master key was encrypted by the service master key, the restored master key will also be encrypted by the service master key.</span></span>  
  
-   <span data-ttu-id="2f942-117">Se il database corrente non include alcuna chiave master, con l'esecuzione di RESTORE MASTER KEY verrà creata una chiave master.</span><span class="sxs-lookup"><span data-stu-id="2f942-117">If there is no master key in the current database, RESTORE MASTER KEY creates a master key.</span></span> <span data-ttu-id="2f942-118">La nuova chiave master non verrà crittografata automaticamente con la chiave master del servizio.</span><span class="sxs-lookup"><span data-stu-id="2f942-118">The new master key will not be automatically encrypted with the service master key.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2f942-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2f942-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2f942-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2f942-120">Permissions</span></span>  
 <span data-ttu-id="2f942-121">È richiesta l'autorizzazione CONTROL per il database.</span><span class="sxs-lookup"><span data-stu-id="2f942-121">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="SSMSProcedure"></a><span data-ttu-id="2f942-122">Utilizzo di SQL Server Management Studio con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2f942-122">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-restore-the-database-master-key"></a><span data-ttu-id="2f942-123">Per ripristinare la chiave master del database</span><span class="sxs-lookup"><span data-stu-id="2f942-123">To restore the database master key</span></span>  
  
1.  <span data-ttu-id="2f942-124">Recuperare una copia della chiave master del database da un supporto di backup fisico o da una directory nel file system locale.</span><span class="sxs-lookup"><span data-stu-id="2f942-124">Retrieve a copy of the backed-up database master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="2f942-125">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f942-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="2f942-126">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="2f942-126">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="2f942-127">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2f942-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the database master key of the AdventureWorks2012 database.  
    USE AdventureWorks2012;  
    GO  
    RESTORE MASTER KEY   
        FROM FILE = 'c:\backups\keys\AdventureWorks2012_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003#GHkf02597gheij04'   
        ENCRYPTION BY PASSWORD = '259087M#MyjkFkjhywiyedfgGDFD';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="2f942-128">Il percorso del file della chiave e della password della chiave (se esistente) sarà diverso da quello indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2f942-128">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="2f942-129">Assicurarsi che entrambi siano specifici della configurazione della chiave e del server in uso.</span><span class="sxs-lookup"><span data-stu-id="2f942-129">Please make sure that both are specific to your server and key set-up.</span></span>  
  
 <span data-ttu-id="2f942-130">Per altre informazioni, vedere [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="2f942-130">For more information, see [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql)</span></span>  
  
  
