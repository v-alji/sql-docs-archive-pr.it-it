---
title: Eliminare relazioni di chiave esterna | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], deleting
- removing foreign keys
- deleting foreign keys
ms.assetid: 9c9e9ae4-9e03-4137-acb6-b18928a0c4ca
author: stevestein
ms.author: sstein
ms.openlocfilehash: 86ae466b9fce53073bfc0645c753246023ff3269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628580"
---
# <a name="delete-foreign-key-relationships"></a><span data-ttu-id="f0fd4-102">Eliminazione di relazioni di chiave esterna</span><span class="sxs-lookup"><span data-stu-id="f0fd4-102">Delete Foreign Key Relationships</span></span>
  <span data-ttu-id="f0fd4-103">È possibile eliminare un vincolo di chiave esterna in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0fd4-103">You can delete a foreign key constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f0fd4-104">L'eliminazione di un vincolo di chiave esterna comporta la rimozione del requisito di attivazione dell'integrità referenziale.</span><span class="sxs-lookup"><span data-stu-id="f0fd4-104">Deleting a foreign key constraint removes the requirement to enforce referential integrity.</span></span>  
  
 <span data-ttu-id="f0fd4-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="f0fd4-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f0fd4-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="f0fd4-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f0fd4-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f0fd4-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f0fd4-108">**Per eliminare un vincolo di chiave esterna utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="f0fd4-108">**To delete a foreign key constraint, using:**</span></span>  
  
     [<span data-ttu-id="f0fd4-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0fd4-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f0fd4-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0fd4-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f0fd4-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="f0fd4-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f0fd4-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f0fd4-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f0fd4-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="f0fd4-113">Permissions</span></span>  
 <span data-ttu-id="f0fd4-114">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="f0fd4-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f0fd4-115">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0fd4-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="f0fd4-116">Per eliminare un vincolo di chiave esterna</span><span class="sxs-lookup"><span data-stu-id="f0fd4-116">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="f0fd4-117">In **Esplora oggetti**espandere la tabella contenente il vincolo, quindi espandere **Chiavi**.</span><span class="sxs-lookup"><span data-stu-id="f0fd4-117">In **Object Explorer**, expand the table with the constraint and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="f0fd4-118">Fare clic con il pulsante destro del mouse sul vincolo e selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="f0fd4-118">Right-click the constraint and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="f0fd4-119">Nella finestra di dialogo **Elimina oggetto** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0fd4-119">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f0fd4-120">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f0fd4-120">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="f0fd4-121">Per eliminare un vincolo di chiave esterna</span><span class="sxs-lookup"><span data-stu-id="f0fd4-121">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="f0fd4-122">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0fd4-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f0fd4-123">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="f0fd4-123">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f0fd4-124">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f0fd4-124">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.DocExe   
    DROP CONSTRAINT FK_Column_B;   
    GO  
    ```  
  
 <span data-ttu-id="f0fd4-125">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f0fd4-125">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
