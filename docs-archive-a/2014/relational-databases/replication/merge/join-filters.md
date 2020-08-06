---
title: Filtri di join | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server replication], join
- publications [SQL Server replication], join filters
- merge replication join filters [SQL Server replication]
- join filters
ms.assetid: dd78fd8f-56e3-4582-9abd-6bc25c91e075
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b97e7d7b53e6a3fdb242d1272e013bbd45f0ed17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623196"
---
# <a name="join-filters"></a><span data-ttu-id="54dcb-102">filtri di join</span><span class="sxs-lookup"><span data-stu-id="54dcb-102">Join Filters</span></span>
  <span data-ttu-id="54dcb-103">Un filtro di join consente di filtrare una tabella in base al tipo di filtro applicato a una tabella correlata nella pubblicazione</span><span class="sxs-lookup"><span data-stu-id="54dcb-103">A join filter allows a table to be filtered based on how a related table in the publication is filtered.</span></span> <span data-ttu-id="54dcb-104">Viene in genere filtrata una tabella padre mediante un filtro con parametri, quindi vengono definiti uno o più filtri di join così come si definisce un join tra tabelle.</span><span class="sxs-lookup"><span data-stu-id="54dcb-104">Typically a parent table is filtered using a parameterized filter; then one or more join filters are defined in much the same way that you define a join between tables.</span></span> <span data-ttu-id="54dcb-105">I filtri di join estendono il filtro con parametri affinché i dati nelle tabelle correlate vengano replicati solo se corrispondenti alla clausola di filtro di join.</span><span class="sxs-lookup"><span data-stu-id="54dcb-105">The join filters extend the parameterized filter so that the data in the related tables is only replicated if it matches the join filter clause.</span></span>  
  
 <span data-ttu-id="54dcb-106">I filtri join seguono in genere le relazioni tra chiavi primarie e chiavi esterne definite per le tabelle alle quali vengono applicati, ma non sono necessariamente limitati a tali relazioni.</span><span class="sxs-lookup"><span data-stu-id="54dcb-106">Join filters typically follow the primary key/foreign key relationships defined for the tables to which they are applied, but they are not limited strictly to primary key/foreign key relationships.</span></span> <span data-ttu-id="54dcb-107">Il filtro di join può essere basato su qualsiasi logica di confronto tra i dati correlati di due tabelle.</span><span class="sxs-lookup"><span data-stu-id="54dcb-107">The join filter can be based on any logic that compares related data in two tables.</span></span>  
  
 <span data-ttu-id="54dcb-108">Si considerino le tabelle seguenti del database di esempio [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] , correlate tramite relazioni di chiave primaria/chiave esterna:</span><span class="sxs-lookup"><span data-stu-id="54dcb-108">Consider the following tables in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database, which are related through primary key to foreign key relationships:</span></span>  
  
-   <span data-ttu-id="54dcb-109">**HumanResources.Employee**</span><span class="sxs-lookup"><span data-stu-id="54dcb-109">**HumanResources.Employee**</span></span>  
  
-   <span data-ttu-id="54dcb-110">**Sales.SalesOrderHeader**</span><span class="sxs-lookup"><span data-stu-id="54dcb-110">**Sales.SalesOrderHeader**</span></span>  
  
-   <span data-ttu-id="54dcb-111">**Sales.SalesOrderDetail**</span><span class="sxs-lookup"><span data-stu-id="54dcb-111">**Sales.SalesOrderDetail**</span></span>  
  
 <span data-ttu-id="54dcb-112">Queste tabelle potrebbero essere utilizzate in un'applicazione per supportare una forza vendita mobile, ma devono essere filtrate affinché ogni venditore della tabella **HumanResources.Employee** riceva soltanto i dati rilevanti per gli ordini dei propri clienti.</span><span class="sxs-lookup"><span data-stu-id="54dcb-112">These tables could be used in an application to support a mobile sales force, but they must be filtered so that each sales person in the **HumanResources.Employee** table receives only the data relevant to their customers' orders.</span></span>  
  
 <span data-ttu-id="54dcb-113">Il primo passaggio consiste nel definire un filtro con parametri per la tabella padre, costituita in questo caso dalla tabella **HumanResources.Employee** .</span><span class="sxs-lookup"><span data-stu-id="54dcb-113">The first step is to define a parameterized filter on the parent table, which in this example is the **HumanResources.Employee** table.</span></span> <span data-ttu-id="54dcb-114">In questa tabella è inclusa la colonna **LoginID**, contenente l'account di accesso per ogni dipendente nel formato *dominio\account accesso*.</span><span class="sxs-lookup"><span data-stu-id="54dcb-114">This table includes the column **LoginID**, which contains the login for each employee in the form *domain\login*.</span></span> <span data-ttu-id="54dcb-115">Per filtrare questa tabella affinché ogni dipendente riceva soltanto i dati pertinenti, specificare la clausola di filtro con parametri:</span><span class="sxs-lookup"><span data-stu-id="54dcb-115">To filter this table so that each employee receives only the data related to them, specify a parameterized filter clause of:</span></span>  
  
