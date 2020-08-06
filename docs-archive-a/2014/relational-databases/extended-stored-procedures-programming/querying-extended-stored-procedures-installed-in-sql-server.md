---
title: Esecuzione di query su stored procedure estese installate in SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], querying
ms.assetid: e02348e6-dba6-438a-98b6-684244bb034d
author: rothja
ms.author: jroth
ms.openlocfilehash: 3f44db9053ad18c3a6902a30aaab4f81610c5a8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626103"
---
# <a name="querying-extended-stored-procedures-installed-in-sql-server"></a><span data-ttu-id="4d19a-102">Esecuzione di query su stored procedure estese installate in SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d19a-102">Querying Extended Stored Procedures Installed in SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="4d19a-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="4d19a-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="4d19a-104">Un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utente autenticato può visualizzare le stored procedure estese attualmente definite e il nome della dll a cui appartiene, eseguendo la procedura **sp_helpextendedproc** sistema.</span><span class="sxs-lookup"><span data-stu-id="4d19a-104">A [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authenticated user can display the currently defined extended stored procedures and the name of the DLL to which each belongs by running the **sp_helpextendedproc** system procedure.</span></span> <span data-ttu-id="4d19a-105">Nell'esempio seguente viene restituita la DLL a cui appartiene **xp_hello** :</span><span class="sxs-lookup"><span data-stu-id="4d19a-105">For example, the following example returns the DLL to which **xp_hello** belongs:</span></span>  
  
```  
sp_helpextendedproc 'xp_hello'  
```  
  
 <span data-ttu-id="4d19a-106">Se **sp_helpextendedproc** viene eseguita senza specificare una stored procedure estesa, vengono visualizzate tutte le stored procedure estese e le relative dll.</span><span class="sxs-lookup"><span data-stu-id="4d19a-106">If **sp_helpextendedproc** is executed without specifying an extended stored procedure, all the extended stored procedures and their DLLs are displayed.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4d19a-107">Verranno restituite le informazioni solo per le stored procedure estese di cui l'utente connesso è il proprietario o di cui dispone delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="4d19a-107">Information will be returned for only those extended stored procedures that the logged in user owns or has permissions to.</span></span> <span data-ttu-id="4d19a-108">Solo i membri del ruolo predefinito del server **sysadmin** e del **db_owner**, **db_securityadmin**e i ruoli predefiniti del database **db_ddladmin** possono visualizzare le informazioni relative a tutte le stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="4d19a-108">Only members of the **sysadmin** fixed server role and the **db_owner**, **db_securityadmin**, and the **db_ddladmin** fixed database roles can view information for all extended stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d19a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d19a-109">See Also</span></span>  
 <span data-ttu-id="4d19a-110">[sp_helpextendedproc &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4d19a-110">[sp_helpextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpextendedproc-transact-sql) </span></span>  
 <span data-ttu-id="4d19a-111">[sp_addextendedproc &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4d19a-111">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="4d19a-112">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d19a-112">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
