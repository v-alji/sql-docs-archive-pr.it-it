---
title: Replica in sottoscrittori di tabelle con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
ms.assetid: 1a8e6bc7-433e-471d-b646-092dc80a2d1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df61b83d2f6d07cbbd21773b8940dd4e5341f76b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624028"
---
# <a name="replication-to-memory-optimized-table-subscribers"></a><span data-ttu-id="b904a-102">Replica in sottoscrittori di tabelle con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="b904a-102">Replication to Memory-Optimized Table Subscribers</span></span>
  <span data-ttu-id="b904a-103">Le tabelle con funzione di sottoscrittori di replica transazionale, esclusa la replica transazionale peer-to-peer, possono essere configurate come tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b904a-103">Tables acting as transactional replication subscribers, excluding Peer-to-peer transactional replication, can be configured as memory-optimized tables.</span></span> <span data-ttu-id="b904a-104">Le altre configurazioni di replica non sono compatibili con le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b904a-104">Other replication configurations are not compatible with memory-optimized tables.</span></span>  
  
## <a name="configuring-a-memory-optimized-table-as-a-subscriber"></a><span data-ttu-id="b904a-105">Configurazione di una tabella ottimizzata per la memoria come sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="b904a-105">Configuring a memory-optimized table as a subscriber</span></span>  
 <span data-ttu-id="b904a-106">Per configurare una tabella ottimizzata per la memoria come sottoscrittore, effettuare le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b904a-106">To configure a memory-optimized table as a subscriber, perform the following steps.</span></span>  
  
 <span data-ttu-id="b904a-107">**Creare e abilitare la pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="b904a-107">**Create and Enable Publication**</span></span>  
  
1.  <span data-ttu-id="b904a-108">Creazione di una pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b904a-108">Create a publication.</span></span>  
  
2.  <span data-ttu-id="b904a-109">Aggiungere articoli alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b904a-109">Add articles to the publication.</span></span> <span data-ttu-id="b904a-110">Per il parametro `@upd_cmd`, utilizzare la convenzione SCALL o SQL.</span><span class="sxs-lookup"><span data-stu-id="b904a-110">For the `@upd_cmd` parameter, use the SCALL or SQL convention.</span></span>  
  
    ```  
    EXEC sp_addarticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @source_owner = N'dbo',  
        @source_object = N'Mem_Table',  
        @type = N'logbased',  
        @description = null,  
        @creation_script = null,  
        @pre_creation_cmd = N'none',  
        @schema_option = 0x00000000080050DF,  
        @identityrangemanagementoption = N'manual',  
        @destination_table = N'Mem_Table',  
        @destination_owner = N'dbo',  
        @vertical_partition = N'false',  
        @ins_cmd = N'CALL sp_MSins_Mem_Table',  
        @del_cmd = N'CALL sp_MSdel_Mem_Table',  
        @upd_cmd = N'SCALL sp_MSupd_Mem_Table';  
    GO  
    ```  
  
 <span data-ttu-id="b904a-111">**Generare uno snapshot e adattare lo schema**</span><span class="sxs-lookup"><span data-stu-id="b904a-111">**Generate a Snapshot and Adjust the Schema**</span></span>  
  
1.  <span data-ttu-id="b904a-112">Creare un processo di snapshot e generare uno snapshot.</span><span class="sxs-lookup"><span data-stu-id="b904a-112">Create a snapshot job and generate a snapshot.</span></span>  
  
    ```  
    EXEC sp_addpublication_snapshot @publication = N'Publication1', @frequency_type = 1;  
    EXEC sp_startpublication_snapshot @publication = N'Publication1';  
    ```  
  
2.  <span data-ttu-id="b904a-113">Passare alla cartella dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="b904a-113">Navigate to the snapshot folder.</span></span> <span data-ttu-id="b904a-114">Il percorso predefinito è "C:\Programmi\Microsoft SQL Server\MSSQL12. \<INSTANCE> \MSSQL\repldata\unc\XXX\YYYYMMDDHHMMSS \\ ".</span><span class="sxs-lookup"><span data-stu-id="b904a-114">The default location is "C:\Program Files\Microsoft SQL Server\MSSQL12.\<INSTANCE>\MSSQL\repldata\unc\XXX\YYYYMMDDHHMMSS\\".</span></span>  
  
