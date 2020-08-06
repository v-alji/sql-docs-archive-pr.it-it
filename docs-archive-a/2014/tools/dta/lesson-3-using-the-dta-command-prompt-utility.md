---
title: "Lezione 3: uso dell'utilità del prompt dei comandi dta | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 30f27f4d-8852-4b12-ba62-57f63e496f1d
author: stevestein
ms.author: sstein
ms.openlocfilehash: abbde02cd73e01937e6d0669c10f2db28da8a76e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711320"
---
# <a name="lesson-3-using-the-dta-command-prompt-utility"></a><span data-ttu-id="b3876-102">Lezione 3: Uso dell'utilità del prompt dei comandi dta</span><span class="sxs-lookup"><span data-stu-id="b3876-102">Lesson 3: Using the dta Command Prompt Utility</span></span>
  <span data-ttu-id="b3876-103">L'utilità del prompt dei comandi **dta** offre una funzionalità aggiuntiva rispetto allo strumento Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="b3876-103">The **dta** command-prompt utility offers functionality in addition to that provided by the Database Engine Tuning Advisor.</span></span>  
  
 <span data-ttu-id="b3876-104">È possibile utilizzare gli strumenti XML preferiti per creare file di input per l'utilità adottando XML Schema di Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="b3876-104">You can use your favorite XML tools to create input files for the utility by using the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="b3876-105">Questo schema viene installato con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ed è disponibile in: C:\Programmi (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span><span class="sxs-lookup"><span data-stu-id="b3876-105">This schema is installed when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and can be found at: C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn\schemas\sqlserver\2004\07\dta\dtaschema.xsd.</span></span>  
  
 <span data-ttu-id="b3876-106">XML Schema di Ottimizzazione guidata motore di database è inoltre disponibile online nel [sito Web Microsoft](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="b3876-106">The Database Engine Tuning Advisor XML schema is also available online at [this Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=43100&clcid=0x409).</span></span>  
  
 <span data-ttu-id="b3876-107">XML Schema dello strumento Ottimizzazione guidata motore di database garantisce una maggiore flessibilità per l'impostazione delle opzioni di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="b3876-107">The Database Engine Tuning Advisor XML schema provides more flexibility to set tuning options.</span></span> <span data-ttu-id="b3876-108">Ad esempio, questo schema consente di eseguire analisi di simulazione.</span><span class="sxs-lookup"><span data-stu-id="b3876-108">For example, it enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="b3876-109">Nell'analisi di simulazione è necessario specificare un set di strutture di progettazione fisica ipotetica per il database che si desidera ottimizzare e quindi eseguire l'analisi con lo strumento Ottimizzazione guidata motore di database per verificare se questa progettazione fisica ipotetica sarà in grado di migliorare le prestazioni dell'elaborazione delle query.</span><span class="sxs-lookup"><span data-stu-id="b3876-109">"What-if" analysis involves specifying a set of existing and hypothetical physical design structures for the database you want to tune, and then analyzing it with the Database Engine Tuning Advisor to find out whether this hypothetical physical design will improve query processing performance.</span></span> <span data-ttu-id="b3876-110">Questo tipo di analisi ha il vantaggio di valutare la nuova configurazione senza l'overhead dovuto all'effettiva implementazione.</span><span class="sxs-lookup"><span data-stu-id="b3876-110">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="b3876-111">Se la progettazione fisica ipotetica non determina i miglioramenti nelle prestazioni desiderati, è possibile modificarla e analizzarla nuovamente con facilità fino a quando non sarà stata raggiunta la configurazione che produce i risultati richiesti.</span><span class="sxs-lookup"><span data-stu-id="b3876-111">If your hypothetical physical design does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="b3876-112">Usando l'XML Schema dello strumento Ottimizzazione guidata motore di database e l'utilità del prompt dei comandi **dta** , è anche possibile integrare la funzionalità dello strumento Ottimizzazione guidata motore di database negli script e usarla con altri strumenti per la progettazione del database.</span><span class="sxs-lookup"><span data-stu-id="b3876-112">In addition, using the Database Engine Tuning Advisor XML schema and the **dta** command-prompt utility, you can incorporate Database Engine Tuning Advisor functionality into scripts and use it with other database design tools.</span></span>  
  
 <span data-ttu-id="b3876-113">In questa lezione non verrà illustrata la funzionalità relativa agli input in formato XML dello strumento Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="b3876-113">Using the XML input functionality of Database Engine Tuning Advisor is beyond the scope of this lesson.</span></span>  
  
 <span data-ttu-id="b3876-114">Questa lezione offre un'introduzione alla sintassi di base dell'utilità del prompt dei comandi **dta** , all'accesso alla Guida e alle procedure per ottimizzare semplici carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b3876-114">This lesson provides an introduction to the basic **dta** command-prompt utility syntax, how to access help, and practice for tuning simple workloads.</span></span>  
  
 <span data-ttu-id="b3876-115">Questa lezione contiene l'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="b3876-115">It contains the following topic:</span></span>  
  
-   <span data-ttu-id="b3876-116">Avvio dell'utilità del prompt dei comandi **DTA** e ottimizzazione di un carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="b3876-116">Starting the **dta** Command Prompt Utility and Tuning a Workload</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b3876-117">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="b3876-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b3876-118">Avvio dell'utilità del prompt dei comandi dta e ottimizzazione di un carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="b3876-118">Starting the dta Command Prompt Utility and Tuning a Workload</span></span>](lesson-1-1-tuning-a-workload.md)  
  
  
