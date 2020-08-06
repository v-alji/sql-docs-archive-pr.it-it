---
title: 'Lezione 2: valutare i criteri per procedure consigliate in base a una pianificazione | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 37ffad63-d6db-4609-8deb-786200659554
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a454e38ec2f07bf9867183a3894ac4ea001a942e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626429"
---
# <a name="lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis"></a><span data-ttu-id="08c2a-102">Lezione 2: Valutazione di criteri per procedure consigliate in base a una pianificazione</span><span class="sxs-lookup"><span data-stu-id="08c2a-102">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>
  <span data-ttu-id="08c2a-103">È possibile configurare valutazioni pianificate di criteri per procedure consigliate in una o più istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08c2a-103">You can configure scheduled evaluations of best practices policies on one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="08c2a-104">Per configurare i criteri per procedure consigliate da eseguire in base a una pianificazione prestabilita, è necessario importare i criteri nell'istanza di destinazione.</span><span class="sxs-lookup"><span data-stu-id="08c2a-104">To configure best practices policies to run on a scheduled basis, you must import the policies into the target instance.</span></span>  
  
 <span data-ttu-id="08c2a-105">Per distribuire criteri pianificati in più server, è possibile importare i criteri in un'istanza, configurare le pianificazioni per tutti i criteri, esportare i criteri pianificati in una cartella, quindi distribuire i criteri pianificati nelle istanze di destinazione tramite Server registrati.</span><span class="sxs-lookup"><span data-stu-id="08c2a-105">To deploy scheduled policies to multiple servers, you can import the policies to one instance, configure the schedules for each policy, export the scheduled policies to a folder, and then deploy the scheduled policies to target instances through Registered Servers.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="08c2a-106">Le istanze di destinazione devono eseguire [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="08c2a-106">The target instances must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="08c2a-107">Ai fini dell'automazione è necessario che i criteri siano archiviati localmente nell'istanza, operazione non supportata dalle versioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] precedenti a [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08c2a-107">Automation requires the policies to be stored locally on the instance, which is not supported by versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="08c2a-108">In questa lezione verranno effettuate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="08c2a-108">In this lesson, you will do the following:</span></span>  
  
-   <span data-ttu-id="08c2a-109">Importazione di criteri per procedure consigliate in un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08c2a-109">Import the best practices policies into an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="08c2a-110">Configurazione di criteri da eseguire in base a una pianificazione.</span><span class="sxs-lookup"><span data-stu-id="08c2a-110">Configure the policies to run on a schedule.</span></span>  
  
-   <span data-ttu-id="08c2a-111">Distribuzione di criteri per procedure consigliate pianificati in più istanze mediante Server registrati.</span><span class="sxs-lookup"><span data-stu-id="08c2a-111">Deploy the scheduled best practices policies to multiple instances through Registered Servers.</span></span>  
  
 <span data-ttu-id="08c2a-112">In questa lezione sono inclusi gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="08c2a-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="08c2a-113">Importazione dei criteri in un'istanza singola</span><span class="sxs-lookup"><span data-stu-id="08c2a-113">Import the Policies to a Single Instance</span></span>](../../2014/tutorials/import-the-policies-to-a-single-instance.md)  
  
-   [<span data-ttu-id="08c2a-114">Pianificazione criteri</span><span class="sxs-lookup"><span data-stu-id="08c2a-114">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
-   [<span data-ttu-id="08c2a-115">Distribuzione di criteri pianificati in istanze multiple</span><span class="sxs-lookup"><span data-stu-id="08c2a-115">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
## <a name="see-also"></a><span data-ttu-id="08c2a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08c2a-116">See Also</span></span>  
 [<span data-ttu-id="08c2a-117">Amministrare più server tramite server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="08c2a-117">Administer Multiple Servers Using Central Management Servers</span></span>](../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
