---
title: Esercitazione su SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.tutorialstart.ssms.f1
helpviewer_keywords:
- projects [SQL Server Management Studio], tutorials
- templates [SQL Server], SQL Server Management Studio
- source controls [SQL Server Management Studio], tutorials
- Help [SQL Server], SQL Server Management Studio
- tutorials [SQL Server Management Studio]
- Transact-SQL tutorials
- solutions [SQL Server Management Studio], tutorials
- SQL Server Management Studio [SQL Server], tutorials
- scripts [SQL Server], SQL Server Management Studio
ms.assetid: d2bade70-07cf-4d94-b5d2-88aecb538ed1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8206fea828d6169975dc1d026a22e18e682f71e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637022"
---
# <a name="tutorial-sql-server-management-studio"></a><span data-ttu-id="0639b-102">Esercitazione su SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0639b-102">Tutorial: SQL Server Management Studio</span></span>
  <span data-ttu-id="0639b-103">Nell'esercitazione di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] viene illustrato l'ambiente integrato per gestire l'infrastruttura di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0639b-103">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tutorial introduces you to the integrated environment for managing your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] infrastructure.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="0639b-104">presenta un'interfaccia grafica per la configurazione, il monitoraggio e l'amministrazione di istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0639b-104">presents a graphical interface for configuring, monitoring, and administering instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0639b-105">Inoltre, consente di distribuire, monitorare e aggiornare i componenti livello dati utilizzati dalle applicazioni, ad esempio i database e i data warehouse.</span><span class="sxs-lookup"><span data-stu-id="0639b-105">It also allows you to deploy, monitor, and upgrade the data-tier components used by your applications, such as databases and data warehouses.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="0639b-106">offre anche [!INCLUDE[tsql](../../includes/tsql-md.md)]e gli editor di linguaggio MDX, DMX e XML per la modifica e il debug di script.</span><span class="sxs-lookup"><span data-stu-id="0639b-106">also provides [!INCLUDE[tsql](../../includes/tsql-md.md)], MDX, DMX, and XML language editors for editing and debugging scripts.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="0639b-107">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="0639b-107">What You Will Learn</span></span>  
 <span data-ttu-id="0639b-108">In questa esercitazione sono incluse nozioni utili relative alla presentazione delle informazioni in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e al modo in cui è possibile utilizzare al meglio le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0639b-108">This tutorial will help you understand the presentation of information in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to take advantage of the features.</span></span> <span data-ttu-id="0639b-109">Si noti che l'esercitazione fa riferimento all'installazione completa di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] inclusa in tutte le edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ad eccezione di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0639b-109">Note that this tutorial applies to the complete installation of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] that is included with all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="0639b-110">Le funzionalità per le installazioni di base di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e per le installazioni di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] fornite con [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] sono leggermente diverse rispetto a quelle descritte nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="0639b-110">Functionality for basic installations of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and for [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] installations that ship with [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] is slightly different than what is presented in this tutorial.</span></span>  
  
 <span data-ttu-id="0639b-111">Il modo migliore per acquisire familiarità con [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] è la pratica diretta.</span><span class="sxs-lookup"><span data-stu-id="0639b-111">The best way to get acquainted with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] is through hands-on practice.</span></span> <span data-ttu-id="0639b-112">In questa esercitazione viene illustrato come gestire i componenti di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] e individuare le funzionalità utilizzate regolarmente.</span><span class="sxs-lookup"><span data-stu-id="0639b-112">This tutorial will teach you how to manage the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and how to find the features that you use regularly.</span></span>  
  
 <span data-ttu-id="0639b-113">L'esercitazione è suddivisa in tre lezioni:</span><span class="sxs-lookup"><span data-stu-id="0639b-113">This tutorial is divided into three lessons:</span></span>  
  
 [<span data-ttu-id="0639b-114">Lezione 1: Navigazione di base in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0639b-114">Lesson 1: Basic Navigation in SQL Server Management Studio</span></span>](lesson-1-basic-navigation-in-sql-server-management-studio.md)  
 <span data-ttu-id="0639b-115">In questa lezione viene illustrato come utilizzare i componenti di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], riconfigurare il layout ambiente e ripristinare il layout predefinito.</span><span class="sxs-lookup"><span data-stu-id="0639b-115">In this lesson you will learn how to use the components of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], how to reconfigure the environment layout, and how to restore the default layout.</span></span>  
  
 [<span data-ttu-id="0639b-116">Lezione 2: Scrittura di codice Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0639b-116">Lesson 2: Writing Transact-SQL</span></span>](lesson-2-writing-transact-sql.md)  
 <span data-ttu-id="0639b-117">In questa lezione viene illustrato come avviare l'editor di query, gestire il codice e utilizzare le altre nuove funzionalità dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="0639b-117">In this lesson, you will learn how to open Query Editor, how to manage code, and how to use the other new features of Query Editor.</span></span>  
  
 [<span data-ttu-id="0639b-118">Lezione 3: Utilizzo di modelli, soluzioni e progetti script</span><span class="sxs-lookup"><span data-stu-id="0639b-118">Lesson 3: Working with Templates, Solutions, and Script Projects</span></span>](lesson-3-working-with-templates-solutions-and-script-projects.md)  
 <span data-ttu-id="0639b-119">In questa lezione viene illustrato come utilizzare i modelli e organizzare gli script nelle soluzioni e nei progetti.</span><span class="sxs-lookup"><span data-stu-id="0639b-119">In this lesson you will learn how to use templates, and organize scripts into solutions and projects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0639b-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0639b-120">Requirements</span></span>  
 <span data-ttu-id="0639b-121">Questa esercitazione è destinata a sviluppatori di database e amministratori di database esperti che non hanno familiarità con [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]ma che conoscono i concetti relativi ai database e il linguaggio [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0639b-121">This tutorial is intended for experienced database administrators and database developers who are not familiar with [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], but who are who are familiar with database concepts and the [!INCLUDE[tsql](../../includes/tsql-md.md)] language.</span></span>  
  
 <span data-ttu-id="0639b-122">Per utilizzare l'esercitazione è necessario che nel sistema siano installati i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0639b-122">Your system must have the following installed to use this tutorial:</span></span>  
  
-   [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="0639b-123">o una versione successiva con i database di esempio di [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0639b-123">or a later version with the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample databases.</span></span> <span data-ttu-id="0639b-124">Per una maggiore sicurezza, i database di esempio non vengono installati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0639b-124">To enhance security, the sample databases are not installed by default.</span></span> <span data-ttu-id="0639b-125">Per installare i database di esempio, vedere la pagina [Installazione degli esempi e dei database di esempio di SQL Server](http://sqlserversamples.codeplex.com).</span><span class="sxs-lookup"><span data-stu-id="0639b-125">To install the sample databases, see [Installing SQL Server Samples and Sample Databases](http://sqlserversamples.codeplex.com).</span></span>  
  
-   <span data-ttu-id="0639b-126">Internet Explorer 9.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="0639b-126">Internet Explorer 9.0 or later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0639b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0639b-127">See Also</span></span>  
 [<span data-ttu-id="0639b-128">Esercitazioni del motore di database</span><span class="sxs-lookup"><span data-stu-id="0639b-128">Database Engine Tutorials</span></span>](../../relational-databases/database-engine-tutorials.md)  
  
  
