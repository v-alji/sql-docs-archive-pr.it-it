---
title: Modificare una stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying stored procedures
- editing stored procedures
- stored procedures [SQL Server], modifying
ms.assetid: 13396239-6100-48ce-aa34-461358d99c92
author: stevestein
ms.author: sstein
ms.openlocfilehash: 906f0e06650da505094d18774ce86dab53d53f38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711807"
---
# <a name="modify-a-stored-procedure"></a><span data-ttu-id="964bf-102">Modificare una stored procedure</span><span class="sxs-lookup"><span data-stu-id="964bf-102">Modify a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-modify-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="964bf-103">In questo argomento viene descritto come modificare una stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="964bf-103">This topic describes how to modify a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="964bf-104">**Prima di iniziare:**  [Limitazioni e restrizioni](#Restrictions), [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="964bf-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="964bf-105">**Per modificare una stored procedure usando:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="964bf-105">**To alter a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="964bf-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="964bf-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="964bf-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="964bf-107">Limitations and Restrictions</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="964bf-108">in stored procedure CLR e viceversa.</span><span class="sxs-lookup"><span data-stu-id="964bf-108">stored procedures cannot be modified to be CLR stored procedures and vice versa.</span></span>  
  
 <span data-ttu-id="964bf-109">Se la definizione di stored procedure precedente è stata creata tramite l'opzione WITH ENCRYPTION o WITH RECOMPILE, tali opzioni sono abilitate solo se incluse nell'istruzione ALTER PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="964bf-109">If the previous procedure definition was created using WITH ENCRYPTION or WITH RECOMPILE, these options are enabled only if they are included in the ALTER PROCEDURE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="964bf-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="964bf-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="964bf-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="964bf-111">Permissions</span></span>  
 <span data-ttu-id="964bf-112">È richiesta l'autorizzazione ALTER PROCEDURE per la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="964bf-112">Requires ALTER PROCEDURE permission on the procedure.</span></span>  
  
##  <a name="how-to-modify-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="964bf-113">Modalità di modifica di una stored procedure</span><span class="sxs-lookup"><span data-stu-id="964bf-113">How to Modify a Stored Procedure</span></span>  
 <span data-ttu-id="964bf-114">È possibile usare uno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="964bf-114">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="964bf-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="964bf-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="964bf-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="964bf-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="964bf-117">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="964bf-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="964bf-118">**Per modificare una stored procedure in Management Studio**</span><span class="sxs-lookup"><span data-stu-id="964bf-118">**To modify a procedure in Management Studio**</span></span>  
  
1.  <span data-ttu-id="964bf-119">In Esplora oggetti connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="964bf-119">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="964bf-120">Espandere **Database**, espandere il database a cui appartiene la stored procedure, quindi espandere **Programmabilità**.</span><span class="sxs-lookup"><span data-stu-id="964bf-120">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="964bf-121">Espandere **Stored procedure**, fare clic con il pulsante destro del mouse sulla stored procedure da modificare, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="964bf-121">Expand **Stored Procedures**, right-click the procedure to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="964bf-122">Modificare il testo della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="964bf-122">Modify the text of the stored procedure.</span></span>  
  
5.  <span data-ttu-id="964bf-123">Per controllare la sintassi, scegliere **Analizza** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="964bf-123">To test the syntax, on the **Query** menu, click **Parse**.</span></span>  
  
