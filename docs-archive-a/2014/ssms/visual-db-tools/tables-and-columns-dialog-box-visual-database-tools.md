---
title: Finestra di dialogo Tabelle e colonne (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.tablesandcolumns
ms.assetid: 8cf27be1-e66d-4735-a428-9ab4b33af4f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28e0c52b74413a3a5a4122412c6028b34e974b09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636507"
---
# <a name="tables-and-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="d78b1-102">Finestra di dialogo Tabelle e colonne (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="d78b1-102">Tables and Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="d78b1-103">Questa finestra di dialogo consente di eseguire il mapping di una chiave primaria in una tabella a una chiave esterna in un'altra tabella.</span><span class="sxs-lookup"><span data-stu-id="d78b1-103">Use this dialog box to map a primary key in one table to a foreign key in another.</span></span> <span data-ttu-id="d78b1-104">Per accedere a tale finestra di dialogo, scegliere **Relazioni** dal menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="d78b1-104">To access this dialog box, from the **Table Designer** menu, click **Relationships**.</span></span> <span data-ttu-id="d78b1-105">Nella finestra di dialogo **Relazioni chiavi esterne** fare clic sul campo **Specifica tabelle e colonne** e quindi sui puntini di sospensione **(...)** a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d78b1-105">In the **Foreign Key Relationships** dialog box, click the **Tables and Columns Specification** field, and then click the ellipses **(...)** to the right of the property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d78b1-106">Se la tabella viene pubblicata per la replica, è necessario apportare modifiche allo schema usando l'istruzione [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) di Transact-SQL oppure SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="d78b1-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="d78b1-107">Quando si apportano modifiche allo schema utilizzando Progettazione tabelle o Progettazione diagrammi di database, viene effettuato il tentativo di rimuovere e rigenerare la tabella.</span><span class="sxs-lookup"><span data-stu-id="d78b1-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="d78b1-108">La modifica allo schema non riuscirà, poiché non è consentita la rimozione di oggetti pubblicati.</span><span class="sxs-lookup"><span data-stu-id="d78b1-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d78b1-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d78b1-109">Options</span></span>  
 <span data-ttu-id="d78b1-110">**Nome relazione**</span><span class="sxs-lookup"><span data-stu-id="d78b1-110">**Relationship name**</span></span>  
 <span data-ttu-id="d78b1-111">Visualizza il nome della relazione.</span><span class="sxs-lookup"><span data-stu-id="d78b1-111">Shows the name of the relationship.</span></span>  
  
 <span data-ttu-id="d78b1-112">**Tabella chiave primaria**</span><span class="sxs-lookup"><span data-stu-id="d78b1-112">**Primary Key Table**</span></span>  
 <span data-ttu-id="d78b1-113">Elenca le tabelle del database.</span><span class="sxs-lookup"><span data-stu-id="d78b1-113">Lists the tables in the database.</span></span> <span data-ttu-id="d78b1-114">Scegliere la tabella che si troverà sul lato chiave primaria della relazione.</span><span class="sxs-lookup"><span data-stu-id="d78b1-114">Choose the table that will be on the primary-key side of the relationship.</span></span>  
  
 <span data-ttu-id="d78b1-115">**Tabella chiave esterna**</span><span class="sxs-lookup"><span data-stu-id="d78b1-115">**Foreign Key Table**</span></span>  
 <span data-ttu-id="d78b1-116">Visualizza la tabella sul lato chiave esterna della relazione.</span><span class="sxs-lookup"><span data-stu-id="d78b1-116">Shows the table on the foreign key side of the relationship.</span></span> <span data-ttu-id="d78b1-117">Corrisponde alla tabella attualmente selezionata in Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="d78b1-117">This is the table currently selected in Table Designer.</span></span>  
  
 <span data-ttu-id="d78b1-118">**Griglia al di sotto della tabella di chiave primaria**</span><span class="sxs-lookup"><span data-stu-id="d78b1-118">**Grid beneath Primary Key Table**</span></span>  
 <span data-ttu-id="d78b1-119">Elenca le colonne della tabella selezionata nell'elenco **Tabella chiave primaria** .</span><span class="sxs-lookup"><span data-stu-id="d78b1-119">List the columns of the table selected in the **Primary Key Table** list.</span></span> <span data-ttu-id="d78b1-120">Immettere le colonne che contribuiscono alla chiave primaria della tabella.</span><span class="sxs-lookup"><span data-stu-id="d78b1-120">Enter the columns contributing to that table's primary key.</span></span>  
  
 <span data-ttu-id="d78b1-121">**Griglia al di sotto della tabella di chiave esterna**</span><span class="sxs-lookup"><span data-stu-id="d78b1-121">**Grid beneath Foreign Key Table**</span></span>  
 <span data-ttu-id="d78b1-122">Elenca le colonne della tabella selezionata nell'elenco **Tabella chiave esterna** .</span><span class="sxs-lookup"><span data-stu-id="d78b1-122">List the columns of the table selected in the **Foreign Key Table** list.</span></span> <span data-ttu-id="d78b1-123">Immettere la colonna chiave esterna della tabella di chiave esterna che corrisponde alla colonna chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="d78b1-123">Enter the foreign-key column of the foreign-key table that corresponds to the primary key column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d78b1-124">Le colonne selezionate per la chiave esterna devono avere lo stesso tipo di dati delle colonne primarie a cui corrispondono.</span><span class="sxs-lookup"><span data-stu-id="d78b1-124">The columns you choose for the foreign key must have the same data type of the primary columns they correspond to.</span></span> <span data-ttu-id="d78b1-125">In ogni chiave deve esistere un numero uguale di colonne.</span><span class="sxs-lookup"><span data-stu-id="d78b1-125">There must be an equal number of columns in each of the keys.</span></span> <span data-ttu-id="d78b1-126">Se ad esempio la chiave primaria della tabella sul lato primario della relazione è composta da due colonne, ognuna di queste colonne dovrà corrispondere a una colonna della tabella sul lato chiave esterna della relazione.</span><span class="sxs-lookup"><span data-stu-id="d78b1-126">For example, if the primary key of the table on the primary side of the relationship is made up of two columns, you will need to match each of those columns with a column in the table for the foreign key side of the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d78b1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d78b1-127">See Also</span></span>  
 [<span data-ttu-id="d78b1-128">Creare relazioni di chiave esterna</span><span class="sxs-lookup"><span data-stu-id="d78b1-128">Create Foreign Key Relationships</span></span>](../../relational-databases/tables/create-foreign-key-relationships.md)  
  
  
