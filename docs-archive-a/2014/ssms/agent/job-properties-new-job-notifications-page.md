---
title: 'Proprietà processo: nuovo processo (pagina notifiche) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.notifications.f1
ms.assetid: ed393cbd-4496-4399-a177-e5baa92fb689
author: stevestein
ms.author: sstein
ms.openlocfilehash: 30eca88943b48bd81bd38e236711d19ee7ec4503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624506"
---
# <a name="job-properties-new-job-notifications-page"></a><span data-ttu-id="ac253-102">Proprietà processo: Nuovo processo (pagina Notifiche)</span><span class="sxs-lookup"><span data-stu-id="ac253-102">Job Properties: New Job (Notifications Page)</span></span>
  <span data-ttu-id="ac253-103">Utilizzare questa pagina per impostare le azioni [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che Agent deve eseguire al completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="ac253-103">Use this page to set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac253-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ac253-104">Options</span></span>  
 <span data-ttu-id="ac253-105">**Posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="ac253-105">**E-mail**</span></span>  
 <span data-ttu-id="ac253-106">Selezionare questa opzione per inviare un messaggio di posta elettronica al completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="ac253-106">Select this option to send e-mail when the job completes.</span></span> <span data-ttu-id="ac253-107">Dopo aver selezionato questa opzione, specificare l'operatore a cui inviare la notifica e la condizione che attiverà tale notifica: **In caso di esito positivo processo**, **In caso di esito negativo processo**o **Al termine del processo**.</span><span class="sxs-lookup"><span data-stu-id="ac253-107">After selecting this option, choose the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="ac253-108">**Page**</span><span class="sxs-lookup"><span data-stu-id="ac253-108">**Page**</span></span>  
 <span data-ttu-id="ac253-109">Selezionare questa opzione per inviare un messaggio di posta elettronica al cercapersone di un operatore al completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="ac253-109">Select this option to send e-mail to an operator's pager when the job completes.</span></span> <span data-ttu-id="ac253-110">Dopo aver selezionato questa opzione, specificare l'operatore a cui inviare la notifica e la condizione che attiverà tale notifica: **In caso di esito positivo processo**, **In caso di esito negativo processo**o **Al termine del processo**.</span><span class="sxs-lookup"><span data-stu-id="ac253-110">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="ac253-111">**NET SEND**</span><span class="sxs-lookup"><span data-stu-id="ac253-111">**Net send**</span></span>  
 <span data-ttu-id="ac253-112">Selezionare questa opzione se al completamento del processo si desidera inviare la notifica all'operatore tramite Net Send.</span><span class="sxs-lookup"><span data-stu-id="ac253-112">Select this option to use net send to notify an operator when the job completes.</span></span> <span data-ttu-id="ac253-113">Dopo aver selezionato questa opzione, specificare l'operatore a cui inviare la notifica e la condizione che attiverà tale notifica: **In caso di esito positivo processo**, **In caso di esito negativo processo**o **Al termine del processo**.</span><span class="sxs-lookup"><span data-stu-id="ac253-113">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="ac253-114">**Scrivi nel registro eventi applicazioni di Windows**</span><span class="sxs-lookup"><span data-stu-id="ac253-114">**Write to the Windows Application event log**</span></span>  
 <span data-ttu-id="ac253-115">Selezionare questa opzione per scrivere una voce nel registro degli eventi dell'applicazione al completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="ac253-115">Select this option to write an entry in the application event log when the job completes.</span></span> <span data-ttu-id="ac253-116">Dopo aver selezionato questa opzione, specificare la condizione che causerà la scrittura della voce: **In caso di esito positivo processo**, **In caso di esito negativo processo**o **Al termine del processo**.</span><span class="sxs-lookup"><span data-stu-id="ac253-116">After selecting this option, specify the condition that will cause the entry to be written: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="ac253-117">**Elimina il processo automaticamente**</span><span class="sxs-lookup"><span data-stu-id="ac253-117">**Automatically delete job**</span></span>  
 <span data-ttu-id="ac253-118">Selezionare questa opzione per eliminare il processo dopo il completamento.</span><span class="sxs-lookup"><span data-stu-id="ac253-118">Select this option to delete the job when the job completes.</span></span> <span data-ttu-id="ac253-119">Dopo aver selezionato questa opzione, specificare la condizione che attiverà l'eliminazione del processo: **In caso di esito positivo processo**, **In caso di esito negativo processo**o **Al termine del processo**.</span><span class="sxs-lookup"><span data-stu-id="ac253-119">After selecting this option, specify the condition that will trigger deletion of the job: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac253-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac253-120">See Also</span></span>  
 <span data-ttu-id="ac253-121">[Implementazione di processi](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="ac253-121">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="ac253-122">Configurare Posta elettronica di SQL Server Agent per l'uso di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="ac253-122">Configure SQL Server Agent Mail to Use Database Mail</span></span>](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)  
  
  
