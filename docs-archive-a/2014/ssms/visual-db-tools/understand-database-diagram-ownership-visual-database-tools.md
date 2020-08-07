---
title: Informazioni sulla proprietà dei diagrammi di database (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.diagnostic.CannotOpenWithInvalidOwner
helpviewer_keywords:
- diagrams [SQL Server], ownership
- database diagrams [SQL Server], ownership
- owners [SQL Server], database diagrams
ms.assetid: 4a27a48e-c4ef-4017-82b8-0cac4d0bbcac
author: stevestein
ms.author: sstein
ms.openlocfilehash: 21d0f6f006328d8843bbbe12ee066a8564fb722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719296"
---
# <a name="understand-database-diagram-ownership-visual-database-tools"></a><span data-ttu-id="16716-102">Informazioni sulla proprietà dei diagrammi di database (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="16716-102">Understand Database Diagram Ownership (Visual Database Tools)</span></span>
  <span data-ttu-id="16716-103">Per poter utilizzare la Progettazione diagrammi di database, è necessario che un membro del ruolo db_owner (un ruolo dei database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ) ne effettui preventivamente la configurazione per il controllo dell'accesso ai diagrammi.</span><span class="sxs-lookup"><span data-stu-id="16716-103">To use Database Diagram Designer it must first be set up by a member of the db_owner role (a role of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases) to control access to diagrams.</span></span> <span data-ttu-id="16716-104">Ciascun diagramma ha un solo proprietario, ovvero l'utente che lo ha creato.</span><span class="sxs-lookup"><span data-stu-id="16716-104">Each diagram has one and only one owner, the user who created it.</span></span> <span data-ttu-id="16716-105">Per ulteriori informazioni sulla configurazione dei diagrammi, vedere la pagina relativa alla [configurazione di Progettazione diagrammi di database &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="16716-105">For more information on setting up diagramming see [Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="16716-106">In relazione alla proprietà dei diagrammi, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="16716-106">Some points to keep in mind about diagram ownership:</span></span>  
  
-   <span data-ttu-id="16716-107">Benché un diagramma possa essere creato da qualsiasi utente che dispone di accesso a un database, potrà essere visualizzato solo dall'utente che lo ha creato e dai membri del ruolo db_owner.</span><span class="sxs-lookup"><span data-stu-id="16716-107">Although any user with access to a database can create a diagram, once the diagram has been created, the only users who can see it are the diagram's creator and any member of the db_owner role.</span></span>  
  
-   <span data-ttu-id="16716-108">La proprietà dei diagrammi può essere trasferita solo ai membri del ruolo db_owner</span><span class="sxs-lookup"><span data-stu-id="16716-108">Ownership of diagrams can only be transferred to members of the db_owner role.</span></span> <span data-ttu-id="16716-109">e soltanto se il proprietario precedente è stato rimosso dal database.</span><span class="sxs-lookup"><span data-stu-id="16716-109">This is only possible if the previous owner of the diagram has been removed from the database.</span></span>  
  
-   <span data-ttu-id="16716-110">Se il proprietario di un diagramma viene rimosso dal database, il diagramma rimarrà all'interno del database finché un membro del ruolo db_owner non tenterà di aprirlo.</span><span class="sxs-lookup"><span data-stu-id="16716-110">If the owner of a diagram has been removed from the database, the diagram will remain in the database until a member of the db_owner role attempts to open it.</span></span> <span data-ttu-id="16716-111">A questo punto, il membro del ruolo db_owner potrà scegliere di subentrare come proprietario del diagramma.</span><span class="sxs-lookup"><span data-stu-id="16716-111">At that point the db_owner member can choose to take over ownership of the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16716-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16716-112">See Also</span></span>  
 <span data-ttu-id="16716-113">[Utilizzare diagrammi di database &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="16716-113">[Work with Database Diagrams &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="16716-114">Impostazione di Progettazione diagrammi di database &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="16716-114">Set Up Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
