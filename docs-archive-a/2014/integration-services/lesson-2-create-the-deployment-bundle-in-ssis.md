---
title: 'Lezione 2: creazione del pacchetto di distribuzione | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab17289d-c3d4-4a5e-b7f5-4fea8ae21707
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 927bcd393e4b54e92971c197d93dcc1e2804dcd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635115"
---
# <a name="lesson-2-creating-the-deployment-bundle"></a><span data-ttu-id="bd134-102">Lezione 2: Creazione del pacchetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="bd134-102">Lesson 2: Creating the Deployment Bundle</span></span>
  <span data-ttu-id="bd134-103">Nella lezione 1, [Preparazione alla creazione del pacchetto di distribuzione](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md), è stato creato il progetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] denominato Deployment Tutorial, sono stati aggiunti i pacchetti e i file di supporto al progetto e sono state implementate le configurazioni nei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="bd134-103">In [Lesson 1: Preparing to Create the Deployment Bundle](../integration-services/lesson-1-preparing-to-create-the-deployment-bundle.md), you created the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project named Deployment Tutorial, added the packages and supporting files to the project, and implemented configurations in packages.</span></span>  
  
 <span data-ttu-id="bd134-104">In questa lezione si procederà alla creazione del pacchetto di distribuzione, ovvero una cartella contenente gli elementi necessari per installare i pacchetti in un altro computer.</span><span class="sxs-lookup"><span data-stu-id="bd134-104">In this lesson, you will create the deployment bundle, which is a folder that contains the items that you need to install packages on another computer.</span></span> <span data-ttu-id="bd134-105">Nel pacchetto di distribuzione verranno inclusi un manifesto di distribuzione, copie dei pacchetti e copie dei file di supporto del progetto Deployment Tutorial.</span><span class="sxs-lookup"><span data-stu-id="bd134-105">The deployment bundle will include a deployment manifest, copies of the packages, and copies of the supporting files from the Deployment Tutorial project.</span></span> <span data-ttu-id="bd134-106">Nel manifesto di distribuzione vengono elencati i pacchetti, i file esterni e le configurazioni incluse nel pacchetto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bd134-106">The deployment manifest lists the packages, miscellaneous files, and configurations in the deployment bundle.</span></span>  
  
 <span data-ttu-id="bd134-107">Verrà inoltre verificato l'elenco dei file inclusi nel pacchetto di distribuzione ed esaminati i contenuti del manifesto.</span><span class="sxs-lookup"><span data-stu-id="bd134-107">You will also verify the file list in the deployment bundle and examine the contents of the manifest.</span></span>  
  
 <span data-ttu-id="bd134-108">**Tempo stimato per il completamento della lezione:** 30 minuti</span><span class="sxs-lookup"><span data-stu-id="bd134-108">**Estimated time to complete this lesson:** 30 minutes</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="bd134-109">Argomenti della lezione</span><span class="sxs-lookup"><span data-stu-id="bd134-109">Lesson Tasks</span></span>  
 <span data-ttu-id="bd134-110">In questa lezione sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="bd134-110">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="bd134-111">Passaggio 1: Compilazione dell'utilità di distribuzione</span><span class="sxs-lookup"><span data-stu-id="bd134-111">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
-   [<span data-ttu-id="bd134-112">Passaggio 2: Verifica del pacchetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="bd134-112">Step 2: Verifying the Deployment Bundle</span></span>](../integration-services/lesson-2-2-verifying-the-deployment-bundle.md)  
  
## <a name="start-the-lesson"></a><span data-ttu-id="bd134-113">Inizio della lezione</span><span class="sxs-lookup"><span data-stu-id="bd134-113">Start the Lesson</span></span>  
 [<span data-ttu-id="bd134-114">Passaggio 1: Compilazione dell'utilità di distribuzione</span><span class="sxs-lookup"><span data-stu-id="bd134-114">Step 1: Building the Deployment Utility</span></span>](../integration-services/lesson-2-1-building-the-deployment-utility.md)  
  
<span data-ttu-id="bd134-115">![Integration Services icona (piccola)](media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="bd134-115">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="bd134-116">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="bd134-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="bd134-117">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="bd134-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="bd134-118">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="bd134-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
