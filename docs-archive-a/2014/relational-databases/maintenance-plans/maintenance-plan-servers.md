---
title: Piano di manutenzione (Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.maintplanproperties.server.f1
- sql12.swb.maint.servers.f1
ms.assetid: ac24d1a8-dd2f-4162-b804-c0df1fc1e61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c971edc9b641846068313f47ca410715ec552014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627231"
---
# <a name="maintenance-plan-servers"></a><span data-ttu-id="4153e-102">Piano di manutenzione (Server)</span><span class="sxs-lookup"><span data-stu-id="4153e-102">Maintenance Plan (Servers)</span></span>
  <span data-ttu-id="4153e-103">Utilizzare la finestra di dialogo **Server** per selezionare i server in cui si desidera eseguire il piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="4153e-103">Use the **Servers** dialog box to select the servers where you want to run the maintenance plan.</span></span>  
  
 <span data-ttu-id="4153e-104">Per creare un piano di manutenzione multiserver, è necessario configurare un ambiente multiserver composto da un server master e uno o più server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4153e-104">A multiserver environment containing one master server and one or more target servers must be configured to create a multiserver maintenance plan.</span></span> <span data-ttu-id="4153e-105">Per i piani di manutenzione multiserver, il server locale deve essere configurato come server master.</span><span class="sxs-lookup"><span data-stu-id="4153e-105">For multiserver maintenance plans, the local server should be configured as a master server.</span></span> <span data-ttu-id="4153e-106">Negli ambienti multiserver, in questa finestra di dialogo vengono visualizzati il server master **(local)** e tutti i server di destinazione corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="4153e-106">In multiserver environments, this dialog box displays the **(local)** master server and all corresponding target servers.</span></span> <span data-ttu-id="4153e-107">Viene creato un processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per il server locale.</span><span class="sxs-lookup"><span data-stu-id="4153e-107">One [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job is created for the local server.</span></span> <span data-ttu-id="4153e-108">Tale processo sarà abilitato o disabilitato a seconda che si selezioni o meno il server **(local)** .</span><span class="sxs-lookup"><span data-stu-id="4153e-108">It is enabled or disabled depending on whether you select the **(local)** server.</span></span> <span data-ttu-id="4153e-109">Se vengono selezionati server di destinazione, viene creato un processo multiserver e tale processo viene poi scaricato in ognuno dei server di destinazione selezionati.</span><span class="sxs-lookup"><span data-stu-id="4153e-109">If target servers are selected, a multiserver job is created and downloaded to each of the selected target servers.</span></span> <span data-ttu-id="4153e-110">Se non viene selezionato alcun server di destinazione, il processo multiserver viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="4153e-110">If no target servers are selected, the multiserver job is deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4153e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4153e-111">See Also</span></span>  
 <span data-ttu-id="4153e-112">[Piani di manutenzione](maintenance-plans.md) </span><span class="sxs-lookup"><span data-stu-id="4153e-112">[Maintenance Plans](maintenance-plans.md) </span></span>  
 <span data-ttu-id="4153e-113">[Creazione di un ambiente multiserver](../../ssms/agent/create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="4153e-113">[Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="4153e-114">[Configurare un server master](../../ssms/agent/make-a-master-server.md) </span><span class="sxs-lookup"><span data-stu-id="4153e-114">[Make a Master Server](../../ssms/agent/make-a-master-server.md) </span></span>  
 [<span data-ttu-id="4153e-115">Configurare un server di destinazione</span><span class="sxs-lookup"><span data-stu-id="4153e-115">Make a Target Server</span></span>](../../ssms/agent/make-a-target-server.md)  
  
  
