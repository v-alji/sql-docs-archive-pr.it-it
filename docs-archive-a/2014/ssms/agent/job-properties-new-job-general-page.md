---
title: Proprietà processo e nuovo processo (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.general.f1
ms.assetid: b6832840-1c18-4db8-94fc-080db880ae9f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7a5d2ab84ed211a03a3c217bd5f4cd54453a4dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715011"
---
# <a name="job-properties-and-new-job-general-page"></a><span data-ttu-id="65313-102">Proprietà processo e Nuovo processo (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="65313-102">Job Properties and New Job (General Page)</span></span>
  <span data-ttu-id="65313-103">Utilizzare questa pagina per visualizzare e modificare le proprietà generali di un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processo di Agent.</span><span class="sxs-lookup"><span data-stu-id="65313-103">Use this page to view and modify the general properties of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span>  
  
## <a name="options"></a><span data-ttu-id="65313-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="65313-104">Options</span></span>  
 <span data-ttu-id="65313-105">**Nome**</span><span class="sxs-lookup"><span data-stu-id="65313-105">**Name**</span></span>  
 <span data-ttu-id="65313-106">Consente di modificare il nome del processo.</span><span class="sxs-lookup"><span data-stu-id="65313-106">Change the name of the job.</span></span>  
  
 <span data-ttu-id="65313-107">**Proprietario**</span><span class="sxs-lookup"><span data-stu-id="65313-107">**Owner**</span></span>  
 <span data-ttu-id="65313-108">Consente di selezionare un proprietario per il processo.</span><span class="sxs-lookup"><span data-stu-id="65313-108">Select the owner for the job.</span></span>  
  
 <span data-ttu-id="65313-109">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="65313-109">**Category**</span></span>  
 <span data-ttu-id="65313-110">Consente di selezionare una categoria di processi per il processo.</span><span class="sxs-lookup"><span data-stu-id="65313-110">Select the job category for the job.</span></span>  
  
 <span data-ttu-id="65313-111">**...**</span><span class="sxs-lookup"><span data-stu-id="65313-111">**...**</span></span>  
 <span data-ttu-id="65313-112">Consente di visualizzare i processi della categoria selezionata.</span><span class="sxs-lookup"><span data-stu-id="65313-112">View the jobs in the selected category.</span></span>  
  
 <span data-ttu-id="65313-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="65313-113">**Description**</span></span>  
 <span data-ttu-id="65313-114">Consente di modificare la descrizione del processo.</span><span class="sxs-lookup"><span data-stu-id="65313-114">Change the description of the job.</span></span>  
  
 <span data-ttu-id="65313-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="65313-115">**Enabled**</span></span>  
 <span data-ttu-id="65313-116">Consente di abilitare il processo.</span><span class="sxs-lookup"><span data-stu-id="65313-116">Enable the job.</span></span> <span data-ttu-id="65313-117">Quando non è abilitato, il processo non viene eseguito in risposta a una pianificazione o a un avviso, sebbene sia comunque possibile avviare il processo usando la stored procedure **sp_start_job** .</span><span class="sxs-lookup"><span data-stu-id="65313-117">When the job is not enabled, the job does not run in response to a schedule or an alert, although you can still start the job using the **sp_start_job** stored procedure.</span></span>  
  
 <span data-ttu-id="65313-118">**Origine**</span><span class="sxs-lookup"><span data-stu-id="65313-118">**Source**</span></span>  
 <span data-ttu-id="65313-119">Visualizza il server master per il processo.</span><span class="sxs-lookup"><span data-stu-id="65313-119">Displays the master server for the job.</span></span> <span data-ttu-id="65313-120">Questa opzione è disponibile solo nella pagina **Proprietà processo - Generale** .</span><span class="sxs-lookup"><span data-stu-id="65313-120">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="65313-121">**Creato**</span><span class="sxs-lookup"><span data-stu-id="65313-121">**Created**</span></span>  
 <span data-ttu-id="65313-122">Visualizza la data e l'ora di creazione del processo.</span><span class="sxs-lookup"><span data-stu-id="65313-122">Displays the date and time that the job was created.</span></span> <span data-ttu-id="65313-123">Questa opzione è disponibile solo nella pagina **Proprietà processo - Generale** .</span><span class="sxs-lookup"><span data-stu-id="65313-123">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="65313-124">**Data Ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="65313-124">**Last modified**</span></span>  
 <span data-ttu-id="65313-125">Visualizza la data e l'ora dell'ultima modifica apportata al processo.</span><span class="sxs-lookup"><span data-stu-id="65313-125">Displays the date and time that the job was last modified.</span></span> <span data-ttu-id="65313-126">Questa opzione è disponibile solo nella pagina **Proprietà processo - Generale** .</span><span class="sxs-lookup"><span data-stu-id="65313-126">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="65313-127">**Data ultima esecuzione**</span><span class="sxs-lookup"><span data-stu-id="65313-127">**Last executed**</span></span>  
 <span data-ttu-id="65313-128">Visualizza la data e l'ora dell'ultima esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="65313-128">Displays the date and time that the job last started running.</span></span> <span data-ttu-id="65313-129">Questa opzione è disponibile solo nella pagina **Proprietà processo - Generale** .</span><span class="sxs-lookup"><span data-stu-id="65313-129">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
 <span data-ttu-id="65313-130">**Visualizza cronologia processo**</span><span class="sxs-lookup"><span data-stu-id="65313-130">**View Job History**</span></span>  
 <span data-ttu-id="65313-131">Consente di visualizzare la cronologia processo per il processo.</span><span class="sxs-lookup"><span data-stu-id="65313-131">View the job history for the job.</span></span> <span data-ttu-id="65313-132">Questa opzione è disponibile solo nella pagina **Proprietà processo - Generale** .</span><span class="sxs-lookup"><span data-stu-id="65313-132">Only available on the **Job PropertiesGeneral** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65313-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65313-133">See Also</span></span>  
 <span data-ttu-id="65313-134">[Implementazione di processi](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="65313-134">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="65313-135">Categorie di processi: Gestisci categorie di processi</span><span class="sxs-lookup"><span data-stu-id="65313-135">Job Categories: Manage Job Categories</span></span>](job-categories-manage-job-categories.md)  
  
  
