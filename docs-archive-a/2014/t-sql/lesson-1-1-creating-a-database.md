---
title: Creazione di un database (esercitazione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorial creating a database
ms.assetid: e1e2c83f-dfad-4bb8-aa7a-09d3f69517ae
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 99d5439c289b5d4e71786d4c6734f158f6bba371
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630188"
---
# <a name="creating-a-database-tutorial"></a><span data-ttu-id="e4ea4-102">Esercitazione per la creazione di un database</span><span class="sxs-lookup"><span data-stu-id="e4ea4-102">Creating a Database (Tutorial)</span></span>
  <span data-ttu-id="e4ea4-103">Analogamente a numerose altre istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] , l'istruzione CREATE DATABASE ha un parametro obbligatorio, ovvero il nome del database.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-103">Like many [!INCLUDE[tsql](../includes/tsql-md.md)] statements, the CREATE DATABASE statement has a required parameter: the name of the database.</span></span> <span data-ttu-id="e4ea4-104">L'istruzione CREATE DATABASE dispone inoltre di numerosi parametri facoltativi, ad esempio il percorso su disco in cui si desidera inserire i file del database.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-104">CREATE DATABASE also has many optional parameters, such as the disk location where you want to put the database files.</span></span> <span data-ttu-id="e4ea4-105">Quando si esegue CREATE DATABASE senza parametri facoltativi, in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] vengono utilizzati i valori predefiniti per molti di tali parametri.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-105">When you execute CREATE DATABASE without the optional parameters, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses default values for many of these parameters.</span></span> <span data-ttu-id="e4ea4-106">In questa esercitazione vengono utilizzati solo alcuni dei parametri facoltativi della sintassi.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-106">This tutorial uses very few of the optional syntax parameters.</span></span>  
  
### <a name="to-create-a-database"></a><span data-ttu-id="e4ea4-107">Per creare un database</span><span class="sxs-lookup"><span data-stu-id="e4ea4-107">To create a database</span></span>  
  
1.  <span data-ttu-id="e4ea4-108">In una finestra dell'editor di query digitare ma non eseguire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e4ea4-108">In a Query Editor window, type but do not execute the following code:</span></span>  
  
    ```  
    CREATE DATABASE TestData  
    GO  
    ```  
  
2.  <span data-ttu-id="e4ea4-109">Usare il puntatore per selezionare le parole `CREATE DATABASE`e quindi premere **F1**.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-109">Use the pointer to select the words `CREATE DATABASE`, and then press **F1**.</span></span> <span data-ttu-id="e4ea4-110">Verrà aperto l'argomento relativo all'istruzione CREATE DATABASE della documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-110">The CREATE DATABASE topic in SQL Server Books Online should open.</span></span> <span data-ttu-id="e4ea4-111">È possibile utilizzare questa tecnica per trovare la sintassi completa di CREATE DATABASE e delle altre istruzioni utilizzate in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-111">You can use this technique to find the complete syntax for CREATE DATABASE and for the other statements that are used in this tutorial.</span></span>  
  
3.  <span data-ttu-id="e4ea4-112">Nell'editor di query premere **F5** per eseguire l'istruzione e creare un database denominato `TestData`.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-112">In Query Editor, press **F5** to execute the statement and create a database named `TestData`.</span></span>  
  
 <span data-ttu-id="e4ea4-113">Quando si crea un database, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] esegue una copia del database **model** e le assegna il nome del database specificato.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-113">When you create a database, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] makes a copy of the **model** database, and renames the copy to the database name.</span></span> <span data-ttu-id="e4ea4-114">L'operazione dovrebbe richiedere solo alcuni secondi a meno che non si specifichi una dimensione iniziale per il database particolarmente grande come parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-114">This operation should only take several seconds, unless you specify a large initial size of the database as an optional parameter.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4ea4-115">La parola chiave GO separa le istruzioni inviate in un singolo batch.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-115">The keyword GO separates statements when more than one statement is submitted in a single batch.</span></span> <span data-ttu-id="e4ea4-116">GO è un elemento facoltativo se il batch contiene un'unica istruzione.</span><span class="sxs-lookup"><span data-stu-id="e4ea4-116">GO is optional when the batch contains only one statement.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e4ea4-117">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="e4ea4-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e4ea4-118">Esercitazione per la creazione di una tabella</span><span class="sxs-lookup"><span data-stu-id="e4ea4-118">Creating a Table &#40;Tutorial&#41;</span></span>](lesson-1-2-creating-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="e4ea4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4ea4-119">See Also</span></span>  
 [<span data-ttu-id="e4ea4-120">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e4ea4-120">CREATE DATABASE &#40;SQL Server Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-sql-server-transact-sql)  
  
  
