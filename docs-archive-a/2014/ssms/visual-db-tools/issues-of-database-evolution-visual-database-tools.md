---
title: Problemi legati all'evoluzione del database (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- compatibility [SQL Server], multuser database changes
- database evolution [SQL Server]
ms.assetid: 1ed6ae10-d212-4ec2-8569-1b94ab1cba6d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 80daa694cd015a83657368902b07da254e6196ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724336"
---
# <a name="issues-of-database-evolution-visual-database-tools"></a><span data-ttu-id="ee610-102">Problemi legati all'evoluzione del database (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ee610-102">Issues of Database Evolution (Visual Database Tools)</span></span>
  <span data-ttu-id="ee610-103">Quando si modifica la struttura di un database distribuito, è necessario assicurarsi che tale modifica sia compatibile con i dati e la struttura del database esistenti.</span><span class="sxs-lookup"><span data-stu-id="ee610-103">If you change the structure of a deployed database, you must take special care that your alteration is compatible with the existing data and database structure.</span></span> <span data-ttu-id="ee610-104">Le seguenti modifiche potrebbero richiedere l'esecuzione di operazioni specifiche:</span><span class="sxs-lookup"><span data-stu-id="ee610-104">You might need to take special steps when you make the following modifications:</span></span>  
  
-   <span data-ttu-id="ee610-105">**Aggiunta di un vincolo** Se si aggiunge un vincolo, il database potrebbe già contenere dati che non lo rispettano.</span><span class="sxs-lookup"><span data-stu-id="ee610-105">**Adding a Constraint** If you add a constraint, the database might already contain data that does not satisfy it.</span></span> <span data-ttu-id="ee610-106">Quando si tenta di salvare il nuovo vincolo, nella casella di dialogo [Notifiche postsalvataggio &#40;Visual Database Tools&#41;](visual-database-tools.md) l'utente verrà avvertito che non è stato possibile creare il vincolo tramite il server del database.</span><span class="sxs-lookup"><span data-stu-id="ee610-106">When you try to save the new constraint, the [Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not create the constraint.</span></span> <span data-ttu-id="ee610-107">Per forzare l'accettazione del nuovo vincolo da parte del database, deselezionare la casella di controllo **Verifica dati esistenti durante la creazione**.</span><span class="sxs-lookup"><span data-stu-id="ee610-107">To force the database to accept the new constraint, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="ee610-108">**Aggiunta di una relazione** Se si aggiunge una relazione, il database potrebbe già contenere righe della tabella chiave esterna che non hanno righe corrispondenti nella tabella chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="ee610-108">**Adding a Relationship** If you add a relationship, the database might already contain rows of the foreign-key table that do not have corresponding rows in the primary-key table.</span></span> <span data-ttu-id="ee610-109">I dati esistenti potrebbero pertanto non soddisfare l'integrità referenziale.</span><span class="sxs-lookup"><span data-stu-id="ee610-109">That is, the existing data might not satisfy referential integrity.</span></span> <span data-ttu-id="ee610-110">Quando si tenta di salvare la nuova relazione, nella casella di dialogo [Notifiche postsalvataggio &#40;Visual Database Tools&#41;](visual-database-tools.md) l'utente verrà avvertito che non è stato possibile salvare la tabella chiave esterna modificata tramite il server del database.</span><span class="sxs-lookup"><span data-stu-id="ee610-110">When you try to save the new relationship, the[Post-Save Notifications Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) informs you that the database server could not save the revised foreign-key table.</span></span> <span data-ttu-id="ee610-111">Per forzare l'accettazione della modifica da parte del database, deselezionare la casella di controllo **Verifica dati esistenti durante la creazione**.</span><span class="sxs-lookup"><span data-stu-id="ee610-111">To force the database to accept the modification, you can clear the **Check existing data on creation** check box.</span></span>  
  
-   <span data-ttu-id="ee610-112">**Modifica di una tabella che contribuisce a una vista indicizzata** Se si modifica una tabella che contribuisce a una vista indicizzata di Microsoft SQL Server, gli indici della vista andranno persi.</span><span class="sxs-lookup"><span data-stu-id="ee610-112">**Modifying a Table Contributing to an Indexed View** If you modify a table that contributes to a Microsoft SQL Server indexed view, the indexes on the view will be lost.</span></span> <span data-ttu-id="ee610-113">Per informazioni sulla creazione degli indici, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ee610-113">See the SQL Server Books Online for information on recreating indexes.</span></span>  
  
-   <span data-ttu-id="ee610-114">**Eliminazione di un oggetto** Se si elimina un oggetto, ad esempio una colonna, una tabella o una vista, verificare prima che nessun altro oggetto del database vi faccia riferimento.</span><span class="sxs-lookup"><span data-stu-id="ee610-114">**Deleting an Object** If you delete an object, such as a column, table, or view, check first to be sure that the object is not referenced by another object in the database.</span></span>  
  
 <span data-ttu-id="ee610-115">Indipendentemente dalla modalità in base a cui si modifica la progettazione del database, è consigliabile mantenere una cronologia delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="ee610-115">No matter how you alter the database design, you should retain a history of the alterations.</span></span> <span data-ttu-id="ee610-116">Una possibile soluzione consiste nel mantenere gli script SQL per tutte le modifiche apportate al database di produzione.</span><span class="sxs-lookup"><span data-stu-id="ee610-116">One approach is to retain SQL scripts for all modifications that you ever make to your production database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee610-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee610-117">See Also</span></span>  
 <span data-ttu-id="ee610-118">[Vincoli UNIQUE e check](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="ee610-118">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="ee610-119">Ambienti multiutente &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ee610-119">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  
