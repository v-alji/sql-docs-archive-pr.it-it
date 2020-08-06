---
title: Eseguire il mapping di relazioni molti-a-molti (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- relationships [SQL Server], many-to-many
- junction tables [SQL Server]
- many-to-many relationships [SQL Server]
- mapping many-to-many relationships [SQL Server]
- database diagrams [SQL Server], relationships
ms.assetid: 2977cf92-98b5-48b2-b0fd-8fbc7040f2b4
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbcbdbdf8d8371baa2a817e43b831535723be7ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637010"
---
# <a name="map-many-to-many-relationships-visual-database-tools"></a><span data-ttu-id="8411a-102">Mapping di relazioni molti-a-molti (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8411a-102">Map Many-to-Many Relationships (Visual Database Tools)</span></span>
  <span data-ttu-id="8411a-103">Le relazioni molti-a-molti consentono di correlare ogni riga di una tabella con molte righe in un'altra tabella e viceversa.</span><span class="sxs-lookup"><span data-stu-id="8411a-103">Many-to-many relationships let you relate each row in one table to many rows in another table, and vice versa.</span></span> <span data-ttu-id="8411a-104">È possibile ad esempio creare una relazione molti-a-molti tra la tabella `authors` e la tabella `titles` per correlare ciascun autore con tutti i relativi libri e ciascun libro a tutti i relativi autori.</span><span class="sxs-lookup"><span data-stu-id="8411a-104">For example, you could create a many-to-many relationship between the `authors` table and the `titles` table to match each author to all of his or her books and to match each book to all of its authors.</span></span> <span data-ttu-id="8411a-105">Creando una relazione uno-a-molti da una delle tue tabelle, invece, si otterrebbe l'erronea indicazione che un libro può essere stato scritto da un solo autore o che ogni autore può scrivere un solo libro.</span><span class="sxs-lookup"><span data-stu-id="8411a-105">Creating a one-to-many relationship from either table would incorrectly indicate that every book can have only one author, or that every author can write only one book.</span></span>  
  
 <span data-ttu-id="8411a-106">Le relazioni molti-a-molti tra le tabelle vengono gestite nei database per mezzo delle tabelle di collegamento (junction table).</span><span class="sxs-lookup"><span data-stu-id="8411a-106">Many-to-many relationships between tables are accommodated in databases by means of junction tables.</span></span> <span data-ttu-id="8411a-107">Una tabella di collegamento contiene le colonne chiave primaria delle due tabelle da correlare.</span><span class="sxs-lookup"><span data-stu-id="8411a-107">A junction table contains the primary key columns of the two tables you want to relate.</span></span> <span data-ttu-id="8411a-108">Successivamente si creerà una relazione dalle colonne chiave primaria di ognuna delle due tabelle alle corrispondenti colonne nella tabella di collegamento.</span><span class="sxs-lookup"><span data-stu-id="8411a-108">You then create a relationship from the primary key columns of each of those two tables to the matching columns in the junction table.</span></span> <span data-ttu-id="8411a-109">Nel database pubs, la tabella `titleauthor` è una tabella di collegamento.</span><span class="sxs-lookup"><span data-stu-id="8411a-109">In the pubs database, the `titleauthor` table is a junction table.</span></span>  
  
### <a name="to-create-a-many-to-many-relationship-between-tables"></a><span data-ttu-id="8411a-110">Per creare una relazione molti-a-molti tra tabelle</span><span class="sxs-lookup"><span data-stu-id="8411a-110">To create a many-to-many relationship between tables</span></span>  
  
1.  <span data-ttu-id="8411a-111">Nel diagramma del database aggiungere le tabelle tra cui si desidera creare una relazione molti-a-molti.</span><span class="sxs-lookup"><span data-stu-id="8411a-111">In your database diagram, add the tables that you want to create a many-to-many relationship between.</span></span>  
  
2.  <span data-ttu-id="8411a-112">Fare clic con il pulsante destro del mouse sul diagramma e scegliere **Nuova tabella** dal menu di scelta rapida per creare una terza tabella,</span><span class="sxs-lookup"><span data-stu-id="8411a-112">Create a third table by right-clicking the diagram and choosing **New Table** from the shortcut menu.</span></span> <span data-ttu-id="8411a-113">che diventerà la tabella di collegamento.</span><span class="sxs-lookup"><span data-stu-id="8411a-113">This will become the junction table.</span></span>  
  
3.  <span data-ttu-id="8411a-114">Nella finestra di dialogo **Scegli nome** modificare il nome di tabella assegnato automaticamente dal sistema.</span><span class="sxs-lookup"><span data-stu-id="8411a-114">In the **Choose Name** dialog box, change the system-assigned table name.</span></span> <span data-ttu-id="8411a-115">Ad esempio, la tabella di collegamento tra la tabella `titles` e la tabella `authors` ora si chiamerà `titleauthors`.</span><span class="sxs-lookup"><span data-stu-id="8411a-115">For example, the junction table between the `titles` table and the `authors` table is now named `titleauthors`.</span></span>  
  
4.  <span data-ttu-id="8411a-116">Copiare nella tabella di collegamento le colonne chiave primaria presenti nelle altre due tabelle.</span><span class="sxs-lookup"><span data-stu-id="8411a-116">Copy the primary key columns from each of the other two tables to the junction table.</span></span> <span data-ttu-id="8411a-117">Così come per qualsiasi altra tabella, è possibile aggiungere delle colonne.</span><span class="sxs-lookup"><span data-stu-id="8411a-117">You can add other columns to this table, just as you can to any other table.</span></span>  
  
5.  <span data-ttu-id="8411a-118">Nella tabella di collegamento impostare la chiave primaria in modo da includere tutte le colonne chiave primaria delle altre due tabelle.</span><span class="sxs-lookup"><span data-stu-id="8411a-118">In the junction table, set the primary key to include all the primary key columns from the other two tables.</span></span> <span data-ttu-id="8411a-119">Per informazioni dettagliate, vedere [creare chiavi primarie](../../relational-databases/tables/create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="8411a-119">For details, see [Create Primary Keys](../../relational-databases/tables/create-primary-keys.md).</span></span>  
  
6.  <span data-ttu-id="8411a-120">Definire una relazione uno-a-molti tra ciascuna delle due tabelle primarie e la tabella di collegamento.</span><span class="sxs-lookup"><span data-stu-id="8411a-120">Define a one-to-many relationship between each of the two primary tables and the junction table.</span></span> <span data-ttu-id="8411a-121">La tabella di collegamento dovrebbe essere sul lato "molti" di entrambe le relazioni create.</span><span class="sxs-lookup"><span data-stu-id="8411a-121">The junction table should be at the "many" side of both of the relationships you create.</span></span> <span data-ttu-id="8411a-122">Per informazioni dettagliate, vedere [creare relazioni di chiave esterna](../../relational-databases/tables/create-foreign-key-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="8411a-122">For details, see [Create Foreign Key Relationships](../../relational-databases/tables/create-foreign-key-relationships.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8411a-123">La creazione di una tabella di collegamento in un diagramma di database non comporta l'inserimento dei dati dalle tabelle correlate nella tabella di collegamento.</span><span class="sxs-lookup"><span data-stu-id="8411a-123">The creation of a junction table in a database diagram does not insert data from the related tables into the junction table.</span></span> <span data-ttu-id="8411a-124">Per informazioni sull'inserimento di dati in una tabella, vedere [Creazione di query di accodamento &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8411a-124">For information about inserting data into a table, see [Create Insert Results Queries &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8411a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8411a-125">See Also</span></span>  
 [<span data-ttu-id="8411a-126">Utilizzare diagrammi di database &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8411a-126">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](work-with-database-diagrams-visual-database-tools.md)  
  
  
