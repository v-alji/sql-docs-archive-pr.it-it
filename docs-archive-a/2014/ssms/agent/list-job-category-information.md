---
title: Elencare le informazioni sulle categorie di processi | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 0fc668d4-6244-4fef-b90e-62d2c776cd7c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 924e2b064980b2ea7068230610414262995da1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720808"
---
# <a name="list-job-category-information"></a><span data-ttu-id="023c4-102">Elencare le informazioni sulle categorie di processi</span><span class="sxs-lookup"><span data-stu-id="023c4-102">List Job Category Information</span></span>
  <span data-ttu-id="023c4-103">Come elencare le informazioni sulle categorie [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] di processi in tramite [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects.</span><span class="sxs-lookup"><span data-stu-id="023c4-103">How to list job category information in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)] or SQL Server Management Objects.</span></span>  

  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="023c4-104">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="023c4-104">Security</span></span>  
 <span data-ttu-id="023c4-105">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="023c4-105">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  

  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="023c4-106">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="023c4-106">Using Transact-SQL</span></span>  
  
#### <a name="to-list-job-category-information"></a><span data-ttu-id="023c4-107">Per elencare le informazioni sulle categorie di processi</span><span class="sxs-lookup"><span data-stu-id="023c4-107">To list job category information</span></span>  
  
1.  <span data-ttu-id="023c4-108">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="023c4-108">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="023c4-109">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="023c4-109">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="023c4-110">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="023c4-110">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- returns information about jobs that are administered locally  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_help_category  
        @type = N'LOCAL' ;  
    GO  
    ```  
  
 <span data-ttu-id="023c4-111">Per ulteriori informazioni, vedere [sp_help_category &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="023c4-111">For more information, see [sp_help_category &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-category-transact-sql).</span></span>  
  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="023c4-112">Utilizzo di SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="023c4-112">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="023c4-113">**Per elencare le informazioni sulle categorie di processi**</span><span class="sxs-lookup"><span data-stu-id="023c4-113">**To list job category information**</span></span>  
  
 <span data-ttu-id="023c4-114">Usare la classe `JobCategory` tramite il linguaggio di programmazione desiderato, ad esempio Visual Basic, Visual C# o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="023c4-114">Use the `JobCategory` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell..</span></span> <span data-ttu-id="023c4-115">Per ulteriori informazioni, vedere [SQL Server Management Objects &#40;SMO&#41; Programming Guide](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span><span class="sxs-lookup"><span data-stu-id="023c4-115">For more information, see [SQL Server Management Objects &#40;SMO&#41; Programming Guide](../../relational-databases/server-management-objects-smo/sql-server-management-objects-smo-programming-guide.md).</span></span>  
