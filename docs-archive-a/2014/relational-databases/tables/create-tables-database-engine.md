---
title: Creare tabelle (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- table creation [SQL Server], Visual Database Tools
ms.assetid: 6f7c6ac5-e6d3-4dca-831e-b28442ba535b
author: stevestein
ms.author: sstein
ms.openlocfilehash: a8d84a4da6a10fbcbae311fe1bf738c03b85a4c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638341"
---
# <a name="create-tables-database-engine"></a><span data-ttu-id="e7f97-102">Creare tabelle (motore di database)</span><span class="sxs-lookup"><span data-stu-id="e7f97-102">Create Tables (Database Engine)</span></span>
  <span data-ttu-id="e7f97-103">È possibile creare una nuova tabella, assegnarle un nome e aggiungerla a un database esistente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7f97-103">You can create a new table, name it, and add it to an existing database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>

> [!NOTE]
>  <span data-ttu-id="e7f97-104">Se si è connessi a un database di SQL Azure, l'opzione Nuova tabella avvierà uno script modello per la creazione della tabella.</span><span class="sxs-lookup"><span data-stu-id="e7f97-104">If you are connected to a SQL Azure database, the new table option launches a create table template script.</span></span> <span data-ttu-id="e7f97-105">Modificare i parametri, quindi eseguire lo script per creare una nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="e7f97-105">Edit the parameters, then run the script to create a new table.</span></span> <span data-ttu-id="e7f97-106">Per ulteriori informazioni, vedere [SQL Azure Overview](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx).</span><span class="sxs-lookup"><span data-stu-id="e7f97-106">For more information, see [SQL Azure Overview](https://microsoft.sharepoint.com/sites/infopedia_g01/pages/cards/azure-sql-database.aspx).</span></span>

 <span data-ttu-id="e7f97-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="e7f97-107">**In This Topic**</span></span>

-   <span data-ttu-id="e7f97-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e7f97-108">**Before you begin:**</span></span>

     [<span data-ttu-id="e7f97-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e7f97-109">Security</span></span>](#Security)

-   <span data-ttu-id="e7f97-110">**Per creare una tabella:**</span><span class="sxs-lookup"><span data-stu-id="e7f97-110">**To create a table, using:**</span></span>

     [<span data-ttu-id="e7f97-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7f97-111">SQL Server Management Studio</span></span>](#SSMSProcedure)

     [<span data-ttu-id="e7f97-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7f97-112">Transact-SQL</span></span>](#TsqlProcedure)

##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e7f97-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e7f97-113">Before You Begin</span></span>

###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e7f97-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e7f97-114">Security</span></span>

####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e7f97-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e7f97-115">Permissions</span></span>
 <span data-ttu-id="e7f97-116">Sono richieste l'autorizzazione CREATE TABLE per il database e l'autorizzazione ALTER per lo schema in cui viene creata la tabella.</span><span class="sxs-lookup"><span data-stu-id="e7f97-116">Requires CREATE TABLE permission in the database and ALTER permission on the schema in which the table is being created.</span></span>

 <span data-ttu-id="e7f97-117">Se tutte le colonne nell'istruzione CREATE TABLE sono definite come tipo CLR definito dall'utente, è necessario che l'utente sia il proprietario del tipo o disponga dell'autorizzazione REFERENCES.</span><span class="sxs-lookup"><span data-stu-id="e7f97-117">If any columns in the CREATE TABLE statement are defined as a CLR user-defined type, either ownership of the type or REFERENCES permission on it is required.</span></span>

 <span data-ttu-id="e7f97-118">Se a una colonna nell'istruzione CREATE TABLE è associata una raccolta di XML Schema, è necessario che l'utente sia il proprietario della raccolta di XML Schema o disponga dell'autorizzazione REFERENCES.</span><span class="sxs-lookup"><span data-stu-id="e7f97-118">If any columns in the CREATE TABLE statement have an XML schema collection associated with them, either ownership of the XML schema collection or REFERENCES permission on it is required.</span></span>

##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e7f97-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e7f97-119">Using SQL Server Management Studio</span></span>

#### <a name="to-create-a-table-with-table-designer"></a><span data-ttu-id="e7f97-120">Per creare una tabella con Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="e7f97-120">To create a table with Table Designer</span></span>

1.  <span data-ttu-id="e7f97-121">In **Esplora oggetti**connettersi all'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] contenente il database da modificare.</span><span class="sxs-lookup"><span data-stu-id="e7f97-121">In **Object Explorer**, connect to the instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] that contains the database to be modified.</span></span>

2.  <span data-ttu-id="e7f97-122">In **Esplora oggetti**espandere il nodo **Database** , quindi espandere il database in cui sarà contenuta la nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="e7f97-122">In **Object Explorer**, expand the **Databases** node and then expand the database that will contain the new table.</span></span>

3.  <span data-ttu-id="e7f97-123">In Esplora oggetti fare clic con il pulsante destro del mouse sul nodo **Tabelle** del database, quindi su **Nuova tabella**.</span><span class="sxs-lookup"><span data-stu-id="e7f97-123">In Object Explorer, right-click the **Tables** node of your database and then click **New Table**.</span></span>

4.  <span data-ttu-id="e7f97-124">Digitare i nomi delle colonne, scegliere i tipi di dati e indicare se sono consentiti i valori Null per ogni colonna come mostrato nell'illustrazione riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="e7f97-124">Type column names, choose data types, and choose whether to allow nulls for each column as shown in the following illustration.</span></span>

     <span data-ttu-id="e7f97-125">![AddColumnsinTableDesigner](../../database-engine/media/addcolumnsintabledesigner.gif "AddColumnsinTableDesigner")</span><span class="sxs-lookup"><span data-stu-id="e7f97-125">![AddColumnsinTableDesigner](../../database-engine/media/addcolumnsintabledesigner.gif "AddColumnsinTableDesigner")</span></span>

5.  <span data-ttu-id="e7f97-126">Per specificare più proprietà di una colonna, ad esempio i valori di colonna calcolata o Identity, fare clic sulla colonna e nella scheda delle proprietà delle colonne scegliere le proprietà appropriate.</span><span class="sxs-lookup"><span data-stu-id="e7f97-126">To specify more properties for a column, such as identity or computed column values, click the column and in the column properties tab, choose the appropriate properties.</span></span> <span data-ttu-id="e7f97-127">Per altre informazioni sulle proprietà delle colonne, vedere [Proprietà delle colonne delle tabelle &#40;SQL Server Management Studio&#41;](table-column-properties-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e7f97-127">For more information about column properties, see [Table Column Properties &#40;SQL Server Management Studio&#41;](table-column-properties-sql-server-management-studio.md).</span></span>

6.  <span data-ttu-id="e7f97-128">Per specificare una colonna come chiave primaria, fare clic con il pulsante destro del mouse sulla colonna e selezionare **Imposta chiave primaria**.</span><span class="sxs-lookup"><span data-stu-id="e7f97-128">To specify a column as a primary key, right-click the column and select **Set Primary Key**.</span></span> <span data-ttu-id="e7f97-129">Per altre informazioni, vedere [Create Primary Keys](../tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="e7f97-129">For more information, see [Create Primary Keys](../tables/create-primary-keys.md).</span></span>

7.  <span data-ttu-id="e7f97-130">Per creare relazioni di chiave esterna, vincoli CHECK o indici, fare clic con il pulsante destro del mouse nel riquadro Progettazione tabelle e selezionare un oggetto nell'elenco come mostrato nell'illustrazione riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="e7f97-130">To create foreign key relationships, check constraints, or indexes, right-click in the Table Designer pane and select an object from the list as shown in the following illustration.</span></span>

     <span data-ttu-id="e7f97-131">![AddTableObjects](../../database-engine/media/addtableobjects.gif "AddTableObjects")</span><span class="sxs-lookup"><span data-stu-id="e7f97-131">![AddTableObjects](../../database-engine/media/addtableobjects.gif "AddTableObjects")</span></span>

     <span data-ttu-id="e7f97-132">Per ulteriori informazioni su questi oggetti, vedere [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) e [Indexes](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="e7f97-132">For more information about these objects, see [Create Foreign Key Relationships](../tables/create-foreign-key-relationships.md), [Create Check Constraints](../tables/create-check-constraints.md) and [Indexes](../indexes/indexes.md).</span></span>

8.  <span data-ttu-id="e7f97-133">Per impostazione predefinita, la tabella è inclusa nello schema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="e7f97-133">By default, the table is contained in the **dbo** schema.</span></span> <span data-ttu-id="e7f97-134">Per specificare uno schema diverso per la tabella, fare clic con il pulsante destro del mouse nel riquadro Progettazione tabelle e selezionare **Proprietà** come mostrato nell'illustrazione riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="e7f97-134">To specify a different schema for the table, right-click in the Table Designer pane and select **Properties** as shown in the following illustration.</span></span> <span data-ttu-id="e7f97-135">Nell'elenco a discesa **Schema** selezionare lo schema appropriato.</span><span class="sxs-lookup"><span data-stu-id="e7f97-135">From the **Schema** drop-down list, select the appropriate schema.</span></span>

     <span data-ttu-id="e7f97-136">![Specifyatableschema](../../database-engine/media/specifyatableschema.gif "Specifyatableschema")</span><span class="sxs-lookup"><span data-stu-id="e7f97-136">![Specifyatableschema](../../database-engine/media/specifyatableschema.gif "Specifyatableschema")</span></span>

     <span data-ttu-id="e7f97-137">Per ulteriori informazioni sugli schemi, vedere [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span><span class="sxs-lookup"><span data-stu-id="e7f97-137">For more information about schemas, see [Create a Database Schema](../security/authentication-access/create-a-database-schema.md).</span></span>

9. <span data-ttu-id="e7f97-138">Scegliere **Salva** *nometabella* dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="e7f97-138">From the **File** menu, choose **Save** *table name*.</span></span>

10. <span data-ttu-id="e7f97-139">Nella finestra di dialogo **Scegli nome** digitare un nome per la tabella, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7f97-139">In the **Choose Name** dialog box, type a name for the table and click **OK**.</span></span>

11. <span data-ttu-id="e7f97-140">Per visualizzare la nuova tabella, in **Esplora oggetti**espandere il nodo **Tabelle** e premere **F5** per aggiornare l'elenco di oggetti.</span><span class="sxs-lookup"><span data-stu-id="e7f97-140">To view the new table, in **Object Explorer**, expand the **Tables** node and press **F5** to refresh the list of objects.</span></span> <span data-ttu-id="e7f97-141">La nuova tabella viene visualizzata nell'elenco di tabelle.</span><span class="sxs-lookup"><span data-stu-id="e7f97-141">The new table is displayed in the list of tables.</span></span>

##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e7f97-142">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e7f97-142">Using Transact-SQL</span></span>

#### <a name="to-create-a-table-in-the-query-editor"></a><span data-ttu-id="e7f97-143">Per creare una tabella nell'editor di query</span><span class="sxs-lookup"><span data-stu-id="e7f97-143">To create a table in the Query Editor</span></span>

1.  <span data-ttu-id="e7f97-144">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7f97-144">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>

2.  <span data-ttu-id="e7f97-145">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="e7f97-145">On the Standard bar, click **New Query**.</span></span>

3.  <span data-ttu-id="e7f97-146">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e7f97-146">Copy and paste the following example into the query window and click **Execute**.</span></span>

    ```
    CREATE TABLE dbo.PurchaseOrderDetail
    (
        PurchaseOrderID int NOT NULL
        ,LineNumber smallint NOT NULL
        ,ProductID int NULL
        ,UnitPrice money NULL
        ,OrderQty smallint NULL
        ,ReceivedQty float NULL
        ,RejectedQty float NULL
        ,DueDate datetime NULL
    );
    ```

 <span data-ttu-id="e7f97-147">Per altri esempi, vedere [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e7f97-147">For more examples, see [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span>