6.  <span data-ttu-id="964bf-124">Per salvare le modifiche alla definizione della stored procedure, scegliere **Esegui** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="964bf-124">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
7.  <span data-ttu-id="964bf-125">Per salvare la definizione della stored procedure aggiornata come script [!INCLUDE[tsql](../../includes/tsql-md.md)] , scegliere **Salva con nome** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="964bf-125">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="964bf-126">Accettare il nome del file o sostituirlo con uno nuovo, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="964bf-126">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="964bf-127">Convalidare sempre input di tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="964bf-127">Validate all user input.</span></span> <span data-ttu-id="964bf-128">Non concatenare l'input dell'utente prima di averlo convalidato.</span><span class="sxs-lookup"><span data-stu-id="964bf-128">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="964bf-129">Non eseguire mai un comando creato dall'input dell'utente non convalidato.</span><span class="sxs-lookup"><span data-stu-id="964bf-129">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="964bf-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="964bf-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="964bf-131">**Per modificare una stored procedure nell'editor di query**</span><span class="sxs-lookup"><span data-stu-id="964bf-131">**To modify a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="964bf-132">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] , quindi espanderla.</span><span class="sxs-lookup"><span data-stu-id="964bf-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="964bf-133">Espandere **Database**ed espandere il database a cui appartiene la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="964bf-133">Expand **Databases**, expand the database in which the procedure belongs.</span></span> <span data-ttu-id="964bf-134">In alternativa, selezionare il database nell'elenco dei database disponibili sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="964bf-134">Or, from the tool bar, select the database from the list of available databases.</span></span> <span data-ttu-id="964bf-135">Per questo esempio, selezionare il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="964bf-135">For this example, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
3.  <span data-ttu-id="964bf-136">Scegliere **Nuova query** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="964bf-136">On the **File** menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="964bf-137">Copiare e incollare l'esempio seguente nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="964bf-137">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="964bf-138">Nell'esempio viene creata la stored procedure `uspVendorAllInfo` mediante la quale vengono restituiti i nomi di tutti i fornitori nel database [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , i prodotti da essi forniti, nonché le informazioni relative alla posizione creditizia e alla disponibilità.</span><span class="sxs-lookup"><span data-stu-id="964bf-138">The example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
    ```  
  
    IF OBJECT_ID ( 'Purchasing.uspVendorAllInfo', 'P' ) IS NOT NULL   
        DROP PROCEDURE Purchasing.uspVendorAllInfo;  
    GO  
    CREATE PROCEDURE Purchasing.uspVendorAllInfo  
    WITH EXECUTE AS CALLER  
    AS  
        SET NOCOUNT ON;  
        SELECT v.Name AS Vendor, p.Name AS 'Product name',   
          v.CreditRating AS 'Rating',   
          v.ActiveFlag AS Availability  
        FROM Purchasing.Vendor v   
        INNER JOIN Purchasing.ProductVendor pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product p  
          ON pv.ProductID = p.ProductID   
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
5.  <span data-ttu-id="964bf-139">Scegliere **Nuova query** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="964bf-139">On the **File** menu, click **New Query**.</span></span>  
  
6.  <span data-ttu-id="964bf-140">Copiare e incollare l'esempio seguente nell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="964bf-140">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="964bf-141">Nell'esempio viene modificata la stored procedure `uspVendorAllInfo` .</span><span class="sxs-lookup"><span data-stu-id="964bf-141">The example modifies the `uspVendorAllInfo` procedure.</span></span> <span data-ttu-id="964bf-142">La clausola EXECUTE AS CALLER viene rimossa e il corpo della stored procedure viene modificato in modo da restituire solo i fornitori del prodotto specificato.</span><span class="sxs-lookup"><span data-stu-id="964bf-142">The EXECUTE AS CALLER clause is removed and the body of the procedure is modified to return only those vendors that supply the specified product.</span></span> <span data-ttu-id="964bf-143">Le funzioni `LEFT` e `CASE` personalizzano l'aspetto del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="964bf-143">The `LEFT` and `CASE` functions customize the appearance of the result set.</span></span>  
  
    ```  
    ALTER PROCEDURE Purchasing.uspVendorAllInfo  
        @Product varchar(25)   
    AS  
        SET NOCOUNT ON;  
        SELECT LEFT(v.Name, 25) AS Vendor, LEFT(p.Name, 25) AS 'Product name',   
        'Rating' = CASE v.CreditRating   
            WHEN 1 THEN 'Superior'  
            WHEN 2 THEN 'Excellent'  
            WHEN 3 THEN 'Above average'  
            WHEN 4 THEN 'Average'  
            WHEN 5 THEN 'Below average'  
            ELSE 'No rating'  
            END  
        , Availability = CASE v.ActiveFlag  
            WHEN 1 THEN 'Yes'  
            ELSE 'No'  
            END  
        FROM Purchasing.Vendor AS v   
        INNER JOIN Purchasing.ProductVendor AS pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product AS p   
          ON pv.ProductID = p.ProductID   
        WHERE p.Name LIKE @Product  
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="964bf-144">Per salvare le modifiche alla definizione della stored procedure, scegliere **Esegui** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="964bf-144">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
8.  <span data-ttu-id="964bf-145">Per salvare la definizione della stored procedure aggiornata come script [!INCLUDE[tsql](../../includes/tsql-md.md)] , scegliere **Salva con nome** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="964bf-145">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="964bf-146">Accettare il nome del file o sostituirlo con uno nuovo, quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="964bf-146">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="964bf-147">Per eseguire la stored procedure modificata, eseguire l'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="964bf-147">To run the modified stored procedure, execute the following example.</span></span>  
  
    ```  
    EXEC Purchasing.uspVendorAllInfo N'LL Crankarm';  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="964bf-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="964bf-148">See Also</span></span>  
 [<span data-ttu-id="964bf-149">ALTER PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="964bf-149">ALTER PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)  
  
  
