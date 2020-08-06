---
title: Configurazione client di Riesecuzione distribuita | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccf03e32-6bd9-43c0-b9b6-9fe0d9163339
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 53124029483c25ed7894b279283e1de02c647350
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637616"
---
# <a name="distributed-replay-client-configuration"></a><span data-ttu-id="23ae2-102">Configurazione client Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="23ae2-102">Distributed Replay Client Configuration</span></span>
  <span data-ttu-id="23ae2-103">Usare la pagina di **Configurazione client Riesecuzione distribuita** dell'Installazione guidata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per specificare gli utenti a cui si desidera concedere autorizzazioni amministrative per il servizio client Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="23ae2-103">Use the **Distributed Replay Client Configuration** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the users you want to grant administrative permissions to for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="23ae2-104">Gli utenti che dispongono di autorizzazioni amministrative disporranno di accesso illimitato al servizio client Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="23ae2-104">Users that have administrative permissions will have unlimited access to the Distributed Replay client service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="23ae2-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="23ae2-105">Options</span></span>  
 <span data-ttu-id="23ae2-106">**Nome controller**</span><span class="sxs-lookup"><span data-stu-id="23ae2-106">**Controller Name**</span></span>  
 <span data-ttu-id="23ae2-107">Si tratta di un parametro facoltativo e il valore predefinito è \<*blank*> .</span><span class="sxs-lookup"><span data-stu-id="23ae2-107">This is an optional parameter, and the default value is \<*blank*>.</span></span>  
  
 <span data-ttu-id="23ae2-108">Immettere il nome del controller che il computer client comunicherà con per il servizio client Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="23ae2-108">Enter the name of the controller that the client computer will communicate with for the Distributed Replay client service.</span></span> <span data-ttu-id="23ae2-109">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="23ae2-109">Note the following:</span></span>  
  
-   <span data-ttu-id="23ae2-110">Il nome deve essere un nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="23ae2-110">The name must be a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="23ae2-111">Ad esempio, è possibile che un host denominato server1 nella gerarchia dei prodotti di Microsoft disponga di un nome di dominio completo server1.products.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="23ae2-111">For example, a host called server1 in the products hierarchy at Microsoft may have an FQDN of server1.products.microsoft.com.</span></span>  
  
-   <span data-ttu-id="23ae2-112">Se è già stato configurato un controller, immettere il nome del controller durante la configurazione di ciascuno client.</span><span class="sxs-lookup"><span data-stu-id="23ae2-112">If you have already set up a controller, enter the name of the controller while configuring each client.</span></span>  
  
-   <span data-ttu-id="23ae2-113">In caso contrario, è possibile lasciare vuoto il nome del controller.</span><span class="sxs-lookup"><span data-stu-id="23ae2-113">If you have net yet set up a controller, you can leave the controller name blank.</span></span> <span data-ttu-id="23ae2-114">Tuttavia, è necessario immettere manualmente il nome del controller nel file **configurazione client** .</span><span class="sxs-lookup"><span data-stu-id="23ae2-114">However, you must manually enter the controller name in the **client configuration** file.</span></span>  
  
 <span data-ttu-id="23ae2-115">**Directory di lavoro**</span><span class="sxs-lookup"><span data-stu-id="23ae2-115">**Working Directory**</span></span>  
 <span data-ttu-id="23ae2-116">Specificare la directory di lavoro per il servizio client Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="23ae2-116">Specify the working directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="23ae2-117">La directory di lavoro predefinita è \<*drive letter*>:\Programmi\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span><span class="sxs-lookup"><span data-stu-id="23ae2-117">The default working directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span></span>  
  
 <span data-ttu-id="23ae2-118">**Directory dei risultati**</span><span class="sxs-lookup"><span data-stu-id="23ae2-118">**Result Directory**</span></span>  
 <span data-ttu-id="23ae2-119">Specificare la directory dei risultati per il servizio client Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="23ae2-119">Specify the result directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="23ae2-120">La directory dei risultati predefinita è \<*drive letter*>:\Programmi\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span><span class="sxs-lookup"><span data-stu-id="23ae2-120">The default result directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span></span>  
  
  
