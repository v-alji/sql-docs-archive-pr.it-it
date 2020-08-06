---
title: Impostare il livello di compatibilità per le pubblicazioni di tipo merge | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], replication
- backward compatibility [SQL Server], replication
- publications [SQL Server replication], backward compatibility
ms.assetid: db47ac73-948b-4d77-b272-bb3565135ea5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04ad80b0c99e7282ff2acfa459a08665efbdee1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637761"
---
# <a name="set-the-compatibility-level-for-merge-publications"></a><span data-ttu-id="37591-102">Impostazione del livello di compatibilità per le pubblicazioni di tipo merge</span><span class="sxs-lookup"><span data-stu-id="37591-102">Set the Compatibility Level for Merge Publications</span></span>
  <span data-ttu-id="37591-103">In questo argomento si illustra come impostare il livello di compatibilità per le pubblicazioni di tipo merge in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37591-103">This topic describes how to set the compatibility level for merge publications in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="37591-104">Il livello di compatibilità delle pubblicazioni viene utilizzato nella replica di tipo merge per determinare le funzionalità che possono essere utilizzate dalle pubblicazioni in un determinato database.</span><span class="sxs-lookup"><span data-stu-id="37591-104">Merge replication uses the publication compatibility level to determine which features can be used by publications in a given database.</span></span>  
  
 <span data-ttu-id="37591-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="37591-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="37591-106">**Per impostare il livello di compatibilità per le pubblicazioni di tipo merge, utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="37591-106">**To set the compatibility level for merge publications, using:**</span></span>  
  
     [<span data-ttu-id="37591-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37591-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="37591-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="37591-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="37591-109">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37591-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="37591-110">Impostare il livello di compatibilità nella pagina **Tipi di Sottoscrittore** della Creazione guidata nuova pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="37591-110">Set the compatibility level on the **Subscriber Types** page of the New Publication Wizard.</span></span> <span data-ttu-id="37591-111">Per ulteriori informazioni sull'accesso a questa procedura guidata, vedere [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="37591-111">For more information on accessing this wizard, see [Create a Publication](create-a-publication.md).</span></span> <span data-ttu-id="37591-112">Dopo la creazione di uno snapshot della pubblicazione, il livello di compatibilità può essere incrementato, ma non ridotto.</span><span class="sxs-lookup"><span data-stu-id="37591-112">After a publication snapshot is created, the compatibility level can be increased but cannot be decreased.</span></span> <span data-ttu-id="37591-113">Incrementare il livello di compatibilità nella pagina **Generale** della finestra di dialogo **Proprietà pubblicazione - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="37591-113">Increase the compatibility level on the **General** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="37591-114">Per ulteriori informazioni sull'accesso a questa finestra di dialogo, vedere [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="37591-114">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="37591-115">Incrementando il livello di compatibilità della pubblicazione, qualsiasi sottoscrizione esistente in server che eseguono versioni che risultano precedenti a tale livello di compatibilità non saranno più in grado di eseguire la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="37591-115">If you increase the publication compatibility level, any existing subscriptions at servers running versions prior to the compatibility level will no longer be able to synchronize.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37591-116">Poiché il livello di compatibilità influisce su altre proprietà della pubblicazione e sugli articoli per cui tali proprietà sono valide, non modificare il livello di compatibilità e le altre proprietà in un'unica operazione all'interno della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="37591-116">Because the compatibility level has implications for other publication properties and for which article properties are valid, do not change the compatibility level and other properties in the same use of the dialog box.</span></span> <span data-ttu-id="37591-117">Dopo la modifica della proprietà, lo snapshot per la pubblicazione dovrà essere rigenerato.</span><span class="sxs-lookup"><span data-stu-id="37591-117">The snapshot for the publication should be regenerated after the property is changed.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level"></a><span data-ttu-id="37591-118">Per impostare il livello di compatibilità della pubblicazione</span><span class="sxs-lookup"><span data-stu-id="37591-118">To set the publication compatibility level</span></span>  
  
-   <span data-ttu-id="37591-119">Nella pagina **Tipi di Sottoscrittore** della Creazione guidata nuova pubblicazione selezionare i tipi di Sottoscrittori che la pubblicazione dovrà supportare.</span><span class="sxs-lookup"><span data-stu-id="37591-119">On the **Subscriber Types** page of the New Publication Wizard, select the types of Subscribers that the publication should support.</span></span>  
  
#### <a name="to-increase-the-publication-compatibility-level"></a><span data-ttu-id="37591-120">Per incrementare il livello di compatibilità della pubblicazione</span><span class="sxs-lookup"><span data-stu-id="37591-120">To increase the publication compatibility level</span></span>  
  
-   <span data-ttu-id="37591-121">Nella pagina **Generale** della finestra di dialogo **Proprietà di pubblicazione - \<Publication>** selezionare un valore per **Livello di compatibilità**.</span><span class="sxs-lookup"><span data-stu-id="37591-121">On the **General** page of the **Publication Properties - \<Publication>** dialog box, select for **Compatibility level**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="37591-122">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="37591-122">Using Transact-SQL</span></span>  
 <span data-ttu-id="37591-123">È possibile impostare il livello di compatibilità per una pubblicazione di tipo merge a livello di programmazione codice quando una pubblicazione viene creata o modificata a livello di programmazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="37591-123">The compatibility level for a merge publication can either be set programmatically when a publication is created or modified programmatically at a later time.</span></span> <span data-ttu-id="37591-124">Per impostare o modificare questa proprietà di pubblicazione, è possibile utilizzare le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="37591-124">You can use replication stored procedures to set or change this publication property.</span></span>  
  
#### <a name="to-set-the-publication-compatibility-level-for-a-merge-publication"></a><span data-ttu-id="37591-125">Per impostare il livello di compatibilità per una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="37591-125">To set the publication compatibility level for a merge publication</span></span>  
  
1.  <span data-ttu-id="37591-126">Nel server di pubblicazione eseguire [sp_addmergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specificando un valore per per **@publication_compatibility_level** rendere la pubblicazione compatibile con le versioni precedenti di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37591-126">At the Publisher, execute [sp_addmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addmergepublication-transact-sql), specifying a value for **@publication_compatibility_level** to make the publication compatible with older versions of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="37591-127">Per altre informazioni, vedere [Create a Publication](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="37591-127">For more information, see [Create a Publication](create-a-publication.md).</span></span>  
  
#### <a name="to-change-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="37591-128">Per modificare il livello di compatibilità di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="37591-128">To change the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="37591-129">Eseguire [sp_changemergepublication &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specificando **publication_compatibility_level** per **@property** e il livello di compatibilità della pubblicazione appropriato per **@value** .</span><span class="sxs-lookup"><span data-stu-id="37591-129">Execute [sp_changemergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changemergepublication-transact-sql), specifying **publication_compatibility_level** for **@property** and the appropriate publication compatibility level for **@value**.</span></span>  
  
#### <a name="to-determine-the-publication-compatibility-level-of-a-merge-publication"></a><span data-ttu-id="37591-130">Per determinare il livello di compatibilità di una pubblicazione di tipo merge</span><span class="sxs-lookup"><span data-stu-id="37591-130">To determine the publication compatibility level of a merge publication</span></span>  
  
1.  <span data-ttu-id="37591-131">Eseguire [sp_helpmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specificando la pubblicazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="37591-131">Execute [sp_helpmergepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpmergepublication-transact-sql), specifying the desired publication.</span></span>  
  
2.  <span data-ttu-id="37591-132">Individuare il livello di compatibilità della pubblicazione nella colonna **backward_comp_level** del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="37591-132">Locate the publication compatibility level in the **backward_comp_level** column in the result set.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="37591-133">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="37591-133">Examples (Transact-SQL)</span></span>  
 <span data-ttu-id="37591-134">In questo esempio viene creata una pubblicazione di tipo merge e viene impostato il livello di compatibilità della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="37591-134">This example creates a merge publication and sets the publication compatibility level.</span></span>  
  
```  
-- To avoid storing the login and password in the script file, the values   
-- are passed into SQLCMD as scripting variables. For information about   
-- how to use scripting variables on the command line and in SQL Server  
-- Management Studio, see the "Executing Replication Scripts" section in  
-- the topic "Programming Replication Using System Stored Procedures".  
  
--Add a new merge publication.  
DECLARE @publicationDB AS sysname;  
DECLARE @publication AS sysname;  
DECLARE @login AS sysname;  
DECLARE @password AS sysname;  
SET @publicationDB = N'AdventureWorks2012';   
SET @publication = N'AdvWorksSalesOrdersMerge'   
SET @login = $(Login);  
SET @password = $(Password);  
  
-- Create a new merge publication.   
USE [AdventureWorks2012]  
EXEC sp_addmergepublication   
@publication = @publication,   
-- Set the compatibility level to SQL Server 2014.  
@publication_compatibility_level = '120RTM';   
  
-- Create the snapshot job for the publication.  
EXEC sp_addpublication_snapshot   
@publication = @publication,  
@job_login = @login,  
@job_password = @password;  
GO  
```  
  
 <span data-ttu-id="37591-135">In questo esempio viene modificato il livello di compatibilità per la pubblicazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="37591-135">This example changes the publication compatibility level for the merge publication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37591-136">È possibile che la modifica del livello di compatibilità della pubblicazione non sia consentita se nella pubblicazione vengono utilizzate caratteristiche che richiedono un livello di compatibilità specifico.</span><span class="sxs-lookup"><span data-stu-id="37591-136">Changing the publication compatibility level might not be allowed if the publication uses any features that require a particular compatibility level.</span></span> <span data-ttu-id="37591-137">Per altre informazioni, vedere [Compatibilità con le versioni precedenti della replica](../replication-backward-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="37591-137">For more information, see [Replication Backward Compatibility](../replication-backward-compatibility.md).</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
  
-- Change the publication compatibility level to   
-- SQL Server 2012.  
EXEC sp_changemergepublication   
@publication = @publication,   
@property = N'publication_compatibility_level',   
@value = N'110RTM';  
GO  
  
```  
  
 <span data-ttu-id="37591-138">In questo esempio viene restituito il livello di compatibilità corrente per la pubblicazione di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="37591-138">This example returns the current publication compatibility level for the merge publication.</span></span>  
  
```  
DECLARE @publication AS sysname;  
SET @publication = N'AdvWorksSalesOrdersMerge' ;  
EXEC sp_helpmergepublication   
@publication = @publication;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="37591-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37591-139">See Also</span></span>  
 [<span data-ttu-id="37591-140">Creare una pubblicazione</span><span class="sxs-lookup"><span data-stu-id="37591-140">Create a Publication</span></span>](create-a-publication.md)  
  
  
