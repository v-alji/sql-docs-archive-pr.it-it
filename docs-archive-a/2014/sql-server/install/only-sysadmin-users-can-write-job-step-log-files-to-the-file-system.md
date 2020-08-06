---
title: Solo gli utenti sysadmin possono scrivere file di log dei passaggi del processo nel file system | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- job step log files [SQL Server Agent]
- log files [SQL Server Agent]
- writing job step log files
ms.assetid: d26a7cef-1a60-4c95-b9df-f8b4fec59f9b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9e2bf5095ac1e6b67f6c6f3f87444879913916e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629154"
---
# <a name="only-sysadmin-users-can-write-job-step-log-files-to-the-file-system"></a><span data-ttu-id="f7ada-102">Solo gli utenti sysadmin possono scrivere file di log dei passaggi del processo nel file system</span><span class="sxs-lookup"><span data-stu-id="f7ada-102">Only sysadmin users can write job step log files to the file system</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="f7ada-103">scrive facoltativamente un log per ogni passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="f7ada-103">optionally writes a log for each job step.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f7ada-104">Componente</span><span class="sxs-lookup"><span data-stu-id="f7ada-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f7ada-105">Agent</span><span class="sxs-lookup"><span data-stu-id="f7ada-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="f7ada-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7ada-106">Description</span></span>  
 <span data-ttu-id="f7ada-107">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent può scrivere log nel file System per i processi di proprietà dei membri del ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="f7ada-107">In [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write logs to the file system for jobs that are owned by members of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="f7ada-108">Se il proprietario del processo non è un membro del ruolo **sysadmin** e se l'account proxy è abilitato, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent può scrivere i log nel file System usando le credenziali dell'account proxy.</span><span class="sxs-lookup"><span data-stu-id="f7ada-108">If the job owner is not a member of the **sysadmin** role and if the proxy account is enabled, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can write logs to the file system by using the credentials of the proxy account.</span></span>  
  
 <span data-ttu-id="f7ada-109">Dopo l'aggiornamento, i processi di proprietà di utenti che non sono membri del ruolo predefinito del server **sysadmin** non possono più scrivere log nel file System.</span><span class="sxs-lookup"><span data-stu-id="f7ada-109">After you upgrade, jobs that are owned by users who are not members of the **sysadmin** fixed server role can no longer write logs to the file system.</span></span> <span data-ttu-id="f7ada-110">Questi utenti possono invece selezionare l'opzione per scrivere i log in una tabella del database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="f7ada-110">Instead, these users can select the option to write their logs to a table in the **msdb** database.</span></span> <span data-ttu-id="f7ada-111">I membri del ruolo **sysadmin** possono comunque scrivere i file di log nel file System.</span><span class="sxs-lookup"><span data-stu-id="f7ada-111">Members of the **sysadmin** role can still write log files to the file system.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f7ada-112">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="f7ada-112">Corrective Action</span></span>  
 <span data-ttu-id="f7ada-113">Dopo l'aggiornamento, i processi di proprietà di utenti che non sono membri del ruolo **sysadmin** continueranno a essere eseguiti, ma i registri non verranno creati.</span><span class="sxs-lookup"><span data-stu-id="f7ada-113">After you upgrade, jobs that are owned by users who are not members of the **sysadmin** role will continue to run, but logs will not be created.</span></span> <span data-ttu-id="f7ada-114">Per registrare i passaggi del processo in una tabella, gli utenti che non sono membri del ruolo **sysadmin** devono aggiornare manualmente i processi.</span><span class="sxs-lookup"><span data-stu-id="f7ada-114">To log job steps to a table, users who are not members of the **sysadmin** role must manually update their jobs.</span></span>  
  
 <span data-ttu-id="f7ada-115">Per ulteriori informazioni, vedere gli argomenti "Creazione di processi", "Creazione di passaggi di processo" e "Gestione di più passaggi di processo" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7ada-115">For more information, see the topics "Creating Jobs," "Creating Job Steps," and "Handling Multiple Job Steps" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ada-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7ada-116">See Also</span></span>  
 [<span data-ttu-id="f7ada-117">Problemi di aggiornamento di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="f7ada-117">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
