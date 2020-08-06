---
title: MSSQLSERVER_107 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 107 (Database Engine error)
ms.assetid: f33f514c-56aa-42e2-841b-e91244da90e2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b9388bbda6f00b1aafd02caee1b6a7b8387564f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635655"
---
# <a name="mssqlserver_107"></a><span data-ttu-id="8f823-102">MSSQLSERVER_107</span><span class="sxs-lookup"><span data-stu-id="8f823-102">MSSQLSERVER_107</span></span>
    
## <a name="details"></a><span data-ttu-id="8f823-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8f823-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f823-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="8f823-104">Product Name</span></span>|<span data-ttu-id="8f823-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8f823-105">SQL Server</span></span>|  
|<span data-ttu-id="8f823-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="8f823-106">Event ID</span></span>|<span data-ttu-id="8f823-107">107</span><span class="sxs-lookup"><span data-stu-id="8f823-107">107</span></span>|  
|<span data-ttu-id="8f823-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="8f823-108">Event Source</span></span>|<span data-ttu-id="8f823-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8f823-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8f823-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8f823-110">Component</span></span>|<span data-ttu-id="8f823-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8f823-111">SQLEngine</span></span>|  
|<span data-ttu-id="8f823-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="8f823-112">Symbolic Name</span></span>|<span data-ttu-id="8f823-113">P_NOCORRMATCH</span><span class="sxs-lookup"><span data-stu-id="8f823-113">P_NOCORRMATCH</span></span>|  
|<span data-ttu-id="8f823-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="8f823-114">Message Text</span></span>|<span data-ttu-id="8f823-115">Il prefisso di colonna '%.\* ls' non corrisponde a un alias o nome di tabella utilizzato nella query.</span><span class="sxs-lookup"><span data-stu-id="8f823-115">The column prefix '%.\*ls' does not match with a table name or alias name used in the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8f823-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8f823-116">Explanation</span></span>  
 <span data-ttu-id="8f823-117">L'elenco di selezione della query contiene un asterisco (\*) qualificato erroneamente con un prefisso della colonna.</span><span class="sxs-lookup"><span data-stu-id="8f823-117">The select list of the query contains an asterisk (\*) that is incorrectly qualified with a column prefix.</span></span> <span data-ttu-id="8f823-118">Questo errore può essere restituito nelle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f823-118">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="8f823-119">Il prefisso di colonna non corrisponde ad alcun alias o nome di tabella utilizzato nella query.</span><span class="sxs-lookup"><span data-stu-id="8f823-119">The column prefix does not correspond to any table or alias name used in the query.</span></span> <span data-ttu-id="8f823-120">Nell'istruzione seguente viene utilizzato ad esempio un nome di alias (`T1`) come prefisso di colonna, ma l'alias non è definito nella clausola FROM.</span><span class="sxs-lookup"><span data-stu-id="8f823-120">For example, the following statement uses an alias name (`T1`) as a column prefix, but the alias is not defined in the FROM clause.</span></span>  
  
    ```  
    SELECT T1.* FROM dbo.ErrorLog;  
    ```  
  
-   <span data-ttu-id="8f823-121">Un nome di tabella viene specificato come un prefisso di colonna quando nella clausola FROM viene specificato un alias per la tabella.</span><span class="sxs-lookup"><span data-stu-id="8f823-121">A table name is specified as a column prefix when an alias name for the table is supplied in the FROM clause.</span></span> <span data-ttu-id="8f823-122">Nell'istruzione seguente, ad esempio, viene utilizzato il nome di tabella `ErrorLog`, ma per la tabella è stato specificato l'alias `T1` nella clausola FROM.</span><span class="sxs-lookup"><span data-stu-id="8f823-122">For example, the following statement uses the table name `ErrorLog` as the column prefix; however, the table has an alias (`T1`) defined in the FROM clause.</span></span>  
  
    ```  
    SELECT ErrorLog.* FROM dbo.ErrorLog AS T1;  
    ```  
  
     <span data-ttu-id="8f823-123">Se nella clausola FROM è stato specificato un alias per il nome di tabella, è possibile utilizzare solo tale alias come prefisso per le colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="8f823-123">If an alias has been provided for a table name in the FROM clause, you can only use the alias to prefix columns from the table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8f823-124">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="8f823-124">User Action</span></span>  
 <span data-ttu-id="8f823-125">Mettere in corrispondenza i prefissi di colonna con in nomi di tabella o gli alias specificati nella clausola FROM della query.</span><span class="sxs-lookup"><span data-stu-id="8f823-125">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="8f823-126">L'istruzione precedente, ad esempio, può essere corretta nel modo indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8f823-126">For example, the statements above can be corrected as follows:</span></span>  
  
```  
SELECT T1.* FROM dbo.ErrorLog AS T1;  
```  
  
 <span data-ttu-id="8f823-127">o</span><span class="sxs-lookup"><span data-stu-id="8f823-127">or</span></span>  
  
```  
SELECT ErrorLog.* FROM dbo.ErrorLog;  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f823-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f823-128">See Also</span></span>  
 [<span data-ttu-id="8f823-129">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="8f823-129">MSSQLSERVER_4104</span></span>](mssqlserver-4104-database-engine-error.md)  
  
  
