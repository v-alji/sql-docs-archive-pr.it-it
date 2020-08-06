---
title: Report per la risoluzione dei problemi relativi all'esecuzione dei pacchetti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fc476ac-bd69-434e-9636-70776e0b3b6c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b20d9c9c02af3f3df96e2ef46a7b25251793fa55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635112"
---
# <a name="troubleshooting-reports-for-package-execution"></a><span data-ttu-id="b90da-102">Risoluzione dei problemi relativi ai report per l'esecuzione del pacchetto</span><span class="sxs-lookup"><span data-stu-id="b90da-102">Troubleshooting Reports for Package Execution</span></span>
  <span data-ttu-id="b90da-103">Nella versione corrente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] sono disponibili report standard per il monitoraggio e la risoluzione dei problemi relativi ai pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] distribuiti nel catalogo di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b90da-103">In the current release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], standard reports are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to help you monitor and troubleshoot [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages that have been deployed to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] catalog.</span></span> <span data-ttu-id="b90da-104">Due di queste report relativi a pacchetti, in particolare, consentono di visualizzare lo stato di esecuzione dei pacchetti e di identificare la causa di errori di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b90da-104">Two of these package reports in particular help you to view package execution status and identify the cause of execution failures.</span></span>  
  
-   <span data-ttu-id="b90da-105">**Dashboard Integration Services** : questo report include una panoramica di tutte le esecuzioni del pacchetto nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nelle ultime 24 ore.</span><span class="sxs-lookup"><span data-stu-id="b90da-105">**Integration Services Dashboard** - This report provides an overview of all the package executions on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance in the past 24 hours.</span></span> <span data-ttu-id="b90da-106">Nel report vengono visualizzate informazioni quali Stato, Tipo operazione, Nome pacchetto e così via, per ogni pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b90da-106">The report displays information such as Status, Operation Type, Package Name, etc., for each package.</span></span>  
  
     <span data-ttu-id="b90da-107">I parametri Ora di inizio, Ora di fine e Durata possono essere interpretati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b90da-107">The Start Time, End Time, and Duration can be interpreted as follows:</span></span>  
  
    -   <span data-ttu-id="b90da-108">Se il pacchetto è ancora in esecuzione, Durata = ora corrente - Ora di inizio</span><span class="sxs-lookup"><span data-stu-id="b90da-108">If the package is still running, then Duration = current time - Start Time</span></span>  
  
    -   <span data-ttu-id="b90da-109">Se il pacchetto è stato completato, Durata = Ora di fine - Ora di inizio</span><span class="sxs-lookup"><span data-stu-id="b90da-109">If the package has completed, then Duration = End Time - Start Time</span></span>  
  
     <span data-ttu-id="b90da-110">Per ogni pacchetto eseguito nel server, il dashboard consente all'utente di effettuare un ingrandimento per trovare dettagli specifici sugli errori di esecuzione del pacchetto che potrebbero essersi verificati.</span><span class="sxs-lookup"><span data-stu-id="b90da-110">For each package that has run on the server, the dashboard allows you to "zoom in" to find specific details on package execution errors that may have occurred.</span></span> <span data-ttu-id="b90da-111">Ad esempio, selezionare **Panoramica** per visualizzare una panoramica ad alto livello dello stato delle attività nell'esecuzione, o **Tutti i messaggi** per visualizzare i messaggi dettagliati acquisiti durante l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b90da-111">For example, click **Overview** to display a high-level overview of the status of the tasks in the execution, or **All Messages** to display the detailed messages that were captured as part of the package execution.</span></span>  
  
     <span data-ttu-id="b90da-112">È possibile filtrare la tabella visualizzata in qualsiasi pagina facendo clic su **Filtro** e selezionando i criteri nella finestra di dialogo **Impostazioni filtro** .</span><span class="sxs-lookup"><span data-stu-id="b90da-112">You can filter the table displayed on any page by clicking **Filter** and then selecting criteria in the **Filter Settings** dialog.</span></span> <span data-ttu-id="b90da-113">I criteri di filtro disponibili dipendono dai dati visualizzati.</span><span class="sxs-lookup"><span data-stu-id="b90da-113">The filter criteria available depends on the data being displayed.</span></span> <span data-ttu-id="b90da-114">È possibile modificare l'ordinamento del report facendo clic sulla relativa icona nella finestra di dialogo **Impostazioni filtro** .</span><span class="sxs-lookup"><span data-stu-id="b90da-114">You can change the sort order of the report by clicking the sort icon in the **Filter Settings** dialog.</span></span>  
  
-   <span data-ttu-id="b90da-115">**Attività - Tutte le esecuzioni**: in questo report viene visualizzato un riepilogo di tutte le esecuzioni di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che sono state eseguite nel server.</span><span class="sxs-lookup"><span data-stu-id="b90da-115">**Activity - All Executions Report** - This report displays a summary of all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] executions that have been performed on the server.</span></span> <span data-ttu-id="b90da-116">Nel riepilogo vengono visualizzate informazioni per ogni esecuzione, ad esempio, stato, ora di inizio e ora di fine.</span><span class="sxs-lookup"><span data-stu-id="b90da-116">The summary displays information for each execution such as status, start time, and end time.</span></span> <span data-ttu-id="b90da-117">Ogni voce del riepilogo include collegamenti a ulteriori informazioni relative all'esecuzione, inclusi i messaggi generati durante l'esecuzione e i dati relativi alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b90da-117">Each summary entry includes links to more information about the execution including messages generated during execution and performance data.</span></span> <span data-ttu-id="b90da-118">Come per il Dashboard Integration Services, è possibile applicare un filtro alla tabella per limitare le informazioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="b90da-118">As with the Integration Services Dashboard, you can apply a filter to the table to narrow down the information displayed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b90da-119">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="b90da-119">Related Tasks</span></span>  
 [<span data-ttu-id="b90da-120">Visualizzare i report per il server Integration Services</span><span class="sxs-lookup"><span data-stu-id="b90da-120">View Reports for the Integration Services Server</span></span>](../view-reports-for-the-integration-services-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="b90da-121">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="b90da-121">Related Content</span></span>  
 [<span data-ttu-id="b90da-122">Report per il server di Integration Services</span><span class="sxs-lookup"><span data-stu-id="b90da-122">Reports for the Integration Services Server</span></span>](../reports-for-the-integration-services-server.md)  
  
 [<span data-ttu-id="b90da-123">Strumenti per la risoluzione dei problemi relativi all'esecuzione dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="b90da-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  
