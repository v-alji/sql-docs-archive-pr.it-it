---
title: Salvare il pacchetto SSIS (Importazione/Esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.savedtspackage.f1
ms.assetid: 7bf8ac6a-5599-43ab-bf5c-e072c11b85a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d4e582558a1f86b18d935fcc6235ba5839faa031
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635130"
---
# <a name="save-ssis-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="2c9a0-102">Salva pacchetto SSIS (Importazione/Esportazione guidata SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2c9a0-102">Save SSIS Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="2c9a0-103">Utilizzare la pagina **Salva pacchetto SSIS** per assegnare un nome, una descrizione e un salvataggio di un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pacchetto Integration Services ( [!INCLUDE[ssIS](../../includes/ssis-md.md)] ) nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database o in un file con estensione dtsx.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-103">Use the **Save SSIS Package** page to name, describe, and save a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Integration Services ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) package to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database or to a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c9a0-104">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] l'opzione per salvare il pacchetto creato con la procedura guidata non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-104">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="2c9a0-105">Per ulteriori informazioni su questa procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2c9a0-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="2c9a0-106">Per informazioni sulle opzioni per avviare la procedura guidata e sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2c9a0-106">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="2c9a0-107">Lo scopo di Importazione/Esportazione guidata SQL Server è la copia di dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="2c9a0-108">La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="2c9a0-109">Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="2c9a0-110">Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2c9a0-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="2c9a0-111">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="2c9a0-111">Static Options</span></span>  
 <span data-ttu-id="2c9a0-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2c9a0-112">**Name**</span></span>  
 <span data-ttu-id="2c9a0-113">Consente di specificare un nome univoco per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-113">Provide a unique name for the package.</span></span>  
  
 <span data-ttu-id="2c9a0-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2c9a0-114">**Description**</span></span>  
 <span data-ttu-id="2c9a0-115">Consente di specificare una descrizione per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-115">Provide a description for the package.</span></span> <span data-ttu-id="2c9a0-116">È consigliabile includere nella descrizione informazioni sugli scopi del pacchetto, in modo da ottenere pacchetti autodocumentati più semplici da gestire.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-116">As a best practice, describe the package in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="2c9a0-117">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="2c9a0-117">**Target**</span></span>  
 <span data-ttu-id="2c9a0-118">Consente di visualizzare la destinazione ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o file) specificata in precedenza per il file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-118">View the target ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or file) that was previously specified for the destination file.</span></span>  
  
## <a name="target-dynamic-options"></a><span data-ttu-id="2c9a0-119">Opzioni dinamiche di Destinazione</span><span class="sxs-lookup"><span data-stu-id="2c9a0-119">Target Dynamic Options</span></span>  
  
### <a name="target--sql-server"></a><span data-ttu-id="2c9a0-120">Destinazione = SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c9a0-120">Target = SQL Server</span></span>  
 <span data-ttu-id="2c9a0-121">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="2c9a0-121">**Server name**</span></span>  
 <span data-ttu-id="2c9a0-122">Se è stata selezionata una destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], digitare o selezionare il nome del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-122">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, type or select the destination server name.</span></span>  
  
 <span data-ttu-id="2c9a0-123">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="2c9a0-123">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="2c9a0-124">Se è stata selezionata una destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], specificare se connettersi al server utilizzando l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-124">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using Windows Integrated Authentication.</span></span> <span data-ttu-id="2c9a0-125">Questo è il metodo di autenticazione ottimale.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-125">This is the preferred authentication method.</span></span>  
  
 <span data-ttu-id="2c9a0-126">**Usa autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="2c9a0-126">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="2c9a0-127">Se è stata selezionata una destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], specificare se connettersi al server utilizzando l'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2c9a0-127">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, specify whether to connect to the server by using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="2c9a0-128">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="2c9a0-128">**User name**</span></span>  
 <span data-ttu-id="2c9a0-129">Se è stata selezionata una destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ed è stata specificata l'autenticazione di SQL Server, digitare il nome utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c9a0-129">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user name.</span></span>  
  
 <span data-ttu-id="2c9a0-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="2c9a0-130">**Password**</span></span>  
 <span data-ttu-id="2c9a0-131">Se è stata selezionata una destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ed è stata specificata l'autenticazione di SQL Server, digitare la password di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c9a0-131">When you have selected a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, and have specified SQL Server Authentication, type the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] password.</span></span>  
  
### <a name="target--file-system"></a><span data-ttu-id="2c9a0-132">Destinazione = File System</span><span class="sxs-lookup"><span data-stu-id="2c9a0-132">Target = File System</span></span>  
 <span data-ttu-id="2c9a0-133">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="2c9a0-133">**File name**</span></span>  
 <span data-ttu-id="2c9a0-134">Quando è stata selezionata una destinazione file, digitare il percorso del file di destinazione oppure usare il pulsante **Sfoglia** .</span><span class="sxs-lookup"><span data-stu-id="2c9a0-134">When you have selected a file destination, type the path for the destination file, or use the **Browse** button.</span></span>  
  
 <span data-ttu-id="2c9a0-135">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="2c9a0-135">**Browse**</span></span>  
 <span data-ttu-id="2c9a0-136">Quando è stata selezionata una destinazione file, passare al file di destinazione utilizzando la finestra di dialogo **Salva pacchetto** .</span><span class="sxs-lookup"><span data-stu-id="2c9a0-136">When you have selected a file destination, browse to the destination file by using the **Save Package** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9a0-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c9a0-137">See Also</span></span>  
 [<span data-ttu-id="2c9a0-138">Salvataggio di pacchetti</span><span class="sxs-lookup"><span data-stu-id="2c9a0-138">Save Packages</span></span>](../save-packages.md)  
  
  
