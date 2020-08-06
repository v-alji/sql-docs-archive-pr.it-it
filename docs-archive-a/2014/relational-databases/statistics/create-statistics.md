---
title: Creare statistiche | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
f1_keywords:
- sql12.swb.statistics.propertis.f1
- sql12.swb.statistics.filter.f1
- sql12.swb.stat.properties.f1
- sql12.swb.stat.columns.f1
helpviewer_keywords:
- creating statistics
- statistics [SQL Server], creating
ms.assetid: 95a455fb-664d-4c95-851e-c6b62d7ebe04
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 230bd4d840c3d59dc1267dd6801754b68386cb32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636629"
---
# <a name="create-statistics"></a><span data-ttu-id="b48c5-102">Creare statistiche</span><span class="sxs-lookup"><span data-stu-id="b48c5-102">Create Statistics</span></span>
  <span data-ttu-id="b48c5-103">È possibile creare statistiche di ottimizzazione delle query per una o più colonne di una tabella o una vista indicizzata in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b48c5-103">You can create query optimization statistics on one or more columns of a table or indexed view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b48c5-104">Per la maggior parte delle query, tramite Query Optimizer vengono già generate le statistiche necessarie per un piano di query di alta qualità, ma in alcuni casi è necessario creare statistiche aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="b48c5-104">For most queries, the query optimizer already generates the necessary statistics for a high-quality query plan; in a few cases, you need to create additional statistics.</span></span>  
  
 <span data-ttu-id="b48c5-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="b48c5-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b48c5-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="b48c5-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b48c5-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b48c5-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b48c5-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b48c5-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b48c5-109">**Creare statistiche tramite:**</span><span class="sxs-lookup"><span data-stu-id="b48c5-109">**To create statistics, using:**</span></span>  
  
     [<span data-ttu-id="b48c5-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b48c5-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b48c5-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b48c5-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b48c5-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b48c5-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b48c5-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b48c5-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b48c5-114">Prima di creare statistiche con l'istruzione CREATE STATISTICS, verificare che l'opzione AUTO_CREATE_STATISTICS sia impostata a livello di database.</span><span class="sxs-lookup"><span data-stu-id="b48c5-114">Before creating statistics with the CREATE STATISTICS statement, verify that the AUTO_CREATE_STATISTICS option is set at the database level.</span></span> <span data-ttu-id="b48c5-115">In questo modo, tramite Query Optimizer continuano a essere normalmente create statistiche di colonna singola per colonne dei predicati di query.</span><span class="sxs-lookup"><span data-stu-id="b48c5-115">This will ensure that the query optimizer continues to routinely create single-column statistics for query predicate columns.</span></span>  
  
-   <span data-ttu-id="b48c5-116">È possibile elencare fino a 32 colonne per ogni oggetto statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-116">You can list up to 32 columns per statistics object.</span></span>  
  
-   <span data-ttu-id="b48c5-117">Non è possibile eliminare, rinominare o modificare la definizione di una colonna di tabella specificata in un predicato delle statistiche filtrate.</span><span class="sxs-lookup"><span data-stu-id="b48c5-117">You cannot drop, rename, or alter the definition of a table column that is defined in a filtered statistics predicate.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b48c5-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b48c5-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b48c5-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b48c5-119">Permissions</span></span>  
 <span data-ttu-id="b48c5-120">L'utente deve essere il proprietario della tabella o della vista indicizzata o un membro di uno dei seguenti ruoli: ruolo predefinito del server **sysadmin** , ruolo predefinito del database **db_owner** o ruolo predefinito del database **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="b48c5-120">Requires that the user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b48c5-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b48c5-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="b48c5-122">Per creare statistiche</span><span class="sxs-lookup"><span data-stu-id="b48c5-122">To create statistics</span></span>  
  
1.  <span data-ttu-id="b48c5-123">In **Esplora oggetti**fare clic sul segno più per espandere il database in cui si desidera creare una nuova statistica.</span><span class="sxs-lookup"><span data-stu-id="b48c5-123">In **Object Explorer**, click the plus sign to expand the database in which you want to create a new statistic.</span></span>  
  
2.  <span data-ttu-id="b48c5-124">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="b48c5-124">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="b48c5-125">Fare clic sul segno più per espandere la tabella in cui si desidera creare una nuova statistica.</span><span class="sxs-lookup"><span data-stu-id="b48c5-125">Click the plus sign to expand the table in which you want to create a new statistic.</span></span>  
  
4.  <span data-ttu-id="b48c5-126">Fare clic con il pulsante destro del mouse sulla cartella **Statistiche** e selezionare **Nuove statistiche...** .</span><span class="sxs-lookup"><span data-stu-id="b48c5-126">Right-click the **Statistics** folder and select **New Statistics...**.</span></span>  
  
     <span data-ttu-id="b48c5-127">Le proprietà seguenti vengono visualizzate nella pagina **generale** della finestra di dialogo **nuove statistiche per**_table_name_ tabella.</span><span class="sxs-lookup"><span data-stu-id="b48c5-127">The following properties show on the **General** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="b48c5-128">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="b48c5-128">**Table Name**</span></span>  
     <span data-ttu-id="b48c5-129">Consente di visualizzare il nome della tabella descritta dalle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-129">Displays the name of the table described by the statistics.</span></span>  
  
     <span data-ttu-id="b48c5-130">**Nome statistiche**</span><span class="sxs-lookup"><span data-stu-id="b48c5-130">**Statistics Name**</span></span>  
     <span data-ttu-id="b48c5-131">Consente di visualizzare il nome dell'oggetto di database in cui sono archiviate le statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-131">Displays the name of the database object where the statistics are stored.</span></span>  
  
     <span data-ttu-id="b48c5-132">**Colonne statistiche**</span><span class="sxs-lookup"><span data-stu-id="b48c5-132">**Statistics Columns**</span></span>  
     <span data-ttu-id="b48c5-133">In questa griglia vengono visualizzate le colonne descritte dal set di statistiche specifico.</span><span class="sxs-lookup"><span data-stu-id="b48c5-133">This grid shows the columns described by this set of statistics.</span></span> <span data-ttu-id="b48c5-134">Tutti i valori presenti nella griglia sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b48c5-134">All values in the grid are read-only.</span></span>  
  
     <span data-ttu-id="b48c5-135">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b48c5-135">**Name**</span></span>  
     <span data-ttu-id="b48c5-136">Consente di visualizzare il nome della colonna descritta dalle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-136">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="b48c5-137">Può trattarsi di una singola colonna o di una combinazione di colonne di una singola tabella.</span><span class="sxs-lookup"><span data-stu-id="b48c5-137">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="b48c5-138">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="b48c5-138">**Data Type**</span></span>  
     <span data-ttu-id="b48c5-139">Consente di indicare il tipo di dati delle colonne descritte dalle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-139">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="b48c5-140">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="b48c5-140">**Size**</span></span>  
     <span data-ttu-id="b48c5-141">Consente di visualizzare le dimensioni del tipo di dati per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="b48c5-141">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="b48c5-142">**Identità**</span><span class="sxs-lookup"><span data-stu-id="b48c5-142">**Identity**</span></span>  
     <span data-ttu-id="b48c5-143">Se è stata selezionata, questa opzione indica una colonna di identità.</span><span class="sxs-lookup"><span data-stu-id="b48c5-143">Indicates an identity column when it is checked.</span></span>  
  
     <span data-ttu-id="b48c5-144">**Consenti valori NULL**</span><span class="sxs-lookup"><span data-stu-id="b48c5-144">**Allow Nulls**</span></span>  
     <span data-ttu-id="b48c5-145">Consente di indicare se la colonna accetta valori NULL.</span><span class="sxs-lookup"><span data-stu-id="b48c5-145">Indicates whether the column accepts NULL values.</span></span>  
  
     <span data-ttu-id="b48c5-146">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="b48c5-146">**Add**</span></span>  
     <span data-ttu-id="b48c5-147">Consente di aggiungere ulteriori colonne dalla tabella alla griglia delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-147">Add additional columns from the table to the statistics grid.</span></span>  
  
     <span data-ttu-id="b48c5-148">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="b48c5-148">**Remove**</span></span>  
     <span data-ttu-id="b48c5-149">Consente di rimuovere la colonna selezionata dalla griglia delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-149">Remove the selected column from the statistics grid.</span></span>  
  
     <span data-ttu-id="b48c5-150">**Sposta su**</span><span class="sxs-lookup"><span data-stu-id="b48c5-150">**Move Up**</span></span>  
     <span data-ttu-id="b48c5-151">Consente di spostare la colonna selezionata in una posizione precedente nella griglia delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-151">Move the selected column to an earlier location in the statistics grid.</span></span> <span data-ttu-id="b48c5-152">La posizione all'interno della griglia può avere un impatto significativo sull'utilità delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-152">The location in the grid can substantially impact the usefulness of the statistics.</span></span>  
  
     <span data-ttu-id="b48c5-153">**Sposta giù**</span><span class="sxs-lookup"><span data-stu-id="b48c5-153">**Move Down**</span></span>  
     <span data-ttu-id="b48c5-154">Consente di spostare la colonna selezionata in una posizione successiva nella griglia delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-154">Move the selected column to a later location in the statistics grid.</span></span>  
  
     <span data-ttu-id="b48c5-155">**Ultimo aggiornamento delle statistiche per le colonne selezionate:**</span><span class="sxs-lookup"><span data-stu-id="b48c5-155">**Statistics for these columns were last updated:**</span></span>  
     <span data-ttu-id="b48c5-156">Indica la data delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-156">Indicates how old the statistics are.</span></span> <span data-ttu-id="b48c5-157">Le statistiche sono più utili se sono aggiornate.</span><span class="sxs-lookup"><span data-stu-id="b48c5-157">Statistics are more valuable when they are current.</span></span> <span data-ttu-id="b48c5-158">Aggiornare le statistiche dopo aver apportato un gran numero di modifiche ai dati o aver aggiunto dati non comuni.</span><span class="sxs-lookup"><span data-stu-id="b48c5-158">Update statistics after large changes to the data or after adding atypical data.</span></span> <span data-ttu-id="b48c5-159">Le statistiche per le tabelle con una distribuzione dei dati uniforme devono essere aggiornate con minore frequenza.</span><span class="sxs-lookup"><span data-stu-id="b48c5-159">Statistics for tables that have a consistent distribution of data need to be updated less frequently.</span></span>  
  
     <span data-ttu-id="b48c5-160">**Aggiorna statistiche per le colonne selezionate**</span><span class="sxs-lookup"><span data-stu-id="b48c5-160">**Update statistics for these columns**</span></span>  
     <span data-ttu-id="b48c5-161">Selezionare questa opzione per aggiornare le statistiche alla chiusura della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b48c5-161">Check to update the statistics when the dialog box is closed.</span></span>  
  
     <span data-ttu-id="b48c5-162">La proprietà seguente viene visualizzata nella pagina **filtro** della finestra di dialogo **nuove statistiche per**_table_name_ tabella.</span><span class="sxs-lookup"><span data-stu-id="b48c5-162">The following property shows on the **Filter** page in the **New Statistics on Table**_table_name_ dialog box.</span></span>  
  
     <span data-ttu-id="b48c5-163">**Espressione filtro**</span><span class="sxs-lookup"><span data-stu-id="b48c5-163">**Filter Expression**</span></span>  
     <span data-ttu-id="b48c5-164">Specifica le righe di dati da includere nelle statistiche filtrate.</span><span class="sxs-lookup"><span data-stu-id="b48c5-164">Defines which data rows to include in the filtered statistics.</span></span> <span data-ttu-id="b48c5-165">Ad esempio, usare `Production.ProductSubcategoryID IN ( 1,2,3 )`</span><span class="sxs-lookup"><span data-stu-id="b48c5-165">For example, `Production.ProductSubcategoryID IN ( 1,2,3 )`</span></span>  
  
5.  <span data-ttu-id="b48c5-166">Nella pagina **generale** della finestra di dialogo **nuove statistiche per**_table_name_ della tabella fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b48c5-166">In the **New Statistics on Table**_table_name_ dialog box, on the **General** page, click **Add**.</span></span>  
  
     <span data-ttu-id="b48c5-167">Nella finestra di dialogo **Seleziona colonne** vengono visualizzate le proprietà seguenti.</span><span class="sxs-lookup"><span data-stu-id="b48c5-167">The following properties show in the **Select Columns** dialog box.</span></span> <span data-ttu-id="b48c5-168">Queste informazioni sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b48c5-168">This information is read-only.</span></span>  
  
     <span data-ttu-id="b48c5-169">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b48c5-169">**Name**</span></span>  
     <span data-ttu-id="b48c5-170">Consente di visualizzare il nome della colonna descritta dalle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-170">Displays the name of the column described by the statistics.</span></span> <span data-ttu-id="b48c5-171">Può trattarsi di una singola colonna o di una combinazione di colonne di una singola tabella.</span><span class="sxs-lookup"><span data-stu-id="b48c5-171">This can be a single column or a combination of columns in a single table.</span></span>  
  
     <span data-ttu-id="b48c5-172">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="b48c5-172">**Data Type**</span></span>  
     <span data-ttu-id="b48c5-173">Consente di indicare il tipo di dati delle colonne descritte dalle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b48c5-173">Indicates the data type of the columns described by the statistics.</span></span>  
  
     <span data-ttu-id="b48c5-174">**Dimensione**</span><span class="sxs-lookup"><span data-stu-id="b48c5-174">**Size**</span></span>  
     <span data-ttu-id="b48c5-175">Consente di visualizzare le dimensioni del tipo di dati per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="b48c5-175">Displays the size of the data type for each column.</span></span>  
  
     <span data-ttu-id="b48c5-176">**Identità**</span><span class="sxs-lookup"><span data-stu-id="b48c5-176">**Identity**</span></span>  
     <span data-ttu-id="b48c5-177">Se viene selezionata, questa opzione consente di indicare una colonna di identità.</span><span class="sxs-lookup"><span data-stu-id="b48c5-177">Indicates an identity column when checked.</span></span>  
  
     <span data-ttu-id="b48c5-178">**Consenti valori Null**</span><span class="sxs-lookup"><span data-stu-id="b48c5-178">**Allow NULLs**</span></span>  
     <span data-ttu-id="b48c5-179">Consente di indicare se la colonna accetta valori NULL.</span><span class="sxs-lookup"><span data-stu-id="b48c5-179">Indicates whether the column accepts NULL values.</span></span>  
  
6.  <span data-ttu-id="b48c5-180">Nella finestra di dialogo **Seleziona colonne** selezionare le caselle di controllo per tutte le colonne per cui si desidera creare una statistica e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b48c5-180">In the **Select Columns** dialog box, select the check box or check boxes of each column for which you want to create a statistic and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="b48c5-181">Nella finestra di dialogo **nuove statistiche per**_table_name_ tabella fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b48c5-181">In the **New Statistics on Table**_table_name_ dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b48c5-182">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b48c5-182">Using Transact-SQL</span></span>  
  
#### <a name="to-create-statistics"></a><span data-ttu-id="b48c5-183">Per creare statistiche</span><span class="sxs-lookup"><span data-stu-id="b48c5-183">To create statistics</span></span>  
  
1.  <span data-ttu-id="b48c5-184">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b48c5-184">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b48c5-185">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="b48c5-185">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b48c5-186">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b48c5-186">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    -- Create new statistic object called ContactMail1  
    -- on the BusinessEntityID and EmailPromotion columns in the Person.Person table.   
  
    CREATE STATISTICS ContactMail1  
        ON Person.Person (BusinessEntityID, EmailPromotion);   
    GO  
    ```  
  
4.  <span data-ttu-id="b48c5-187">La statistica creata nella procedura precedente può garantire risultati migliori per la query seguente.</span><span class="sxs-lookup"><span data-stu-id="b48c5-187">The statistic created above potentially improves the results for the following query.</span></span>  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    SELECT LastName, FirstName  
    FROM Person.Person  
    WHERE EmailPromotion = 2  
    ORDER BY LastName, FirstName;   
    GO  
    ```  
  
 <span data-ttu-id="b48c5-188">Per altre informazioni, vedere [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b48c5-188">For more information, see [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  
