---
title: Ambienti multiutente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- users [SQL Server], multiuser environments
- conflict resolution [Visual Database Tools]
- multiple users making database changes
- multiuser environments [Visual Database Tools]
- database modifications [SQL Server]
- version control [Visual Database Tools]
- Visual Database Tools [SQL Server], multiuser environments
ms.assetid: 330bd48c-9427-4967-b58e-b7c492d5ee36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2e219ecda25f477aa459de674a43d9c2360376ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626449"
---
# <a name="multiuser-environments-visual-database-tools"></a><span data-ttu-id="12850-102">Ambienti multiutente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="12850-102">Multiuser Environments (Visual Database Tools)</span></span>
  <span data-ttu-id="12850-103">Un ambiente multiutente è un ambiente in cui altri utenti possono connettersi e apportare modifiche allo stesso database sul quale si sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="12850-103">A multiuser environment is one in which other users can connect and make changes to the same database that you are working with.</span></span> <span data-ttu-id="12850-104">È quindi possibile che numerosi utenti modifichino contemporaneamente gli stessi oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="12850-104">As a result, several users might be working with the same database objects at the same time.</span></span> <span data-ttu-id="12850-105">In un ambiente multiutente è pertanto possibile che sul database in cui si stanno apportando le proprie modifiche incidano le modifiche apportate contemporaneamente da altri utenti e viceversa.</span><span class="sxs-lookup"><span data-stu-id="12850-105">Thus, a multiuser environment introduces the possibility of the database being affected by changes made by other users while you are making changes, and vice versa.</span></span>  
  
 <span data-ttu-id="12850-106">Un aspetto fondamentale quando si utilizza un database in un ambiente multiutente è rappresentato dalle autorizzazioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="12850-106">A key issue when working with databases in a multiuser environment is access permissions.</span></span> <span data-ttu-id="12850-107">Le autorizzazioni di cui si dispone per il database determinano la gamma di attività che è possibile eseguire sul database.</span><span class="sxs-lookup"><span data-stu-id="12850-107">The permissions you have for the database determine the extent of the work you can do with the database.</span></span> <span data-ttu-id="12850-108">Per apportare, ad esempio, modifiche a oggetti in un database, è necessario disporre delle autorizzazioni di scrittura appropriate per il database.</span><span class="sxs-lookup"><span data-stu-id="12850-108">For example, to make changes to objects in a database, you must have the appropriate write permissions for the database.</span></span> <span data-ttu-id="12850-109">Per ulteriori informazioni sulle autorizzazioni per il database in uso, vedere la documentazione del database.</span><span class="sxs-lookup"><span data-stu-id="12850-109">For more information about permissions in your database, see your database documentation.</span></span> <span data-ttu-id="12850-110">Per altre informazioni, vedere [Autorizzazioni e Visual Database Tools &#40;Visual Database Tools&#41](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12850-110">For more information see [Permissions and Visual Database Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="12850-111">Quando si salvano le modifiche apportate alle tabelle, in Progettazione tabelle viene verificato che il database non sia stato modificato dall'ultimo salvataggio delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="12850-111">When you save changes made to tables, Table Designer verifies that the database has not been modified since you last saved changes.</span></span> <span data-ttu-id="12850-112">Se un altro utente ha apportato modifiche, si verrà informati che il database è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="12850-112">If another user has made changes, you will be notified that the database has been modified.</span></span> <span data-ttu-id="12850-113">A quel punto, è possibile decidere di riconciliare tali modifiche.</span><span class="sxs-lookup"><span data-stu-id="12850-113">You may need to reconcile these changes.</span></span> <span data-ttu-id="12850-114">Per altre informazioni, vedere [Riconciliare le modifiche apportate da più utenti &#40;Visual Database Tools&#41;](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12850-114">For more information, see [Reconcile Changes Made by Multiple Users &#40;Visual Database Tools&#41;](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="12850-115">In un ambiente multiutente è opportuno prendere alcune precauzioni per evitare che le modifiche generino conflitti.</span><span class="sxs-lookup"><span data-stu-id="12850-115">In a multiuser environment there are special considerations to keep in mind to avoid conflicting changes.</span></span> <span data-ttu-id="12850-116">Per altre informazioni, vedere [Problemi legati all'evoluzione del database & #40; Visual Database Tools & #41;](issues-of-database-evolution-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12850-116">For more information, see [Issues of Database Evolution &#40;Visual Database Tools&#41;](issues-of-database-evolution-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="12850-117">Per evitare che si verifichino problemi, è possibile apportare le modifiche desiderate in una copia del database, ad esempio un database di verifica, quindi creare uno script delle modifiche da eseguire per estendere le modifiche al database originale dopo avere risolto i conflitti offline.</span><span class="sxs-lookup"><span data-stu-id="12850-117">One way to avoid problems is to work in a copy of the database, such as a test database, when you make changes, then you can create a change script that you can run to make those changes on the original database after resolving conflicts offline.</span></span> <span data-ttu-id="12850-118">Per altre informazioni, vedere [Database di sviluppo, verifica e produzione &#40;Visual Database Tools&#41;](development-test-and-production-databases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12850-118">For more information see [Development, Test, and Production Databases &#40;Visual Database Tools&#41;](development-test-and-production-databases-visual-database-tools.md).</span></span>  
  
  
