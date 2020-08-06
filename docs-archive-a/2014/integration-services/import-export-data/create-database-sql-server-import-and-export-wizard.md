---
title: Crea database (Importazione/Esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createdatabase.f1
ms.assetid: 56a8a79f-086c-4bdc-8888-0045bb4b0cbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 617b3fe10a17ae2d8659b51e85cdb3fed4470506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635147"
---
# <a name="create-database-sql-server-import-and-export-wizard"></a><span data-ttu-id="659c8-102">Crea database (Importazione/Esportazione guidata SQL Server)</span><span class="sxs-lookup"><span data-stu-id="659c8-102">Create Database (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="659c8-103">Utilizzare la pagina **Crea database** per definire un nuovo database per un file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="659c8-103">Use the **Create Database** page to define a new database for a destination file.</span></span>  
  
 <span data-ttu-id="659c8-104">Nella pagina è incluso un subset delle opzioni disponibili per la creazione di un nuovo database.</span><span class="sxs-lookup"><span data-stu-id="659c8-104">This page offers a subset of the available options for creating a new database.</span></span> <span data-ttu-id="659c8-105">Per visualizzare tutte le opzioni, usare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="659c8-105">To view all the options, use [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="659c8-106">Per ulteriori informazioni su questa procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="659c8-106">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="659c8-107">Per informazioni sulle opzioni per avviare la procedura guidata e sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="659c8-107">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="659c8-108">Lo scopo di Importazione/Esportazione guidata SQL Server è la copia di dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="659c8-108">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="659c8-109">La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="659c8-109">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="659c8-110">Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database.</span><span class="sxs-lookup"><span data-stu-id="659c8-110">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="659c8-111">Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="659c8-111">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="659c8-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="659c8-112">Options</span></span>  
 <span data-ttu-id="659c8-113">**Nome**</span><span class="sxs-lookup"><span data-stu-id="659c8-113">**Name**</span></span>  
 <span data-ttu-id="659c8-114">Consente di specificare un nome univoco per il database di SQL Server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="659c8-114">Provide a unique name for the destination SQL Server database.</span></span> <span data-ttu-id="659c8-115">Accertarsi di rispettare le convenzioni di denominazione dei database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="659c8-115">Make sure that you follow SQL Server conventions when you name this database.</span></span>  
  
 <span data-ttu-id="659c8-116">**Nome file di dati**</span><span class="sxs-lookup"><span data-stu-id="659c8-116">**Data file name**</span></span>  
 <span data-ttu-id="659c8-117">Consente di visualizzare il nome del file di dati.</span><span class="sxs-lookup"><span data-stu-id="659c8-117">View the name of the data file.</span></span> <span data-ttu-id="659c8-118">Tale nome è tratto dal nome del database specificato precedentemente.</span><span class="sxs-lookup"><span data-stu-id="659c8-118">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="659c8-119">**Nome file di log**</span><span class="sxs-lookup"><span data-stu-id="659c8-119">**Log file name**</span></span>  
 <span data-ttu-id="659c8-120">Consente di visualizzare il nome del file di log.</span><span class="sxs-lookup"><span data-stu-id="659c8-120">View the name of the log file.</span></span> <span data-ttu-id="659c8-121">Tale nome è tratto dal nome del database specificato precedentemente.</span><span class="sxs-lookup"><span data-stu-id="659c8-121">This is derived from the database name you provided earlier.</span></span>  
  
 <span data-ttu-id="659c8-122">**Dimensioni iniziali (file di dati)**</span><span class="sxs-lookup"><span data-stu-id="659c8-122">**Initial size (data file)**</span></span>  
 <span data-ttu-id="659c8-123">Consente di specificare il numero di megabyte per le dimensioni iniziali del file di dati.</span><span class="sxs-lookup"><span data-stu-id="659c8-123">Specify the number of megabytes for the initial size of the data file.</span></span>  
  
 <span data-ttu-id="659c8-124">**Aumento dimensioni non consentito (file di dati)**</span><span class="sxs-lookup"><span data-stu-id="659c8-124">**No growth allowed (data file)**</span></span>  
 <span data-ttu-id="659c8-125">Consente di indicare se le dimensioni del file di dati possono eccedere le dimensioni iniziali specificate.</span><span class="sxs-lookup"><span data-stu-id="659c8-125">Indicate whether the data file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="659c8-126">**Aumento dimensioni in percentuale (file di dati)**</span><span class="sxs-lookup"><span data-stu-id="659c8-126">**Grow by percentage (data file)**</span></span>  
 <span data-ttu-id="659c8-127">Consente di specificare che le dimensioni del file di dati possono aumentare in base a un valore percentuale.</span><span class="sxs-lookup"><span data-stu-id="659c8-127">Specify a percentage by which the data file can grow.</span></span>  
  
 <span data-ttu-id="659c8-128">**Aumento dimensioni (file di dati)**</span><span class="sxs-lookup"><span data-stu-id="659c8-128">**Grow by size (data file)**</span></span>  
 <span data-ttu-id="659c8-129">Consente di specificare che le dimensioni del file di dati possono aumentare in base a un numero di megabyte.</span><span class="sxs-lookup"><span data-stu-id="659c8-129">Specify a number of megabytes by which the data file can grow.</span></span>  
  
 <span data-ttu-id="659c8-130">**Dimensioni iniziali (file di log)**</span><span class="sxs-lookup"><span data-stu-id="659c8-130">**Initial size (log file)**</span></span>  
 <span data-ttu-id="659c8-131">Consente di specificare il numero di megabyte per le dimensioni iniziali del file di log.</span><span class="sxs-lookup"><span data-stu-id="659c8-131">Specify the number of megabytes for the initial size of the log file.</span></span>  
  
 <span data-ttu-id="659c8-132">**Aumento dimensioni non consentito (file di log)**</span><span class="sxs-lookup"><span data-stu-id="659c8-132">**No growth allowed (log file)**</span></span>  
 <span data-ttu-id="659c8-133">Consente di indicare se le dimensioni del file di log possono eccedere le dimensioni iniziali specificate.</span><span class="sxs-lookup"><span data-stu-id="659c8-133">Indicate whether the log file can grow beyond the specified initial size.</span></span>  
  
 <span data-ttu-id="659c8-134">**Aumento dimensioni in percentuale (file di log)**</span><span class="sxs-lookup"><span data-stu-id="659c8-134">**Grow by percentage (log file)**</span></span>  
 <span data-ttu-id="659c8-135">Consente di specificare che le dimensioni del file di log possono aumentare in base a un valore percentuale.</span><span class="sxs-lookup"><span data-stu-id="659c8-135">Specify a percentage by which the log file can grow.</span></span>  
  
 <span data-ttu-id="659c8-136">**Aumento dimensioni (file di log)**</span><span class="sxs-lookup"><span data-stu-id="659c8-136">**Grow by size (log file)**</span></span>  
 <span data-ttu-id="659c8-137">Consente di specificare che le dimensioni del file di log possono aumentare in base a un numero di megabyte.</span><span class="sxs-lookup"><span data-stu-id="659c8-137">Specify a number of megabytes by which the log file can grow.</span></span>  
  
  