3.  <span data-ttu-id="b904a-115">Individuare il **. File SCH** per la tabella e aprirlo in Management Studio.</span><span class="sxs-lookup"><span data-stu-id="b904a-115">Locate the **.SCH** file for your table and open it in Management Studio.</span></span> <span data-ttu-id="b904a-116">Modificare lo schema della tabella e aggiornare la stored procedure, come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="b904a-116">Change the table schema and update the stored procedure as described below.</span></span>  
  
     <span data-ttu-id="b904a-117">Valutare gli indici definiti nel file IDX.</span><span class="sxs-lookup"><span data-stu-id="b904a-117">Evaluate the indexes defined in the IDX file.</span></span> <span data-ttu-id="b904a-118">Modificare `CREATE TABLE` per specificare gli indici, i vincoli, la chiave primaria e la sintassi ottimizzata per la memoria obbligatori.</span><span class="sxs-lookup"><span data-stu-id="b904a-118">Modify `CREATE TABLE` to specify the required indexes, constraints, primary key, and memory-optimized syntax.</span></span> <span data-ttu-id="b904a-119">Per le tabelle ottimizzate per la memoria, le colonne di indice devono essere NOT NULL e le colonne di indice di tipi di carattere devono essere Unicode e utilizzare le regole di confronto BIN2.</span><span class="sxs-lookup"><span data-stu-id="b904a-119">For memory-optimized tables, index columns should be NOT NULL and index columns of character types must be Unicode and use BIN2 collation.</span></span> <span data-ttu-id="b904a-120">Vedere l'esempio riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b904a-120">See example below:</span></span>  
  
    ```  
    SET ANSI_PADDING ON;  
    GO  
  
    SET ANSI_NULLS ON;  
    GO  
  
    SET QUOTED_IDENTIFIER ON;  
    GO  
  
    CREATE TABLE [dbo].[Mem_Table]([c1] [int] NOT NULL,  
        [c2] [float] NOT NULL,  
        [c3] [decimal](10, 2) NOT NULL,  
        [c4] [nvarchar](5) COLLATE SQL_Latin1_General_CP850_BIN2 NOT NULL,  
        INDEX [hash_index_sample_memoryoptimizedtable_c2] HASH (c2) WITH (BUCKET_COUNT = 1024),  
        INDEX [index_sample_memoryoptimizedtable_c3] NONCLUSTERED ([c3]),  
        INDEX [nvarchar_index_sample_memoryoptimizedtable_c4] ([c4]),  
        CONSTRAINT [PK_sample_memoryoptimizedtable] PRIMARY KEY NONCLUSTERED ([c1])) WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA);  
    GO  
    ```  
  
