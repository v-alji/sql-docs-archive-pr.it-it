---
title: Abilitazione dell'integrazione con CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- clr enabled option
- common language runtime [SQL Server], enabling
ms.assetid: eb3e9c64-7486-42e7-baf6-c956fb311a2c
author: rothja
ms.author: jroth
ms.openlocfilehash: d7187906f1376deb81ca7ff4770af7b12b63c022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720010"
---
# <a name="enabling-clr-integration"></a><span data-ttu-id="4fec1-102">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="4fec1-102">Enabling CLR Integration</span></span>
  <span data-ttu-id="4fec1-103">Per impostazione predefinita, la funzionalità di integrazione con Common Language Runtime (CLR) è disabilitata e deve essere abilitata per poter utilizzare gli oggetti implementati mediante l'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="4fec1-103">The common language runtime (CLR) integration feature is off by default, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="4fec1-104">Per abilitare l'integrazione con CLR, utilizzare l'opzione **clr enabled** della stored procedure **sp_configure** :</span><span class="sxs-lookup"><span data-stu-id="4fec1-104">To enable CLR integration, use the **clr enabled** option of the **sp_configure** stored procedure:</span></span>  
  
```  
  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'clr enabled', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="4fec1-105">È possibile disabilitare l'integrazione CLR impostando l'opzione **clr enabled** su 0.</span><span class="sxs-lookup"><span data-stu-id="4fec1-105">You can disable CLR integration by setting the **clr enabled** option to 0.</span></span> <span data-ttu-id="4fec1-106">Quando si disabilita l'integrazione con CLR, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] viene arrestata l'esecuzione di tutte le routine CLR e vengono scaricati tutti i domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4fec1-106">When you disable CLR integration, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stops executing all CLR routines and unloads all application domains.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4fec1-107">Per abilitare l'integrazione con CLR, è necessario disporre dell'autorizzazione ALTER SETTINGS a livello di server, che viene utilizzata in modo implicito dai membri dei ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="4fec1-107">To enable CLR integration, you must have ALTER SETTINGS server level permission, which is implicitly held by members of the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4fec1-108">I computer configurati con grandi quantità di memoria e con un gran numero di processori potrebbero non riuscire a caricare la funzionalità di integrazione con CLR di SQL Server all'avvio del server.</span><span class="sxs-lookup"><span data-stu-id="4fec1-108">Computers configured with large amounts of memory and a large number of processors may fail to load the CLR integration feature of SQL Server when starting the server.</span></span> <span data-ttu-id="4fec1-109">Per risolvere questo problema, avviare il server utilizzando l'opzione di avvio del servizio **-gmemory_to_reserve** [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e specificare un valore di memoria sufficientemente grande.</span><span class="sxs-lookup"><span data-stu-id="4fec1-109">To address this issue, start the server by using the **-gmemory_to_reserve**[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service startup option, and specify a memory value large enough.</span></span> <span data-ttu-id="4fec1-110">Per altre informazioni, vedere [Opzioni di avvio del servizio del motore di database](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="4fec1-110">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4fec1-111">L'esecuzione di CLR (Common Language Runtime) non è supportata nell'ambito dell'opzione lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="4fec1-111">Common language runtime (CLR) execution is not supported under lightweight pooling.</span></span> <span data-ttu-id="4fec1-112">Prima di abilitare l'integrazione con CLR, è necessario disabilitare il lightweight pooling.</span><span class="sxs-lookup"><span data-stu-id="4fec1-112">Before enabling CLR integration, you must disable lightweight pooling.</span></span> <span data-ttu-id="4fec1-113">Per altre informazioni, vedere [lightweight pooling Server Configuration Option](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="4fec1-113">For more information, see [lightweight pooling Server Configuration Option](../../database-engine/configure-windows/lightweight-pooling-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fec1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fec1-114">See Also</span></span>  
 <span data-ttu-id="4fec1-115">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4fec1-115">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="4fec1-116">[Opzione di configurazione del server clr enabled](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="4fec1-116">[clr enabled Server Configuration Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) </span></span>  
 <span data-ttu-id="4fec1-117">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4fec1-117">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="4fec1-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4fec1-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="4fec1-119">Ruoli a livello di server</span><span class="sxs-lookup"><span data-stu-id="4fec1-119">Server-Level Roles</span></span>](../security/authentication-access/server-level-roles.md)  
  
  
