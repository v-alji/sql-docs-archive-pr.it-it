---
title: Eseguire il backup della chiave master di un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], exporting
ms.assetid: 7ad9a0a0-6e4f-4f7b-8801-8c1b9d49c4d8
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 9a66d28fea8289719d3efb2351409e0f14379ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725407"
---
# <a name="back-up-a-database-master-key"></a><span data-ttu-id="0568a-102">Backup della chiave master di un database</span><span class="sxs-lookup"><span data-stu-id="0568a-102">Back Up a Database Master Key</span></span>
  <span data-ttu-id="0568a-103">In questo argomento viene descritto come eseguire il backup di una chiave master del database in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0568a-103">This topic describes how to back up a database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0568a-104">La chiave master viene usata per crittografare altre chiavi e certificati all'interno di un database.</span><span class="sxs-lookup"><span data-stu-id="0568a-104">The database master key is used to encrypt other keys and certificates inside a database.</span></span> <span data-ttu-id="0568a-105">Se questa chiave viene eliminata oppure danneggiata, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] potrebbe non essere in grado di decrittografare tali chiavi e i dati crittografati con tali chiavi verranno di fatto persi.</span><span class="sxs-lookup"><span data-stu-id="0568a-105">If it is deleted or corrupted, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] may be unable to decrypt those keys, and the data encrypted using them will be effectively lost.</span></span> <span data-ttu-id="0568a-106">Per tale motivo, è consigliabile eseguire il backup della chiave master di un database e archiviare la copia di backup in un altro luogo adeguatamente protetto.</span><span class="sxs-lookup"><span data-stu-id="0568a-106">For this reason, you should back up the database master key and store the backup in a secure off-site location.</span></span>  
  
 <span data-ttu-id="0568a-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="0568a-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0568a-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="0568a-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0568a-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="0568a-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="0568a-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0568a-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="0568a-111">Per eseguire il backup di una chiave master del database tramite Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0568a-111">To back up a database master key using Transact-SQL</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0568a-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0568a-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0568a-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="0568a-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="0568a-114">È necessario aprire e pertanto decrittografare la chiave master prima di eseguirne il backup.</span><span class="sxs-lookup"><span data-stu-id="0568a-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="0568a-115">Se è crittografata con la chiave master del servizio, non è necessario aprire in modo esplicito la chiave master.</span><span class="sxs-lookup"><span data-stu-id="0568a-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened.</span></span> <span data-ttu-id="0568a-116">Se invece la chiave master è crittografata solo con una password dovrà essere aperta in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="0568a-116">But if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="0568a-117">È consigliabile creare una copia di backup della chiave master subito dopo la creazione e archiviare il backup in una posizione esterna sicura.</span><span class="sxs-lookup"><span data-stu-id="0568a-117">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0568a-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0568a-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0568a-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="0568a-119">Permissions</span></span>  
 <span data-ttu-id="0568a-120">È richiesta l'autorizzazione CONTROL per il database.</span><span class="sxs-lookup"><span data-stu-id="0568a-120">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="Procedure"></a><span data-ttu-id="0568a-121">Utilizzo di SQL Server Management Studio con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0568a-121">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-database-master-key"></a><span data-ttu-id="0568a-122">Per eseguire il backup della chiave master di un database</span><span class="sxs-lookup"><span data-stu-id="0568a-122">To back-up the database master key</span></span>  
  
1.  <span data-ttu-id="0568a-123">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]connettersi all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] contenente la chiave master del database di cui si desidera eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="0568a-123">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the database master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="0568a-124">Scegliere una password che verrà usata per crittografare la chiave master del database sul supporto di backup.</span><span class="sxs-lookup"><span data-stu-id="0568a-124">Choose a password that will be used to encrypt the database master key on the backup medium.</span></span> <span data-ttu-id="0568a-125">Questa password è soggetta ai controlli di complessità delle password.</span><span class="sxs-lookup"><span data-stu-id="0568a-125">This password is subject to complexity checks.</span></span>  
  
3.  <span data-ttu-id="0568a-126">Procurarsi un supporto di backup rimovibile per l'archiviazione di una copia della chiave di cui viene eseguito il backup.</span><span class="sxs-lookup"><span data-stu-id="0568a-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="0568a-127">Identificare una directory NTFS in cui creare il backup della chiave.</span><span class="sxs-lookup"><span data-stu-id="0568a-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="0568a-128">Il file specificato nel passaggio successivo verrà creato in questa directory,</span><span class="sxs-lookup"><span data-stu-id="0568a-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="0568a-129">che è consigliabile proteggere tramite elenchi di controllo di accesso altamente restrittivi.</span><span class="sxs-lookup"><span data-stu-id="0568a-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="0568a-130">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0568a-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="0568a-131">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="0568a-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="0568a-132">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0568a-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key. Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;   
    GO  
    OPEN MASTER KEY DECRYPTION BY PASSWORD = 'sfj5300osdVdgwdfkli7';   
  
    BACKUP MASTER KEY TO FILE = 'c:\temp\exportedmasterkey'   
        ENCRYPTION BY PASSWORD = 'sd092735kjn$&adsg';   
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="0568a-133">Il percorso del file della chiave e della password della chiave (se esistente) sarà diverso da quello indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="0568a-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="0568a-134">Assicurarsi che entrambi siano specifici della configurazione della chiave e del server in uso.</span><span class="sxs-lookup"><span data-stu-id="0568a-134">Please make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="0568a-135">Copiare il file nel supporto di backup e verificare la copia.</span><span class="sxs-lookup"><span data-stu-id="0568a-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="0568a-136">Archiviare il file in una posizione esterna protetta.</span><span class="sxs-lookup"><span data-stu-id="0568a-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="0568a-137">Per altre informazioni, vedere [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) e [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0568a-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  
