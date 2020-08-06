---
title: Definizione di stored procedure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- stored procedures [Analysis Services]
- OLAP [Analysis Services], stored procedures
- external routines [Analysis Services]
- stored procedures [Analysis Services], about stored procedures
ms.assetid: f9c57d91-f60f-4f0e-8f7f-d87f4ba97b7c
author: minewiskan
ms.author: owend
ms.openlocfilehash: cc1f028f822d2289ee79702feb2494487040977c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715839"
---
# <a name="defining-stored-procedures"></a><span data-ttu-id="03572-102">Definizione delle stored procedure</span><span class="sxs-lookup"><span data-stu-id="03572-102">Defining Stored Procedures</span></span>
  <span data-ttu-id="03572-103">È possibile utilizzare stored procedure per chiamare routine esterne da [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03572-103">You can use stored procedures to call external routines from [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="03572-104">È possibile scrivere una routine esterna chiamata da una stored procedure in ogni linguaggio di Common Runtime Language (CLR), ad esempio C, C++, C#, Visual Basic o Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="03572-104">You can write an external routines called by a stored procedure in any common language runtime (CLR) language, such as C, C++, C#, Visual Basic, or Visual Basic .NET.</span></span> <span data-ttu-id="03572-105">Una stored procedure può essere creata una volta e chiamata da vari contesti, ad esempio da altre stored procedure, da misure calcolate o da applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="03572-105">A stored procedure can be created once and called from many contexts, such as other stored procedures, calculated measures, or client applications.</span></span> <span data-ttu-id="03572-106">Consentendo di sviluppare il codice comune una sola volta e di archiviarlo in una singola posizione, le stored procedure semplificano le operazioni di sviluppo e di implementazione del database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03572-106">Stored procedures simplify [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database development and implementation by allowing common code to be developed once and stored in a single location.</span></span> <span data-ttu-id="03572-107">Possono essere utilizzate per aggiungere alle applicazioni funzionalità business non presenti in quelle native di MDX.</span><span class="sxs-lookup"><span data-stu-id="03572-107">Stored procedures can be used to add business functionality to your applications that is not provided by the native functionality of MDX.</span></span>  
  
 <span data-ttu-id="03572-108">In questa sezione vengono fornite le informazioni necessarie per comprendere, progettare e implementare stored procedure.</span><span class="sxs-lookup"><span data-stu-id="03572-108">This section provides the information necessary to understand, design, and implement stored procedures.</span></span>  
  
|<span data-ttu-id="03572-109">Argomento</span><span class="sxs-lookup"><span data-stu-id="03572-109">Topic</span></span>|<span data-ttu-id="03572-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03572-110">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="03572-111">Progettazione di stored procedure</span><span class="sxs-lookup"><span data-stu-id="03572-111">Designing Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/designing-stored-procedures.md)|<span data-ttu-id="03572-112">Descrive la procedura per progettare assembly da utilizzare con [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03572-112">Describes how to design assemblies for use with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="03572-113">Creazione di stored procedure</span><span class="sxs-lookup"><span data-stu-id="03572-113">Creating Stored Procedures</span></span>](creating-stored-procedures.md)|<span data-ttu-id="03572-114">Descrive la procedura per creare assembly per [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03572-114">Describes how to create assemblies for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="03572-115">Chiamata di stored procedure</span><span class="sxs-lookup"><span data-stu-id="03572-115">Calling Stored Procedures</span></span>](calling-stored-procedures.md)|<span data-ttu-id="03572-116">Offre informazioni sull'utilizzo degli assembly in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03572-116">Provides information on how to use assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="03572-117">Accesso al contesto di query nelle stored procedure</span><span class="sxs-lookup"><span data-stu-id="03572-117">Accessing Query Context in Stored Procedures</span></span>](accessing-query-context-in-stored-procedures.md)|<span data-ttu-id="03572-118">Descrive la procedura per accedere alle informazioni sul contesto e l'ambito con gli assembly.</span><span class="sxs-lookup"><span data-stu-id="03572-118">Describes how to access scope and context information with assemblies.</span></span>|  
|[<span data-ttu-id="03572-119">Impostazione della sicurezza per stored procedure</span><span class="sxs-lookup"><span data-stu-id="03572-119">Setting Security for Stored Procedures</span></span>](setting-security-for-stored-procedures.md)|<span data-ttu-id="03572-120">Descrive la procedura per configurare la sicurezza degli assembly in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03572-120">Describes how to configure security for assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="03572-121">Debug di stored procedure</span><span class="sxs-lookup"><span data-stu-id="03572-121">Debugging Stored Procedures</span></span>](debugging-stored-procedures.md)|<span data-ttu-id="03572-122">Descrive la procedura per eseguire il debug degli assembly in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03572-122">Describes how to debug assemblies in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03572-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03572-123">See Also</span></span>  
 [<span data-ttu-id="03572-124">Gestione di assembly di modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="03572-124">Multidimensional Model Assemblies Management</span></span>](../multidimensional-models/multidimensional-model-assemblies-management.md)  
  
  