```  
LoginID = SUSER_SNAME()  
```  
  
 <span data-ttu-id="54dcb-116">Questo filtro garantisce che la sottoscrizione di ogni dipendente contenga soltanto i dati della tabella **HumanResources.Employee** rilevanti per tale dipendente. In questo caso, si tratta di una singola riga.</span><span class="sxs-lookup"><span data-stu-id="54dcb-116">This filter ensures that each employee's subscription only contains data from the **HumanResources.Employee** table that is relevant to that employee (which in this case is a single row).</span></span> <span data-ttu-id="54dcb-117">Per altre informazioni sui filtri di riga con parametri, vedere [Filtri di riga con parametri](parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="54dcb-117">For more information, see [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span></span>  
  
 <span data-ttu-id="54dcb-118">Il passaggio successivo consiste nell'estendere questo filtro a ogni tabella correlata, utilizzando una sintassi simile a quella utilizzata per specificare un join tra due tabelle.</span><span class="sxs-lookup"><span data-stu-id="54dcb-118">The next step is to extend this filter to each of the related tables, using syntax similar to that used to specify a join between two tables.</span></span> <span data-ttu-id="54dcb-119">La prima clausola di filtro di join è:</span><span class="sxs-lookup"><span data-stu-id="54dcb-119">The first join filter clause is:</span></span>  
  
```  
Employee.EmployeeID = SalesOrderHeader.SalesPersonID  
```  
  
 <span data-ttu-id="54dcb-120">Ciò garantisce che la sottoscrizione conterrà soltanto i dati degli ordini rilevanti per ogni venditore.</span><span class="sxs-lookup"><span data-stu-id="54dcb-120">This ensures the subscription contains only the order data relevant to each sales person.</span></span> <span data-ttu-id="54dcb-121">La seconda clausola di filtro di join è:</span><span class="sxs-lookup"><span data-stu-id="54dcb-121">The second join filter clause is:</span></span>  
  
