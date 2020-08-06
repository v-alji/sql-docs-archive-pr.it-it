---
title: Visualizzazione del registro applicazioni di Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- application logs [SQL Server]
- Windows application logs [SQL Server]
- viewing Windows application logs
- errors [SQL Server], logs
- system logs [SQL Server]
- security logs [SQL Server]
- displaying Windows application logs
- logs [SQL Server], Windows application logs
ms.assetid: f9853b74-7db7-47cc-b957-e49ed5bc0a1a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22f900a0b203e652bbc9cc6e9638711d138756c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628034"
---
# <a name="viewing-the-windows-application-log"></a><span data-ttu-id="9541f-102">Visualizzazione del registro applicazioni di Windows</span><span class="sxs-lookup"><span data-stu-id="9541f-102">Viewing the Windows Application Log</span></span>
  <span data-ttu-id="9541f-103">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è configurato per l'utilizzo del registro applicazioni di Microsoft Windows, durante ogni sessione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono scritti nuovi eventi in tale registro.</span><span class="sxs-lookup"><span data-stu-id="9541f-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Microsoft Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="9541f-104">A differenza di quanto avviene per il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , non viene creato un nuovo registro applicazioni a ogni avvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9541f-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9541f-105">È possibile visualizzare e gestire il registro applicazioni di Windows tramite il Visualizzatore eventi di Windows o il Visualizzatore log di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9541f-105">View and manage the Windows application log by using Windows Event Viewer or the Log Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="9541f-106">Il Visualizzatore eventi consente di visualizzare tre tipi di registro.</span><span class="sxs-lookup"><span data-stu-id="9541f-106">There are three logs that can be viewed with Event Viewer.</span></span>  
  
|<span data-ttu-id="9541f-107">Tipo di registro di Windows</span><span class="sxs-lookup"><span data-stu-id="9541f-107">Windows log type</span></span>|<span data-ttu-id="9541f-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9541f-108">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="9541f-109">Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="9541f-109">System log</span></span>|<span data-ttu-id="9541f-110">Registra gli eventi rilevati dai componenti del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="9541f-110">Records events logged by the Windows operating system components.</span></span> <span data-ttu-id="9541f-111">Ad esempio, un errore di un driver o di un altro componente di sistema da caricare all'avvio viene inserito nel registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="9541f-111">For example, the failure of a driver or other system component to load during startup is recorded in the system log.</span></span>|  
|<span data-ttu-id="9541f-112">Registro di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9541f-112">Security log</span></span>|<span data-ttu-id="9541f-113">Registra gli eventi di sicurezza, ad esempio i tentativi di accesso non riusciti.</span><span class="sxs-lookup"><span data-stu-id="9541f-113">Records security events, such as failed login attempts.</span></span> <span data-ttu-id="9541f-114">In questo modo è possibile tenere traccia delle modifiche apportate al sistema di sicurezza e identificare eventuali punti deboli.</span><span class="sxs-lookup"><span data-stu-id="9541f-114">This helps track changes to the security system and identify possible breaches to security.</span></span> <span data-ttu-id="9541f-115">Ad esempio, è possibile inserire nel registro di sicurezza i tentativi di accesso al sistema, in base alle impostazioni di controllo specificate in User Manager.</span><span class="sxs-lookup"><span data-stu-id="9541f-115">For example, attempts to log on to the system may be recorded in the security log, depending on the audit settings in the User Manager.</span></span><br /><br /> <span data-ttu-id="9541f-116">Soltanto i membri del ruolo predefinito del server **sysadmin** possono visualizzare il registro di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9541f-116">Only members of the **sysadmin** fixed server role can view the security log.</span></span>|  
|<span data-ttu-id="9541f-117">Registro applicazioni</span><span class="sxs-lookup"><span data-stu-id="9541f-117">Application log</span></span>|<span data-ttu-id="9541f-118">Registra gli eventi rilevati dalle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9541f-118">Records events that are logged by applications.</span></span> <span data-ttu-id="9541f-119">Ad esempio, è possibile che un'applicazione del database inserisca un errore di file nel registro applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9541f-119">For example, a database application might record a file error in the application log.</span></span>|  
  
 <span data-ttu-id="9541f-120">Per ulteriori informazioni sull'utilizzo del Visualizzatore eventi, sulla gestione del registro applicazioni e sul relativo contenuto, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="9541f-120">For more information about using Event Viewer, managing the application log, and understanding the information it presents, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="9541f-121">**Per visualizzare il registro delle applicazioni di Windows**</span><span class="sxs-lookup"><span data-stu-id="9541f-121">**To view the Windows application log**</span></span>  
  
 [<span data-ttu-id="9541f-122">Visualizzazione del log applicazioni di &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="9541f-122">View the Windows Application Log &#40;Windows&#41;</span></span>](../../relational-databases/performance/view-the-windows-application-log-windows-10.md)  
  
  
