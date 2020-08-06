---
title: 'Scenario: Aggiunta e modifica di un diagramma di database | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- database diagrams [SQL Server], about database diagrams
- database diagrams [SQL Server], designing
- database diagrams [SQL Server], creating
ms.assetid: 228caa0d-8f24-46ab-86d1-b6d8631322bc
author: stevestein
ms.author: sstein
ms.openlocfilehash: c35eb3674c817e98a25a74cd0309fc7376fe2f58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624502"
---
# <a name="walkthrough-adding-and-changing-a-database-diagram"></a><span data-ttu-id="82115-102">Scenario: Aggiunta e modifica di un diagramma di database</span><span class="sxs-lookup"><span data-stu-id="82115-102">Walkthrough: Adding and Changing a Database Diagram</span></span>
  <span data-ttu-id="82115-103">In questo scenario viene illustrato come creare e modificare un diagramma di database e apportare modifiche al database tramite il componente per i diagrammi di database.</span><span class="sxs-lookup"><span data-stu-id="82115-103">This walkthrough illustrates how to create and modify a database diagram and make changes to the database through the database diagrams component.</span></span> <span data-ttu-id="82115-104">Verrà descritto come aggiungere tabelle ai diagrammi, creare relazioni tra le tabelle, creare vincoli e indici su colonne e modificare il livello delle informazioni visualizzate per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="82115-104">You will see how to add tables to diagrams, create relationships between tables, create constraints and indexes on columns, and change the level of information you see for each table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="82115-105">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="82115-105">Prerequisites</span></span>  
 <span data-ttu-id="82115-106">Per completare questo scenario, saranno necessari gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="82115-106">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="82115-107">Accedere a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82115-107">Access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database</span></span>  
  
-   <span data-ttu-id="82115-108">Un account con privilegi `dbo` di proprietario del database.</span><span class="sxs-lookup"><span data-stu-id="82115-108">An account with database owner `dbo` privileges</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82115-109">Se si tenta di apportare modifiche quando si utilizza un account senza privilegi sufficienti ad apportare modifiche alle tabelle, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="82115-109">If you attempt to make changes when using an account without sufficient privileges to make changes to tables, then an error message appears.</span></span>  
  
## <a name="creating-a-diagram"></a><span data-ttu-id="82115-110">Creazione di un diagramma</span><span class="sxs-lookup"><span data-stu-id="82115-110">Creating a Diagram</span></span>  
  
#### <a name="to-create-a-new-database-diagram"></a><span data-ttu-id="82115-111">Per creare un nuovo diagramma di database</span><span class="sxs-lookup"><span data-stu-id="82115-111">To create a new database diagram</span></span>  
  
1.  <span data-ttu-id="82115-112">Dal menu **Visualizza** fare clic su **Esplora oggetti**.</span><span class="sxs-lookup"><span data-stu-id="82115-112">On the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="82115-113">Aprire il nodo Database e quindi il nodo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82115-113">Open the Databases node and then open the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] node.</span></span>  
  
