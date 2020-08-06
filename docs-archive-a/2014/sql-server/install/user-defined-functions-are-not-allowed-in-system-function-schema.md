---
title: Le funzioni definite dall'utente non sono consentite nelle system_function_schema | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- system functions [SQL Server]
- user-defined functions [SQL Server], system
ms.assetid: 3cb54053-ef65-4558-ae96-8686b6b22f4f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7242f9fda74288a2b7354ac0550ff4966e05c555
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726440"
---
# <a name="user-defined-functions-are-not-allowed-in-system_function_schema"></a><span data-ttu-id="2b05a-102">In system_function_schema non sono consentite funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="2b05a-102">User-defined functions are not allowed in system_function_schema</span></span>
  <span data-ttu-id="2b05a-103">Sono state rilevate funzioni definite dall'utente di proprietà dell'utente non documentato **system_function_schema**.</span><span class="sxs-lookup"><span data-stu-id="2b05a-103">The Upgrade Advisor detected user-defined functions that are owned by the undocumented user **system_function_schema**.</span></span> <span data-ttu-id="2b05a-104">Non è possibile creare una funzione di sistema definita dall'utente specificando tale utente.</span><span class="sxs-lookup"><span data-stu-id="2b05a-104">You cannot create a user-defined system function by specifying this user.</span></span> <span data-ttu-id="2b05a-105">Il nome utente **system_function_schema** non esiste e l'ID utente associato a questo nome (UID = 4) è riservato allo schema **sys** ed è limitato a un uso interno.</span><span class="sxs-lookup"><span data-stu-id="2b05a-105">The **system_function_schema** user name does not exist, and the user ID that is associated with this name (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
## <a name="component"></a><span data-ttu-id="2b05a-106">Componente</span><span class="sxs-lookup"><span data-stu-id="2b05a-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="2b05a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b05a-107">Description</span></span>  
 <span data-ttu-id="2b05a-108">Le operazioni di archiviazione e accesso agli oggetti di sistema sono state modificate nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b05a-108">System object storage and access has changed in the following ways:</span></span>  
  
-   <span data-ttu-id="2b05a-109">Gli oggetti di sistema sono archiviati nel database **Resource** di sola lettura e gli aggiornamenti diretti degli oggetti di sistema non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="2b05a-109">System objects are stored in the read-only **Resource** database, and direct system object updates are not permitted.</span></span>  
  
     <span data-ttu-id="2b05a-110">Gli oggetti di sistema vengono visualizzati logicamente nello schema **sys** di ogni database.</span><span class="sxs-lookup"><span data-stu-id="2b05a-110">System objects logically appear in the **sys** schema of every database.</span></span> <span data-ttu-id="2b05a-111">In questo modo è possibile richiamare le funzioni di sistema da qualsiasi database specificando un nome di funzione composto da una sola parte.</span><span class="sxs-lookup"><span data-stu-id="2b05a-111">This maintains the ability to invoke system functions from any database by specifying a one-part function name.</span></span> <span data-ttu-id="2b05a-112">Ad esempio, l'istruzione `SELECT * FROM fn_helpcollations()` può essere eseguita da qualsiasi database.</span><span class="sxs-lookup"><span data-stu-id="2b05a-112">For example, the statement `SELECT * FROM fn_helpcollations()` can be run from any database.</span></span>  
  
-   <span data-ttu-id="2b05a-113">Il **system_function_schema** utente non documentato è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="2b05a-113">The undocumented user **system_function_schema** has been removed.</span></span>  
  
-   <span data-ttu-id="2b05a-114">L'ID utente associato a **system_function_schema** (UID = 4) è riservato allo schema **sys** ed è limitato a un uso interno.</span><span class="sxs-lookup"><span data-stu-id="2b05a-114">The user ID associated with **system_function_schema** (UID = 4) is reserved for the **sys** schema and is restricted to internal use only.</span></span>  
  
 <span data-ttu-id="2b05a-115">Queste modifiche hanno l'effetto seguente sulle funzioni di sistema definite dall'utente:</span><span class="sxs-lookup"><span data-stu-id="2b05a-115">These changes have the following effect on user-defined system functions:</span></span>  
  
-   <span data-ttu-id="2b05a-116">Le istruzioni DDL (Data Definition Language) che fanno riferimento a **system_function_schema** avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2b05a-116">Data Definition Language (DDL) statements that reference **system_function_schema** will fail.</span></span> <span data-ttu-id="2b05a-117">Ad esempio, l'istruzione `CREATE FUNCTION system` _ `function` \_ `schema.fn` \_ `MySystemFunction` ... avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2b05a-117">For example, the statement `CREATE FUNCTION system`_`function`\_`schema.fn`\_`MySystemFunction` ... will not succeed.</span></span>  
  
-   <span data-ttu-id="2b05a-118">Dopo l'aggiornamento a [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] , gli oggetti esistenti di proprietà di **system_function_schema** sono contenuti solo nello schema **sys** del database **Master** .</span><span class="sxs-lookup"><span data-stu-id="2b05a-118">After you upgrade to [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], existing objects that are owned by **system_function_schema** are contained only in the **sys** schema of the **master** database.</span></span> <span data-ttu-id="2b05a-119">Poiché gli oggetti di sistema non possono essere modificati, queste funzioni non possono mai essere modificate o eliminate dal database **Master** .</span><span class="sxs-lookup"><span data-stu-id="2b05a-119">Because system objects cannot be modified, these functions can never be changed or dropped from the **master** database.</span></span> <span data-ttu-id="2b05a-120">Inoltre, non possono essere richiamate da altri database specificando un nome di funzione composto da una sola parte.</span><span class="sxs-lookup"><span data-stu-id="2b05a-120">Additionally, these functions cannot be invoked from other databases by specifying only a one-part function name.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="2b05a-121">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="2b05a-121">Corrective Action</span></span>  
 <span data-ttu-id="2b05a-122">Prima di eseguire l'aggiornamento, completare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b05a-122">Before you upgrade , complete the following tasks:</span></span>  
  
1.  <span data-ttu-id="2b05a-123">Modificare la proprietà delle funzioni definite dall'utente esistenti in **dbo** usando il stored procedure di sistema **sp_changeobjectowner** .</span><span class="sxs-lookup"><span data-stu-id="2b05a-123">Change the ownership of existing user-defined functions to **dbo** by using the **sp_changeobjectowner** system stored procedure.</span></span>  
  
2.  <span data-ttu-id="2b05a-124">Rinominare la funzione in modo da non utilizzare il prefisso 'fn_'</span><span class="sxs-lookup"><span data-stu-id="2b05a-124">Consider renaming the function so that is does not use the prefix 'fn_'.</span></span> <span data-ttu-id="2b05a-125">per evitare potenziali conflitti di nome con le funzioni di sistema correnti o future.</span><span class="sxs-lookup"><span data-stu-id="2b05a-125">This will avoid potential name conflicts with current or future system functions.</span></span>  
  
3.  <span data-ttu-id="2b05a-126">Aggiungere una copia delle funzioni modificate in ogni database in cui vengono utilizzate.</span><span class="sxs-lookup"><span data-stu-id="2b05a-126">Add a copy of the modified functions in every database that uses them.</span></span>  
  
4.  <span data-ttu-id="2b05a-127">Sostituire i riferimenti a **system_function_schema** con **dbo** in tutti gli script che contengono istruzioni DDL di funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="2b05a-127">Replace references to **system_function_schema** with **dbo** in all scripts that contain user-defined function DDL statements.</span></span>  
  
5.  <span data-ttu-id="2b05a-128">Modificare gli script che richiamano queste funzioni per utilizzare il nome in due parti dbo **.** _function_name_o il nome in tre parti _database_name_**.** dbo. *function_name*.</span><span class="sxs-lookup"><span data-stu-id="2b05a-128">Modify scripts that invoke these functions to use either the two-part name dbo **.**_function_name_, or the three-part name _database_name_**.** dbo.*function_name*.</span></span>  
  
 <span data-ttu-id="2b05a-129">Per ulteriori informazioni, vedere gli argomenti seguenti della documentazione online di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="2b05a-129">For more information, see the following topics in SQL Server Books Online:</span></span>  
  
-   <span data-ttu-id="2b05a-130">"sp_changeobjectowner"</span><span class="sxs-lookup"><span data-stu-id="2b05a-130">"sp_changeobjectowner"</span></span>  
  
-   <span data-ttu-id="2b05a-131">"Separazione fra schema e utente"</span><span class="sxs-lookup"><span data-stu-id="2b05a-131">"User-schema Separation"</span></span>  
  
-   <span data-ttu-id="2b05a-132">"Database Resource"</span><span class="sxs-lookup"><span data-stu-id="2b05a-132">"Resource Database"</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b05a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b05a-133">See Also</span></span>  
 <span data-ttu-id="2b05a-134">[SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;](sql-server-2014-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="2b05a-134">[SQL Server 2014 Upgrade Advisor &#91;new&#93;](sql-server-2014-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="2b05a-135">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2b05a-135">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 <span data-ttu-id="2b05a-136">[Rimuovere istruzioni che modificano oggetti di sistema](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span><span class="sxs-lookup"><span data-stu-id="2b05a-136">[Remove statements that modify system objects](../../../2014/sql-server/install/remove-statements-that-modify-system-objects.md) </span></span>  
 [<span data-ttu-id="2b05a-137">Rimuovere le istruzioni che eliminano oggetti di sistema</span><span class="sxs-lookup"><span data-stu-id="2b05a-137">Remove statements that drop system objects</span></span>](../../../2014/sql-server/install/remove-statements-that-drop-system-objects.md)  
  
  
