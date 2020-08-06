---
title: Creare un evento definito dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent alerts, user-defined events
- user-defined events [SQL Server]
- multiple language support [SQL Server], alerts
- languages [SQL Server], alerts
- severity levels [SQL Server]
- global considerations [SQL Server], alerts
- events [SQL Server], user-defined
- SQL Server Agent alerts, multiple-language environments
- alerts [SQL Server], user-defined events
- alerts [SQL Server], multiple-language environments
- custom events [SQL Server Agent]
- international considerations [SQL Server], alerts
ms.assetid: 03d71a35-97fa-4bba-aa9a-23ac9c9cf879
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2323dc4da3d1a8a67dad41ea189877ade25eff0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726424"
---
# <a name="create-a-user-defined-event"></a><span data-ttu-id="5372d-102">Creazione di un evento definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="5372d-102">Create a User-Defined Event</span></span>
  <span data-ttu-id="5372d-103">Per monitorare eventi diversi da quelli predefiniti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è possibile creare eventi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="5372d-103">You can create user-defined events if you want to monitor events other than events that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5372d-104">È inoltre possibile assegnare un livello di gravità a ogni evento definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="5372d-104">You can also assign a severity level to each user-defined event.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5372d-105">Quando si usa [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], selezionare l'opzione **Scrivi nel registro eventi delle applicazioni di Windows** per ogni messaggio di evento definito dall'utente, in modo da assicurarsi che i messaggi vengano registrati.</span><span class="sxs-lookup"><span data-stu-id="5372d-105">When using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the **Write to Windows application event log** option for each user-defined event message, to ensure that the messages are logged.</span></span> <span data-ttu-id="5372d-106">Per impostazione predefinita, i messaggi definiti dall'utente con livello di gravità minore di 19 non vengono inviati al registro delle applicazioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows quando si verificano.</span><span class="sxs-lookup"><span data-stu-id="5372d-106">By default, user-defined messages of severity lower than 19 are not sent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log when they occur.</span></span> <span data-ttu-id="5372d-107">Tali messaggi non generano quindi avvisi di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="5372d-107">User-defined messages of severity lower than 19 therefore do not trigger SQL Server Agent alerts.</span></span>  
  
 <span data-ttu-id="5372d-108">È necessario che agli eventi definiti dall'utente sia associato un numero di messaggio univoco.</span><span class="sxs-lookup"><span data-stu-id="5372d-108">User-defined events must have a unique message number.</span></span> <span data-ttu-id="5372d-109">Tali numeri devono essere maggiori di 50.000.</span><span class="sxs-lookup"><span data-stu-id="5372d-109">Message numbers for a user-defined event must be greater than 50,000.</span></span> <span data-ttu-id="5372d-110">È possibile definire messaggi per l'evento in più lingue.</span><span class="sxs-lookup"><span data-stu-id="5372d-110">You can define messages for the event in multiple languages.</span></span> <span data-ttu-id="5372d-111">Prima di potere aggiungere messaggi in altre lingue, è tuttavia necessario che sia disponibile un messaggio **En-US** .</span><span class="sxs-lookup"><span data-stu-id="5372d-111">However, an **En-US** error message must exist before messages in other languages can be added.</span></span>  
  
 <span data-ttu-id="5372d-112">Se si amministra un ambiente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] multilingue, creare messaggi definiti dall'utente in ciascuna lingua supportata.</span><span class="sxs-lookup"><span data-stu-id="5372d-112">If you administer a multiple-language [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment, create user-defined messages in each of the languages that are supported.</span></span> <span data-ttu-id="5372d-113">Ad esempio se si crea un nuovo messaggio dell'evento che verrà utilizzato sia in un server con sistema operativo in inglese che in un server con sistema operativo in tedesco, utilizzare lo stesso numero di messaggio e lo stesso livello di gravità per entrambi, ma assegnare una lingua diversa a ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="5372d-113">For example, if you are creating a new event message to be used on both an English and a German server, use the same message number and severity for both, but assign a different language to each.</span></span>  
  
 <span data-ttu-id="5372d-114">Nelle attività riportate di seguito sono disponibili informazioni su come creare eventi definiti dall'utente e avvisi in risposta a tali eventi.</span><span class="sxs-lookup"><span data-stu-id="5372d-114">The following tasks provide information about how to create user-defined events and alerts that respond to them:</span></span>  
  
 <span data-ttu-id="5372d-115">**Per creare un avviso in base a un numero di messaggio**</span><span class="sxs-lookup"><span data-stu-id="5372d-115">**To create an alert based on a message number**</span></span>  
  
-   [<span data-ttu-id="5372d-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5372d-116">SQL Server Management Studio</span></span>](create-an-alert-using-an-error-number.md)  
  
-   [<span data-ttu-id="5372d-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5372d-117">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="5372d-118">**Per creare un avviso in base ai livelli di gravità**</span><span class="sxs-lookup"><span data-stu-id="5372d-118">**To create an alert based on severity levels**</span></span>  
  
-   [<span data-ttu-id="5372d-119">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5372d-119">SQL Server Management Studio</span></span>](create-an-alert-using-severity-level.md)  
  
-   [<span data-ttu-id="5372d-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5372d-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 <span data-ttu-id="5372d-121">**Per definire la risposta a un avviso**</span><span class="sxs-lookup"><span data-stu-id="5372d-121">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="5372d-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5372d-122">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
-   [<span data-ttu-id="5372d-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5372d-123">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
 <span data-ttu-id="5372d-124">**Per creare un messaggio di errore relativo a un evento definito dall'utente**</span><span class="sxs-lookup"><span data-stu-id="5372d-124">**To create a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="5372d-125">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5372d-125">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql)  
  
 <span data-ttu-id="5372d-126">**Per modificare un messaggio di errore relativo a un evento definito dall'utente**</span><span class="sxs-lookup"><span data-stu-id="5372d-126">**To modify a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="5372d-127">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5372d-127">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
 <span data-ttu-id="5372d-128">**Per eliminare un messaggio di errore relativo a un evento definito dall'utente**</span><span class="sxs-lookup"><span data-stu-id="5372d-128">**To delete a user-defined event error message**</span></span>  
  
-   [<span data-ttu-id="5372d-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5372d-129">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropmessage-transact-sql)  
  
 <span data-ttu-id="5372d-130">**Per disabilitare o riattivare un avviso**</span><span class="sxs-lookup"><span data-stu-id="5372d-130">**To disable or reactivate an alert**</span></span>  
  
-   [<span data-ttu-id="5372d-131">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5372d-131">SQL Server Management Studio</span></span>](disable-or-reactivate-an-alert.md)  
  
-   [<span data-ttu-id="5372d-132">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5372d-132">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="5372d-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5372d-133">See Also</span></span>  
 [<span data-ttu-id="5372d-134">sp_update_alert &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5372d-134">sp_update_alert &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
  
