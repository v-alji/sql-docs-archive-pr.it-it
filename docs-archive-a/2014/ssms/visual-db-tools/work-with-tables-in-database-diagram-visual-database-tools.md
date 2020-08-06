---
title: Usare tabelle in diagrammi di database (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- database diagrams [SQL Server], tables
- Table Designer, database diagrams
- tables [SQL Server], database diagrams
- database diagrams [SQL Server], Table Designer
ms.assetid: ee2c5d84-22bf-4597-ac70-a27ed8cc94f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: f648cd5fd08ed47c6670491ad5b7f3d75b7ead47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630196"
---
# <a name="work-with-tables-in-database-diagram-visual-database-tools"></a><span data-ttu-id="a7220-102">Utilizzo di tabelle in diagrammi di database (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a7220-102">Work with Tables in Database Diagram (Visual Database Tools)</span></span>
  <span data-ttu-id="a7220-103">È possibile modificare e creare tabelle di database in Progettazione tabelle o in Progettazione diagrammi di database.</span><span class="sxs-lookup"><span data-stu-id="a7220-103">You can modify and create database tables in either Table Designer or Database Diagram Designer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7220-104">Se la tabella viene pubblicata per la replica, è necessario apportare modifiche allo schema usando l'istruzione [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) di Transact-SQL oppure SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="a7220-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="a7220-105">Quando si apportano modifiche allo schema utilizzando Progettazione tabelle o Progettazione diagrammi di database, viene effettuato il tentativo di rimuovere e rigenerare la tabella.</span><span class="sxs-lookup"><span data-stu-id="a7220-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="a7220-106">La modifica allo schema non riuscirà, poiché non è consentita la rimozione di oggetti pubblicati.</span><span class="sxs-lookup"><span data-stu-id="a7220-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7220-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a7220-107">In This Section</span></span>  
 [<span data-ttu-id="a7220-108">Aggiunta di tabelle a diagrammi &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a7220-108">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
 [<span data-ttu-id="a7220-109">Aggiungere tabelle correlate a diagrammi &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a7220-109">Add Related Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](add-related-tables-to-diagrams-visual-database-tools.md)  
  
 [<span data-ttu-id="a7220-110">Salvataggio di tabelle selezionate di un diagramma &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a7220-110">Save Selected Tables on a Diagram &#40;Visual Database Tools&#41;</span></span>](save-selected-tables-on-a-diagram-visual-database-tools.md)  
  
 [<span data-ttu-id="a7220-111">Copia di tabelle da un diagramma di database a un altro &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a7220-111">Copy Tables from One Database Diagrams to Another &#40;Visual Database Tools&#41;</span></span>](copy-tables-from-one-database-diagrams-to-another-visual-database-tools.md)  
  
 [<span data-ttu-id="a7220-112">Rimozione di tabelle da diagrammi di database &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a7220-112">Remove Tables from Database Diagrams &#40;Visual Database Tools&#41;</span></span>](remove-tables-from-database-diagrams-visual-database-tools.md)  
  
 [<span data-ttu-id="a7220-113">Mapping di relazioni molti-a-molti &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a7220-113">Map Many-to-Many Relationships &#40;Visual Database Tools&#41;</span></span>](map-many-to-many-relationships-visual-database-tools.md)  
  
 [<span data-ttu-id="a7220-114">Creazione di relazioni riflessive &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a7220-114">Draw Reflexive Relationships &#40;Visual Database Tools&#41;</span></span>](draw-reflexive-relationships-visual-database-tools.md)  
  
## <a name="reference"></a><span data-ttu-id="a7220-115">Riferimento</span><span class="sxs-lookup"><span data-stu-id="a7220-115">Reference</span></span>  
 [<span data-ttu-id="a7220-116">Finestra di dialogo Aggiungi tabella &#40;Database Designer&#41; &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a7220-116">Add Table Dialog Box &#40;Database Designer&#41; &#40;Visual Database Tools&#41;</span></span>](add-table-dialog-box-database-designer-visual-database-tools.md)  
  
## <a name="related-sections"></a><span data-ttu-id="a7220-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a7220-117">Related Sections</span></span>  
  
