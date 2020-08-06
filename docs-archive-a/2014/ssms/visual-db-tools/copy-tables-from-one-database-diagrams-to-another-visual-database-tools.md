---
title: Copia di tabelle da un diagramma di database a un altro (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- duplicating tables
ms.assetid: 155a4f09-9321-4887-a7d4-aa2ce6b51277
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7e90c8f324e80f7c59674def06a77e93a5bf0cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711451"
---
# <a name="copy-tables-from-one-database-diagrams-to-another-visual-database-tools"></a><span data-ttu-id="40285-102">Copia di tabelle da un diagramma di database a un altro (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="40285-102">Copy Tables from One Database Diagrams to Another (Visual Database Tools)</span></span>
  <span data-ttu-id="40285-103">È possibile copiare una tabella da un diagramma di database a un altro nello stesso database.</span><span class="sxs-lookup"><span data-stu-id="40285-103">You can copy a table from one database diagram to another in the same database.</span></span>  
  
 <span data-ttu-id="40285-104">Quando si esegue questa operazione, viene semplicemente aggiunto un riferimento alla tabella nel secondo diagramma.</span><span class="sxs-lookup"><span data-stu-id="40285-104">Copying a table from one database diagram to another diagram adds a reference to the table in the second diagram.</span></span> <span data-ttu-id="40285-105">La tabella non viene duplicata nel database.</span><span class="sxs-lookup"><span data-stu-id="40285-105">The table is not duplicated in your database.</span></span> <span data-ttu-id="40285-106">Se ad esempio si copia la tabella `authors` da un diagramma di database a un altro, ogni diagramma farà riferimento alla stessa tabella `authors` nel database.</span><span class="sxs-lookup"><span data-stu-id="40285-106">For example, if you copy the `authors` table from one database diagram to another, each diagram references the same `authors` table in the database.</span></span>  
  
### <a name="to-copy-a-table-from-another-database-diagram"></a><span data-ttu-id="40285-107">Per copiare una tabella da un diverso diagramma di database</span><span class="sxs-lookup"><span data-stu-id="40285-107">To copy a table from another database diagram</span></span>  
  
1.  <span data-ttu-id="40285-108">Assicurarsi di essere connessi al database di cui si desidera copiare la tabella.</span><span class="sxs-lookup"><span data-stu-id="40285-108">Make sure you are connected to the database whose table you want to copy.</span></span>  
  
2.  <span data-ttu-id="40285-109">Aprire i diagrammi di database di origine e destinazione e, all'interno del diagramma d'origine, selezionare la tabella da copiare nel diagramma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="40285-109">Open the source and target database diagrams and within the source diagram, select the table that you want to copy to the target diagram.</span></span>  
  
3.  <span data-ttu-id="40285-110">Fare clic sul pulsante **Copia** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="40285-110">Click the **Copy** button on the toolbar.</span></span> <span data-ttu-id="40285-111">La definizione della tabella selezionata verrà copiata negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="40285-111">This action places the selected table definition on the Clipboard.</span></span>  
  
4.  <span data-ttu-id="40285-112">Passare al diagramma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="40285-112">Switch to the target diagram.</span></span> <span data-ttu-id="40285-113">Il diagramma deve essere nello stesso database del diagramma di origine.</span><span class="sxs-lookup"><span data-stu-id="40285-113">This diagram must be in the same database as the source diagram.</span></span>  
  
5.  <span data-ttu-id="40285-114">Fare clic sul pulsante **Incolla** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="40285-114">Click the **Paste** button on the toolbar.</span></span> <span data-ttu-id="40285-115">Il contenuto degli Appunti verrà inserito nella nuova posizione e rimarrà evidenziato fino a quando non si farà clic in un altro punto.</span><span class="sxs-lookup"><span data-stu-id="40285-115">The Clipboard contents appear at the new location and remain highlighted until you click elsewhere.</span></span> <span data-ttu-id="40285-116">Se esistono delle relazioni tra le tabelle selezionate e altre tabelle nel diagramma di destinazione, verranno tracciate automaticamente le linee delle relazioni.</span><span class="sxs-lookup"><span data-stu-id="40285-116">If relationships exist between the selected tables and other tables in the target diagram, relationship lines are automatically drawn.</span></span>  
  
 <span data-ttu-id="40285-117">Le modifiche apportate alla tabella in uno dei due diagrammi verranno riportate in entrambi i diagrammi.</span><span class="sxs-lookup"><span data-stu-id="40285-117">When you edit the table in either diagram, your changes are reflected in both diagrams.</span></span> <span data-ttu-id="40285-118">Allo stesso modo, dopo avere salvato la tabella in uno dei due diagrammi, essa non verrà più considerata "modificata" in nessuno dei due.</span><span class="sxs-lookup"><span data-stu-id="40285-118">Similarly, once you save the table in either diagram, the table is no longer considered "modified" in either diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40285-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40285-119">See Also</span></span>  
 <span data-ttu-id="40285-120">[Utilizzare diagrammi di database &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="40285-120">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="40285-121">Aggiunta di tabelle a diagrammi &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="40285-121">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](add-tables-to-diagrams-visual-database-tools.md)  
  
  
