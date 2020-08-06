---
title: Completare i passaggi di post-installazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 0a788a2a-9b4f-4bfc-b1b5-83eeb1ea9ab2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1e9aae3dccaa409bcebc473213286f3edf19e7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629662"
---
# <a name="complete-the-post-installation-steps"></a><span data-ttu-id="4d2ab-102">Completare i passaggi successivi all'installazione</span><span class="sxs-lookup"><span data-stu-id="4d2ab-102">Complete the Post-Installation Steps</span></span>
  <span data-ttu-id="4d2ab-103">Dopo aver installato il componente Riesecuzione distribuita, è necessario modificare gli account del controller e del servizio client relativi.</span><span class="sxs-lookup"><span data-stu-id="4d2ab-103">After you install Distributed Replay you must modify the Distributed Replay controller and client services accounts.</span></span>  
  
### <a name="to-complete-the-post-installation-steps"></a><span data-ttu-id="4d2ab-104">Per completare i passaggi di post-installazione</span><span class="sxs-lookup"><span data-stu-id="4d2ab-104">To complete the post-installation steps</span></span>  
  
1.  <span data-ttu-id="4d2ab-105">**Creare regole del firewall**: nei computer controller e client è necessario consentire il traffico in ingresso attraverso il firewall per il servizio corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4d2ab-105">**Create firewall rules**: On the controller and client computers, you must allow inbound traffic through the firewall for the corresponding service.</span></span> <span data-ttu-id="4d2ab-106">Specificare le regole del firewall per i file eseguibili del servizio, all'interno delle cartelle di installazione.</span><span class="sxs-lookup"><span data-stu-id="4d2ab-106">Specify the firewall rules for the service executables, located in the installation folders.</span></span>  
  
    1.  <span data-ttu-id="4d2ab-107">Per il servizio controller, creare una regola per **DReplayController.exe**, che si trova nella cartella di installazione.</span><span class="sxs-lookup"><span data-stu-id="4d2ab-107">For the controller service, create a rule for **DReplayController.exe**, located in the installation folder.</span></span> <span data-ttu-id="4d2ab-108">Il comando seguente, ad esempio, abilita questa regola, dove `%InstallPath%` è la cartella di installazione del servizio:</span><span class="sxs-lookup"><span data-stu-id="4d2ab-108">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay controller" dir=in program="%InstallPath%\DReplayController\DReplayController.exe" action=allow`  
  
    2.  <span data-ttu-id="4d2ab-109">Per il servizio client, in ogni computer client creare una regola per **DReplayClient.exe**, che si trova nella cartella di installazione.</span><span class="sxs-lookup"><span data-stu-id="4d2ab-109">For the client service, on each client computer, create a rule for **DReplayClient.exe**, located in the installation folder.</span></span> <span data-ttu-id="4d2ab-110">Il comando seguente, ad esempio, abilita questa regola, dove `%InstallPath%` è la cartella di installazione del servizio:</span><span class="sxs-lookup"><span data-stu-id="4d2ab-110">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay client" dir=in program="%InstallPath%\DReplayClient\DReplayClient.exe" action=allow`  
  
2.  <span data-ttu-id="4d2ab-111">**Concedere a ogni client le autorizzazioni per il server di destinazione**: al termine dell'installazione del servizio client nei computer client, è necessario aggiungere manualmente gli account del servizio client al ruolo sysadmin nell'istanza di destinazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d2ab-111">**Grant each client permissions on the target server**: After you have completed installing the client service on the client computers, you must manually add the client service accounts to the sysadmin role on the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4d2ab-112">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4d2ab-112">.NET Framework Security</span></span>  
 <span data-ttu-id="4d2ab-113">Per installare qualsiasi funzionalità di Riesecuzione distribuita, è necessario disporre di autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4d2ab-113">You must have administrative permissions in order to install any of the Distributed Replay features.</span></span> <span data-ttu-id="4d2ab-114">Solo un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che dispone di autorizzazioni sysadmin può aggiungere gli account del servizio client al ruolo del server sysadmin del server di prova.</span><span class="sxs-lookup"><span data-stu-id="4d2ab-114">Only a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login having sysadmin permissions can add the client service accounts to the sysadmin server role of the test server.</span></span> <span data-ttu-id="4d2ab-115">Per alcune considerazioni relative alla sicurezza di Riesecuzione distribuita, vedere [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="4d2ab-115">For more information about Distributed Replay security considerations, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
  
