---
title: Configurazione destinazione file flat (Importazione/Esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.configureflatfiledest.f1
ms.assetid: 318e8da0-37d3-46cd-943a-fc5d66aad93a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2af8a1653d9a1aef0828aa112a25825ed23b8bf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635151"
---
# <a name="configure-flat-file-destination-sql-server-import-and-export-wizard"></a><span data-ttu-id="0f63b-102">Configurazione destinazione file flat (Importazione/Esportazione guidata SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0f63b-102">Configure Flat File Destination (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="0f63b-103">Utilizzare la pagina **Configura destinazione file flat** per specificare le opzioni di formattazione per il file flat di destinazione e per visualizzare l'anteprima dei risultati prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0f63b-103">Use the **Configure Flat File Destination** page to specify formatting options for the destination flat file, and to preview results before continuing.</span></span>  
  
 <span data-ttu-id="0f63b-104">Per ulteriori informazioni su questa procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0f63b-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="0f63b-105">Per informazioni sulle opzioni di avvio della procedura guidata, nonché sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0f63b-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="0f63b-106">Lo scopo di Importazione/Esportazione guidata SQL Server è la copia di dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="0f63b-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="0f63b-107">La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0f63b-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="0f63b-108">Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database.</span><span class="sxs-lookup"><span data-stu-id="0f63b-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="0f63b-109">Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0f63b-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0f63b-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0f63b-110">Options</span></span>  
 <span data-ttu-id="0f63b-111">**File flat di origine**</span><span class="sxs-lookup"><span data-stu-id="0f63b-111">**Source flat file**</span></span>  
 <span data-ttu-id="0f63b-112">Nome del file di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0f63b-112">The name of the destination file.</span></span>  
  
 <span data-ttu-id="0f63b-113">**Delimitatore di riga**</span><span class="sxs-lookup"><span data-stu-id="0f63b-113">**Row delimiter**</span></span>  
 <span data-ttu-id="0f63b-114">Consente di selezionare un delimitatore di riga nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0f63b-114">Select from the list of delimiters for rows.</span></span>  
  
|<span data-ttu-id="0f63b-115">Valore</span><span class="sxs-lookup"><span data-stu-id="0f63b-115">Value</span></span>|<span data-ttu-id="0f63b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f63b-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f63b-117">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-117">**{CR}{LF}**</span></span>|<span data-ttu-id="0f63b-118">La riga è delimitata dalla combinazione di caratteri ritorno a capo/avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="0f63b-118">The row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="0f63b-119">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-119">**{CR}**</span></span>|<span data-ttu-id="0f63b-120">La riga è delimitata da un ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="0f63b-120">The row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="0f63b-121">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-121">**{LF}**</span></span>|<span data-ttu-id="0f63b-122">La riga è delimitata da un avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="0f63b-122">The row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="0f63b-123">**Punto e virgola {;}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-123">**Semicolon {;}**</span></span>|<span data-ttu-id="0f63b-124">La riga è delimitata da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="0f63b-124">The row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="0f63b-125">**Due punti {:}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-125">**Colon {:}**</span></span>|<span data-ttu-id="0f63b-126">La riga è delimitata da due punti.</span><span class="sxs-lookup"><span data-stu-id="0f63b-126">The row is delimited by a colon.</span></span>|  
|<span data-ttu-id="0f63b-127">**Virgola {,}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-127">**Comma {,}**</span></span>|<span data-ttu-id="0f63b-128">La riga è delimitata da una virgola.</span><span class="sxs-lookup"><span data-stu-id="0f63b-128">The row is delimited by a comma.</span></span>|  
|<span data-ttu-id="0f63b-129">**Tabulazione {t}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-129">**Tab {t}**</span></span>|<span data-ttu-id="0f63b-130">La riga è delimitata da una tabulazione.</span><span class="sxs-lookup"><span data-stu-id="0f63b-130">The row is delimited by a tab.</span></span>|  
|<span data-ttu-id="0f63b-131">**Barra verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-131">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="0f63b-132">La riga è delimitata da una barra verticale.</span><span class="sxs-lookup"><span data-stu-id="0f63b-132">The row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="0f63b-133">**Delimitatore di colonna**</span><span class="sxs-lookup"><span data-stu-id="0f63b-133">**Column delimiter**</span></span>  
 <span data-ttu-id="0f63b-134">Consente di selezionare un delimitatore di colonna nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0f63b-134">Select from the list of delimiters for columns.</span></span>  
  
|<span data-ttu-id="0f63b-135">Valore</span><span class="sxs-lookup"><span data-stu-id="0f63b-135">Value</span></span>|<span data-ttu-id="0f63b-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f63b-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f63b-137">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-137">**{CR}{LF}**</span></span>|<span data-ttu-id="0f63b-138">Le colonne sono delimitate dalla combinazione di caratteri ritorno a capo/avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="0f63b-138">The columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="0f63b-139">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-139">**{CR}**</span></span>|<span data-ttu-id="0f63b-140">Le colonne sono delimitate da un ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="0f63b-140">The columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="0f63b-141">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-141">**{LF}**</span></span>|<span data-ttu-id="0f63b-142">Le colonne sono delimitate da un avanzamento riga.</span><span class="sxs-lookup"><span data-stu-id="0f63b-142">The columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="0f63b-143">**Punto e virgola {;}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-143">**Semicolon {;}**</span></span>|<span data-ttu-id="0f63b-144">Le colonne sono delimitate da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="0f63b-144">The columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="0f63b-145">**Due punti {:}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-145">**Colon {:}**</span></span>|<span data-ttu-id="0f63b-146">Le colonne sono delimitate da due punti.</span><span class="sxs-lookup"><span data-stu-id="0f63b-146">The columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="0f63b-147">**Virgola {,}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-147">**Comma {,}**</span></span>|<span data-ttu-id="0f63b-148">Le colonne sono delimitate da una virgola.</span><span class="sxs-lookup"><span data-stu-id="0f63b-148">The columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="0f63b-149">**Tabulazione {t}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-149">**Tab {t}**</span></span>|<span data-ttu-id="0f63b-150">Le colonne sono delimitate da una tabulazione.</span><span class="sxs-lookup"><span data-stu-id="0f63b-150">The columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="0f63b-151">**Barra verticale {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="0f63b-151">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="0f63b-152">Le colonne sono delimitate da una barra verticale.</span><span class="sxs-lookup"><span data-stu-id="0f63b-152">The columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="0f63b-153">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="0f63b-153">**Preview**</span></span>  
 <span data-ttu-id="0f63b-154">Visualizzazione nella finestra di dialogo **Anteprima dati** i risultati delle opzioni di formattazione selezionate per il file flat di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0f63b-154">View in the **Preview Data** dialog box the results of the selected formatting options for the destination flat file.</span></span>  
  
 <span data-ttu-id="0f63b-155">**Modifica trasformazione**</span><span class="sxs-lookup"><span data-stu-id="0f63b-155">**Edit transform**</span></span>  
 <span data-ttu-id="0f63b-156">Eliminare righe, accodare righe e configurare le colonne nel file di destinazione utilizzando la finestra di dialogo **Mapping colonne** .</span><span class="sxs-lookup"><span data-stu-id="0f63b-156">Delete rows, append rows, and configure columns in the destination file by using the **Column Mappings** dialog box.</span></span>  
  
  
