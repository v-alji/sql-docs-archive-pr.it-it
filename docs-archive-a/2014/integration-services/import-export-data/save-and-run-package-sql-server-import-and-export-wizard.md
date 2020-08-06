---
title: Salvare ed eseguire il pacchetto (importazione/esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.saveschedule.f1
ms.assetid: b582c462-3d7a-4a4c-a2a2-2c79fedab75a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a23f69bf66ca3355f1e1c62cc42d51e4aea3da5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635134"
---
# <a name="save-and-execute-package-sql-server-import-and-export-wizard"></a><span data-ttu-id="a97a8-102">Salvataggio ed esecuzione pacchetto (Importazione/Esportazione guidata SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a97a8-102">Save and Execute Package (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="a97a8-103">Utilizzare la finestra di dialogo **Salva ed Esegui pacchetto** per eseguire il pacchetto immediatamente, salvarlo in modo che venga eseguito in un secondo momento o in entrambi.</span><span class="sxs-lookup"><span data-stu-id="a97a8-103">Use the **Save and Execute Package** dialog box to run the package immediately, save it to run later, or both.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a97a8-104"> Se l'esecuzione di un pacchetto viene arrestata prima del completamento, il pacchetto non verrà salvato, anche se si seleziona la casella di controllo **Salva** .</span><span class="sxs-lookup"><span data-stu-id="a97a8-104">If you stop a package before it finishes running, the package is not saved, even if you selected the **Save** check box.</span></span>  
  
 <span data-ttu-id="a97a8-105">Per ulteriori informazioni su questa procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a97a8-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="a97a8-106">Per informazioni sulle opzioni di avvio della procedura guidata, nonché sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a97a8-106">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="a97a8-107">Lo scopo di Importazione/Esportazione guidata SQL Server è la copia di dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="a97a8-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="a97a8-108">La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a97a8-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="a97a8-109">Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database.</span><span class="sxs-lookup"><span data-stu-id="a97a8-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="a97a8-110">Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="a97a8-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a97a8-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a97a8-111">Options</span></span>  
 <span data-ttu-id="a97a8-112">**Esegui immediatamente**</span><span class="sxs-lookup"><span data-stu-id="a97a8-112">**Execute immediately**</span></span>  
 <span data-ttu-id="a97a8-113">Selezionare questa opzione per eseguire il pacchetto immediatamente.</span><span class="sxs-lookup"><span data-stu-id="a97a8-113">Select this option to run the package immediately.</span></span>  
  
 <span data-ttu-id="a97a8-114">**Salva pacchetto SSIS**</span><span class="sxs-lookup"><span data-stu-id="a97a8-114">**Save SSIS Package**</span></span>  
 <span data-ttu-id="a97a8-115">Consente di salvare il pacchetto per eseguirlo in un momento successivo con l'opzione per l'esecuzione immediata.</span><span class="sxs-lookup"><span data-stu-id="a97a8-115">Save the package to run later, with the option to run it immediately.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a97a8-116">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] l'opzione per salvare il pacchetto creato con la procedura guidata non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a97a8-116">In [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], the option to save the package created by the wizard is not available.</span></span>  
  
 <span data-ttu-id="a97a8-117">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a97a8-117">**SQL Server**</span></span>  
 <span data-ttu-id="a97a8-118">Selezionare questa opzione per salvare il pacchetto nel [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database.</span><span class="sxs-lookup"><span data-stu-id="a97a8-118">Select this option to save the package to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `msdb` database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a97a8-119">Questa opzione è disponibile solo se è stata selezionata l'opzione **Salva pacchetto SSIS** .</span><span class="sxs-lookup"><span data-stu-id="a97a8-119">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="a97a8-120">**File system**</span><span class="sxs-lookup"><span data-stu-id="a97a8-120">**File system**</span></span>  
 <span data-ttu-id="a97a8-121">Selezionare questa opzione per salvare il pacchetto come file con estensione dtsx.</span><span class="sxs-lookup"><span data-stu-id="a97a8-121">Select this option to save the package as a file that has the .dtsx extension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a97a8-122">Questa opzione è disponibile solo se è stata selezionata l'opzione **Salva pacchetto SSIS** .</span><span class="sxs-lookup"><span data-stu-id="a97a8-122">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="a97a8-123">**Livello di protezione pacchetto**</span><span class="sxs-lookup"><span data-stu-id="a97a8-123">**Package protection level**</span></span>  
 <span data-ttu-id="a97a8-124">Selezionare un livello di protezione dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="a97a8-124">Select a protection level from the list.</span></span>  
  
 <span data-ttu-id="a97a8-125">Il livello di protezione determina il metodo di protezione, la password o chiave utente e l'ambito di protezione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a97a8-125">The protection level determines the protection method, the password or user key, and the scope of package protection.</span></span> <span data-ttu-id="a97a8-126">La protezione può includere tutti i dati o solo i dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="a97a8-126">Protection can include all data or sensitive data only.</span></span> <span data-ttu-id="a97a8-127">Per informazioni sui requisiti e le opzioni per la sicurezza dei pacchetti, vedere [Access Control for sensitive data in Packages](../security/access-control-for-sensitive-data-in-packages.md) and [security Overview &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="a97a8-127">To understand the requirements and options for package security, see [Access Control for Sensitive Data in Packages](../security/access-control-for-sensitive-data-in-packages.md) and [Security Overview &#40;Integration Services&#41;](../security/security-overview-integration-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a97a8-128">Questa opzione è disponibile solo se è stata selezionata l'opzione **Salva pacchetto SSIS** .</span><span class="sxs-lookup"><span data-stu-id="a97a8-128">This option is available only if you have selected the **Save SSIS Package** option.</span></span>  
  
 <span data-ttu-id="a97a8-129">**Password**</span><span class="sxs-lookup"><span data-stu-id="a97a8-129">**Password**</span></span>  
 <span data-ttu-id="a97a8-130">Digitare una password.</span><span class="sxs-lookup"><span data-stu-id="a97a8-130">Type a password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a97a8-131">Questa opzione è disponibile solo se è stata impostata l'opzione **livello di protezione pacchetto** per **crittografare i dati sensibili con una password** o **crittografare tutti i dati con una password**.</span><span class="sxs-lookup"><span data-stu-id="a97a8-131">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
 <span data-ttu-id="a97a8-132">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="a97a8-132">**Retype password**</span></span>  
 <span data-ttu-id="a97a8-133">Digitare di nuovo la password.</span><span class="sxs-lookup"><span data-stu-id="a97a8-133">Type the password again.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a97a8-134">Questa opzione è disponibile solo se è stata impostata l'opzione **livello di protezione pacchetto** per **crittografare i dati sensibili con una password** o **crittografare tutti i dati con una password**.</span><span class="sxs-lookup"><span data-stu-id="a97a8-134">This option is available only if you have set the **Package protection level** option to either **Encrypt sensitive data with password** or **Encrypt all data with password**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a97a8-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a97a8-135">See Also</span></span>  
 <span data-ttu-id="a97a8-136">[Esecuzione di progetti e pacchetti](../packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="a97a8-136">[Execution of Projects and Packages](../packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="a97a8-137">Salvataggio di pacchetti</span><span class="sxs-lookup"><span data-stu-id="a97a8-137">Save Packages</span></span>](../save-packages.md)  
  
  
