---
title: 'Passaggio 1: Copia del pacchetto di distribuzione| Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6ef1e56-d278-4a24-afd3-68d8e0595cbb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 326a85a4d04fc22382457b4e2e919f81096ce989
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637427"
---
# <a name="step-1-copying-the-deployment-bundle"></a><span data-ttu-id="4b91e-102">Passaggio 1: Copia del pacchetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="4b91e-102">Step 1: Copying the Deployment Bundle</span></span>
  <span data-ttu-id="4b91e-103">In questa attività si procederà alla copia del pacchetto di distribuzione nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4b91e-103">In this task, you will copy the deployment bundle to the destination computer.</span></span>  
  
 <span data-ttu-id="4b91e-104">Il modo più semplice per copiare il pacchetto di distribuzione nel computer di destinazione consiste innanzitutto nella creazione di una condivisione pubblica in tale computer, l'esecuzione del mapping di un'unità alla condivisione pubblica e quindi la copia in quest'ultima del pacchetto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4b91e-104">The easiest way to copy the deployment bundle to the destination computer is to first create a public share on the destination computer, map a drive to the public share, and then copy the deployment bundle to the share.</span></span> <span data-ttu-id="4b91e-105">Se sono necessarie informazioni su come creare e configurare le cartelle pubbliche oppure il mapping delle unità, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="4b91e-105">If you do not know how to create and configure public folders or map drives, see the Windows documentation.</span></span>  
  
### <a name="to-copy-the-deployment-bundle"></a><span data-ttu-id="4b91e-106">Per copiare il pacchetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="4b91e-106">To copy the deployment bundle</span></span>  
  
1.  <span data-ttu-id="4b91e-107">Individuare il pacchetto di distribuzione nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="4b91e-107">Locate the deployment bundle on your computer.</span></span>  
  
     <span data-ttu-id="4b91e-108">Se si è utilizzato il percorso predefinito, il pacchetto di distribuzione si trova nella cartella Bin\Deployment all'interno della cartella Deployment Tutorial.</span><span class="sxs-lookup"><span data-stu-id="4b91e-108">If you used the default location, the deployment bundle is the Bin\Deployment folder within the Deployment Tutorial folder.</span></span>  
  
2.  <span data-ttu-id="4b91e-109">Fare clic con il pulsante destro del mouse sulla cartella Deployment e scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="4b91e-109">Right-click the Deployment folder and click **Copy**.</span></span>  
  
3.  <span data-ttu-id="4b91e-110">Individuare la condivisione pubblica in cui si desidera copiare la cartella nel computer di destinazione e scegliere **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="4b91e-110">Locate the public share to which you want to copy the folder on the target computer and click **Paste**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4b91e-111">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="4b91e-111">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4b91e-112">Passaggio 2: Esecuzione dell'Installazione guidata pacchetti</span><span class="sxs-lookup"><span data-stu-id="4b91e-112">Step 2: Running the Package Installation Wizard</span></span>](../integration-services/lesson-3-2-running-the-package-installation-wizard.md)  
  
<span data-ttu-id="4b91e-113">![Integration Services icona (piccola)](media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4b91e-113">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4b91e-114">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="4b91e-114">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4b91e-115">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="4b91e-115">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4b91e-116">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="4b91e-116">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
