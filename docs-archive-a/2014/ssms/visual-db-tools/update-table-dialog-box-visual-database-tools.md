---
title: Finestra di dialogo Aggiorna tabella (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.updatetable
- vdtsql.chm:69643
ms.assetid: 174c7275-5b15-42a9-b172-5ff30de575a1
author: stevestein
ms.author: sstein
ms.openlocfilehash: 426c842b85d6404ba101b57a9b572107dbc76bb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630195"
---
# <a name="update-table-dialog-box-visual-database-tools"></a><span data-ttu-id="65c07-102">Finestra di dialogo Aggiorna tabella (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="65c07-102">Update Table Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="65c07-103">Questa finestra di dialogo consente di specificare la tabella da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="65c07-103">This dialog box allows you to specify the table to be updated.</span></span>  
  
 <span data-ttu-id="65c07-104">Viene visualizzata quando nel riquadro Diagramma sono aperte più tabelle e si cambia il tipo di query in modo da disporre di una query di aggiornamento (Update).</span><span class="sxs-lookup"><span data-stu-id="65c07-104">This dialog box appears if more than one table is displayed in the Diagram pane when you change a query's type to be an Update query.</span></span>  
  
 <span data-ttu-id="65c07-105">Selezionare la tabella da aggiornare e quindi scegliere **OK**. </span><span class="sxs-lookup"><span data-stu-id="65c07-105">Select the table to update, and then choose **OK**.</span></span>\  
  
> [!NOTE]  
>  <span data-ttu-id="65c07-106">Se la tabella viene pubblicata per la replica, è necessario apportare modifiche allo schema usando l'istruzione [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) di Transact-SQL oppure SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="65c07-106">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="65c07-107">Quando si apportano modifiche allo schema utilizzando Progettazione tabelle o Progettazione diagrammi di database, viene effettuato il tentativo di rimuovere e rigenerare la tabella.</span><span class="sxs-lookup"><span data-stu-id="65c07-107">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="65c07-108">La modifica allo schema non riuscirà, poiché non è consentita la rimozione di oggetti pubblicati.</span><span class="sxs-lookup"><span data-stu-id="65c07-108">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c07-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65c07-109">See Also</span></span>  
 [<span data-ttu-id="65c07-110">Creare query di aggiornamento &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="65c07-110">Create Update Queries &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
