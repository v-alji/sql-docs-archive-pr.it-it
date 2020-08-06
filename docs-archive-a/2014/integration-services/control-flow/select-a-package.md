---
title: Seleziona pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.selectapackage.f1
helpviewer_keywords:
- Select a Package dialog box
ms.assetid: 92b47a2b-21b5-460a-885d-6cc4bb567249
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b35276791b004a011a1c2656057046be05ed6770
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623433"
---
# <a name="select-a-package"></a><span data-ttu-id="bc7d4-102">Seleziona pacchetto</span><span class="sxs-lookup"><span data-stu-id="bc7d4-102">Select a Package</span></span>
  <span data-ttu-id="bc7d4-103">Utilizzare la finestra di dialogo **Seleziona pacchetto** per specificare il pacchetto da cui l'attività Message Queue può ricevere messaggi.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-103">Use the **Select a Package** dialog box to specify the package from which the Message Queue task can receive messages.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="bc7d4-104">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="bc7d4-104">Static Options</span></span>  
 <span data-ttu-id="bc7d4-105">**Posizione**</span><span class="sxs-lookup"><span data-stu-id="bc7d4-105">**Location**</span></span>  
 <span data-ttu-id="bc7d4-106">Consente di specificare il percorso del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-106">Specify the location of the package.</span></span> <span data-ttu-id="bc7d4-107">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-107">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="bc7d4-108">valore</span><span class="sxs-lookup"><span data-stu-id="bc7d4-108">Value</span></span>|<span data-ttu-id="bc7d4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bc7d4-109">Description</span></span>|  
|-----------|-----------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<span data-ttu-id="bc7d4-110">Impostare il percorso su un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bc7d4-110">Set the location to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bc7d4-111">Se si seleziona questo valore vengono visualizzate le opzioni dinamiche **Server**, **Usa autenticazione di Windows**, **Usa autenticazione di SQL Server**, **Nome utente**e **Password**.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-111">Selecting this value displays the dynamic options, **Server**, **Use Windows Authentication**, **Use SQL Server Authentication**, **User name**, and **Password**.</span></span>|  
|<span data-ttu-id="bc7d4-112">File DTSX</span><span class="sxs-lookup"><span data-stu-id="bc7d4-112">DTSX file</span></span>|<span data-ttu-id="bc7d4-113">Consente di impostare il percorso su un file DTSX.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-113">Set the location to a DTSX file.</span></span> <span data-ttu-id="bc7d4-114">Se si seleziona questo valore viene visualizzata l'opzione dinamica **Nome file**.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-114">Selecting this value displays the dynamic option, **File name**.</span></span>|  
  
## <a name="location-dynamic-options"></a><span data-ttu-id="bc7d4-115">Opzioni dinamiche relative al percorso</span><span class="sxs-lookup"><span data-stu-id="bc7d4-115">Location Dynamic Options</span></span>  
  
### <a name="location--sql-server"></a><span data-ttu-id="bc7d4-116">Percorso = SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc7d4-116">Location = SQL Server</span></span>  
 <span data-ttu-id="bc7d4-117">**Nome pacchetto**</span><span class="sxs-lookup"><span data-stu-id="bc7d4-117">**Package name**</span></span>  
 <span data-ttu-id="bc7d4-118">Consente di selezionare un pacchetto archiviato nel server specificato.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-118">Select a package that is stored on the specified server.</span></span>  
  
 <span data-ttu-id="bc7d4-119">**Server**</span><span class="sxs-lookup"><span data-stu-id="bc7d4-119">**Server**</span></span>  
 <span data-ttu-id="bc7d4-120">Consente di specificare il nome del server o di selezionarlo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-120">Provide a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="bc7d4-121">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="bc7d4-121">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="bc7d4-122">Fare clic su questa opzione per utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-122">Click to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="bc7d4-123">**Usa autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="bc7d4-123">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="bc7d4-124">Fare clic su questa opzione per usare l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc7d4-124">Click to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="bc7d4-125">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="bc7d4-125">**User name**</span></span>  
 <span data-ttu-id="bc7d4-126">Se si usa l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , specificare il nome utente da usare per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-126">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a user name to use when logging on to the server.</span></span>  
  
 <span data-ttu-id="bc7d4-127">**Password**</span><span class="sxs-lookup"><span data-stu-id="bc7d4-127">**Password**</span></span>  
 <span data-ttu-id="bc7d4-128">Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , specificare una password.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-128">If using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
### <a name="location--dtsx-file"></a><span data-ttu-id="bc7d4-129">Percorso = File DTSX</span><span class="sxs-lookup"><span data-stu-id="bc7d4-129">Location = DTSX file</span></span>  
 <span data-ttu-id="bc7d4-130">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="bc7d4-130">**File name**</span></span>  
 <span data-ttu-id="bc7d4-131">Specificare il percorso di un pacchetto oppure fare clic sul pulsante Sfoglia **(...)** per trovare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="bc7d4-131">Provide the path of a package or click the browse button **(...)** and locate the package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc7d4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc7d4-132">See Also</span></span>  
 [<span data-ttu-id="bc7d4-133">Attività Message Queue</span><span class="sxs-lookup"><span data-stu-id="bc7d4-133">Message Queue Task</span></span>](message-queue-task.md)  
  
  
