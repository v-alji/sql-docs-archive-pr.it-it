---
title: Configurare un database mirror per l'uso della proprietà Trustworthy (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- TRUSTWORTHY database option
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 6993b076-78ef-453e-b0ea-e341b8e5ee3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd46a08037bcb6eee178a96d84bdab358e5350d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716728"
---
# <a name="set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql"></a><span data-ttu-id="2ecc7-102">Impostazione di un database mirror per l'utilizzo della proprietà Trustworthy (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2ecc7-102">Set Up a Mirror Database to Use the Trustworthy Property (Transact-SQL)</span></span>
  <span data-ttu-id="2ecc7-103">Quando viene eseguito il backup di un database, la proprietà TRUSTWORTHY del database viene impostata su OFF.</span><span class="sxs-lookup"><span data-stu-id="2ecc7-103">When a database is backed up, the TRUSTWORTHY database property is set to OFF.</span></span> <span data-ttu-id="2ecc7-104">Di conseguenza, la proprietà TRUSTWORTHY di un nuovo database mirror è sempre impostata su OFF.</span><span class="sxs-lookup"><span data-stu-id="2ecc7-104">Therefore, on a new mirror database TRUSTWORTHY is always OFF.</span></span> <span data-ttu-id="2ecc7-105">Se il database deve risultare attendibile dopo un failover, è necessario eseguire passaggi di configurazione aggiuntivi dopo l'avvio del mirroring.</span><span class="sxs-lookup"><span data-stu-id="2ecc7-105">If the database needs to be trustworthy after a failover, extra setup steps are necessary after mirroring begins.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ecc7-106">Per informazioni su questa proprietà di database, vedere [Proprietà di database TRUSTWORTHY](../../relational-databases/security/trustworthy-database-property.md).</span><span class="sxs-lookup"><span data-stu-id="2ecc7-106">For information about this database property, see [TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="2ecc7-107">Procedura</span><span class="sxs-lookup"><span data-stu-id="2ecc7-107">Procedure</span></span>  
  
#### <a name="to-setup-a-mirror-database-to-use-the-trustworthy-property"></a><span data-ttu-id="2ecc7-108">Per impostare un database mirror per l'utilizzo della proprietà Trustworthy</span><span class="sxs-lookup"><span data-stu-id="2ecc7-108">To setup a mirror database to use the Trustworthy Property</span></span>  
  
1.  <span data-ttu-id="2ecc7-109">Sull'istanza del server principale verificare che nel database principale la proprietà Trustworthy sia impostata su ON.</span><span class="sxs-lookup"><span data-stu-id="2ecc7-109">On the principal server instance, verify that the principal database has the Trustworthy property turned on.</span></span>  
  
    ```  
    SELECT name, database_id, is_trustworthy_on FROM sys.databases   
    ```  
  
     <span data-ttu-id="2ecc7-110">Per altre informazioni, vedere [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ecc7-110">For more information, see [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span>  
  
2.  <span data-ttu-id="2ecc7-111">Dopo l'avvio del mirroring, verificare che il database sia impostato quale database principale, che nella sessione venga utilizzata una modalità operativa sincrona e che la sessione sia già sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="2ecc7-111">After starting mirroring, verify that the database is currently the principal database, the session is using a synchronous operating mode, and the session is already synchronized.</span></span>  
  
    ```  
    SELECT database_id, mirroring_role, mirroring_safety_level_desc, mirroring_state_desc FROM sys.database_mirroring  
    ```  
  
     <span data-ttu-id="2ecc7-112">Per altre informazioni, vedere [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ecc7-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
3.  <span data-ttu-id="2ecc7-113">Dopo la sincronizzazione della sessione di mirroring, eseguire manualmente il failover sul database mirror.</span><span class="sxs-lookup"><span data-stu-id="2ecc7-113">Once the mirroring session is synchronized, manually fail over to the mirror database.</span></span>  
  
     <span data-ttu-id="2ecc7-114">Questa operazione può essere eseguita in SQL Server Management Studio o mediante Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="2ecc7-114">This can be done in either SQL Server Management Studio or using Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="2ecc7-115">Failover manuale di una sessione di mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2ecc7-115">Manually Fail Over a Database Mirroring Session &#40;SQL Server Management Studio&#41;</span></span>](manually-fail-over-a-database-mirroring-session-sql-server-management-studio.md)  
  
    -   [<span data-ttu-id="2ecc7-116">Eseguire il failover manuale di una sessione di mirroring del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2ecc7-116">Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](manually-fail-over-a-database-mirroring-session-transact-sql.md)  
  
4.  <span data-ttu-id="2ecc7-117">Impostare la proprietà Trustworthy del database su ON utilizzando il comando ALTER DATABASE seguente:</span><span class="sxs-lookup"><span data-stu-id="2ecc7-117">Turn on the trustworthy database property using the following ALTER DATABASE command:</span></span>  
  
    ```  
    ALTER DATABASE <database_name> SET TRUSTWORTHY ON  
    ```  
  
     <span data-ttu-id="2ecc7-118">Per altre informazioni, vedere[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2ecc7-118">For more information, see[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
5.  <span data-ttu-id="2ecc7-119">Facoltativamente, eseguire di nuovo il failover manuale per tornare al database principale originale.</span><span class="sxs-lookup"><span data-stu-id="2ecc7-119">Optionally, manually failover again to return to the original principal.</span></span>  
  
6.  <span data-ttu-id="2ecc7-120">Facoltativamente, passare in modalità asincrona a prestazioni elevate impostando SAFETY su OFF e verificando che anche WITNESS sia impostato su OFF.</span><span class="sxs-lookup"><span data-stu-id="2ecc7-120">Optionally, switch to asynchronous, high-performance mode by setting SAFETY to OFF and ensuring that WITNESS is also set to OFF.</span></span>  
  
     <span data-ttu-id="2ecc7-121">In Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="2ecc7-121">In Transact-SQL:</span></span>  
  
    -   [<span data-ttu-id="2ecc7-122">Modificare la sicurezza delle transazioni in una sessione di mirroring del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2ecc7-122">Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md)  
  
    -   [<span data-ttu-id="2ecc7-123">Rimuovere il server di controllo del mirroring da una sessione di mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2ecc7-123">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
     <span data-ttu-id="2ecc7-124">In SQL Server Management Studio:</span><span class="sxs-lookup"><span data-stu-id="2ecc7-124">In SQL Server Management Studio:</span></span>  
  
    -   [<span data-ttu-id="2ecc7-125">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2ecc7-125">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ecc7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ecc7-126">See Also</span></span>  
 <span data-ttu-id="2ecc7-127">[Proprietà di database TRUSTWORTHY](../../relational-databases/security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="2ecc7-127">[TRUSTWORTHY Database Property](../../relational-databases/security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="2ecc7-128">Impostazione di un database mirror crittografato</span><span class="sxs-lookup"><span data-stu-id="2ecc7-128">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
