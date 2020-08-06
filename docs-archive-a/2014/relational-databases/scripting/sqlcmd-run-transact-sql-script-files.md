---
title: Esecuzione di file script Transact-SQL mediante sqlcmd
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- transact sql scripts
ms.assetid: 90067eb8-ca3e-44e8-bb1a-bf7d1a359423
author: rothja
ms.author: jroth
ms.openlocfilehash: cd34b089fc4e971cac9e5713cbe303192a7a48c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625292"
---
# <a name="run-transact-sql-script-files-using-sqlcmd"></a><span data-ttu-id="0f9e2-102">Esecuzione di file script Transact-SQL mediante sqlcmd</span><span class="sxs-lookup"><span data-stu-id="0f9e2-102">Run Transact-SQL Script Files Using sqlcmd</span></span>
  <span data-ttu-id="0f9e2-103">È possibile utilizzare `sqlcmd` per eseguire un file script [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f9e2-103">You can use `sqlcmd` to run a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="0f9e2-104">Un file script [!INCLUDE[tsql](../../includes/tsql-md.md)] è un file di testo che può contenere una combinazione di istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)], comandi di `sqlcmd` e variabili di scripting.</span><span class="sxs-lookup"><span data-stu-id="0f9e2-104">A [!INCLUDE[tsql](../../includes/tsql-md.md)] script file is a text file that can contain a combination of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, `sqlcmd` commands, and scripting variables.</span></span>  
  
 <span data-ttu-id="0f9e2-105">Per creare un file script [!INCLUDE[tsql](../../includes/tsql-md.md)] semplice in Blocco note, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="0f9e2-105">To create a simple [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using Notepad, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0f9e2-106">Fare clic su **Start**, scegliere **Tutti i programmi**, **Accessori**e quindi fare clic su **Blocco note**.</span><span class="sxs-lookup"><span data-stu-id="0f9e2-106">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Notepad**.</span></span>  
  
2.  <span data-ttu-id="0f9e2-107">Copiare e incollare il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente in Blocco note:</span><span class="sxs-lookup"><span data-stu-id="0f9e2-107">Copy and paste the following [!INCLUDE[tsql](../../includes/tsql-md.md)] code into Notepad:</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT p.FirstName + ' ' + p.LastName AS 'Employee Name',  
    a.AddressLine1, a.AddressLine2 , a.City, a.PostalCode   
    FROM Person.Person AS p   
       INNER JOIN HumanResources.Employee AS e   
            ON p.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.BusinessEntityAddress bea   
            ON bea.BusinessEntityID = e.BusinessEntityID  
        INNER JOIN Person.Address AS a   
            ON a.AddressID = bea.AddressID;  
    GO  
    ```  
  
3.  <span data-ttu-id="0f9e2-108">Salvare il file con il nome **myScript.sql** nell'unità C.</span><span class="sxs-lookup"><span data-stu-id="0f9e2-108">Save the file as **myScript.sql** in the C drive.</span></span>  
  
### <a name="to-run-the-script-file"></a><span data-ttu-id="0f9e2-109">Per eseguire il file script</span><span class="sxs-lookup"><span data-stu-id="0f9e2-109">To run the script file</span></span>  
  
1.  <span data-ttu-id="0f9e2-110">Aprire una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="0f9e2-110">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="0f9e2-111">Nella finestra del prompt dei comandi digitare: `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span><span class="sxs-lookup"><span data-stu-id="0f9e2-111">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql`</span></span>  
  
3.  <span data-ttu-id="0f9e2-112">Premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0f9e2-112">Press ENTER.</span></span>  
  
 <span data-ttu-id="0f9e2-113">Nella finestra del prompt dei comandi verrà visualizzato un elenco di nomi e indirizzi di dipendenti di [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0f9e2-113">A list of [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] employee names and addresses is written to the command prompt window.</span></span>  
  
### <a name="to-save-this-output-to-a-text-file"></a><span data-ttu-id="0f9e2-114">Per salvare l'output in un file di testo</span><span class="sxs-lookup"><span data-stu-id="0f9e2-114">To save this output to a text file</span></span>  
  
1.  <span data-ttu-id="0f9e2-115">Aprire una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="0f9e2-115">Open a command prompt window.</span></span>  
  
2.  <span data-ttu-id="0f9e2-116">Nella finestra del prompt dei comandi digitare: `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span><span class="sxs-lookup"><span data-stu-id="0f9e2-116">In the Command Prompt window, type: `sqlcmd -S myServer\instanceName -i C:\myScript.sql -o C:\EmpAdds.txt`</span></span>  
  
3.  <span data-ttu-id="0f9e2-117">Premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0f9e2-117">Press ENTER.</span></span>  
  
 <span data-ttu-id="0f9e2-118">Nella finestra del prompt dei comandi non verrà restituito alcun output.</span><span class="sxs-lookup"><span data-stu-id="0f9e2-118">No output is returned in the Command Prompt window.</span></span> <span data-ttu-id="0f9e2-119">L'output verrà invece inviato al file EmpAdds.txt.</span><span class="sxs-lookup"><span data-stu-id="0f9e2-119">Instead, the output is sent to the EmpAdds.txt file.</span></span> <span data-ttu-id="0f9e2-120">È possibile verificare l'output aprendo il file EmpAdds.txt.</span><span class="sxs-lookup"><span data-stu-id="0f9e2-120">You can verify this output by opening the EmpAdds.txt file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f9e2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f9e2-121">See Also</span></span>  
 <span data-ttu-id="0f9e2-122">[Avvio dell'utilità sqlcmd](sqlcmd-start-the-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0f9e2-122">[Start the sqlcmd Utility](sqlcmd-start-the-utility.md) </span></span>  
 [<span data-ttu-id="0f9e2-123">Utilità sqlcmd</span><span class="sxs-lookup"><span data-stu-id="0f9e2-123">sqlcmd Utility</span></span>](../../tools/sqlcmd-utility.md)  
  
  
