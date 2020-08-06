---
title: Eseguire il backup della chiave master del servizio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server], exporting
ms.assetid: f60b917c-6408-48be-b911-f93b05796904
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: b79212040df67c22ae7e34cd380a1a1f1bd10773
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725400"
---
# <a name="back-up-the-service-master-key"></a><span data-ttu-id="11431-102">Backup della chiave master del servizio</span><span class="sxs-lookup"><span data-stu-id="11431-102">Back Up the Service Master Key</span></span>
  <span data-ttu-id="11431-103">In questo argomento viene descritto come eseguire il backup di una chiave master del servizio in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11431-103">This topic describes how to back-up the Service Master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="11431-104">La chiave master del servizio è l'elemento radice della gerarchia di crittografia.</span><span class="sxs-lookup"><span data-stu-id="11431-104">The service master key is the root of the encryption hierarchy.</span></span> <span data-ttu-id="11431-105">È consigliabile crearne una copia di backup e archiviarla in una posizione esterna sicura.</span><span class="sxs-lookup"><span data-stu-id="11431-105">It should be backed up and stored in a secure, off-site location.</span></span> <span data-ttu-id="11431-106">La creazione di questa copia di backup dovrebbe essere una delle prime operazioni amministrative eseguite nel server.</span><span class="sxs-lookup"><span data-stu-id="11431-106">Creating this backup should be one of the first administrative actions performed on the server.</span></span>  
  
 <span data-ttu-id="11431-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="11431-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="11431-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="11431-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="11431-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="11431-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="11431-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="11431-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="11431-111">Per eseguire il backup della chiave master del servizio</span><span class="sxs-lookup"><span data-stu-id="11431-111">To back-up the Service Master key</span></span>](#Procedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="11431-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="11431-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="11431-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="11431-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="11431-114">È necessario aprire e pertanto decrittografare la chiave master prima di eseguirne il backup.</span><span class="sxs-lookup"><span data-stu-id="11431-114">The master key must be open and, therefore, decrypted before it is backed up.</span></span> <span data-ttu-id="11431-115">Se crittografata con la chiave master del servizio, non è necessario che la chiave master venga aperta in modo esplicito. Tuttavia, se la chiave master viene crittografata solo con una password, è necessario aprirla in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="11431-115">If it is encrypted with the service master key, the master key does not have to be explicitly opened; however, if the master key is encrypted only with a password, it must be explicitly opened.</span></span>  
  
-   <span data-ttu-id="11431-116">È consigliabile creare una copia di backup della chiave master subito dopo la creazione e archiviare il backup in una posizione esterna sicura.</span><span class="sxs-lookup"><span data-stu-id="11431-116">We recommend that you back up the master key as soon as it is created, and store the backup in a secure, off-site location.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="11431-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="11431-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="11431-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="11431-118">Permissions</span></span>  
 <span data-ttu-id="11431-119">È richiesta l'autorizzazione CONTROL per il database.</span><span class="sxs-lookup"><span data-stu-id="11431-119">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="Procedure"></a> <span data-ttu-id="11431-120">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="11431-120">Using Transact-SQL</span></span>  
  
#### <a name="to-back-up-the-service-master-key"></a><span data-ttu-id="11431-121">Per eseguire il backup della chiave master del servizio</span><span class="sxs-lookup"><span data-stu-id="11431-121">To back-up the Service Master key</span></span>  
  
1.  <span data-ttu-id="11431-122">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]connettersi all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] contenente la chiave master del servizio di cui si desidera eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="11431-122">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance containing the service master key you wish to back up.</span></span>  
  
2.  <span data-ttu-id="11431-123">Scegliere una password da utilizzare per crittografare la chiave master del servizio nel supporto di backup.</span><span class="sxs-lookup"><span data-stu-id="11431-123">Choose a password that will be used to encrypt the service master key on the backup medium.</span></span> <span data-ttu-id="11431-124">Questa password è soggetta ai controlli di complessità delle password.</span><span class="sxs-lookup"><span data-stu-id="11431-124">This password is subject to complexity checks.</span></span> <span data-ttu-id="11431-125">Per ulteriori informazioni, vedere [Password Policy](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="11431-125">For more information, see [Password Policy](../password-policy.md).</span></span>  
  
3.  <span data-ttu-id="11431-126">Procurarsi un supporto di backup rimovibile per l'archiviazione di una copia della chiave di cui viene eseguito il backup.</span><span class="sxs-lookup"><span data-stu-id="11431-126">Obtain a removable backup medium for storing a copy of the backed-up key.</span></span>  
  
4.  <span data-ttu-id="11431-127">Identificare una directory NTFS in cui creare il backup della chiave.</span><span class="sxs-lookup"><span data-stu-id="11431-127">Identify an NTFS directory in which to create the backup of the key.</span></span> <span data-ttu-id="11431-128">Il file specificato nel passaggio successivo verrà creato in questa directory,</span><span class="sxs-lookup"><span data-stu-id="11431-128">This is where you will create the file specified in the next step.</span></span> <span data-ttu-id="11431-129">che è consigliabile proteggere tramite elenchi di controllo di accesso altamente restrittivi.</span><span class="sxs-lookup"><span data-stu-id="11431-129">The directory should be protected with highly restrictive access control lists (ACLs).</span></span>  
  
5.  <span data-ttu-id="11431-130">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11431-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
6.  <span data-ttu-id="11431-131">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="11431-131">On the Standard bar, click **New Query**.</span></span>  
  
7.  <span data-ttu-id="11431-132">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="11431-132">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates a backup of the "AdventureWorks2012" master key.  
    -- Because this master key is not encrypted by the service master key, a password must be specified when it is opened.  
    USE AdventureWorks2012;  
    GO  
    BACKUP SERVICE MASTER KEY TO FILE = 'c:\temp_backups\keys\service_master_ key'   
        ENCRYPTION BY PASSWORD = '3dH85Hhk003GHk2597gheij4';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="11431-133">Il percorso del file della chiave e della password della chiave (se esistente) sarà diverso da quello indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="11431-133">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="11431-134">Assicurarsi che entrambi siano specifici della configurazione della chiave e del server in uso.</span><span class="sxs-lookup"><span data-stu-id="11431-134">Make sure that both are specific to your server and key set-up.</span></span>  
  
8.  <span data-ttu-id="11431-135">Copiare il file nel supporto di backup e verificare la copia.</span><span class="sxs-lookup"><span data-stu-id="11431-135">Copy the file to the backup medium and verify the copy.</span></span>  
  
9. <span data-ttu-id="11431-136">Archiviare il file in una posizione esterna protetta.</span><span class="sxs-lookup"><span data-stu-id="11431-136">Store the backup in a secure, off-site location.</span></span>  
  
 <span data-ttu-id="11431-137">Per altre informazioni, vedere [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) e [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="11431-137">For more information, see [OPEN MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/open-master-key-transact-sql) and [BACKUP MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-master-key-transact-sql).</span></span>  
  
  