```  
SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
```  
  
 <span data-ttu-id="54dcb-122">Ciò garantisce che la sottoscrizione conterrà soltanto i dati di dettaglio correlati ai dati degli ordini per ogni venditore.</span><span class="sxs-lookup"><span data-stu-id="54dcb-122">This ensures the subscription contains only the detail data related to the order data for each sales person.</span></span> <span data-ttu-id="54dcb-123">In questo esempio viene illustrato il join di una singola tabella in ogni fase. È inoltre possibile unire in join più tabelle in ogni fase.</span><span class="sxs-lookup"><span data-stu-id="54dcb-123">This example shows a single table being joined at each point; it is also possible to join more than one table at each point.</span></span>  
  
 <span data-ttu-id="54dcb-124">I filtri di join possono essere aggiunti uno per volta tramite la Creazione guidata nuova pubblicazione e la finestra di dialogo **Proprietà pubblicazione** oppure a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="54dcb-124">Join filters can be added one at a time through the New Publication Wizard and the **Publication Properties** dialog box, or they can be added programmatically.</span></span> <span data-ttu-id="54dcb-125">Possono inoltre essere generati automaticamente tramite la Creazione guidata nuova pubblicazione: specificando un filtro di riga per una tabella verranno applicati filtri di join a tutte le tabelle correlate.</span><span class="sxs-lookup"><span data-stu-id="54dcb-125">They can also be generated automatically through the New Publication Wizard: you specify a row filter for a table and join filters are applied to all related tables.</span></span> <span data-ttu-id="54dcb-126">Per altre informazioni, vedere [Definire e modificare un filtro di join tra articoli di merge](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Generare automaticamente un set di filtri di join tra gli articoli di merge &#40;SQL Server Management Studio&#41;](../publish/automatically-generate-join-filters-between-merge-articles.md) e [Definire un articolo](../publish/define-an-article.md).</span><span class="sxs-lookup"><span data-stu-id="54dcb-126">For more information, see [Define and Modify a Join Filter Between Merge Articles](../publish/define-and-modify-a-join-filter-between-merge-articles.md), [Automatically Generate a Set of Join Filters Between Merge Articles &#40;SQL Server Management Studio&#41;](../publish/automatically-generate-join-filters-between-merge-articles.md), and [Define an Article](../publish/define-an-article.md).</span></span>  
  
## <a name="optimizing-join-filter-performance"></a><span data-ttu-id="54dcb-127">Ottimizzazione delle prestazioni dei filtri di join</span><span class="sxs-lookup"><span data-stu-id="54dcb-127">Optimizing Join Filter Performance</span></span>  
 <span data-ttu-id="54dcb-128">È possibile ottimizzare le prestazioni dei filtri di join attenendosi alle linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="54dcb-128">Join filter performance can be optimized by following these guidelines:</span></span>  
  
-   <span data-ttu-id="54dcb-129">Limitare il numero massimo di tabelle nella gerarchia dei filtri di join.</span><span class="sxs-lookup"><span data-stu-id="54dcb-129">Limit the number of tables in the join filter hierarchy.</span></span>  
  
     <span data-ttu-id="54dcb-130">I filtri di join possono includere un numero illimitato di tabelle, ma filtri con un numero elevato di tabelle possono influire significativamente sulle prestazioni durante l'elaborazione di processi di merge.</span><span class="sxs-lookup"><span data-stu-id="54dcb-130">Join Filters can involve an unlimited number of tables, but filters with a large number of tables can significantly impact performance during merge processing.</span></span> <span data-ttu-id="54dcb-131">Se si generano filtri di join di cinque o più tabelle, considerare altre soluzioni: non filtrare tabelle piccole, non soggette a modifica o tabelle che fungono principalmente da tabelle di ricerca.</span><span class="sxs-lookup"><span data-stu-id="54dcb-131">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="54dcb-132">Utilizzare i filtri di join solo tra tabelle che devono essere partizionate tra diverse sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="54dcb-132">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="54dcb-133">Se appropriato, impostare la proprietà **JoinUniqueKey** su **True** .</span><span class="sxs-lookup"><span data-stu-id="54dcb-133">Set the **join unique key** option to **True** where appropriate.</span></span>  
  
     <span data-ttu-id="54dcb-134">Se la colonna unita in join nella tabella padre è univoca, per il processo di merge sono disponibili speciali procedure di ottimizzazione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="54dcb-134">The merge process has special performance optimizations available if the joined column in the parent is unique.</span></span> <span data-ttu-id="54dcb-135">Se la condizione di join è basata su una colonna univoca, impostare la proprietà **JoinUniqueKey** per il filtro di join.</span><span class="sxs-lookup"><span data-stu-id="54dcb-135">If the join condition is based on a unique column, set the **join unique key** option for the join filter.</span></span> <span data-ttu-id="54dcb-136">Per informazioni sull'impostazione di questa proprietà, vedere le procedure elencate nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="54dcb-136">For information about setting this option, see the how-to topics listed in the previous section.</span></span>  
  
-   <span data-ttu-id="54dcb-137">Verificare che le colonne a cui viene fatto riferimento nei filtri di join siano indicizzate.</span><span class="sxs-lookup"><span data-stu-id="54dcb-137">Ensure that the columns referenced in join filters are indexed.</span></span>  
  
     <span data-ttu-id="54dcb-138">Se le colonne a cui viene fatto riferimento nel filtro sono indicizzate, i filtri possono essere elaborati dalla replica in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="54dcb-138">If the columns referenced in the filter are indexed, replication can process the filters more efficiently.</span></span>  
  
-   <span data-ttu-id="54dcb-139">Non creare filtri di riga che svolgono la funzione di filtri di join.</span><span class="sxs-lookup"><span data-stu-id="54dcb-139">Do not create row filters that mimic join filters.</span></span>  
  
     <span data-ttu-id="54dcb-140">È possibile creare filtri di riga che svolgono la funzione di filtri di join utilizzando una sottoquery in una clausola WHERE, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="54dcb-140">It is possible to create row filters that mimic join filters by using a subquery in a WHERE clause, such as:</span></span>  
  
    ```  
    WHERE Customer.SalesPersonID IN (SELECT EmployeeID FROM Employee WHERE LoginID = SUSER_SNAME())   
    ```  
  
     <span data-ttu-id="54dcb-141">È consigliabile esprimere tale logica in un filtro di join, anziché in una sottoquery.</span><span class="sxs-lookup"><span data-stu-id="54dcb-141">It is strongly recommended that all such logic be expressed in a join filter rather than a subquery.</span></span> <span data-ttu-id="54dcb-142">Se l'applicazione richiede l'utilizzo di una sottoquery in un filtro di riga, verificare che la sottoquery faccia riferimento soltanto a dati di ricerca non soggetti a modifiche.</span><span class="sxs-lookup"><span data-stu-id="54dcb-142">If your application requires a row filter to use a subsquery, ensure that the subquery only references lookup data that does not change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54dcb-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54dcb-143">See Also</span></span>  
 <span data-ttu-id="54dcb-144">[Filtrare i dati pubblicati per la replica di tipo merge](filter-published-data-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="54dcb-144">[Filter Published Data for Merge Replication](filter-published-data-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="54dcb-145">Filtri di riga con parametri</span><span class="sxs-lookup"><span data-stu-id="54dcb-145">Parameterized Row Filters</span></span>](parameterized-filters-parameterized-row-filters.md)  
  
  
