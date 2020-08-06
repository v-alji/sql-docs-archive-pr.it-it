---
title: Opzione di configurazione del server xp_cmdshell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- xp_cmdshell
ms.assetid: c147c9e1-b81d-49c8-b800-3019f4d86a13
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a7feec1765cf6ffaa3e46a300a5155ae73fb13db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638084"
---
# <a name="xp_cmdshell-server-configuration-option"></a><span data-ttu-id="3dd61-102">Opzione di configurazione del server xp_cmdshell</span><span class="sxs-lookup"><span data-stu-id="3dd61-102">xp_cmdshell Server Configuration Option</span></span>
  <span data-ttu-id="3dd61-103">L'opzione **xp_cmdshell** è un'opzione di configurazione server di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che consente agli amministratori di sistema di controllare se la stored procedure estesa **xp_cmdshell** può essere eseguita in un sistema.</span><span class="sxs-lookup"><span data-stu-id="3dd61-103">The **xp_cmdshell** option is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] server configuration option that enables system administrators to control whether the **xp_cmdshell** extended stored procedure can be executed on a system.</span></span> <span data-ttu-id="3dd61-104">Nelle nuove installazioni l'opzione **xp_cmdshell** è disabilitata per impostazione predefinita e può essere abilitata usando la gestione basata su criteri oppure eseguendo la stored procedure di sistema **sp_configure** , come illustrato nell'esempio di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="3dd61-104">By default, the **xp_cmdshell** option is disabled on new installations and can be enabled by using the Policy-Based Management or by running the **sp_configure** system stored procedure as shown in the following code example:</span></span>  
  
```  
-- To allow advanced options to be changed.  
EXEC sp_configure 'show advanced options', 1;  
GO  
-- To update the currently configured value for advanced options.  
RECONFIGURE;  
GO  
-- To enable the feature.  
EXEC sp_configure 'xp_cmdshell', 1;  
GO  
-- To update the currently configured value for this feature.  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="3dd61-105">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dd61-105">See Also</span></span>  
 <span data-ttu-id="3dd61-106">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3dd61-106">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="3dd61-107">Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="3dd61-107">Administer Servers by Using Policy-Based Management</span></span>](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
