---
title: Aggiornare tutti i server di destinazione prima di aggiornare il server master | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- TSX [SQL Server Agent]
- target servers [SQL Server Agent]
- MSX [SQL Server Agent]
- master servers [SQL Server Agent]
ms.assetid: 2c231793-3878-4a5e-a425-1fa0d787ba84
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 031fedc4af4b058704cef1da8df846397b235305
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624524"
---
# <a name="upgrade-all-target-servers-before-upgrading-the-master-server"></a><span data-ttu-id="da08b-102">Aggiornare tutti i server di destinazione prima di aggiornare il server master</span><span class="sxs-lookup"><span data-stu-id="da08b-102">Upgrade all target servers before upgrading the master server</span></span>
  <span data-ttu-id="da08b-103">Prima di aggiornare il server master, aggiornare tutti i computer in cui è in esecuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e che sono configurati come server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="da08b-103">Before you upgrade the master server, upgrade all computers that are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are configured as target servers.</span></span>  
  
## <a name="component"></a><span data-ttu-id="da08b-104">Componente</span><span class="sxs-lookup"><span data-stu-id="da08b-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="da08b-105">Agent</span><span class="sxs-lookup"><span data-stu-id="da08b-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="da08b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da08b-106">Description</span></span>  
 <span data-ttu-id="da08b-107">Per automatizzare l'amministrazione negli ambienti multiserver, è necessario disporre almeno di un server master e di un server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="da08b-107">To automate administration in multiserver environments, you must have at least one master server and at least one target server.</span></span> <span data-ttu-id="da08b-108">Il server master distribuisce processi ai server di destinazione e riceve eventi da tali server.</span><span class="sxs-lookup"><span data-stu-id="da08b-108">A master server distributes jobs to, and receives events from, target servers.</span></span> <span data-ttu-id="da08b-109">Nel server master è inoltre archiviata la copia centrale delle definizioni di processo per i processi eseguiti nei server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="da08b-109">A master server also stores the central copy of job definitions for jobs that are run on target servers.</span></span>  
  
 <span data-ttu-id="da08b-110">Se il server corrente è configurato come server master, prima di aggiornare il server master aggiornare tutti i server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="da08b-110">If the current server is configured as a master server, upgrade all of your target servers first before you upgrade the master server.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="da08b-111">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="da08b-111">Corrective Action</span></span>  
 <span data-ttu-id="da08b-112">Se non è possibile aggiornare tutti i server di destinazione prima di aggiornare il server master, è necessario escludere tutti i server di destinazione e reintegrarli dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="da08b-112">If you cannot upgrade all target servers before you upgrade the master server, you must defect all target servers and reenlist them after you upgrade.</span></span>  
  
 <span data-ttu-id="da08b-113">Per ulteriori informazioni, vedere gli argomenti "Automatizzazione dell'amministrazione in un'organizzazione", "Procedura: Esclusione di un server di destinazione da un server master" e "Procedura: Integrazione di un server di destinazione in un server master" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da08b-113">For more information, see the topics "Automating Administration across an Enterprise," "How to: Defect a Target Server from a Master Server," and "How to: Enlist a Target Server to a Master" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da08b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da08b-114">See Also</span></span>  
 <span data-ttu-id="da08b-115">[Problemi di aggiornamento SQL Server Agent](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="da08b-115">[SQL Server Agent Upgrade Issues](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="da08b-116">Problemi di aggiornamento di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="da08b-116">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
