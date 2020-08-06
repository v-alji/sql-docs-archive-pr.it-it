---
title: Aggiungere tabelle a diagrammi (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- inserting tables
- adding tables
ms.assetid: 5440fdf7-ac04-4325-9f32-181f4cd402e5
author: stevestein
ms.author: sstein
ms.openlocfilehash: fe5c1274ac390f4834bd8ac1088258061fc0406d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629141"
---
# <a name="add-tables-to-diagrams-visual-database-tools"></a><span data-ttu-id="5a0dc-102">Aggiunta di tabelle a diagrammi (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="5a0dc-102">Add Tables to Diagrams (Visual Database Tools)</span></span>
  <span data-ttu-id="5a0dc-103">È possibile aggiungere una tabella al diagramma di database per modificarne la struttura o per correlarla ad altre tabelle nel diagramma,</span><span class="sxs-lookup"><span data-stu-id="5a0dc-103">You can add a table to your database diagram to edit its structure or relate it to other tables in your diagram.</span></span> <span data-ttu-id="5a0dc-104">aggiungendo una tabella di database esistente o inserendone una nuova non ancora definita nel database.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-104">You can either add existing database tables to a diagram or insert a new table that has not yet been defined in the database.</span></span>  
  
### <a name="to-insert-a-new-table-into-a-diagram"></a><span data-ttu-id="5a0dc-105">Per inserire una nuova tabella nel diagramma</span><span class="sxs-lookup"><span data-stu-id="5a0dc-105">To insert a new table into a diagram</span></span>  
  
1.  <span data-ttu-id="5a0dc-106">Assicurarsi di essere connessi al database nel quale si desidera creare la tabella.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-106">Make sure you are connected to the database in which you want to create the table.</span></span>  
  
     <span data-ttu-id="5a0dc-107">Per creare una tabella nel diagramma corrente, fare clic sul pulsante **Nuova tabella** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-107">To create a table in your current diagram, click the **New Table** button on the toolbar.</span></span>  
  
     <span data-ttu-id="5a0dc-108">-oppure-</span><span class="sxs-lookup"><span data-stu-id="5a0dc-108">-or-</span></span>  
  
     <span data-ttu-id="5a0dc-109">Fare clic con il pulsante destro del mouse nel diagramma e scegliere **Nuova tabella**.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-109">Right-click in the diagram and select **New Table**.</span></span>  
  
2.  <span data-ttu-id="5a0dc-110">Nella finestra di dialogo **Scegli nome** modificare o accettare il nome di tabella assegnato dal sistema e scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-110">Modify or accept the system-assigned table name, in the **Choose Name** dialog box, and then choose **OK**.</span></span>  
  
     <span data-ttu-id="5a0dc-111">Verrà visualizzata una nuova tabella nella vista Standard.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-111">A new table appears in the diagram in Standard view.</span></span>  
  
3.  <span data-ttu-id="5a0dc-112">Digitare un nome di colonna nella prima cella della nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-112">In the first cell of the new table, type a column name.</span></span> <span data-ttu-id="5a0dc-113">Premere quindi il tasto TAB per passare alla cella successiva.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-113">Then press the TAB key to move to the next cell.</span></span>  
  
4.  <span data-ttu-id="5a0dc-114">In **Tipo di dati**selezionare un tipo di dati per la colonna.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-114">Under **Data Type**, select a data type for the column.</span></span> <span data-ttu-id="5a0dc-115">A ciascuna colonna deve corrispondere un nome e un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-115">Each column must have a name and data type.</span></span>  
  
     <span data-ttu-id="5a0dc-116">Le altre proprietà della colonna possono essere impostate in Progettazione tabelle.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-116">You can set the column's other properties in Table Designer.</span></span>  
  
5.  <span data-ttu-id="5a0dc-117">Ripetere i passaggi 3 e 4 per ogni colonna da aggiungere alla tabella.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-117">Repeat steps 3 and 4 for each column you want to add to the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a0dc-118">Una volta salvato il diagramma di database, la nuova tabella verrà aggiunta al database.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-118">When you save your database diagram, the new table will be added to your database.</span></span>  
  
### <a name="to-add-an-existing-table-to-a-diagram"></a><span data-ttu-id="5a0dc-119">Per aggiungere una tabella esistente a un diagramma</span><span class="sxs-lookup"><span data-stu-id="5a0dc-119">To add an existing table to a diagram</span></span>  
  
1.  <span data-ttu-id="5a0dc-120">Assicurarsi di essere connessi al database di cui si desidera modificare le tabelle.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-120">Make sure you are connected to the database whose tables you want to edit.</span></span>  
  
2.  <span data-ttu-id="5a0dc-121">Selezionare una tabella nella cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="5a0dc-121">Select a table in the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="5a0dc-122">Trascinare la tabella nel diagramma di database.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-122">Drag the table into your database diagram.</span></span>  
  
4.  <span data-ttu-id="5a0dc-123">Rilasciare il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-123">Release the mouse button.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a0dc-124">Se esistono delle relazioni tra la tabella selezionata e altre tabelle nel diagramma, verranno tracciate automaticamente le linee delle relazioni.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-124">If relationships exist between the selected table and other tables in your diagram, relationship lines are automatically drawn.</span></span>  
  
### <a name="to-add-related-tables-to-a-diagram"></a><span data-ttu-id="5a0dc-125">Per aggiungere tabelle correlate a un diagramma</span><span class="sxs-lookup"><span data-stu-id="5a0dc-125">To add related tables to a diagram</span></span>  
  
1.  <span data-ttu-id="5a0dc-126">Selezionare una o più tabelle con vincoli di chiave esterna nel diagramma di database.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-126">Select one or more tables with foreign key constraints in the database diagram.</span></span>  
  
2.  <span data-ttu-id="5a0dc-127">Fare clic con il pulsante destro del mouse su una delle tabelle selezionate e scegliere **Aggiungi tabelle correlate**.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-127">Right-click any of the selected tables and choose **Add Related Tables**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a0dc-128">Verranno aggiunte al diagramma sia le tabelle a cui fa riferimento un vincolo di chiave esterna dalle tabelle selezionate, sia quelle che fanno riferimento alle tabelle selezionate con un vincolo di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="5a0dc-128">Both those tables referenced by a foreign key constraint from the selected table(s) and those referencing the selected table(s) with a foreign key constraint are added to the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a0dc-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a0dc-129">See Also</span></span>  
 <span data-ttu-id="5a0dc-130">[Utilizzare diagrammi di database &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="5a0dc-130">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="5a0dc-131">Utilizzo di tabelle in diagrammi di database &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="5a0dc-131">Work with Tables in Database Diagram &#40;Visual Database Tools&#41;</span></span>](work-with-tables-in-database-diagram-visual-database-tools.md)  
  
  