4.  <span data-ttu-id="b904a-121">Quando si utilizza la convenzione SCALL per il parametro `@upd_cmd`, passare al file di schema (con estensione SCH) e modificare l'istruzione di aggiornamento della tabella in `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]` per rimuovere le colonne di chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="b904a-121">When using SCALL convention for the `@upd_cmd` parameter, go to the schema (.SCH) file and change the table update statement in `create procedure [sp_MSupd_<SCHEMA><TABLE_NAME>]` to remove primary key columns.</span></span>  
  
     <span data-ttu-id="b904a-122">Per supportare gli aggiornamenti di chiave primaria, utilizzare una stored procedure di aggiornamento personalizzata per sostituire l'istruzione di aggiornamento della chiave primaria, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b904a-122">To support primary key updates, use a custom update stored procedure to replace the primary key update statement, as follows:</span></span>  
  
    1.  <span data-ttu-id="b904a-123">Selezionare i valori di colonna mancanti (SCALL fornisce solo la colonna interessata dall'operazione di aggiornamento).</span><span class="sxs-lookup"><span data-stu-id="b904a-123">Select missing column values (SCALL only provides the column involved into the update operation).</span></span>  
  
    2.  <span data-ttu-id="b904a-124">Eliminare il record esistente.</span><span class="sxs-lookup"><span data-stu-id="b904a-124">Delete the existing record.</span></span>  
  
    3.  <span data-ttu-id="b904a-125">Inserire un nuovo record con nuovi valori forniti, inclusa la nuova chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="b904a-125">Insert a new record with new values provided including the new primary key.</span></span>  
  
     <span data-ttu-id="b904a-126">La procedura di aggiornamento originale è la seguente:</span><span class="sxs-lookup"><span data-stu-id="b904a-126">The original update procedure looks like this:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
                   [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="b904a-127">Se la chiave primaria non deve essere mai aggiornata in un server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b904a-127">If the primary key should never be updated on a publisher.</span></span> <span data-ttu-id="b904a-128">Impostare come commento l'aggiornamento di tali colonne nella procedura di aggiornamento come segue:</span><span class="sxs-lookup"><span data-stu-id="b904a-128">Comment out the update to such columns in the update procedure as follows:</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                   @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    update [dbo].[Mem_Table] set  
    --             [c1] = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
     <span data-ttu-id="b904a-129">Per consentire il supporto degli aggiornamenti alla chiave primaria, modificare la procedura di aggiornamento nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b904a-129">To allow the support of updates to the primary key, modify the update procedure to read as follows</span></span>  
  
    ```  
    create procedure [sp_MSupd_Mem_Table]  
                   @c1 int = NULL,  
                   @c2 float = NULL,  
                   @c3 decimal(10,2) = NULL,  
                   @c4 nvarchar(5) = NULL,  
                    @pkc1 int = NULL,  
                   @bitmap binary(1)  
    as  
    begin    
    if (substring(@bitmap,1,1) & 1 = 1)  
    begin   
    select  
                   @c1 = case substring(@bitmap,1,1) & 1 when 1 then @c1 else [c1] end,  
                   @c2 = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   @c3 = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   @c4 = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    from [dbo].[Mem_Table] where [c1] = @pkc1  
    if @@rowcount <> 0 begin  
            delete [dbo].[Mem_Table] where [c1] = @pkc1  
            if @@rowcount <> 0  
                   insert into [dbo].[Mem_Table]([c1],  
                           [c2],  
                           [c3],  
                           [c4]) values (  
                           @c1,  
                           @c2,  
                           @c3,  
                           @c4  
                   )   
    end  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end    
    else  
    begin   
    update [dbo].[Mem_Table] set  
                   [c2] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [c2] end,  
                   [c3] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [c3] end,  
                   [c4] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [c4] end  
    where [c1] = @pkc1  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sp_MSreplraiserror 20598  
    end   
    end   
    go  
    ```  
  
5.  <span data-ttu-id="b904a-130">Creare il database del Sottoscrittore utilizzando l'opzione **eleva per l'isolamento dello snapshot** e impostare le regole di confronto predefinite su Latin1_General_CS_AS_KS_WS in caso di utilizzo di tipi di dati carattere non Unicode.</span><span class="sxs-lookup"><span data-stu-id="b904a-130">Create subscriber database using the **elevate to snapshot isolation** option and set the default collation to Latin1_General_CS_AS_KS_WS in case of using non Unicode character data types.</span></span>  
  
    ```  
    CREATE DATABASE [Sub]   
    CONTAINMENT = NONE   
    ON PRIMARY ( NAME = [Sub], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.mdf]),   
    FILEGROUP [mem] CONTAINS MEMORY_OPTIMIZED_DATA ( NAME = [mem],   
    FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub])  
    LOG ON ( NAME = [Sub_log], FILENAME = [C:\Program Files\Microsoft SQL Server\MSSQL12\MSSQL\DATA\Sub.ldf])  
    COLLATE Latin1_General_CS_AS_KS_WS;  
  
    ALTER DATABASE [Sub] SET MEMORY_OPTIMIZED_ELEVATE_TO_SNAPSHOT = ON;  
    GO  
    ```  
  
6.  <span data-ttu-id="b904a-131">Applicare lo schema al database di un Sottoscrittore e salvare lo schema per un utilizzo futuro.</span><span class="sxs-lookup"><span data-stu-id="b904a-131">Apply the schema to a subscriber's database and save the schema for future use.</span></span>  
  
7.  <span data-ttu-id="b904a-132">Caricare i dati (origine) del server di pubblicazione nel sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="b904a-132">Load the publisher (source) data to the subscriber.</span></span> <span data-ttu-id="b904a-133">I dati non devono essere modificati nel server di pubblicazione finché non si aggiunge una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="b904a-133">Data should not change at the publisher until you add a subscription.</span></span>  <span data-ttu-id="b904a-134">È possibile utilizzare BCP come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b904a-134">You can use BCP as shown below:</span></span>  
  
    ```  
    bcp Pub.dbo.Mem_Table out Mem_Table.bcp -S. -T -C1252 -n  
    bcp Sub.dbo.Mem_Table in Mem_Table.bcp -S. -T -C1252 -n  
    ```  
  
8.  <span data-ttu-id="b904a-135">Riconfigurare l'articolo per disabilitare le modifiche dello schema nel sottoscrittore:</span><span class="sxs-lookup"><span data-stu-id="b904a-135">Reconfigure the article to disable schema changes on the subscriber:</span></span>  
  
    ```  
    EXEC sp_changearticle  
        @publication = N'Publication1',  
        @article = N'Mem_Table',  
        @property = N'schema_option',  
        @value = 0,  
        @force_invalidate_snapshot = 1,  
        @force_reinit_subscription = 1;  
    GO  
    ```  
  
 <span data-ttu-id="b904a-136">**Aggiungere una sottoscrizione no sync**</span><span class="sxs-lookup"><span data-stu-id="b904a-136">**Add no sync Subscription**</span></span>  
  
 <span data-ttu-id="b904a-137">Aggiungere una sottoscrizione no sync.</span><span class="sxs-lookup"><span data-stu-id="b904a-137">Add a nosync subscription.</span></span>  
  
```  
EXEC sp_addsubscription  
    @publication = N' Publication1',  
    @subscriber = @@ServerName,  
    @destination_db = N'Sub',  
    @subscription_type = N'Push',  
    @sync_type = N'replication support only',  
    @article = N'all',  
    @update_mode = N'read only',  
    @subscriber_type = 0;  
GO  
```  
  
 <span data-ttu-id="b904a-138">Le tabelle con ottimizzazione per la memoria dovrebbero ora iniziare a ricevere aggiornamenti dal server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b904a-138">Memory-optimized tables should now start receiving updates from the publisher.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="b904a-139">Restrizioni</span><span class="sxs-lookup"><span data-stu-id="b904a-139">Restrictions</span></span>  
 <span data-ttu-id="b904a-140">È supportata una sola replica transazionale unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="b904a-140">Only one-way transactional replication is supported.</span></span> <span data-ttu-id="b904a-141">La replica transazionale peer-to-peer non è supportata.</span><span class="sxs-lookup"><span data-stu-id="b904a-141">Peer-to-peer transactional replication is not supported.</span></span>  
  
 <span data-ttu-id="b904a-142">Non è possibile pubblicare le tabelle con ottimizzazione per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b904a-142">Memory-optimized tables cannot be published.</span></span>  
  
 <span data-ttu-id="b904a-143">Non è possibile configurare le tabelle di replica nel distributore come tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b904a-143">Replication tables on the distributor cannot be configured as memory-optimized tables.</span></span>  
  
 <span data-ttu-id="b904a-144">La replica di tipo merge non può includere tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b904a-144">Merge replication cannot include memory-optimized tables.</span></span>  
  
 <span data-ttu-id="b904a-145">Nel sottoscrittore le tabelle interessate dalla replica transazionale possono essere configurate come tabelle ottimizzate per la memoria, ma le tabelle del sottoscrittore devono soddisfare i requisiti delle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b904a-145">At the subscriber, tables involved in transactional replication can be configured as memory optimized tables, but the subscriber tables must meet the requirements of memory-optimized tables.</span></span> <span data-ttu-id="b904a-146">Si applicano pertanto le restrizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b904a-146">This requires the following restrictions.</span></span>  
  
-   <span data-ttu-id="b904a-147">Per creare una tabella ottimizzata per la memoria in un sottoscrittore di replica transazionale, è necessario modificare manualmente i file dello schema dello snapshot utilizzati per creare le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b904a-147">To create a memory-optimized table on a transactional replication subscriber, the snapshot schema files used to create the memory-optimized tables must be manually modified.</span></span> <span data-ttu-id="b904a-148">Per ulteriori informazioni, vedere [modifica di un file di schema](#Schema).</span><span class="sxs-lookup"><span data-stu-id="b904a-148">For more information, see [Modifying a schema file](#Schema).</span></span>  
  
-   <span data-ttu-id="b904a-149">Alle tabelle replicate in tabelle ottimizzate per la memoria in un sottoscrittore si applica il limite di 8060 byte per riga delle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b904a-149">Tables replicated to memory-optimized tables on a subscriber are limited to the 8060 bytes per row limit of memory-optimized tables.</span></span>  
  
-   <span data-ttu-id="b904a-150">Le tabelle replicate in tabelle ottimizzate per la memoria in un sottoscrittore sono limitate ai tipi di dati consentiti nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b904a-150">Tables replicated to memory-optimized tables on a subscriber are limited to the data types permitted in memory-optimized tables.</span></span> <span data-ttu-id="b904a-151">Per ulteriori informazioni, vedere [tipi di dati supportati](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span><span class="sxs-lookup"><span data-stu-id="b904a-151">For more information, see [Supported Data Types](../in-memory-oltp/supported-data-types-for-in-memory-oltp.md).</span></span>  
  
-   <span data-ttu-id="b904a-152">Vengono applicate restrizioni all'aggiornamento della chiave primaria delle tabelle replicate in una tabella ottimizzata per la memoria in un sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="b904a-152">There are restrictions on updating the primary key of tables being replicated to a memory-optimized table on a subscriber.</span></span> <span data-ttu-id="b904a-153">Per ulteriori informazioni, vedere [replica delle modifiche in una chiave primaria](#PrimaryKey).</span><span class="sxs-lookup"><span data-stu-id="b904a-153">For more information, see [Replicating changes to a primary key](#PrimaryKey).</span></span>  
  
-   <span data-ttu-id="b904a-154">Chiave esterna, vincolo univoco, trigger, modifiche dello schema, ROWGUIDCOL, colonne calcolate, compressione dei dati, tipi di dati alias, controllo delle versioni e blocchi non sono supportati nelle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b904a-154">Foreign key, unique constraint, triggers, schema modifications, ROWGUIDCOL, computed columns, data compression, alias data types, versioning, and locks are not supported in memory-optimized tables.</span></span> <span data-ttu-id="b904a-155">Per informazioni, vedere [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) .</span><span class="sxs-lookup"><span data-stu-id="b904a-155">See [Transact-SQL Constructs Not Supported by In-Memory OLTP](../in-memory-oltp/transact-sql-constructs-not-supported-by-in-memory-oltp.md) for information.</span></span>  
  
##  <a name="modifying-a-schema-file"></a><a name="Schema"></a><span data-ttu-id="b904a-156">Modifica di un file di schema</span><span class="sxs-lookup"><span data-stu-id="b904a-156">Modifying a schema file</span></span>  
  
-   <span data-ttu-id="b904a-157">Gli indici cluster non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="b904a-157">Clustered indexes are not supported.</span></span> <span data-ttu-id="b904a-158">Modificare gli indici cluster in indici non cluster.</span><span class="sxs-lookup"><span data-stu-id="b904a-158">Change any clustered indexes to nonclustered indexes.</span></span>  
  
-   <span data-ttu-id="b904a-159">Tutte le colonne nella chiave di un indice devono essere specificate come `NOT NULL`.</span><span class="sxs-lookup"><span data-stu-id="b904a-159">All columns in the key of an index must be specified as `NOT NULL`.</span></span>  
  
-   <span data-ttu-id="b904a-160">Se si utilizza l'opzione della tabella ottimizzata per la memoria `DURABILITY = SCHEMA_AND_DATA`, la tabella deve disporre di un indice di chiave primaria non cluster.</span><span class="sxs-lookup"><span data-stu-id="b904a-160">If using the memory-optimized table option `DURABILITY = SCHEMA_AND_DATA` the table must have a nonclustered primary key index.</span></span>  
  
-   <span data-ttu-id="b904a-161">ANSI_PADDING deve essere ON.</span><span class="sxs-lookup"><span data-stu-id="b904a-161">ANSI_PADDING must be ON.</span></span>  
  
##  <a name="replicating-changes-to-a-primary-key"></a><a name="PrimaryKey"></a><span data-ttu-id="b904a-162">Replica delle modifiche a una chiave primaria</span><span class="sxs-lookup"><span data-stu-id="b904a-162">Replicating changes to a primary key</span></span>  
 <span data-ttu-id="b904a-163">Non è possibile aggiornare la chiave primaria di una tabella ottimizzata per la memoria.</span><span class="sxs-lookup"><span data-stu-id="b904a-163">The primary key of a memory-optimized table cannot be updated.</span></span> <span data-ttu-id="b904a-164">Per replicare un aggiornamento della chiave primaria in un sottoscrittore, modificare la stored procedure di aggiornamento per recapitare l'aggiornamento come coppia di eliminazione e inserimento.</span><span class="sxs-lookup"><span data-stu-id="b904a-164">To replicate a primary key update on a subscriber, modify the update stored procedure to deliver the update as a delete and insert pair.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b904a-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b904a-165">See Also</span></span>  
 [<span data-ttu-id="b904a-166">Replica di SQL Server</span><span class="sxs-lookup"><span data-stu-id="b904a-166">SQL Server Replication</span></span>](sql-server-replication.md)  
  
  