3.  <span data-ttu-id="82115-114">Fare clic con il pulsante destro del mouse sul nodo Diagrammi database e scegliere **Nuovo diagramma database**.</span><span class="sxs-lookup"><span data-stu-id="82115-114">Right-click the Database Diagrams node and choose **New Database Diagram**.</span></span>  
  
     <span data-ttu-id="82115-115">Se il database non include gli oggetti necessari alla creazione dei diagrammi, verrà visualizzato il messaggio seguente: **Per il database non sono disponibili uno o più oggetti di supporto necessari per l'utilizzo dei diagrammi. Creare tali oggetti?**</span><span class="sxs-lookup"><span data-stu-id="82115-115">If the database does not have objects necessary to create diagrams, the following message appears: **This database does not have one or more of the support objects required to use database diagramming. Do you wish to create them?**</span></span> <span data-ttu-id="82115-116">Scegliere **Sì**.</span><span class="sxs-lookup"><span data-stu-id="82115-116">Choose **Yes**.</span></span>  
  
     <span data-ttu-id="82115-117">Verrà visualizzata la finestra di dialogo **Aggiungi tabella** .</span><span class="sxs-lookup"><span data-stu-id="82115-117">The **Add Table** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="82115-118">Selezionare **AddressType (Person)** (Tipo indirizzo (Persona) e **Address (Person)** (Indirizzo (Persona) e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="82115-118">Select **AddressType (Person)** and **Address (Person)** and click **Add**.</span></span>  
  
     <span data-ttu-id="82115-119">Al diagramma verranno aggiunte due tabelle.</span><span class="sxs-lookup"><span data-stu-id="82115-119">Two tables are added to the diagram.</span></span>  
  
5.  <span data-ttu-id="82115-120">Chiudere la finestra di dialogo **Aggiungi tabella** .</span><span class="sxs-lookup"><span data-stu-id="82115-120">Close the **Add Table** dialog box.</span></span>  
  
#### <a name="to-view-different-column-data"></a><span data-ttu-id="82115-121">Per visualizzare dati di colonne diverse</span><span class="sxs-lookup"><span data-stu-id="82115-121">To view different column data</span></span>  
  
1.  <span data-ttu-id="82115-122">Fare clic con il pulsante destro del mouse sulla tabella `Address` .</span><span class="sxs-lookup"><span data-stu-id="82115-122">Right-click the `Address` table.</span></span> <span data-ttu-id="82115-123">Nel menu di scelta rapida scegliere **Vista tabella**e fare clic su **Standard**.</span><span class="sxs-lookup"><span data-stu-id="82115-123">On the shortcut menu, point to **Table View**, and then click **Standard**.</span></span>  
  
     <span data-ttu-id="82115-124">Nella griglia della tabella sono visualizzate tre colonne: **Nome colonna**, **Tipo di dati**e **Consenti valori Null**.</span><span class="sxs-lookup"><span data-stu-id="82115-124">The table grid shows three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
2.  <span data-ttu-id="82115-125">Fare clic con il pulsante destro del mouse sulla tabella `Address` , fare clic su **Vista tabella** e scegliere **Chiavi**.</span><span class="sxs-lookup"><span data-stu-id="82115-125">Right-click the `Address` table, click **Table View** and select **Keys**.</span></span>  
  
     <span data-ttu-id="82115-126">Nella griglia della tabella è visualizzata una colonna, con i nomi delle colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="82115-126">The table grid shows one column, with the table-column names.</span></span> <span data-ttu-id="82115-127">Sono visualizzate solo le colonne incluse negli indici.</span><span class="sxs-lookup"><span data-stu-id="82115-127">Only those columns participating in indexes appear.</span></span>  
  
## <a name="creating-new-tables"></a><span data-ttu-id="82115-128">Creazione di nuove tabelle</span><span class="sxs-lookup"><span data-stu-id="82115-128">Creating New Tables</span></span>  
  
#### <a name="to-create-tables-within-diagram-designer"></a><span data-ttu-id="82115-129">Per creare tabelle all'interno di Progettazione diagrammi</span><span class="sxs-lookup"><span data-stu-id="82115-129">To create tables within Diagram Designer</span></span>  
  
1.  <span data-ttu-id="82115-130">Fare clic con il pulsante destro del mouse su Progettazione diagrammi all'esterno delle tabelle esistenti e scegliere **Nuova tabella**.</span><span class="sxs-lookup"><span data-stu-id="82115-130">Right-click the Diagram Designer outside the existing tables and choose **New Table**.</span></span>  
  
2.  <span data-ttu-id="82115-131">Nella finestra di dialogo **Scegli nome** fare clic su **OK** per accettare il nome predefinito `Table1` .</span><span class="sxs-lookup"><span data-stu-id="82115-131">In the **Choose Name** dialog box, click **OK** to accept the default name `Table1`.</span></span>  
  
     <span data-ttu-id="82115-132">Verrà visualizzata una nuova griglia della tabella con tre colonne: **Nome colonna**, **Tipo di dati**e **Consenti valori Null**.</span><span class="sxs-lookup"><span data-stu-id="82115-132">A new table grid appears with three columns: **Column Name**, **Data Type**, and **Allow Nulls**.</span></span>  
  
3.  <span data-ttu-id="82115-133">Aggiungere le informazioni seguenti a `Table1` :</span><span class="sxs-lookup"><span data-stu-id="82115-133">Add the following information to `Table1`:</span></span>  
  
    |<span data-ttu-id="82115-134">**Nome colonna**</span><span class="sxs-lookup"><span data-stu-id="82115-134">**Column Name**</span></span>|<span data-ttu-id="82115-135">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="82115-135">**Data Type**</span></span>|<span data-ttu-id="82115-136">**Consenti valori NULL**</span><span class="sxs-lookup"><span data-stu-id="82115-136">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T1col1`|`int`|<span data-ttu-id="82115-137">checked</span><span class="sxs-lookup"><span data-stu-id="82115-137">checked</span></span>|  
    |`T1col2`|`varchar(50)`|<span data-ttu-id="82115-138">checked</span><span class="sxs-lookup"><span data-stu-id="82115-138">checked</span></span>|  
    |`T1col3`|`float`|<span data-ttu-id="82115-139">selezionata</span><span class="sxs-lookup"><span data-stu-id="82115-139">checked</span></span>|  
  
4.  <span data-ttu-id="82115-140">Fare clic con il pulsante destro del mouse su `T1col1` e selezionare **Imposta chiave primaria**.</span><span class="sxs-lookup"><span data-stu-id="82115-140">Right-click `T1col1` and select **Set Primary Key**.</span></span>  
  
     <span data-ttu-id="82115-141">Accanto al nome della colonna verrà visualizzata un'icona a forma di chiave.</span><span class="sxs-lookup"><span data-stu-id="82115-141">A key icon will appear beside the column name.</span></span>  
  
5.  <span data-ttu-id="82115-142">Scegliere **Salva Diagram1** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="82115-142">From the **File** menu, click **Save Diagram1**.</span></span>  
  
6.  <span data-ttu-id="82115-143">Nella finestra di dialogo **Scegli nome** fare clic su **OK** per accettare il nome predefinito `Diagram1` .</span><span class="sxs-lookup"><span data-stu-id="82115-143">In the **Choose Name** dialog box, click **OK** to accept the default name `Diagram1`.</span></span>  
  
7.  <span data-ttu-id="82115-144">Verrà visualizzata la finestra di dialogo **Salva** con un messaggio che indica che `Table1` verrà salvata nel database.</span><span class="sxs-lookup"><span data-stu-id="82115-144">The **Save** dialog box appears with a message that `Table1` will be saved to the database.</span></span> <span data-ttu-id="82115-145">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="82115-145">Click **Yes**.</span></span>  
  
## <a name="modifying-table-structure"></a><span data-ttu-id="82115-146">Modifica della struttura della tabella</span><span class="sxs-lookup"><span data-stu-id="82115-146">Modifying Table Structure</span></span>  
 <span data-ttu-id="82115-147">È possibile aggiungere vincoli CHECK e creare relazioni tra le tabelle in Progettazione diagrammi.</span><span class="sxs-lookup"><span data-stu-id="82115-147">You can add check constraints and make relationships between tables in Diagram Designer.</span></span>  
  
#### <a name="to-create-check-constraints"></a><span data-ttu-id="82115-148">Per creare vincoli CHECK</span><span class="sxs-lookup"><span data-stu-id="82115-148">To create check constraints</span></span>  
  
1.  <span data-ttu-id="82115-149">In `Table1`fare clic con il pulsante destro del mouse sulla riga `T1col3` e scegliere **Vincoli CHECK**.</span><span class="sxs-lookup"><span data-stu-id="82115-149">In `Table1`, right-click the `T1col3` row and choose **Check Constraints**.</span></span>  
  
     <span data-ttu-id="82115-150">Verrà visualizzata la finestra di dialogo **Vincoli CHECK** .</span><span class="sxs-lookup"><span data-stu-id="82115-150">The **Check Constraints** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="82115-151">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="82115-151">Click **Add**.</span></span>  
  
     <span data-ttu-id="82115-152">Verrà visualizzato un nuovo vincolo nell'elenco **Selected Check Constraint** (Vincolo CHECK selezionato), con il nome predefinito `CK_Table1`.</span><span class="sxs-lookup"><span data-stu-id="82115-152">A new constraint appears in the **Selected Check Constraint** list, with the default name `CK_Table1`.</span></span>  
  
3.  <span data-ttu-id="82115-153">Selezionare la riga **Espressione** nella griglia e fare clic sul pulsante con i puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="82115-153">Select the **Expression** row in the grid and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="82115-154">Verrà visualizzata la finestra di dialogo **Espressione vincolo CHECK**.</span><span class="sxs-lookup"><span data-stu-id="82115-154">The **Check Constraint Expression** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="82115-155">Digitare `T1col3 > 5` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="82115-155">Type `T1col3 > 5` and click **OK**.</span></span>  
  
     <span data-ttu-id="82115-156">`Table1` include ora un vincolo in base al quale tutti i valori immessi in `T1col3` devono essere maggiori di 5.</span><span class="sxs-lookup"><span data-stu-id="82115-156">`Table1` now has a constraint that all values entered into `T1col3` must be greater than 5.</span></span>  
  
5.  <span data-ttu-id="82115-157">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="82115-157">Click **Close**.</span></span>  
  
#### <a name="to-create-relationships-between-tables"></a><span data-ttu-id="82115-158">Per creare relazioni tra le tabelle</span><span class="sxs-lookup"><span data-stu-id="82115-158">To create relationships between tables</span></span>  
  
1.  <span data-ttu-id="82115-159">Creare una nuova tabella in Progettazione diagrammi denominata `Table2` con le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="82115-159">Create a new table in Diagram designer named `Table2` with the following columns:</span></span>  
  
    |<span data-ttu-id="82115-160">**Nome colonna**</span><span class="sxs-lookup"><span data-stu-id="82115-160">**Column Name**</span></span>|<span data-ttu-id="82115-161">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="82115-161">**Data Type**</span></span>|<span data-ttu-id="82115-162">**Consenti valori NULL**</span><span class="sxs-lookup"><span data-stu-id="82115-162">**Allow Nulls**</span></span>|  
    |---------------------|-------------------|---------------------|  
    |`T2col1`|`int`|<span data-ttu-id="82115-163">non selezionata</span><span class="sxs-lookup"><span data-stu-id="82115-163">not checked</span></span>|  
    |`T2col2`|`varchar(50)`|<span data-ttu-id="82115-164">checked</span><span class="sxs-lookup"><span data-stu-id="82115-164">checked</span></span>|  
    |`T2col3`|`xml`|<span data-ttu-id="82115-165">checked</span><span class="sxs-lookup"><span data-stu-id="82115-165">checked</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="82115-166">Le colonne della chiave primaria di una relazione di chiave esterna devono far parte di un vincolo UNIQUE o PRIMARY KEY.</span><span class="sxs-lookup"><span data-stu-id="82115-166">The columns on the primary key side of a foreign key relationship must participate in either a Primary Key or a Unique Constraint.</span></span>  
  
2.  <span data-ttu-id="82115-167">Trascinare `T2col1` in `T1col1`.</span><span class="sxs-lookup"><span data-stu-id="82115-167">Drag `T2col1` to `T1col1`.</span></span>  
  
     <span data-ttu-id="82115-168">Verranno visualizzate due finestre di dialogo: **Relazione chiavi esterne** sullo sfondo e **Tabelle e colonne** in primo piano.</span><span class="sxs-lookup"><span data-stu-id="82115-168">Two dialog boxes appear: **Foreign Key Relationship** in the background and **Tables and Columns** in the foreground.</span></span>  
  
3.  <span data-ttu-id="82115-169">Fare clic su **OK** per salvare la nuova relazione.</span><span class="sxs-lookup"><span data-stu-id="82115-169">Click **OK** to save the new relationship.</span></span>  
  
4.  <span data-ttu-id="82115-170">Fare di nuovo clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="82115-170">Click **OK** again.</span></span>  
  
## <a name="creating-indexes"></a><span data-ttu-id="82115-171">Creazione di indici</span><span class="sxs-lookup"><span data-stu-id="82115-171">Creating Indexes</span></span>  
 <span data-ttu-id="82115-172">È possibile creare indici per la maggioranza dei tipi di dati, inclusi i dati XML.</span><span class="sxs-lookup"><span data-stu-id="82115-172">You can create indexes on most types of data, including XML.</span></span>  
  
#### <a name="to-create-a-standard-index"></a><span data-ttu-id="82115-173">Per creare un indice standard</span><span class="sxs-lookup"><span data-stu-id="82115-173">To create a standard index</span></span>  
  
1.  <span data-ttu-id="82115-174">Fare clic con il pulsante destro del mouse su `Table1` e scegliere **Indici/chiavi**.</span><span class="sxs-lookup"><span data-stu-id="82115-174">Right-click `Table1` and choose **Indexes/Keys**.</span></span>  
  
     <span data-ttu-id="82115-175">Verrà visualizzata la finestra di dialogo **Indici/chiavi** .</span><span class="sxs-lookup"><span data-stu-id="82115-175">The **Indexes/Keys** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="82115-176">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="82115-176">Click **Add**.</span></span>  
  
     <span data-ttu-id="82115-177">Verrà visualizzato un nuovo indice nell'elenco **Chiave o indice primario/univoco selezionato** , con un nome predefinito simile a `IX_Table1`.</span><span class="sxs-lookup"><span data-stu-id="82115-177">A new index appears in the **Selected Primary/Unique Key or Index** list, with a default name similar to `IX_Table1`.</span></span>  
  
3.  <span data-ttu-id="82115-178">Selezionare la riga **Colonne** e fare clic sul pulsante con i puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="82115-178">Select the **Columns** row and click the ellipsis button.</span></span>  
  
     <span data-ttu-id="82115-179">Verrà visualizzata la finestra di dialogo **Colonne indice** .</span><span class="sxs-lookup"><span data-stu-id="82115-179">The **Index Columns** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="82115-180">Fare clic sulla freccia a discesa in **Nome colonna** e selezionare `T1col2`.</span><span class="sxs-lookup"><span data-stu-id="82115-180">Click the drop-down arrow under **Column Name** and select `T1col2`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="82115-181">È possibile aggiungere colonne aggiuntive all'indice selezionando la cella sotto `T1col2` e scegliendo un altro nome di colonna.</span><span class="sxs-lookup"><span data-stu-id="82115-181">You may add additional columns to this index by selecting the cell below `T1col2` and choosing another column name.</span></span>  
  
5.  <span data-ttu-id="82115-182">Fare clic su **OK** per salvare l'indice.</span><span class="sxs-lookup"><span data-stu-id="82115-182">Click **OK** to save this index.</span></span>  
  
6.  <span data-ttu-id="82115-183">Fare clic su **Chiudi** nella finestra di dialogo **Indici/chiavi** .</span><span class="sxs-lookup"><span data-stu-id="82115-183">Click **Close** in the **Indexes/Keys** dialog box.</span></span>  
  
#### <a name="to-create-an-xml-index"></a><span data-ttu-id="82115-184">Per creare un indice XML</span><span class="sxs-lookup"><span data-stu-id="82115-184">To create an XML index</span></span>  
  
1.  <span data-ttu-id="82115-185">Fare clic con il pulsante destro del mouse su `T2col1` e selezionare **Imposta chiave primaria**.</span><span class="sxs-lookup"><span data-stu-id="82115-185">Right-click `T2col1` and choose **Set Primary Key**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="82115-186">Per l'aggiunta di un indice XML è necessario che un'altra colonna nella tabella sia impostata come chiave primaria cluster.</span><span class="sxs-lookup"><span data-stu-id="82115-186">Adding an XML index requires that another column in the table be set as a clustered primary key.</span></span>  
  
2.  <span data-ttu-id="82115-187">Fare clic con il pulsante destro del mouse sulla riga `T2col3` in `Table2` e scegliere **Indici XML**.</span><span class="sxs-lookup"><span data-stu-id="82115-187">Right-click the `T2col3` row in `Table2` and select **XML Indexes**.</span></span>  
  
     <span data-ttu-id="82115-188">Verrà visualizzata la finestra di dialogo **Indici XML** .</span><span class="sxs-lookup"><span data-stu-id="82115-188">The **XML Indexes** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="82115-189">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="82115-189">Click **Add**.</span></span>  
  
     <span data-ttu-id="82115-190">Un indice XML con valori predefiniti verrà aggiunto all'elenco **Selected XML Index** (Indice XML selezionato).</span><span class="sxs-lookup"><span data-stu-id="82115-190">An XML index with default values will be added to the **Selected XML Index** list.</span></span>  
  
4.  <span data-ttu-id="82115-191">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="82115-191">Click **Close**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="82115-192">Gli indici XML vengono creati per colonna.</span><span class="sxs-lookup"><span data-stu-id="82115-192">XML indexes are created per-column.</span></span> <span data-ttu-id="82115-193">Il primo indice XML è primario, eventuali indici aggiuntivi sono secondari.</span><span class="sxs-lookup"><span data-stu-id="82115-193">The first XML index is primary; any additional indexes are secondary.</span></span>  
  
## <a name="saving-the-diagram"></a><span data-ttu-id="82115-194">Salvataggio del diagramma</span><span class="sxs-lookup"><span data-stu-id="82115-194">Saving the Diagram</span></span>  
 <span data-ttu-id="82115-195">Tutte le modifiche apportate a un diagramma non vengono inviate al database fino al salvataggio.</span><span class="sxs-lookup"><span data-stu-id="82115-195">All of the changes you make to a diagram are not posted to the database until you save it.</span></span> <span data-ttu-id="82115-196">Nel caso in cui siano presenti problemi o conflitti, verrà visualizzata una finestra di dialogo con ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="82115-196">If there are problems or conflicts, a dialog box appears with more information.</span></span>  
  
#### <a name="to-save-a-database-diagram"></a><span data-ttu-id="82115-197">Per salvare un diagramma di database</span><span class="sxs-lookup"><span data-stu-id="82115-197">To save a database diagram</span></span>  
  
1.  <span data-ttu-id="82115-198">Dal menu **File** selezionare **Salva Diagram1**.</span><span class="sxs-lookup"><span data-stu-id="82115-198">On the **File** menu, select **Save Diagram1**.</span></span>  
  
     <span data-ttu-id="82115-199">Verrà visualizzata la finestra di dialogo **Salva** .</span><span class="sxs-lookup"><span data-stu-id="82115-199">The **Save** dialog box appears.</span></span> <span data-ttu-id="82115-200">Se l'opzione **Avvisa in caso le tabelle siano modificate** è selezionata, vengono indicate informazioni sulle tabelle nuove o modificate.</span><span class="sxs-lookup"><span data-stu-id="82115-200">If **Warn about Tables Affected** is selected, information about new or changed tables is listed.</span></span>  
  
2.  <span data-ttu-id="82115-201">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="82115-201">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="82115-202">Se si sono verificati errori, verrà visualizzata la finestra di dialogo **Notifiche postsalvataggio** con gli errori e le relative cause.</span><span class="sxs-lookup"><span data-stu-id="82115-202">If any errors occurred, the **Post-Save Notifications** dialog box appears with the errors and their causes.</span></span> <span data-ttu-id="82115-203">Correggere gli errori e salvare nuovamente il diagramma.</span><span class="sxs-lookup"><span data-stu-id="82115-203">Fix the errors and save the diagram again.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="82115-204">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="82115-204">Next Steps</span></span>  
 <span data-ttu-id="82115-205">Si tratta di un diagramma di base con due tabelle esistenti e due tabelle nuove, che illustra comunque le potenzialità della creazione di diagrammi per un database esistente o di creazione di un nuovo schema in modo visivo.</span><span class="sxs-lookup"><span data-stu-id="82115-205">This is a basic diagram with just two existing and two new tables, but it illustrates the potential for diagramming an existing database or creating a new schema visually.</span></span> <span data-ttu-id="82115-206">Alcuni suggerimenti per un'analisi più ampia dell'argomento includono:</span><span class="sxs-lookup"><span data-stu-id="82115-206">Suggestions for more exploration include:</span></span>  
  
-   <span data-ttu-id="82115-207">Creazione di nuovi diagrammi che contengono gruppi di tabelle correlate</span><span class="sxs-lookup"><span data-stu-id="82115-207">Create new diagrams containing groups of related tables</span></span>  
  
-   <span data-ttu-id="82115-208">Personalizzazione della quantità di informazioni visualizzate per ogni tabella</span><span class="sxs-lookup"><span data-stu-id="82115-208">Customize the amount of information shown for each table</span></span>  
  
-   <span data-ttu-id="82115-209">Modifica del layout e aggiunta di annotazioni</span><span class="sxs-lookup"><span data-stu-id="82115-209">Change the layout and add annotations</span></span>  
  
-   <span data-ttu-id="82115-210">Copia del diagramma in una bitmap</span><span class="sxs-lookup"><span data-stu-id="82115-210">Copy the diagram to a bitmap</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82115-211">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82115-211">See Also</span></span>  
 <span data-ttu-id="82115-212">[Personalizzare la quantità di informazioni visualizzate nei diagrammi &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="82115-212">[Customize the Amount of Information Displayed in Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="82115-213">[Configurare Progettazione diagrammi di database &#40;Visual Database Tools&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="82115-213">[Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](set-up-database-diagram-designer-visual-database-tools.md) </span></span>  
 <span data-ttu-id="82115-214">[Aggiunta di tabelle a diagrammi &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="82115-214">[Add Tables to Diagrams &#40;Visual Database Tools&#41;](add-tables-to-diagrams-visual-database-tools.md) </span></span>  
 <span data-ttu-id="82115-215">[Creazione di relazioni tra tabelle in un diagramma &#40;Visual Database Tools&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="82115-215">[Create Relationships Between Tables on a Diagram &#40;Visual Database Tools&#41;](create-relationships-between-tables-on-a-diagram-visual-database-tools.md) </span></span>  
 <span data-ttu-id="82115-216">[Creazione di indici XML](../../relational-databases/xml/create-xml-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="82115-216">[Create XML Indexes](../../relational-databases/xml/create-xml-indexes.md) </span></span>  
 <span data-ttu-id="82115-217">[Copiare un'immagine di un diagramma di database negli Appunti &#40;Visual Database Tools&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="82115-217">[Copy an Image of a Database Diagram to the Clipboard &#40;Visual Database Tools&#41;](copy-an-image-of-a-database-diagram-to-the-clipboard-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="82115-218">Utilizzare il layout di un diagramma &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="82115-218">Work with Diagram Layout &#40;Visual Database Tools&#41;</span></span>](work-with-diagram-layout-visual-database-tools.md)  
  
  
