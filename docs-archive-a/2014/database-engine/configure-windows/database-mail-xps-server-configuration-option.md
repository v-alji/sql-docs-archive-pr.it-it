---
title: Opzione di configurazione del server Stored procedure estese di posta elettronica database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Database Mail XPs option
- Database Mail [SQL Server], enabling
ms.assetid: e22c4e63-1792-473b-af11-14a7931ca9ed
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 33ee15e862e0992f39373ec30275040c4fcacc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630025"
---
# <a name="database-mail-xps-server-configuration-option"></a><span data-ttu-id="36131-102">Opzione di configurazione del server Database Mail XPs</span><span class="sxs-lookup"><span data-stu-id="36131-102">Database Mail XPs Server Configuration Option</span></span>
  <span data-ttu-id="36131-103">Usare l'opzione **Stored procedure estese di posta elettronica database** per abilitare Posta elettronica database nel server.</span><span class="sxs-lookup"><span data-stu-id="36131-103">Use the **DatabaseMail XPs** option to enable Database Mail on this server.</span></span> <span data-ttu-id="36131-104">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="36131-104">The possible values are:</span></span>  
  
-   <span data-ttu-id="36131-105">**0** per indicare che Posta elettronica database non è disponibile (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="36131-105">**0** indicating Database Mail is not available (default).</span></span>  
  
-   <span data-ttu-id="36131-106">**1** per indicare che Posta elettronica database è disponibile.</span><span class="sxs-lookup"><span data-stu-id="36131-106">**1** indicating Database Mail is available.</span></span>  
  
 <span data-ttu-id="36131-107">L'impostazione diventa effettiva immediatamente e non richiede l'arresto e il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="36131-107">The setting takes effect immediately without a server stop and restart.</span></span>  
  
 <span data-ttu-id="36131-108">Dopo aver abilitato Posta elettronica database, è necessario configurare un database host di Posta elettronica database per l'utilizzo di tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="36131-108">After enabling Database Mail, you must configure a Database Mail host database to use Database Mail.</span></span>  
  
 <span data-ttu-id="36131-109">Quando l'applicazione Posta elettronica database viene configurata tramite **Configurazione guidata posta elettronica database** , le stored procedure estese dell'applicazione vengono abilitate nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="36131-109">Configuring Database Mail using the **Database Mail Configuration Wizard** enables the Database Mail extended stored procedures in the **msdb** database.</span></span> <span data-ttu-id="36131-110">Se si esegue la **Configurazione guidata**, è possibile ignorare l'esempio **sp_configure** riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="36131-110">If you use the **Database Mail Configuration Wizard**, you do not have to use the **sp_configure** example below.</span></span>  
  
 <span data-ttu-id="36131-111">L'impostazione dell'opzione **Stored procedure estese di posta elettronica database** su 0 impedisce l'avvio di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="36131-111">Setting the **Database Mail XPs** option to 0 prevents Database Mail from starting.</span></span> <span data-ttu-id="36131-112">Se quando si imposta l'opzione su 0 l'applicazione è già in esecuzione, continuerà a essere eseguita fino a quando non rimane inattiva per il periodo di tempo impostato nell'opzione **DatabaseMailExeMinimumLifeTime** .</span><span class="sxs-lookup"><span data-stu-id="36131-112">If it is running when the option is set to 0, it continues to run and send mail until it is idle for the time configured in the **DatabaseMailExeMinimumLifeTime** option.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="36131-113">Esempi</span><span class="sxs-lookup"><span data-stu-id="36131-113">Examples</span></span>  
 <span data-ttu-id="36131-114">Nel codice di esempio seguente vengono abilitate le stored procedure estese di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="36131-114">The following example enables the Database Mail extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Database Mail XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="36131-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36131-115">See Also</span></span>  
 [<span data-ttu-id="36131-116">Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="36131-116">Database Mail</span></span>](../../relational-databases/database-mail/database-mail.md)  
  
  
