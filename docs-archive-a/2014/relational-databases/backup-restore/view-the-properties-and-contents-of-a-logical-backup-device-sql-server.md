---
title: Visualizzare le proprietà e il contenuto di un dispositivo di backup logico (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- displaying backup content
- viewing backup content
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
- backing up databases [SQL Server], properties
- displaying backup properties
- backup devices [SQL Server], viewing information
- viewing backup properties
- database backups [SQL Server], properties
ms.assetid: 3a309074-e816-454d-b6c3-fcfdde0cbf74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f2bdf41e3dbda079e3627ff7a7c1c3c78103b728
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718282"
---
# <a name="view-the-properties-and-contents-of-a-logical-backup-device-sql-server"></a><span data-ttu-id="cfd67-102">Visualizzazione delle proprietà e del contenuto di un dispositivo di backup logico (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cfd67-102">View the Properties and Contents of a Logical Backup Device (SQL Server)</span></span>
  <span data-ttu-id="cfd67-103">In questo argomento viene illustrato come visualizzare le proprietà e il contenuto di un dispositivo di backup logico in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfd67-103">This topic describes how to view the properties and contents of a logical backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="cfd67-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="cfd67-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cfd67-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="cfd67-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cfd67-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cfd67-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cfd67-107">**Per visualizzare le proprietà e il contenuto di un dispositivo di backup logico utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="cfd67-107">**To view the properties and contents of a logical backup device, using:**</span></span>  
  
     [<span data-ttu-id="cfd67-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfd67-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cfd67-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cfd67-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cfd67-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="cfd67-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cfd67-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cfd67-111">Security</span></span>  
 <span data-ttu-id="cfd67-112">Per informazioni sulla sicurezza, vedere [RESTORE LABELONLY & #40; Transact-SQL & #41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cfd67-112">For information about security, see [RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cfd67-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="cfd67-113">Permissions</span></span>  
 <span data-ttu-id="cfd67-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] e versioni successive, per ottenere informazioni su un set o un dispositivo di backup è necessario disporre dell'autorizzazione CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="cfd67-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="cfd67-115">Per altre informazioni, vedere [GRANT - autorizzazioni per database &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cfd67-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cfd67-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cfd67-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="cfd67-117">Per visualizzare le proprietà e il contenuto di un dispositivo di backup logico</span><span class="sxs-lookup"><span data-stu-id="cfd67-117">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="cfd67-118">Dopo aver stabilito la connessione all'istanza appropriata del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server per espanderne l'albero.</span><span class="sxs-lookup"><span data-stu-id="cfd67-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="cfd67-119">Espandere **Oggetti server**e quindi **Dispositivi di backup**.</span><span class="sxs-lookup"><span data-stu-id="cfd67-119">Expand **Server Objects**, and expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="cfd67-120">Fare clic sul dispositivo e quindi fare clic con il pulsante destro del mouse su **Proprietà**per visualizzare la finestra di dialogo **Dispositivo di backup** .</span><span class="sxs-lookup"><span data-stu-id="cfd67-120">Click the device and right-click **Properties**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="cfd67-121">Nella pagina **Generale** sono indicati il nome del dispositivo e la destinazione, costituita da un dispositivo nastro o da un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="cfd67-121">The **General** page displays the device name and destination, which is either a tape device or file path.</span></span>  
  
5.  <span data-ttu-id="cfd67-122">Nel riquadro **Selezione pagina** fare clic su **Contenuto supporti**.</span><span class="sxs-lookup"><span data-stu-id="cfd67-122">In the **Select a Page** pane, click **Media Contents**.</span></span>  
  
6.  <span data-ttu-id="cfd67-123">Nel riquadro di destra verranno visualizzati i pannelli delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfd67-123">The right-hand pane displays in the following properties panels:</span></span>  
  
    -   <span data-ttu-id="cfd67-124">**Supporti**</span><span class="sxs-lookup"><span data-stu-id="cfd67-124">**Media**</span></span>  
  
         <span data-ttu-id="cfd67-125">Informazioni sulla sequenza dei supporti, ovvero numero di sequenza dei supporti, numero di sequenza del gruppo e identificatore mirror, se presente, e data e ora di creazione dei supporti.</span><span class="sxs-lookup"><span data-stu-id="cfd67-125">Media sequence information (the media sequence number, the family sequence number, and the mirror identifier, if any) and the media creation date and time.</span></span>  
  
    -   <span data-ttu-id="cfd67-126">**Set di supporti**</span><span class="sxs-lookup"><span data-stu-id="cfd67-126">**Media set**</span></span>  
  
         <span data-ttu-id="cfd67-127">Informazioni sul set di supporti: nome e, se disponibile, descrizione del set di supporti e numero di gruppi nel set.</span><span class="sxs-lookup"><span data-stu-id="cfd67-127">Media set information: the media set name and description, if any, and the number of families in the media set.</span></span>  
  
7.  <span data-ttu-id="cfd67-128">Nella griglia **Set di backup** sono visualizzate le informazioni sui contenuti del set di supporti.</span><span class="sxs-lookup"><span data-stu-id="cfd67-128">The **Backup sets** grid displays information about the contents of the media set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfd67-129">Per altre informazioni, vedere [Pagina Contenuto supporti](backup-device-media-contents-page.md).</span><span class="sxs-lookup"><span data-stu-id="cfd67-129">For more information, see [Media Contents Page](backup-device-media-contents-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cfd67-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cfd67-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="cfd67-131">Per visualizzare le proprietà e il contenuto di un dispositivo di backup logico</span><span class="sxs-lookup"><span data-stu-id="cfd67-131">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="cfd67-132">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cfd67-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cfd67-133">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="cfd67-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cfd67-134">Utilizzare l'istruzione [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="cfd67-134">Use the [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) statement.</span></span> <span data-ttu-id="cfd67-135">In questo esempio vengono restituite informazioni sul dispositivo di backup logico `AdvWrks2008R2Backup` .</span><span class="sxs-lookup"><span data-stu-id="cfd67-135">This example returns information about the `AdvWrks2008R2Backup` logical backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE LABELONLY  
   FROM AdvWrks2008R2Backup ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfd67-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfd67-136">See Also</span></span>  
 <span data-ttu-id="cfd67-137">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfd67-137">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="cfd67-138">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfd67-138">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="cfd67-139">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfd67-139">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="cfd67-140">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfd67-140">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="cfd67-141">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfd67-141">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="cfd67-142">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cfd67-142">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 [<span data-ttu-id="cfd67-143">Dispositivi di backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cfd67-143">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
