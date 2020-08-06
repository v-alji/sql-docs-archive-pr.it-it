---
title: Eliminazione degli oggetti di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- deleting database objects
ms.assetid: dbb94fdf-c85b-477b-8e84-f830d259bade
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 6bd69935dbfac020c4c75bb391e7932009fd4197
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624503"
---
# <a name="deleting-database-objects"></a><span data-ttu-id="f9bd2-102">Eliminazione degli oggetti di database</span><span class="sxs-lookup"><span data-stu-id="f9bd2-102">Deleting Database Objects</span></span>
  <span data-ttu-id="f9bd2-103">Per rimuovere completamente tutte le tracce di questa esercitazione, è sufficiente eliminare il database.</span><span class="sxs-lookup"><span data-stu-id="f9bd2-103">To remove all traces of this tutorial, you could just delete the database.</span></span> <span data-ttu-id="f9bd2-104">In questo argomento verranno comunque illustrate le procedure per annullare ogni azione eseguita nell'ambito dell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="f9bd2-104">However, in this topic, you will go through the steps to reverse every action you took doing the tutorial.</span></span>  
  
### <a name="removing-permissions-and-objects"></a><span data-ttu-id="f9bd2-105">Rimozione di autorizzazioni e oggetti</span><span class="sxs-lookup"><span data-stu-id="f9bd2-105">Removing permissions and objects</span></span>  
  
1.  <span data-ttu-id="f9bd2-106">Prima di eliminare gli oggetti, verificare di trovarsi nel database corretto:</span><span class="sxs-lookup"><span data-stu-id="f9bd2-106">Before you delete objects, make sure you are in the correct database:</span></span>  
  
    ```  
    USE TestData;  
    GO  
    ```  
  
2.  <span data-ttu-id="f9bd2-107">Utilizzare l'istruzione `REVOKE` per rimuovere l'autorizzazione di esecuzione per `Mary` sulla stored procedure:</span><span class="sxs-lookup"><span data-stu-id="f9bd2-107">Use the `REVOKE` statement to remove execute permission for `Mary` on the stored procedure:</span></span>  
  
    ```  
    REVOKE EXECUTE ON pr_Names FROM Mary;  
    GO  
  
    ```  
  
3.  <span data-ttu-id="f9bd2-108">Utilizzare l'istruzione `DROP` per rimuovere l'autorizzazione di accesso per `Mary` al database `TestData` :</span><span class="sxs-lookup"><span data-stu-id="f9bd2-108">Use the `DROP` statement to remove permission for `Mary` to access the `TestData` database:</span></span>  
  
    ```  
    DROP USER Mary;  
    GO  
  
    ```  
  
4.  <span data-ttu-id="f9bd2-109">Utilizzare l'istruzione `DROP` per rimuovere l'autorizzazione di accesso per `Mary` all'istanza di [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f9bd2-109">Use the `DROP` statement to remove permission for `Mary` to access this instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]:</span></span>  
  
    ```  
    DROP LOGIN [<computer_name>\Mary];  
    GO  
  
    ```  
  
5.  <span data-ttu-id="f9bd2-110">Utilizzare l'istruzione `DROP` per rimuovere la stored procedure `pr_Names`:</span><span class="sxs-lookup"><span data-stu-id="f9bd2-110">Use the `DROP` statement to remove the store procedure `pr_Names`:</span></span>  
  
    ```  
    DROP PROC pr_Names;  
    GO  
  
    ```  
  
6.  <span data-ttu-id="f9bd2-111">Utilizzare l'istruzione `DROP` per rimuovere la vista `vw_Names`:</span><span class="sxs-lookup"><span data-stu-id="f9bd2-111">Use the `DROP` statement to remove the view `vw_Names`:</span></span>  
  
    ```  
    DROP View vw_Names;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="f9bd2-112">Utilizzare l'istruzione `DELETE` per rimuovere tutte le righe della tabella `Products` :</span><span class="sxs-lookup"><span data-stu-id="f9bd2-112">Use the `DELETE` statement to remove all rows from the `Products` table:</span></span>  
  
    ```  
    DELETE FROM Products;  
    GO  
  
    ```  
  
8.  <span data-ttu-id="f9bd2-113">Utilizzare l'istruzione `DROP` per rimuovere la tabella `Products` :</span><span class="sxs-lookup"><span data-stu-id="f9bd2-113">Use the `DROP` statement to remove the `Products` table:</span></span>  
  
    ```  
    DROP Table Products;  
    GO  
  
    ```  
  
9. <span data-ttu-id="f9bd2-114">Non è possibile rimuovere il database `TestData` se è in uso. Passare pertanto a un altro database e quindi utilizzare l'istruzione `DROP` per rimuovere il database `TestData` :</span><span class="sxs-lookup"><span data-stu-id="f9bd2-114">You cannot remove the `TestData` database while you are in the database; therefore, first switch context to another database, and then use the `DROP` statement to remove the `TestData` database:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    DROP DATABASE TestData;  
    GO  
  
    ```  
  
 <span data-ttu-id="f9bd2-115">In questo modo si conclude l'esercitazione per la scrittura di istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f9bd2-115">This concludes the Writing [!INCLUDE[tsql](../includes/tsql-md.md)] Statements tutorial.</span></span> <span data-ttu-id="f9bd2-116">Tenere presente che questa esercitazione rappresenta una breve panoramica in cui non vengono descritte tutte le opzioni delle istruzioni utilizzate.</span><span class="sxs-lookup"><span data-stu-id="f9bd2-116">Remember, this tutorial is a brief overview and it does not describe all the options to the statements that are used.</span></span> <span data-ttu-id="f9bd2-117">La progettazione e la creazione di una struttura di database efficiente e la configurazione dell'accesso sicuro ai dati richiede un database più complesso di quello illustrato in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="f9bd2-117">Designing and creating an efficient database structure and configuring secure access to the data requires a more complex database than that shown in this tutorial.</span></span>  
  
## <a name="return-to-sql-server-tools-portal"></a><span data-ttu-id="f9bd2-118">Torna al portale degli strumenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="f9bd2-118">Return to SQL Server Tools Portal</span></span>  
 [<span data-ttu-id="f9bd2-119">Esercitazione: Scrittura di istruzioni Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f9bd2-119">Tutorial: Writing Transact-SQL Statements</span></span>](tutorial-writing-transact-sql-statements.md)  
  
## <a name="see-also"></a><span data-ttu-id="f9bd2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9bd2-120">See Also</span></span>  
 <span data-ttu-id="f9bd2-121">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9bd2-121">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="f9bd2-122">[DROP USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9bd2-122">[DROP USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-user-transact-sql) </span></span>  
 <span data-ttu-id="f9bd2-123">[DROP LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9bd2-123">[DROP LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-login-transact-sql) </span></span>  
 <span data-ttu-id="f9bd2-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9bd2-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="f9bd2-125">[DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9bd2-125">[DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql) </span></span>  
 <span data-ttu-id="f9bd2-126">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9bd2-126">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="f9bd2-127">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f9bd2-127">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 [<span data-ttu-id="f9bd2-128">DROP DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f9bd2-128">DROP DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-database-audit-specification-transact-sql)  
  
  
