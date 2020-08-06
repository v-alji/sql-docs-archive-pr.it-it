---
title: Modificare l'ordine delle colonne in una tabella | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], change order in a table
- column order, change
ms.assetid: cd99ef56-9085-431a-a0fc-58e7add5399f
author: stevestein
ms.author: sstein
ms.openlocfilehash: d162f9dc793ceb9ea423d94922f7358f1729712e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628587"
---
# <a name="change-column-order-in-a-table"></a><span data-ttu-id="6d412-102">Modificare l'ordine delle colonne in una tabella</span><span class="sxs-lookup"><span data-stu-id="6d412-102">Change Column Order in a Table</span></span>
  <span data-ttu-id="6d412-103">In Progettazione tabelle è possibile modificare l'ordine delle colonne in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d412-103">You can change the order of columns in Table Designer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="6d412-104">La modifica dell'ordine delle colonne potrebbe influire su codice e applicazioni che dipendono da un ordine specifico,</span><span class="sxs-lookup"><span data-stu-id="6d412-104">Changing the column order of a table may affect code and applications that depend on the specific order of columns.</span></span> <span data-ttu-id="6d412-105">incluse query, viste, stored procedure, funzioni definite dall'utente e applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="6d412-105">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="6d412-106">è pertanto opportuno valutare attentamente ogni eventuale modifica da apportare all'ordine delle colonne prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="6d412-106">Carefully consider any changes you want to make to column order before making it.</span></span> <span data-ttu-id="6d412-107">La procedura consigliata è specificare l'ordine nel quale le colonne vengono restituite all'applicazione e il livello della query.</span><span class="sxs-lookup"><span data-stu-id="6d412-107">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="6d412-108">Non è necessario basarsi sull'utilizzo di SELECT \* per restituire tutte le colonne nell'ordine previsto basato sull'ordine nel quale sono definiti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="6d412-108">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="6d412-109">Nelle query e nelle applicazioni, specificare sempre le colonne per nome nell'ordine nel quale si desidera visualizzarle.</span><span class="sxs-lookup"><span data-stu-id="6d412-109">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
 <span data-ttu-id="6d412-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="6d412-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="6d412-111">**Per modificare l'ordine delle colonne:**</span><span class="sxs-lookup"><span data-stu-id="6d412-111">**To change the column order, using:**</span></span>  
  
     [<span data-ttu-id="6d412-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6d412-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="6d412-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d412-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="6d412-114">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="6d412-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-column-order"></a><span data-ttu-id="6d412-115">Per modificare l'ordine delle colonne</span><span class="sxs-lookup"><span data-stu-id="6d412-115">To change the column order</span></span>  
  
1.  <span data-ttu-id="6d412-116">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulle colonne da riordinare e selezionare **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="6d412-116">In **Object Explorer**, right-click the table with columns you want to reorder and click **Design**.</span></span>  
  
2.  <span data-ttu-id="6d412-117">Selezionare la casella a sinistra del nome della colonna che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="6d412-117">Select the box to the left of the column name that you want to reorder.</span></span>  
  
3.  <span data-ttu-id="6d412-118">Trascinare la colonna in una posizione diversa nella tabella.</span><span class="sxs-lookup"><span data-stu-id="6d412-118">Drag the column to another location within the table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="6d412-119">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d412-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="6d412-120">**Per modificare l'ordine delle colonne**</span><span class="sxs-lookup"><span data-stu-id="6d412-120">**To change the column order**</span></span>  
  
 <span data-ttu-id="6d412-121">Non è possibile eseguire questa attività utilizzando istruzioni Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="6d412-121">This task cannot be performed using Transact-SQL statements.</span></span>  
  
###  <a name="TsqlExample"></a>  
