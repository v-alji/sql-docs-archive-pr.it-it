---
title: Aggiungere colonne a una tabella (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- adding columns
ms.assetid: abeb8d52-d562-4e29-9e1e-2923ae874859
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7e9294de10be0df9ef470c75d0934e9f8787b55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628586"
---
# <a name="add-columns-to-a-table-database-engine"></a><span data-ttu-id="c5738-102">Aggiungere colonne a una tabella (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="c5738-102">Add Columns to a Table (Database Engine)</span></span>
  <span data-ttu-id="c5738-103">In questo argomento viene descritto come aggiungere nuove colonne a una tabella in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5738-103">This topic describes how to add new columns to a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c5738-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c5738-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c5738-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c5738-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c5738-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c5738-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c5738-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c5738-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c5738-108">**Per inserire le colonne:**</span><span class="sxs-lookup"><span data-stu-id="c5738-108">**To insert columns, using:**</span></span>  
  
     [<span data-ttu-id="c5738-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c5738-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c5738-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c5738-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c5738-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c5738-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c5738-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c5738-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="c5738-113">L'utilizzo dell'istruzione ALTER TABLE per aggiungere automaticamente colonne a una tabella aggiunge tali colonne alla fine della tabella.</span><span class="sxs-lookup"><span data-stu-id="c5738-113">Using the ALTER TABLE statement to add columns to a table automatically adds those columns to the end of the table.</span></span> <span data-ttu-id="c5738-114">Se si desidera le colonne in un ordine specifico all'interno della tabella, utilizzare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5738-114">If you want the columns in a specific order in the table, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="c5738-115">Tuttavia, notare che questa non è una procedura consigliata di progettazione del database.</span><span class="sxs-lookup"><span data-stu-id="c5738-115">However, note that this is not a database design best practice.</span></span> <span data-ttu-id="c5738-116">La procedura consigliata è specificare l'ordine nel quale le colonne vengono restituite all'applicazione e il livello della query.</span><span class="sxs-lookup"><span data-stu-id="c5738-116">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="c5738-117">Non è necessario basarsi sull'utilizzo di SELECT \* per restituire tutte le colonne nell'ordine previsto basato sull'ordine nel quale sono definiti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="c5738-117">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="c5738-118">Nelle query e nelle applicazioni, specificare sempre le colonne per nome nell'ordine nel quale si desidera visualizzarle.</span><span class="sxs-lookup"><span data-stu-id="c5738-118">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c5738-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c5738-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c5738-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c5738-120">Permissions</span></span>  
 <span data-ttu-id="c5738-121">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="c5738-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c5738-122">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c5738-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-insert-columns-into-a-table-with-table-designer"></a><span data-ttu-id="c5738-123">Per inserire colonne in una tabella con Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="c5738-123">To insert columns into a table with Table Designer</span></span>  
  
1.  <span data-ttu-id="c5738-124">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulla tabella a cui si vogliono aggiungere colonne e scegliere **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="c5738-124">In **Object Explorer**, right-click the table to which you want to add columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="c5738-125">Fare clic sulla prima cella vuota nella colonna **Nome colonna** .</span><span class="sxs-lookup"><span data-stu-id="c5738-125">Click in the first blank cell in the **Column Name** column.</span></span>  
  
3.  <span data-ttu-id="c5738-126">Immettere il nome della colonna nella cella.</span><span class="sxs-lookup"><span data-stu-id="c5738-126">Type the column name in the cell.</span></span> <span data-ttu-id="c5738-127">Il nome della colonna non può essere omesso.</span><span class="sxs-lookup"><span data-stu-id="c5738-127">The column name is a required value.</span></span>  
  
4.  <span data-ttu-id="c5738-128">Premere TAB per posizionarsi sulla cella **Tipo di dati** e selezionare un tipo di dati dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="c5738-128">Press the TAB key to go to the **Data Type** cell and select a data type from the dropdown.</span></span> <span data-ttu-id="c5738-129">Anche questo è un valore obbligatorio. Se non viene specificato, verrà assegnato un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="c5738-129">This too is a required value, and will be assigned the default value if you don't choose one.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5738-130"> Il valore predefinito può essere modificato nella finestra di dialogo **Opzioni** in **Database Tools**.</span><span class="sxs-lookup"><span data-stu-id="c5738-130">You can change the default value in the **Options** dialog box under **Database Tools**.</span></span>  
  
5.  <span data-ttu-id="c5738-131">Proseguire con la definizione delle altre proprietà della colonna nella scheda **Proprietà colonne** .</span><span class="sxs-lookup"><span data-stu-id="c5738-131">Continue to define any other column properties in the **Column Properties** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c5738-132"> Quando si crea una nuova colonna, le vengono assegnati i valori predefiniti per le diverse proprietà. Tali valori possono comunque essere modificati nella scheda **Proprietà colonne** .</span><span class="sxs-lookup"><span data-stu-id="c5738-132">The default values for your column properties are added when you create a new column, but you can change them in the **Column Properties** tab.</span></span>  
  
6.  <span data-ttu-id="c5738-133">Dopo aver completato l'aggiunta delle colonne, scegliere **Salva**_nome tabella_ dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="c5738-133">When you are finished adding columns, from the **File** menu, choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c5738-134">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c5738-134">Using Transact-SQL</span></span>  
  
#### <a name="to-insert-columns-into-a-table"></a><span data-ttu-id="c5738-135">Per inserire le colonne in una tabella</span><span class="sxs-lookup"><span data-stu-id="c5738-135">To insert columns into a table</span></span>  
  
1.  <span data-ttu-id="c5738-136">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5738-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c5738-137">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c5738-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c5738-138">Negli esempi seguenti vengono aggiunte due colonne alla tabella `dbo.doc_exa`.</span><span class="sxs-lookup"><span data-stu-id="c5738-138">The following example adds two columns to the table `dbo.doc_exa`.</span></span> <span data-ttu-id="c5738-139">Copiare e incollare l'esempio seguente nella finestra Query e quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c5738-139">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
```  
ALTER TABLE dbo.doc_exa ADD column_b VARCHAR(20) NULL, column_c INT NULL ;  
```  
  
##  <a name="for-more-information-see-alter-table-40transact-sql41"></a><a name="FollowUp"></a><span data-ttu-id="c5738-140">Per ulteriori informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="c5738-140">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
