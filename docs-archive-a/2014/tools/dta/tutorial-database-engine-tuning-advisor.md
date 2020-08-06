---
title: 'Esercitazione: Ottimizzazione guidata motore di database | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], tutorials
- tutorials [Database Engine Tuning Advisor]
ms.assetid: 3b54cbbe-d8c6-424d-92f1-aa58179f4da8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 68e026cb28b875b834f20c906232285ede8e217b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624496"
---
# <a name="tutorial-database-engine-tuning-advisor"></a><span data-ttu-id="57919-102">Esercitazione: Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="57919-102">Tutorial: Database Engine Tuning Advisor</span></span>
  <span data-ttu-id="57919-103">In questa esercitazione verrà illustrata</span><span class="sxs-lookup"><span data-stu-id="57919-103">Welcome to the Database Engine Tuning Advisor tutorial.</span></span> <span data-ttu-id="57919-104">Ottimizzazione guidata motore di database che esamina il modo in cui vengono elaborate le query nei database specificati e offre indicazioni su come migliorare le prestazioni di elaborazione attraverso la modifica delle strutture di database, ad esempio indici, viste indicizzate e partizionamento.</span><span class="sxs-lookup"><span data-stu-id="57919-104">Database Engine Tuning Advisor examines how queries are processed in the databases you specify, and then recommends how you can improve query processing performance by modifying database structures such as indexes, indexed views, and partitioning.</span></span>  
  
 <span data-ttu-id="57919-105">Ottimizzazione guidata motore di database ha due interfacce utente, vale a dire un'interfaccia utente grafica (GUI) e l'utilità del prompt dei comandi **dta** .</span><span class="sxs-lookup"><span data-stu-id="57919-105">Database Engine Tuning Advisor provides two user interfaces: a graphical user interface (GUI) and the **dta** command prompt utility.</span></span> <span data-ttu-id="57919-106">L'interfaccia utente grafica consente di visualizzare rapidamente i risultati delle sessioni di ottimizzazione, mentre con l'utilità **dta** è possibile incorporare con semplicità la funzionalità dello strumento Ottimizzazione guidata motore di database in script per l'ottimizzazione automatica.</span><span class="sxs-lookup"><span data-stu-id="57919-106">The GUI makes it easy to quickly view the results of tuning sessions, and the **dta** utility makes it easy to incorporate Database Engine Tuning Advisor functionality into scripts for automated tuning.</span></span> <span data-ttu-id="57919-107">Lo strumento Ottimizzazione guidata motore di database, inoltre, può utilizzare input in formato XML, che garantisce un maggiore controllo sul processo di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="57919-107">In addition, Database Engine Tuning Advisor can take XML input, which offers more control over the tuning process.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="57919-108">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="57919-108">What You Will Learn</span></span>  
 <span data-ttu-id="57919-109">In questa esercitazione verrà illustrato come navigare nell'interfaccia utente grafica dello strumento Ottimizzazione guidata motore di database ed eseguire alcune semplici attività usando sia la GUI che l'utilità **dta** .</span><span class="sxs-lookup"><span data-stu-id="57919-109">This tutorial will teach you how to navigate the Database Engine Tuning Advisor GUI, and how to perform some basic tasks with both the GUI and the **dta** utility.</span></span> <span data-ttu-id="57919-110">Questa esercitazione contiene le lezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="57919-110">It contains the following lessons:</span></span>  
  
 [<span data-ttu-id="57919-111">Lezione 1: Navigazione di base in Ottimizzazione guidata motore di database</span><span class="sxs-lookup"><span data-stu-id="57919-111">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
 <span data-ttu-id="57919-112">In questa lezione sarà possibile acquisire familiarità con la GUI dello strumento Ottimizzazione guidata motore di database e ottenere informazioni su come impostare il layout e le opzioni di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="57919-112">In this lesson, you will familiarize yourself with the new Database Engine Tuning Advisor GUI and learn how to set display options and layout.</span></span>  
  
 [<span data-ttu-id="57919-113">Lezione 2: Uso di Ottimizzazione guidata motore di database</span><span class="sxs-lookup"><span data-stu-id="57919-113">Lesson 2: Using Database Engine Tuning Advisor</span></span>](lesson-2-using-database-engine-tuning-advisor.md)  
 <span data-ttu-id="57919-114">In questa lezione verranno descritte le procedure per eseguire alcune semplici attività di ottimizzazione utilizzando la GUI dello strumento Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="57919-114">In this lesson, you will learn how to perform basic tuning tasks with the Database Engine Tuning Advisor GUI.</span></span>  
  
 [<span data-ttu-id="57919-115">Lezione 3: Uso dell'utilità del prompt dei comandi dta</span><span class="sxs-lookup"><span data-stu-id="57919-115">Lesson 3: Using the dta Command Prompt Utility</span></span>](lesson-3-using-the-dta-command-prompt-utility.md)  
 <span data-ttu-id="57919-116">In questa lezione verranno descritte le procedure per avviare l'utilità del prompt dei comandi **dta** e per eseguire alcune semplici comandi per l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="57919-116">In this lesson, you learn how to start the **dta** command prompt utility and how to run some simple tuning commands.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57919-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57919-117">Requirements</span></span>  
 <span data-ttu-id="57919-118">Questa esercitazione è destinata agli amministratori di database che non hanno familiarità con l'interfaccia utente grafica dello strumento Ottimizzazione guidata motore di database o con l'utilità del prompt dei comandi **dta** , ma che hanno tuttavia esperienza in merito ai concetti e alle strutture relativi ai database, quali indici e viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="57919-118">This tutorial is intended for database administrators who are not familiar with the Database Engine Tuning Advisor GUI or the **dta** command prompt utility, but who are experienced with database concepts and structures, such as indexes and indexed views.</span></span>  
  
 <span data-ttu-id="57919-119">È necessario installare [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , o una versione successiva, con i database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="57919-119">You must install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] (or a later version) with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="57919-120">Per una maggiore sicurezza, i database di esempio non vengono installati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="57919-120">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="57919-121">Per installare i database di esempio, vedere la pagina [Installazione degli esempi e dei database di esempio di SQL Server](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="57919-121">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
## <a name="after-you-finish-this-tutorial"></a><span data-ttu-id="57919-122">Al termine di questa esercitazione</span><span class="sxs-lookup"><span data-stu-id="57919-122">After You Finish This Tutorial</span></span>  
 <span data-ttu-id="57919-123">Al termine di questa esercitazione, per ulteriori informazioni sullo strumento Ottimizzazione guidata motore di database, è possibile consultare gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="57919-123">After you finish the lessons in this tutorial, refer to the following topics for more information about Database Engine Tuning Advisor:</span></span>  
  
-   <span data-ttu-id="57919-124">[Ottimizzazione guidata motore di database](../../relational-databases/performance/database-engine-tuning-advisor.md) per le descrizioni sull'uso di questo strumento in determinate attività.</span><span class="sxs-lookup"><span data-stu-id="57919-124">[Database Engine Tuning Advisor](../../relational-databases/performance/database-engine-tuning-advisor.md) for descriptions of how to perform tasks with this tool.</span></span>  
  
-   <span data-ttu-id="57919-125">[Utilità dta](dta-utility.md) per materiale di riferimento sull'utilità del prompt dei comandi e sul file XML facoltativo disponibile per usare l'utilità.</span><span class="sxs-lookup"><span data-stu-id="57919-125">[dta Utility](dta-utility.md) for reference material on the command prompt utility and the optional XML file you can use to control the operation of the utility.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="57919-126">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="57919-126">Next Lesson</span></span>  
 [<span data-ttu-id="57919-127">Lezione 1: Navigazione di base in Ottimizzazione guidata motore di database</span><span class="sxs-lookup"><span data-stu-id="57919-127">Lesson 1: Basic Navigation in Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
