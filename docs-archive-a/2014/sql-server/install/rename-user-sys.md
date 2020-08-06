---
title: Rinominare l'utente sys | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sys user names [SQL Server]
ms.assetid: d622d646-83e4-4b6f-9a21-77b301af04b5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3af9d31a54adc5645cab6fcc7104ae7ff27a61b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623745"
---
# <a name="rename-user-sys"></a><span data-ttu-id="e53c4-102">Rinominare l'utente sys</span><span class="sxs-lookup"><span data-stu-id="e53c4-102">Rename user sys</span></span>
  <span data-ttu-id="e53c4-103">È stato rilevato il nome utente **sys** in un database.</span><span class="sxs-lookup"><span data-stu-id="e53c4-103">Upgrade Advisor detected the user name **sys** in a database.</span></span> <span data-ttu-id="e53c4-104">Questo nome è riservato.</span><span class="sxs-lookup"><span data-stu-id="e53c4-104">This name is reserved.</span></span> <span data-ttu-id="e53c4-105">Rinominare l'utente prima di eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e53c4-105">Rename the user before you upgrade.</span></span> <span data-ttu-id="e53c4-106">Se l'utente non viene rinominato, il database si troverà in stato sospetto dopo il processo di aggiornamento e non sarà disponibile finché non viene portato online.</span><span class="sxs-lookup"><span data-stu-id="e53c4-106">If the user is not renamed, the database will be in a suspect state after the upgrade process and will be unavailable until the database is brought online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="e53c4-107">Componente</span><span class="sxs-lookup"><span data-stu-id="e53c4-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="e53c4-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e53c4-108">Description</span></span>  
 <span data-ttu-id="e53c4-109">L'utente **sys** è riservato.</span><span class="sxs-lookup"><span data-stu-id="e53c4-109">User **sys** is reserved.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="e53c4-110">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="e53c4-110">Corrective Action</span></span>  
  
### <a name="before-upgrade-procedure"></a><span data-ttu-id="e53c4-111">Procedura precedente all'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e53c4-111">Before Upgrade Procedure</span></span>  
 <span data-ttu-id="e53c4-112">Prima di eseguire l'aggiornamento, in ogni database che contiene l'utente **sys**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e53c4-112">Before you upgrade, in each database that contains user **sys**, do the following:</span></span>  
  
1.  <span data-ttu-id="e53c4-113">Creare un nuovo utente.</span><span class="sxs-lookup"><span data-stu-id="e53c4-113">Create a new user.</span></span>  
  
2.  <span data-ttu-id="e53c4-114">Utilizzare le istruzioni seguenti per visualizzare tutte le autorizzazioni concesse dall'utente **sys** e concesse all'utente **sys**.</span><span class="sxs-lookup"><span data-stu-id="e53c4-114">Use the following statements to display all permissions that are granted by user **sys** and granted to user **sys**.</span></span>  
  
    ```  
    -- Return permissions granted by user sys.  
    SELECT * FROM sysprotects WHERE grantor = USER_ID('sys')  
    -- Return permissions granted to user sys.  
    SELECT * FROM sysprotects WHERE uid = USER_ID('sys')  
    ```  
  
3.  <span data-ttu-id="e53c4-115">Per trasferire la proprietà di tutti gli oggetti di proprietà di **sys** al nuovo utente, utilizzare **sp_changeobjectowner**.</span><span class="sxs-lookup"><span data-stu-id="e53c4-115">To transfer ownership of all objects owned by **sys** to the new user, use **sp_changeobjectowner**.</span></span>  
  
4.  <span data-ttu-id="e53c4-116">Elimina utente **sys**.</span><span class="sxs-lookup"><span data-stu-id="e53c4-116">Drop user **sys**.</span></span>  
  
5.  <span data-ttu-id="e53c4-117">Per ripristinare le autorizzazioni originali acquisite nel passaggio 2, utilizzare la clausola AS *new_user* dell'istruzione Grant.</span><span class="sxs-lookup"><span data-stu-id="e53c4-117">To restore the original permissions captured in step 2, use the AS *new_user* clause of the GRANT statement.</span></span>  
  
6.  <span data-ttu-id="e53c4-118">Modificare gli script in modo che facciano riferimento al nuovo utente.</span><span class="sxs-lookup"><span data-stu-id="e53c4-118">Modify scripts to reference the new user.</span></span> <span data-ttu-id="e53c4-119">Ad esempio, gli script che contengono istruzioni come `SELECT * FROM sys.my`_`table` devono essere modificati in `SELECT * FROM new_user.my_table`.</span><span class="sxs-lookup"><span data-stu-id="e53c4-119">For example, scripts that contain statements such as `SELECT * FROM sys.my`_`table` must be changed to `SELECT * FROM new_user.my_table`.</span></span>  
  
### <a name="after-upgrade-procedure"></a><span data-ttu-id="e53c4-120">Procedura successiva all'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e53c4-120">After Upgrade Procedure</span></span>  
 <span data-ttu-id="e53c4-121">Se l'utente **sys** non è stato rinominato prima dell'aggiornamento, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e53c4-121">If the user **sys** was not renamed prior to upgrading, do the following:</span></span>  
  
1.  <span data-ttu-id="e53c4-122">Eseguire l'istruzione `ALTER DATABASE db_name SET ONLINE`.</span><span class="sxs-lookup"><span data-stu-id="e53c4-122">Execute the statement `ALTER DATABASE db_name SET ONLINE`.</span></span> <span data-ttu-id="e53c4-123">Il database sarà in modalità SINGLE_USER.</span><span class="sxs-lookup"><span data-stu-id="e53c4-123">The database will be in SINGLE_USER mode.</span></span>  
  
2.  <span data-ttu-id="e53c4-124">Seguire tutti i passaggi riportati nella sezione "Procedura precedente all'aggiornamento".</span><span class="sxs-lookup"><span data-stu-id="e53c4-124">Follow all steps in the Before Upgrade Procedure section.</span></span>  
  
3.  <span data-ttu-id="e53c4-125">Eseguire l'istruzione `ALTER DATABASE db_name SET MULTI_USER`.</span><span class="sxs-lookup"><span data-stu-id="e53c4-125">Execute the statement `ALTER DATABASE db_name SET MULTI_USER`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e53c4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e53c4-126">See Also</span></span>  
 <span data-ttu-id="e53c4-127">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="e53c4-127">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="e53c4-128">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="e53c4-128">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
