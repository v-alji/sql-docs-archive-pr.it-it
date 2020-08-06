---
title: Creazione di relazioni tra tabelle in un diagramma (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- diagrams [SQL Server], designing
ms.assetid: 28e9630c-dff4-46cc-bb0e-fe77998b6ac2
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7d627a37f84dcb66b2129bb9c7dbc5890ccd46c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724359"
---
# <a name="create-relationships-between-tables-on-a-diagram-visual-database-tools"></a><span data-ttu-id="47caf-102">Creazione di relazioni tra tabelle in un diagramma (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="47caf-102">Create Relationships Between Tables on a Diagram (Visual Database Tools)</span></span>
  <span data-ttu-id="47caf-103">È possibile creare relazioni tra le colonne in diverse tabelle in Progettazione diagrammi di database trascinando le colonne all'interno delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="47caf-103">You can create relationships between columns in different tables in the Diagram Designer by dragging columns between tables.</span></span>  
  
### <a name="to-create-a-relationship-graphically"></a><span data-ttu-id="47caf-104">Per creare una relazione graficamente</span><span class="sxs-lookup"><span data-stu-id="47caf-104">To create a relationship graphically</span></span>  
  
1.  <span data-ttu-id="47caf-105">In Progettazione database fare clic sul selettore delle righe per una o più colonne di database che si desidera correlare a una colonna in un'altra tabella.</span><span class="sxs-lookup"><span data-stu-id="47caf-105">In Database Designer, click the row selector for one or more database columns that you want to relate to a column in another table.</span></span>  
  
2.  <span data-ttu-id="47caf-106">Trascinare la colonna o le colonne selezionate nella tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="47caf-106">Drag the selected column(s) to the related table.</span></span>  
  
3.  <span data-ttu-id="47caf-107">Verranno visualizzate due finestre di dialogo: **Relazione chiavi esterne** e **Tabelle e colonne**, quest'ultima visualizzata in primo piano.</span><span class="sxs-lookup"><span data-stu-id="47caf-107">Two dialog boxes appear: **Foreign Key Relationship** and **Tables and Columns**, with the latter appearing in the foreground.</span></span>  
  
4.  <span data-ttu-id="47caf-108">Il nome della **relazione** ha un nome fornito dal sistema nel formato FK_*assegnato*_*foreignTable*.</span><span class="sxs-lookup"><span data-stu-id="47caf-108">**Relationship name** has a system-provided name in the format FK_*localtable*_*foreigntable*.</span></span> <span data-ttu-id="47caf-109">È possibile modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="47caf-109">You may change this value.</span></span>  
  
5.  <span data-ttu-id="47caf-110">Verificare che in **Tabella di chiave primaria** sia specificata la tabella corretta.</span><span class="sxs-lookup"><span data-stu-id="47caf-110">Verify that **Primary key table** specifies the correct table.</span></span>  
  
6.  <span data-ttu-id="47caf-111">Nella griglia sono indicate le colonne locali e le colonne esterne corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="47caf-111">The grid lists the local columns and their matching foreign columns.</span></span> <span data-ttu-id="47caf-112">È possibile aggiungere o rimuovere le colonne di tabella o modificare i mapping.</span><span class="sxs-lookup"><span data-stu-id="47caf-112">You can add or remove table columns or change mappings.</span></span>  
  
7.  <span data-ttu-id="47caf-113">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="47caf-113">Choose **OK**.</span></span>  
  
     <span data-ttu-id="47caf-114">Verrà visualizzata la finestra di dialogo **Relazione chiavi esterne** .</span><span class="sxs-lookup"><span data-stu-id="47caf-114">The **Foreign Key Relationship** dialog box appears.</span></span> <span data-ttu-id="47caf-115">**Relazione selezionata** visualizza la relazione creata.</span><span class="sxs-lookup"><span data-stu-id="47caf-115">**Selected Relationship** shows the relationship you have created.</span></span>  
  
8.  <span data-ttu-id="47caf-116">Modificare le proprietà della relazione nella griglia.</span><span class="sxs-lookup"><span data-stu-id="47caf-116">Change properties for the relationship in the grid.</span></span>  
  
9. <span data-ttu-id="47caf-117">Scegliere **OK** per creare la relazione.</span><span class="sxs-lookup"><span data-stu-id="47caf-117">Choose **OK** to create the relationship.</span></span>  
  
     <span data-ttu-id="47caf-118">Progettazione database mostra una relazione tra le colonne selezionate.</span><span class="sxs-lookup"><span data-stu-id="47caf-118">Database Designer shows a relationship between the columns you chose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47caf-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47caf-119">See Also</span></span>  
 <span data-ttu-id="47caf-120">[Finestra di dialogo tabelle e colonne &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="47caf-120">[Tables and Columns Dialog Box &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="47caf-121">[Vincoli UNIQUE e check](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="47caf-121">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="47caf-122">Utilizzo di tabelle in diagrammi di database &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="47caf-122">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
