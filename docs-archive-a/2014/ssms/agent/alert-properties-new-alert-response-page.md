---
title: Proprietà avviso-nuovo avviso (pagina risposta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.response.f1
ms.assetid: 72daf008-f9ea-4077-b217-5048e7759d3e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 34e7f11ff3210ec4fc1835751bc35b140d3fa0ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722223"
---
# <a name="alert-properties-new-alert-response-page"></a><span data-ttu-id="a42b0-102">Proprietà avviso-nuovo avviso (pagina risposta)</span><span class="sxs-lookup"><span data-stu-id="a42b0-102">Alert Properties-New Alert (Response Page)</span></span>
  <span data-ttu-id="a42b0-103">Utilizzare questa pagina per specificare un processo che si desidera eseguire e per ottenere un elenco di operatori da notificare in risposta a un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avviso di Agent.</span><span class="sxs-lookup"><span data-stu-id="a42b0-103">Use this page to specify a job that you want to run and to obtain a list of operators to be notified in response to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a42b0-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a42b0-104">Options</span></span>  
 <span data-ttu-id="a42b0-105">**Esegui processo**</span><span class="sxs-lookup"><span data-stu-id="a42b0-105">**Execute job**</span></span>  
 <span data-ttu-id="a42b0-106">Abilita le opzioni **Elenco processi**, **Nuovo processo** e **Visualizza processo** .</span><span class="sxs-lookup"><span data-stu-id="a42b0-106">Enables the **Job list**, **New job** and **View job** options.</span></span>  
  
 <span data-ttu-id="a42b0-107">**Nuovo processo**</span><span class="sxs-lookup"><span data-stu-id="a42b0-107">**New job**</span></span>  
 <span data-ttu-id="a42b0-108">Apre la finestra di dialogo **Nuovo processo** .</span><span class="sxs-lookup"><span data-stu-id="a42b0-108">Open the **New Job** dialog box.</span></span> <span data-ttu-id="a42b0-109">Questo pulsante non è disponibile se l'opzione **Esegui processo** non è selezionata.</span><span class="sxs-lookup"><span data-stu-id="a42b0-109">This button is not available when **Execute job** is not selected.</span></span>  
  
 <span data-ttu-id="a42b0-110">**Visualizzare il processo**</span><span class="sxs-lookup"><span data-stu-id="a42b0-110">**View job**</span></span>  
 <span data-ttu-id="a42b0-111">Consente di visualizzare o modificare il processo selezionato.</span><span class="sxs-lookup"><span data-stu-id="a42b0-111">View or modify the selected job.</span></span> <span data-ttu-id="a42b0-112">Questa opzione non è disponibile se l'opzione **Esegui processo** non è selezionata.</span><span class="sxs-lookup"><span data-stu-id="a42b0-112">This option is not available when **Execute job** is not selected.</span></span>  
  
 <span data-ttu-id="a42b0-113">**Invia notifica a operatori**</span><span class="sxs-lookup"><span data-stu-id="a42b0-113">**Notify operators**</span></span>  
 <span data-ttu-id="a42b0-114">Consente di abilitare i controlli che consentono di aggiungere, rimuovere o modificare operatori.</span><span class="sxs-lookup"><span data-stu-id="a42b0-114">Enables the controls that allow you to add, remove, or change operators.</span></span>  
  
 <span data-ttu-id="a42b0-115">**Elenco operatori**</span><span class="sxs-lookup"><span data-stu-id="a42b0-115">**Operator list**</span></span>  
 <span data-ttu-id="a42b0-116">In questo elenco sono presenti gli operatori da utilizzare per notificare che si è verificato un avviso.</span><span class="sxs-lookup"><span data-stu-id="a42b0-116">Lists the operators to notify when an alert occurs.</span></span> <span data-ttu-id="a42b0-117">Per specificare un metodo di notifica, selezionare la casella di controllo **Posta elettronica**, **Cercapersone**o **Net send** visualizzate dopo il nome dell'operatore. Questa opzione non disponibile se l'opzione **Invia notifica a operatori** non è selezionata.</span><span class="sxs-lookup"><span data-stu-id="a42b0-117">To specify a notification method, select the **E-mail**, **Pager**, or **Net send** check box that is displayed after the operator name.This option not available when **Notify operators** is not selected.</span></span>  
  
 <span data-ttu-id="a42b0-118">**Posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="a42b0-118">**E-mail**</span></span>  
 <span data-ttu-id="a42b0-119">Consente di utilizzare la posta elettronica per l'invio della notifica all'operatore.</span><span class="sxs-lookup"><span data-stu-id="a42b0-119">Use e-mail to notify the operator.</span></span>  
  
 <span data-ttu-id="a42b0-120">**Cercapersone**</span><span class="sxs-lookup"><span data-stu-id="a42b0-120">**Pager**</span></span>  
 <span data-ttu-id="a42b0-121">Utilizzare l'indirizzo di posta elettronica del cercapersone per l'invio della notifica all'operatore.</span><span class="sxs-lookup"><span data-stu-id="a42b0-121">Use the pager e-mail address to notify the operator.</span></span>  
  
 <span data-ttu-id="a42b0-122">**NET SEND**</span><span class="sxs-lookup"><span data-stu-id="a42b0-122">**Net send**</span></span>  
 <span data-ttu-id="a42b0-123">Usare **Net Send** per l'invio della notifica all'operatore.</span><span class="sxs-lookup"><span data-stu-id="a42b0-123">Use **net send** to notify the operator.</span></span>  
  
 <span data-ttu-id="a42b0-124">**Operatore New**</span><span class="sxs-lookup"><span data-stu-id="a42b0-124">**New operator**</span></span>  
 <span data-ttu-id="a42b0-125">Visualizza la finestra di dialogo **Nuovo operatore** in cui è possibile creare un nuovo operatore.</span><span class="sxs-lookup"><span data-stu-id="a42b0-125">Displays the **New Operator** dialog box, which you can use to create a new operator.</span></span>  
  
 <span data-ttu-id="a42b0-126">**Visualizza operatore**</span><span class="sxs-lookup"><span data-stu-id="a42b0-126">**View operator**</span></span>  
 <span data-ttu-id="a42b0-127">Visualizza la finestra di dialogo **Proprietà** per l'operatore attualmente selezionato.</span><span class="sxs-lookup"><span data-stu-id="a42b0-127">Displays the **Properties** dialog box for the currently selected operator.</span></span> <span data-ttu-id="a42b0-128">È possibile visualizzare e modificare le proprietà dell'operatore nella finestra di dialogo **Proprietà operatore**.</span><span class="sxs-lookup"><span data-stu-id="a42b0-128">You can view and modified operator properties on the **Operator Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a42b0-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a42b0-129">See Also</span></span>  
 <span data-ttu-id="a42b0-130">[Avvisi](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="a42b0-130">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="a42b0-131">[Creare un avviso utilizzando il livello di gravità](create-an-alert-using-severity-level.md) </span><span class="sxs-lookup"><span data-stu-id="a42b0-131">[Create an Alert Using Severity Level](create-an-alert-using-severity-level.md) </span></span>  
 <span data-ttu-id="a42b0-132">[Avvisi](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="a42b0-132">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="a42b0-133">[Modificare un avviso](edit-an-alert.md) </span><span class="sxs-lookup"><span data-stu-id="a42b0-133">[Edit an Alert](edit-an-alert.md) </span></span>  
 [<span data-ttu-id="a42b0-134">Delete an Alert</span><span class="sxs-lookup"><span data-stu-id="a42b0-134">Delete an Alert</span></span>](delete-an-alert.md)  
  
  
