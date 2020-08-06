---
title: Rimozione di una stored procedure estesa da SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- deleting extended stored procedures
- removing extended stored procedures
- extended stored procedures [SQL Server], removing
- dropping extended stored procedures
ms.assetid: 7827e574-3f59-4279-9a9b-532582e041cb
author: rothja
ms.author: jroth
ms.openlocfilehash: 284da815de073248669da032c06ddeeb68c697a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726936"
---
# <a name="removing-an-extended-stored-procedure-from-sql-server"></a><span data-ttu-id="f65f9-102">Rimozione di una stored procedure estesa da SQL Server</span><span class="sxs-lookup"><span data-stu-id="f65f9-102">Removing an Extended Stored Procedure from SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="f65f9-103">Utilizzare invece la funzionalità di integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="f65f9-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="f65f9-104">Per eliminare ogni funzione di stored procedure estesa in una DLL di stored procedure estesa definita dall'utente, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è necessario che un amministratore di sistema esegua il stored procedure di sistema **sp_dropextendedproc** , specificando il nome della funzione e il nome della dll in cui risiede la funzione.</span><span class="sxs-lookup"><span data-stu-id="f65f9-104">To drop each extended stored procedure function in a user-defined extended stored procedure DLL, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator must run the **sp_dropextendedproc** system stored procedure, specifying the name of the function and the name of the DLL in which that function resides.</span></span> <span data-ttu-id="f65f9-105">Ad esempio, questo comando rimuove la funzione **xp_hello**, che si trova in una DLL denominata xp_hello.dll, da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="f65f9-105">For example, this command removes the function **xp_hello**, located in a DLL named xp_hello.dll, from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
```  
sp_dropextendedproc 'xp_hello'  
```  
  
 <span data-ttu-id="f65f9-106">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , **sp_dropextendedproc** non elimina le stored procedure estese di sistema.</span><span class="sxs-lookup"><span data-stu-id="f65f9-106">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], **sp_dropextendedproc** does not drop system extended stored procedures.</span></span> <span data-ttu-id="f65f9-107">L'amministratore di sistema deve invece negare l'autorizzazione EXECUTE per il stored procedure esteso al ruolo **public** .</span><span class="sxs-lookup"><span data-stu-id="f65f9-107">Instead, the system administrator should deny EXECUTE permission on the extended stored procedure to the **public** role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f65f9-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f65f9-108">See Also</span></span>  
 [<span data-ttu-id="f65f9-109">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f65f9-109">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
