---
title: Ripristinare la chiave master del servizio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], importing
- service master key [SQL Server], restoring
ms.assetid: 14bdbbbe-d384-4692-b670-4243d2466fe1
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 2ad99fc9baa518d50678ddd6e6db1ec554658823
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726847"
---
# <a name="restore-the-service-master-key"></a><span data-ttu-id="6cfd6-102">Ripristino della chiave master del servizio</span><span class="sxs-lookup"><span data-stu-id="6cfd6-102">Restore the Service Master Key</span></span>
  <span data-ttu-id="6cfd6-103">In questo argomento viene descritto come ripristinare una chiave master del servizio in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cfd6-103">This topic describes how to restore the service master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="6cfd6-104">È improbabile che sia mai necessario ripristinare la chiave master del servizio.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-104">It is unlikely that you will ever need to restore the service master key.</span></span> <span data-ttu-id="6cfd6-105">In tal caso, tuttavia, è consigliabile procedere con estrema cautela.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-105">If you do, you should proceed with extreme caution.</span></span> <span data-ttu-id="6cfd6-106">Per altre informazioni, vedere [Back Up the Service Master Key](service-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="6cfd6-106">For more information, see [Back Up the Service Master Key](service-master-key.md).</span></span>  
  
 <span data-ttu-id="6cfd6-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6cfd6-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6cfd6-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="6cfd6-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="6cfd6-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6cfd6-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="6cfd6-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6cfd6-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="6cfd6-111">Per ripristinare la chiave master del servizio tramite Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6cfd6-111">To restore the service master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6cfd6-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="6cfd6-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="6cfd6-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="6cfd6-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="6cfd6-114">Quando si ripristina la chiave master del servizio, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vengono decrittografati tutti i segreti e tutte le chiavi crittografate con la chiave master del servizio corrente. Tali elementi vengono poi crittografati nuovamente con la chiave master del servizio caricata dal file di backup.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-114">When the service master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys and secrets that have been encrypted with the current service master key, and then encrypts them with the service master key loaded from the backup file.</span></span>  
  
-   <span data-ttu-id="6cfd6-115">In caso di esito negativo di una qualsiasi delle operazioni di decrittografia, il ripristino avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-115">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="6cfd6-116">È possibile utilizzare l'opzione FORCE per ignorare eventuali errori, ma in questo caso andranno perduti tutti i dati che non possono essere decrittografati.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-116">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="6cfd6-117">La rigenerazione della gerarchia di crittografia è un'operazione che utilizza molte risorse</span><span class="sxs-lookup"><span data-stu-id="6cfd6-117">Regenerating the encryption hierarchy is a resource-intensive operation.</span></span> <span data-ttu-id="6cfd6-118">e pertanto dovrebbe essere pianificata in periodi di carico ridotto.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-118">You should schedule this during a period of low demand.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="6cfd6-119">La chiave master del servizio è l'elemento radice della gerarchia di crittografia di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6cfd6-119">The service master key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="6cfd6-120">Con la chiave master del servizio vengono protette direttamente o indirettamente tutte le altre chiavi nell'albero.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-120">The service master key directly or indirectly secures all other keys in the tree.</span></span> <span data-ttu-id="6cfd6-121">Se non è possibile decrittografare una chiave dipendente durante un ripristino forzato, i dati protetti da tale chiave andranno perduti.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-121">If a dependent key cannot be decrypted during a forced restore, data that is secured by that key will be lost.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6cfd6-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="6cfd6-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6cfd6-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6cfd6-123">Permissions</span></span>  
 <span data-ttu-id="6cfd6-124">È richiesta l'autorizzazione CONTROL SERVER per il server.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-124">Requires CONTROL SERVER permission on the server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6cfd6-125">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6cfd6-125">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-the-service-master-key"></a><span data-ttu-id="6cfd6-126">Per ripristinare la chiave master del servizio</span><span class="sxs-lookup"><span data-stu-id="6cfd6-126">To restore the service master key</span></span>  
  
1.  <span data-ttu-id="6cfd6-127">Recuperare una copia della chiave master del servizio da un supporto di backup fisico o da una directory nel file system locale.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-127">Retrieve a copy of the backed-up service master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="6cfd6-128">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cfd6-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="6cfd6-129">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-129">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="6cfd6-130">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the service master key from a backup file.  
    RESTORE SERVICE MASTER KEY   
        FROM FILE = 'c:\temp_backups\keys\service_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="6cfd6-131">Il percorso del file della chiave e della password della chiave (se esistente) sarà diverso da quello indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-131">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="6cfd6-132">Assicurarsi che entrambi siano specifici della configurazione della chiave e del server in uso.</span><span class="sxs-lookup"><span data-stu-id="6cfd6-132">Please make sure that both are specific to your server and key set-up.</span></span>  
  
  
