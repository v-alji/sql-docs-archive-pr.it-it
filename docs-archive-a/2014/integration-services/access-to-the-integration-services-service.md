---
title: Accesso al servizio Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- viewing packages while running
- displaying packacges while running
- security [Integration Services], running packages
- packages [Integration Services], security
- current packages running
- Integration Services packages, security
- SQL Server Integration Services packages, security
ms.assetid: 1088aafc-14c5-4e7d-9930-606a24c3049b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7dd6fbed4bedc285069306ab4c400f0f67f9f293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625529"
---
# <a name="access-to-the-integration-services-service"></a><span data-ttu-id="bd0ce-102">Accesso al servizio Integration Services</span><span class="sxs-lookup"><span data-stu-id="bd0ce-102">Access to the Integration Services Service</span></span>
  <span data-ttu-id="bd0ce-103">Tramite i livelli di protezione dei pacchetti è possibile limitare gli utenti a cui è consentito modificare ed eseguire un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="bd0ce-103">Package protection levels can limit who is allowed to edit and execute a package.</span></span> <span data-ttu-id="bd0ce-104">Per limitare gli utenti a cui è consentito visualizzare l'elenco di pacchetti attualmente in esecuzione in un server e arrestare i pacchetti attualmente in esecuzione in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]è necessaria una protezione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="bd0ce-104">Additional protection is needed to limit who can view the list of packages currently running on a server and who can stop currently executing packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="bd0ce-105">usa il servizio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per visualizzare l'elenco dei pacchetti in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bd0ce-105">uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service to list running packages.</span></span> <span data-ttu-id="bd0ce-106">I membri del gruppo Administrators di Windows possono visualizzare e arrestare tutti i pacchetti in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bd0ce-106">Members of the Windows Administrators group can view and stop all currently running packages.</span></span> <span data-ttu-id="bd0ce-107">Gli utenti che non appartengono a questo gruppo possono visualizzare e arrestare solo i pacchetti che hanno avviato personalmente.</span><span class="sxs-lookup"><span data-stu-id="bd0ce-107">Users who are not members of the Administrators group can view and stop only packages that they started.</span></span>  
  
 <span data-ttu-id="bd0ce-108">È importante limitare l'accesso ai computer che eseguono un servizio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , soprattutto se si tratta di un servizio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] che consente l'enumerazione di cartelle remote.</span><span class="sxs-lookup"><span data-stu-id="bd0ce-108">It is important to restrict access to computers that run an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service, especially an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service that can enumerate remote folders.</span></span> <span data-ttu-id="bd0ce-109">Gli utenti autenticati possono richiedere l'enumerazione di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="bd0ce-109">Any authenticated user can request the enumeration of packages.</span></span> <span data-ttu-id="bd0ce-110">Anche se il servizio non viene individuato, le cartelle vengono comunque enumerate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="bd0ce-110">Even if the service doesn not find the service, the service enumerates folders.</span></span> <span data-ttu-id="bd0ce-111">Questi nomi di cartella potrebbero essere sfruttati da un utente malintenzionato.</span><span class="sxs-lookup"><span data-stu-id="bd0ce-111">These folder names may be useful to a malicious user.</span></span> <span data-ttu-id="bd0ce-112">Se un amministratore ha configurato il servizio in modo da consentire l'enumerazione di cartelle in un computer remoto, agli utenti potrebbero essere visualizzati anche i nomi di cartella in genere non visibili.</span><span class="sxs-lookup"><span data-stu-id="bd0ce-112">If an administrator has configured the service to enumerate folders on a remote machine, users may also be able to see folder names that they would normally not be able to see.</span></span>  
  
  
