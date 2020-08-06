---
title: Scegliere l'account del servizio SQL Server Agent appropriato per gli ambienti multiserver | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, service accounts
- multiserver environments [SQL Server], SQL Server Agent service account behavior
ms.assetid: a07e2f38-281c-495b-965b-13fad03ba548
author: stevestein
ms.author: sstein
ms.openlocfilehash: 94ef890f5d2ef2b85d2f4d1023a93747e903a7f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637592"
---
# <a name="choose-the-right-sql-server-agent-service-account-for-multiserver-environments"></a><span data-ttu-id="3fbbc-102">Scegliere l'account di servizio SQL Server Agent adatto ad ambienti multiserver</span><span class="sxs-lookup"><span data-stu-id="3fbbc-102">Choose the Right SQL Server Agent Service Account for Multiserver Environments</span></span>
  <span data-ttu-id="3fbbc-103">L'account di Windows scelto per il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent può influenzare il comportamento di un ambiente multiserver, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3fbbc-103">The Windows account you choose for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can affect the behavior of a multiserver environment, as follows:</span></span>  
  
-   <span data-ttu-id="3fbbc-104">Se si esegue il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent con un account che non appartiene al gruppo Administrators locale di Windows, è possibile che l'integrazione dei server di destinazione nei server master abbia esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3fbbc-104">If you run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service under an account that is not a member of the local Windows Administrators group, enlisting target servers to master servers may fail.</span></span> <span data-ttu-id="3fbbc-105">In questo caso, verrà visualizzato il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="3fbbc-105">If it does, the following error message is returned:</span></span>  
  
     <span data-ttu-id="3fbbc-106">"Operazione di integrazione non riuscita."</span><span class="sxs-lookup"><span data-stu-id="3fbbc-106">"The enlistment operation failed."</span></span>  
  
     <span data-ttu-id="3fbbc-107">Per risolvere il problema, riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e i servizi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="3fbbc-107">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent services to resolve this issue.</span></span>  
  
-   <span data-ttu-id="3fbbc-108">Quando il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent viene eseguito con l'account di sistema locale, le operazioni tra server master e server di destinazione sono supportate solo se entrambi risiedono nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="3fbbc-108">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is run under the Local System account, master server-target server operations are supported only if both the master server and the target server reside on the same computer.</span></span> <span data-ttu-id="3fbbc-109">Se si utilizza questa configurazione, quando si integrano i server di destinazione in un server master, verrà visualizzato il seguente messaggio:</span><span class="sxs-lookup"><span data-stu-id="3fbbc-109">If you use this configuration, the following message is returned when you enlist target servers to a master server:</span></span>  
  
     <span data-ttu-id="3fbbc-110">"Verifica che l'account di avvio dell'agente per *<target_server_computer_name>* disponga dei diritti per l'accesso come server di destinazione".</span><span class="sxs-lookup"><span data-stu-id="3fbbc-110">"Ensure the agent start-up account for *<target_server_computer_name>* has rights to log on as targetServer."</span></span>  
  
     <span data-ttu-id="3fbbc-111">Questo messaggio può essere ignorato.</span><span class="sxs-lookup"><span data-stu-id="3fbbc-111">You can ignore this informational message.</span></span> <span data-ttu-id="3fbbc-112">L'operazione di integrazione verrà completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3fbbc-112">The enlistment operation should complete successfully.</span></span>  
  
 <span data-ttu-id="3fbbc-113">Per informazioni su come selezionare l'account di avvio del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, vedere [Selezionare un account per il servizio SQL Server Agent](select-an-account-for-the-sql-server-agent-service.md).</span><span class="sxs-lookup"><span data-stu-id="3fbbc-113">For more information about choosing an account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, see [Select an Account for the SQL Server Agent Service](select-an-account-for-the-sql-server-agent-service.md).</span></span>  
  
  
