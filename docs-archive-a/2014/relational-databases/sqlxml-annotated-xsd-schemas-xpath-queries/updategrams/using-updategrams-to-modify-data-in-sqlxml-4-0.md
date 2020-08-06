---
title: Utilizzo di updategram per modificare i dati in SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, updategrams
- data insertions [SQLXML]
- data deletions [SQLXML]
- updating data [SQLXML]
- modifying data [SQLXML]
- OPENXML function
- updategrams [SQLXML]
- database modifications [SQLXML]
- data updates [SQLXML]
- modifying databases
- data modifications [SQLXML]
- deleting data
- inserting data
ms.assetid: b8b3b892-cb73-41d0-b945-bce148d81d9b
author: rothja
ms.author: jroth
ms.openlocfilehash: a4a2397668ed08df91377cc35dea22fd52788580
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634942"
---
# <a name="using-updategrams-to-modify-data-in-sqlxml-40"></a><span data-ttu-id="a65db-102">Utilizzo di updategram per modificare dati in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="a65db-102">Using Updategrams to Modify Data in SQLXML 4.0</span></span>
  <span data-ttu-id="a65db-103">È possibile modificare (inserire, aggiornare o eliminare) un database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] da un documento XML esistente utilizzando un updategram o la [!INCLUDE[tsql](../../../includes/tsql-md.md)] funzione OPENXML.</span><span class="sxs-lookup"><span data-stu-id="a65db-103">You can modify (insert, update, or delete) a database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from an existing XML document by using an updategram or the OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="a65db-104">In questa sezione sono incluse informazioni sugli updategram e alcuni esempi del relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="a65db-104">This section provides information about updategrams and examples of their usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a65db-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a65db-105">In This Section</span></span>  
 [<span data-ttu-id="a65db-106">Introduzione agli updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a65db-106">Introduction to Updategrams &#40;SQLXML 4.0&#41;</span></span>](introduction-to-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="a65db-107">Vengono forniti informazioni ed esempi di base sugli updategram.</span><span class="sxs-lookup"><span data-stu-id="a65db-107">Provides basic information and examples of updategrams.</span></span>  
  
 [<span data-ttu-id="a65db-108">Specifica di uno schema di mapping con annotazioni in un updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a65db-108">Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;</span></span>](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md)  
 <span data-ttu-id="a65db-109">Vengono forniti e descritti esempi di schemi di mapping con annotazioni negli updategram.</span><span class="sxs-lookup"><span data-stu-id="a65db-109">Explains and provides examples of annotated mapping schemas in updategrams.</span></span>  
  
 [<span data-ttu-id="a65db-110">Gestione dei valori NULL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a65db-110">NULL Handling &#40;SQLXML 4.0&#41;</span></span>](null-handling-sqlxml-4-0.md)  
 <span data-ttu-id="a65db-111">Viene descritto come specificare NULL per valori di elementi e attributi.</span><span class="sxs-lookup"><span data-stu-id="a65db-111">Describes how to specify NULL for element and attribute values.</span></span>  
  
 [<span data-ttu-id="a65db-112">Inserimento di dati mediante updategram XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a65db-112">Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](inserting-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="a65db-113">Vengono forniti e descritti esempi dell'utilizzo di updategram per inserire dati.</span><span class="sxs-lookup"><span data-stu-id="a65db-113">Describes and provides examples of using updategrams to insert data.</span></span>  
  
 [<span data-ttu-id="a65db-114">Eliminazione di dati mediante updategram XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a65db-114">Deleting Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](deleting-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="a65db-115">Vengono forniti e descritti esempi dell'utilizzo di updategram per eliminare dati.</span><span class="sxs-lookup"><span data-stu-id="a65db-115">Describes and provides examples of using updategrams to delete data.</span></span>  
  
 [<span data-ttu-id="a65db-116">Aggiornamento di dati mediante updategram XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a65db-116">Updating Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](updating-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="a65db-117">Vengono forniti e descritti esempi dell'utilizzo di updategram per modificare dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="a65db-117">Describes and provides examples of using updategrams to modify existing data.</span></span>  
  
 [<span data-ttu-id="a65db-118">Passaggio di parametri agli updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a65db-118">Passing Parameters to Updategrams &#40;SQLXML 4.0&#41;</span></span>](passing-parameters-to-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="a65db-119">Vengono forniti e descritti esempi del passaggio di parametri agli updategram.</span><span class="sxs-lookup"><span data-stu-id="a65db-119">Describes and provides examples of passing parameters to updategrams.</span></span>  
  
 [<span data-ttu-id="a65db-120">Gestione dei problemi di concorrenza di database negli updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a65db-120">Handling Database Concurrency Issues in Updategrams &#40;SQLXML 4.0&#41;</span></span>](handling-database-concurrency-issues-in-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="a65db-121">Vengono descritti i diversi livelli di protezione possibili per la gestione di problemi di concorrenza negli updategram e sono inclusi alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="a65db-121">Describes the various levels of protection possible for handling concurrency issues in updategrams, and provides examples.</span></span>  
  
 [<span data-ttu-id="a65db-122">Applicazioni di esempio updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a65db-122">Updategram Sample Applications &#40;SQLXML 4.0&#41;</span></span>](../../../database-engine/dev-guide/updategram-sample-applications-sqlxml-4-0.md)  
 <span data-ttu-id="a65db-123">Vengono fornite applicazioni di esempio che utilizzano updategram.</span><span class="sxs-lookup"><span data-stu-id="a65db-123">Provides sample applications that use updategrams.</span></span>  
  
 [<span data-ttu-id="a65db-124">Linee guida e limitazioni degli updategram XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a65db-124">Guidelines and Limitations of XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](guidelines-and-limitations-of-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="a65db-125">Sono elencate alcune considerazioni da tenere presenti quando si utilizzano updategram.</span><span class="sxs-lookup"><span data-stu-id="a65db-125">Lists some things to remember when working with updategrams.</span></span>  
  
  
