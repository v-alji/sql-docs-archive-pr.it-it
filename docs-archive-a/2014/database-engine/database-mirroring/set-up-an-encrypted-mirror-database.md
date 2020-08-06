---
title: Impostare un database mirror crittografato | Microsoft Docs
ms.custom: ''
ms.date: 06/26/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], database mirroring
- encryption [SQL Server], database mirroring
- database master key [SQL Server], database mirroring
- mirror database [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 7329a575-be29-46e0-abc6-1344db37920c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a5148411792f1ea881bba59e599252284575bbdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716727"
---
# <a name="set-up-an-encrypted-mirror-database"></a><span data-ttu-id="c5a0b-102">Impostazione di un database mirror crittografato</span><span class="sxs-lookup"><span data-stu-id="c5a0b-102">Set Up an Encrypted Mirror Database</span></span>

<span data-ttu-id="c5a0b-103">Per abilitare la decrittografia automatica della chiave master del database di un database mirror, è necessario fornire la password utilizzata per crittografare tale chiave nell'istanza del server mirror.</span><span class="sxs-lookup"><span data-stu-id="c5a0b-103">To enable automatic decryption of the database master key of a mirror database, you must provide the password used to encrypt the master key to the mirror server instance.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="c5a0b-104">e versioni successive includono meccanismi per trasferire la password.</span><span class="sxs-lookup"><span data-stu-id="c5a0b-104">and later versions include mechanisms to transfer the password.</span></span> <span data-ttu-id="c5a0b-105">Usare **sp_control_dbmasterkey_password** per creare una credenziale per la chiave master del database prima di avviare il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="c5a0b-105">Use **sp_control_dbmasterkey_password** to create a credential for the database master key before you start database mirroring.</span></span> <span data-ttu-id="c5a0b-106">Questa operazione va ripetuta per ogni database per il quale si desidera eseguire il mirroring.</span><span class="sxs-lookup"><span data-stu-id="c5a0b-106">You must repeat this process for every database that will be mirrored.</span></span> <span data-ttu-id="c5a0b-107">Per altre informazioni, vedere [sp_control_dbmasterkey_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c5a0b-107">For more information, see [sp_control_dbmasterkey_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql).</span></span>
  
> [!CAUTION]  
>  <span data-ttu-id="c5a0b-108">Non abilitare la decrittografia di failover di un database che deve rimanere inaccessibile a **sa** e altre entità server con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="c5a0b-108">Do not enable failover decryption of a database that must remain inaccessible to **sa** and other highly privileged server principals.</span></span> <span data-ttu-id="c5a0b-109">È possibile configurare un database in modo che la sua gerarchia di chiavi non possa essere decrittografata dalla chiave master del servizio.</span><span class="sxs-lookup"><span data-stu-id="c5a0b-109">You can configure a database so that its key hierarchy cannot be decrypted by the service master key.</span></span> <span data-ttu-id="c5a0b-110">Questa opzione viene supportata come difesa in profondità per database che contengono informazioni che non vanno rese accessibili a entità server **sa** o altre entità server con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="c5a0b-110">This option is supported as a defense-in-depth for databases that contain information that should not be accessible to **sa** or other highly privileged server principals.</span></span> <span data-ttu-id="c5a0b-111">Abilitando la decrittografia di failover per un database di questo tipo si elimina questa difesa in profondità, consentendo a entità server **sa** e altre entità server con privilegi elevati di decrittografare il database.</span><span class="sxs-lookup"><span data-stu-id="c5a0b-111">Enabling failover decryption of such a database removes this defense-in-depth, enabling **sa** and other highly privileged server principals to decrypt the database.</span></span>  


<!-- Note: We cannot append '?view=sql-server-2016' to these, even tho in theory we might want to. -->

## <a name="see-also"></a><span data-ttu-id="c5a0b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5a0b-112">See Also</span></span>

[<span data-ttu-id="c5a0b-113">sp_control_dbmasterkey_password &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5a0b-113">sp_control_dbmasterkey_password &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-control-dbmasterkey-password-transact-sql)

[<span data-ttu-id="c5a0b-114">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5a0b-114">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)

[<span data-ttu-id="c5a0b-115">ALTER MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5a0b-115">ALTER MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-master-key-transact-sql)

[<span data-ttu-id="c5a0b-116">Gerarchia di crittografia</span><span class="sxs-lookup"><span data-stu-id="c5a0b-116">Encryption Hierarchy</span></span>](../../relational-databases/security/encryption/encryption-hierarchy.md)

[<span data-ttu-id="c5a0b-117">Impostazione del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c5a0b-117">Setting Up Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)

