---
title: Applicazione sqlagent90 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- starting SQL Server Agent
- sqlagent90 application
- SQL Server Agent, starting
- command prompt utilities [SQL Server], sqlagent90
ms.assetid: e8b80e8d-d0c9-4500-a868-0ce08233da08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 290cb69f39aa3b08bb290c210b2d37977614a1ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626430"
---
# <a name="sqlagent90-application"></a><span data-ttu-id="66777-102">sqlagent90 - applicazione</span><span class="sxs-lookup"><span data-stu-id="66777-102">sqlagent90 Application</span></span>
  <span data-ttu-id="66777-103">L'applicazione **sqlagent90** avvia [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="66777-103">The **sqlagent90** application starts [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent from the command prompt.</span></span> <span data-ttu-id="66777-104">In genere, è consigliabile eseguire [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent da [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] oppure utilizzando i metodi SQL-DMO in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="66777-104">Usually, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should be run from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or by using SQL-SMO methods in an application.</span></span> <span data-ttu-id="66777-105">Eseguire **sqlagent90** dal prompt dei comandi solo per attività di diagnostica su [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent o se viene richiesto dal personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="66777-105">Only run **sqlagent90** from the command prompt when you are diagnosing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, or when you are directed to it by your primary support provider.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66777-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66777-106">Syntax</span></span>  
  
```  
  
sqlagent90  
-c [-v] [-iinstance_name]  
```  
  
## <a name="arguments"></a><span data-ttu-id="66777-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="66777-107">Arguments</span></span>  
 <span data-ttu-id="66777-108">**-c**</span><span class="sxs-lookup"><span data-stu-id="66777-108">**-c**</span></span>  
 <span data-ttu-id="66777-109">Indica che [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent viene eseguito dal prompt dei comandi ed è indipendente da Gestione controllo servizi di Windows.</span><span class="sxs-lookup"><span data-stu-id="66777-109">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent is running from the command prompt and is independent of the Microsoft Windows Services Control Manager.</span></span> <span data-ttu-id="66777-110">Se si utilizza **-c** , non è possibile controllare [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent utilizzando l'applicazione Servizi in Strumenti di amministrazione oppure Gestione configurazione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66777-110">When **-c** is used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent cannot be controlled from either the Services application in Administrative Tools or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="66777-111">Questo argomento è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="66777-111">This argument is mandatory.</span></span>  
  
 <span data-ttu-id="66777-112">**-v**</span><span class="sxs-lookup"><span data-stu-id="66777-112">**-v**</span></span>  
 <span data-ttu-id="66777-113">Indica l'esecuzione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent in modalità dettagliata e attiva la scrittura delle informazioni di diagnostica nella finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="66777-113">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent runs in verbose mode and writes diagnostic information to the command-prompt window.</span></span> <span data-ttu-id="66777-114">Le informazioni di diagnostica sono uguali a quelle scritte nel log degli errori di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="66777-114">The diagnostic information is the same as the information written to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error log.</span></span>  
  
 <span data-ttu-id="66777-115">**-i** *instance_name*</span><span class="sxs-lookup"><span data-stu-id="66777-115">**-i** *instance_name*</span></span>  
 <span data-ttu-id="66777-116">Indica che [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent si connette all'istanza denominata di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] specificata da *instance_name*.</span><span class="sxs-lookup"><span data-stu-id="66777-116">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent connects to the named [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance specified by *instance_name*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66777-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="66777-117">Remarks</span></span>  
 <span data-ttu-id="66777-118">Dopo il messaggio del copyright, **sqlagent90** visualizza l'output nella finestra del prompt dei comandi solo quando è specificata l'opzione **-v** .</span><span class="sxs-lookup"><span data-stu-id="66777-118">After displaying a copyright message, **sqlagent90** displays output in the command prompt window only when the **-v** switch is specified.</span></span> <span data-ttu-id="66777-119">Per arrestare **sqlagent90**, premere CTRL+C al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="66777-119">To stop **sqlagent90**, press CTRL+C at the command prompt.</span></span> <span data-ttu-id="66777-120">Non chiudere la finestra del prompt dei comandi senza aver arrestato **sqlagent90**.</span><span class="sxs-lookup"><span data-stu-id="66777-120">Do not close the command-prompt window before stopping **sqlagent90**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66777-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66777-121">See Also</span></span>  
 [<span data-ttu-id="66777-122">Automatizzazione delle attività amministrative &#40;SQL Server Agent&#41;</span><span class="sxs-lookup"><span data-stu-id="66777-122">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../ssms/agent/automated-administration-tasks-sql-server-agent.md)  
  
  
