---
title: 'Lezione 3: aggiunta della registrazione | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 64cd24cc-ba8e-4bd7-b10b-6b80d8b04af6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 58fcc29759f19ad215a76a1b9ed9bf313b4c869c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627885"
---
# <a name="lesson-3-adding-logging"></a><span data-ttu-id="353cd-102">Lezione 3: Aggiunta delle funzionalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="353cd-102">Lesson 3: Adding Logging</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="353cd-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] include funzionalità di registrazione che consentono di risolvere i problemi e monitorare l'esecuzione dei pacchetti offrendo una traccia degli eventi generati dalle attività e dai contenitori.</span><span class="sxs-lookup"><span data-stu-id="353cd-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes logging features that let you troubleshoot and monitor package execution by providing a trace of task and container events.</span></span> <span data-ttu-id="353cd-104">Le caratteristiche di registrazione sono flessibili ed è possibile attivarle a livello di pacchetto o a livello di singole attività o contenitori del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="353cd-104">The logging features are flexible, and can be enabled at the package level or on individual tasks and containers within the package.</span></span> <span data-ttu-id="353cd-105">È possibile selezionare gli eventi che si desidera registrare e creare più log per un singolo pacchetto.</span><span class="sxs-lookup"><span data-stu-id="353cd-105">You can select which events you want to log, and create multiple logs against a single package.</span></span>  
  
 <span data-ttu-id="353cd-106">La registrazione è garantita da un provider di log.</span><span class="sxs-lookup"><span data-stu-id="353cd-106">Logging is provided by a log provider.</span></span> <span data-ttu-id="353cd-107">Ogni provider di log è in grado di scrivere le informazioni di registrazione in diversi formati e tipi di destinazione.</span><span class="sxs-lookup"><span data-stu-id="353cd-107">Each log provider can write logging information to different formats and destination types.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="353cd-108">rende disponibili i provider di log seguenti:</span><span class="sxs-lookup"><span data-stu-id="353cd-108">provides the following log providers:</span></span>  
  
-   <span data-ttu-id="353cd-109">File di testo</span><span class="sxs-lookup"><span data-stu-id="353cd-109">Text file</span></span>  
  
-   [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)]  
  
-   <span data-ttu-id="353cd-110">Registro eventi di Windows</span><span class="sxs-lookup"><span data-stu-id="353cd-110">Windows Event log</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]  
  
-   <span data-ttu-id="353cd-111">File XML</span><span class="sxs-lookup"><span data-stu-id="353cd-111">XML file</span></span>  
  
 <span data-ttu-id="353cd-112">In questa lezione verrà creata una copia del pacchetto creato nella [lezione 2: aggiunta del ciclo](lesson-2-adding-looping-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="353cd-112">In this lesson, you will create a copy of the package that you created in [Lesson 2: Adding Looping](lesson-2-adding-looping-with-ssis.md).</span></span> <span data-ttu-id="353cd-113">Usando questo nuovo pacchetto, verranno aggiunte e configurate funzionalità di registrazione per monitorare eventi specifici durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="353cd-113">Working with this new package, you will then add and configure logging to monitor specific events during package execution.</span></span> <span data-ttu-id="353cd-114">Se non è stata completata nessuna delle lezioni precedenti, è possibile copiare il pacchetto della lezione 2 completato incluso nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="353cd-114">If you have not completed any of the previous lessons, you can also copy the completed Lesson 2 package that is included with the tutorial.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="353cd-115">Per eseguire questa esercitazione, è necessario il database di esempio **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="353cd-115">This tutorial requires the **AdventureWorksDW2012** sample database.</span></span> <span data-ttu-id="353cd-116">Per altre informazioni su come installare e distribuire **AdventureWorksDW2012**, [Reporting Services esempi di prodotto su GitHub](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="353cd-116">For more information about how to install and deploy **AdventureWorksDW2012**, [Reporting Services Product Samples on GitHub](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="353cd-117">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="353cd-117">Lesson Tasks</span></span>  
 <span data-ttu-id="353cd-118">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="353cd-118">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="353cd-119">Passaggio 1: Copia del pacchetto della lezione 2</span><span class="sxs-lookup"><span data-stu-id="353cd-119">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
-   [<span data-ttu-id="353cd-120">Passaggio 2: Aggiunta e configurazione di funzionalità di registrazione</span><span class="sxs-lookup"><span data-stu-id="353cd-120">Step 2: Adding and Configuring Logging</span></span>](lesson-3-2-adding-and-configuring-logging.md)  
  
-   [<span data-ttu-id="353cd-121">Passaggio 3: Test del pacchetto creato nella lezione 3 dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="353cd-121">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="353cd-122">Inizio della lezione</span><span class="sxs-lookup"><span data-stu-id="353cd-122">Start the Lesson</span></span>  
 [<span data-ttu-id="353cd-123">Passaggio 1: Copia del pacchetto della lezione 2</span><span class="sxs-lookup"><span data-stu-id="353cd-123">Step 1: Copying the Lesson 2 Package</span></span>](lesson-3-1-copying-the-lesson-2-package.md)  
  
  
