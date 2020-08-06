---
title: Eliminare una stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- removing stored procedures
- stored procedures [SQL Server], deleting
- deleting stored procedures
ms.assetid: 232dbf4d-392a-406f-af3a-579518cd8e46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 418e68d4bb7c6ba6632767a554aea72e85726840
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636609"
---
# <a name="delete-a-stored-procedure"></a><span data-ttu-id="08be2-102">Eliminare una stored procedure</span><span class="sxs-lookup"><span data-stu-id="08be2-102">Delete a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-delete-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="08be2-103">In questo argomento viene descritto come eliminare una stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08be2-103">This topic describes how to delete a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="08be2-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#Restrictions), [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="08be2-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="08be2-105">**Per eliminare una stored procedure usando:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="08be2-105">**To delete a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="08be2-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="08be2-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="08be2-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="08be2-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="08be2-108">L'eliminazione di una stored procedure può causare errori negli oggetti e script dipendenti quando questi non vengono aggiornati per riflettere la rimozione della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="08be2-108">Deleting a procedure can cause dependent objects and scripts to fail when the objects and scripts are not updated to reflect the removal of the procedure.</span></span> <span data-ttu-id="08be2-109">Tuttavia, se si crea una nuova stored procedure con lo stesso nome e gli stessi parametri per sostituire quella eliminata, gli altri oggetti che fanno riferimento ancora alla stored procedure verranno elaborati correttamente.</span><span class="sxs-lookup"><span data-stu-id="08be2-109">However, if a new procedure of the same name and the same parameters is created to replace the one that was deleted, other objects that reference it will still process successfully.</span></span> <span data-ttu-id="08be2-110">Per altre informazioni, vedere [Visualizzare le dipendenze di una stored procedure](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="08be2-110">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="08be2-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="08be2-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="08be2-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="08be2-112">Permissions</span></span>  
 <span data-ttu-id="08be2-113">È richiesta l'autorizzazione ALTER per lo schema a cui appartiene la stored procedure oppure l'autorizzazione CONTROL per la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="08be2-113">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span>  
  
##  <a name="how-to-delete-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="08be2-114">Modalità di eliminazione di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="08be2-114">How to Delete a Stored Procedure</span></span>  
 <span data-ttu-id="08be2-115">È possibile usare uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="08be2-115">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="08be2-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="08be2-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="08be2-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="08be2-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="08be2-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="08be2-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="08be2-119">**Per eliminare una stored procedure in Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="08be2-119">**To delete a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="08be2-120">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="08be2-120">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="08be2-121">Espandere **Database**, espandere il database a cui appartiene la stored procedure, quindi espandere **Programmabilità**.</span><span class="sxs-lookup"><span data-stu-id="08be2-121">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="08be2-122">Espandere **Stored procedure**, fare clic con il pulsante destro del mouse sulla stored procedure da rimuovere e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="08be2-122">Expand **Stored Procedures**, right-click the procedure to remove, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="08be2-123">Per visualizzare gli oggetti dipendenti dalla stored procedure, fare clic su **Mostra dipendenze**.</span><span class="sxs-lookup"><span data-stu-id="08be2-123">To view objects that depend on the procedure, click **Show Dependencies**.</span></span>  
  
5.  <span data-ttu-id="08be2-124">Confermare che è stata selezionata la stored procedure corretta, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="08be2-124">Confirm the correct procedure is selected, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="08be2-125">Rimuovere i riferimenti alla stored procedure da tutti gli oggetti e script dipendenti.</span><span class="sxs-lookup"><span data-stu-id="08be2-125">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="08be2-126">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="08be2-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="08be2-127">**Per eliminare una stored procedure nell'editor di query**</span><span class="sxs-lookup"><span data-stu-id="08be2-127">**To delete a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="08be2-128">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="08be2-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="08be2-129">Espandere **Database**ed espandere il database a cui appartiene la stored procedure. In alternativa, dalla barra degli strumenti selezionare il database dall'elenco di database disponibili.</span><span class="sxs-lookup"><span data-stu-id="08be2-129">Expand **Databases**, expand the database in which the procedure belongs, or, from the tool bar, select the database from the list of available databases.</span></span>  
  
3.  <span data-ttu-id="08be2-130">Scegliere **Nuova query**dal menu File.</span><span class="sxs-lookup"><span data-stu-id="08be2-130">On the File menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="08be2-131">Ottenere il nome della stored procedure da rimuovere nel database corrente.</span><span class="sxs-lookup"><span data-stu-id="08be2-131">Obtain the name of stored procedure to remove in the current database.</span></span> <span data-ttu-id="08be2-132">Da Esplora oggetti espandere **Programmabilità** , quindi espandere **Stored procedure**.</span><span class="sxs-lookup"><span data-stu-id="08be2-132">From Object Explorer, expand **Programmability** and then expand **Stored Procedures**.</span></span> <span data-ttu-id="08be2-133">In alternativa, nell'editor di query eseguire l'istruzione riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="08be2-133">Alternatively, in the query editor, run the following statement.</span></span>  
  
    ```sql  
    SELECT name AS procedure_name   
        ,SCHEMA_NAME(schema_id) AS schema_name  
        ,type_desc  
        ,create_date  
        ,modify_date  
    FROM sys.procedures;  
    ```  
  
5.  <span data-ttu-id="08be2-134">Copiare e incollare l'esempio seguente nell'editor di query e inserire il nome di una stored procedure da eliminare dal database corrente.</span><span class="sxs-lookup"><span data-stu-id="08be2-134">Copy and paste the following example into the query editor and insert a stored procedure name to delete from the current database.</span></span>  
  
    ```sql  
    DROP PROCEDURE <stored procedure name>;  
    GO  
    ```  
  
6.  <span data-ttu-id="08be2-135">Rimuovere i riferimenti alla stored procedure da tutti gli oggetti e script dipendenti.</span><span class="sxs-lookup"><span data-stu-id="08be2-135">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08be2-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08be2-136">See Also</span></span>  
 <span data-ttu-id="08be2-137">[Creazione di una stored procedure](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="08be2-137">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="08be2-138">[Modificare una stored procedure](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="08be2-138">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="08be2-139">[Rinominare una stored procedure](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="08be2-139">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="08be2-140">[Visualizzare la definizione di una stored procedure](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="08be2-140">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="08be2-141">[Visualizzare le dipendenze di una stored procedure](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="08be2-141">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="08be2-142">DROP PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="08be2-142">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
