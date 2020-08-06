---
title: Esecuzione delle operazioni (Importazione/Esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.performingoperation.f1
ms.assetid: 83259509-71d6-4a64-a7f2-4e9603b30bd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6cdac605da2288149909a3fb6e9f245e10eebf8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635145"
---
# <a name="performing-operation-sql-server-import-and-export-wizard"></a><span data-ttu-id="98f35-102">Esecuzione delle operazioni (Importazione/Esportazione guidata SQL Server)</span><span class="sxs-lookup"><span data-stu-id="98f35-102">Performing Operation (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="98f35-103">Utilizzare la finestra di dialogo **Esecuzione delle operazioni** per visualizzare lo stato e i risultati dell'operazione di importazione/esportazione ed eventualmente interrompere l'operazione.</span><span class="sxs-lookup"><span data-stu-id="98f35-103">Use the **Performing Operation** page to view the progress and the results of the import/export operation, and to interrupt the operation if necessary.</span></span>  
  
 <span data-ttu-id="98f35-104">Per ulteriori informazioni su questa procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="98f35-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="98f35-105">Per informazioni sulle opzioni di avvio della procedura guidata, nonché sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="98f35-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="98f35-106">Lo scopo di Importazione/Esportazione guidata SQL Server è la copia di dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="98f35-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="98f35-107">La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="98f35-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="98f35-108">Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database.</span><span class="sxs-lookup"><span data-stu-id="98f35-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="98f35-109">Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="98f35-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="98f35-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="98f35-110">Options</span></span>  
 <span data-ttu-id="98f35-111">**Azione**</span><span class="sxs-lookup"><span data-stu-id="98f35-111">**Action**</span></span>  
 <span data-ttu-id="98f35-112">Consente di visualizzare ogni azione che fa parte dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="98f35-112">Displays each action that is part of the operation.</span></span>  
  
 <span data-ttu-id="98f35-113">**Status**</span><span class="sxs-lookup"><span data-stu-id="98f35-113">**Status**</span></span>  
 <span data-ttu-id="98f35-114">Consente di visualizzare l'esito positivo o negativo di ogni azione.</span><span class="sxs-lookup"><span data-stu-id="98f35-114">Displays the success or failure of each action.</span></span>  
  
 <span data-ttu-id="98f35-115">**Message**</span><span class="sxs-lookup"><span data-stu-id="98f35-115">**Message**</span></span>  
 <span data-ttu-id="98f35-116">Consente di visualizzare i messaggi informativi e di errore eventualmente generati dall'azione.</span><span class="sxs-lookup"><span data-stu-id="98f35-116">Displays informational and error messages that the action might generate.</span></span>  
  
 <span data-ttu-id="98f35-117">**Filter**</span><span class="sxs-lookup"><span data-stu-id="98f35-117">**Filter**</span></span>  
 <span data-ttu-id="98f35-118">Consente di scegliere se si desidera visualizzare solo gli errori, gli avvisi o le azioni riuscite.</span><span class="sxs-lookup"><span data-stu-id="98f35-118">Choose whether you want to display only errors, warnings, or successful actions.</span></span> <span data-ttu-id="98f35-119">Per ripristinare la visualizzazione predefinita scegliere **Mostra tutte le azioni**.</span><span class="sxs-lookup"><span data-stu-id="98f35-119">You can revert to the default display by choosing **Show All Actions**.</span></span>  
  
 <span data-ttu-id="98f35-120">**Stop**</span><span class="sxs-lookup"><span data-stu-id="98f35-120">**Stop**</span></span>  
 <span data-ttu-id="98f35-121">Consente di interrompere l'operazione, se necessario, utilizzando il pulsante **Arresta** .</span><span class="sxs-lookup"><span data-stu-id="98f35-121">Interrupt the operation, if necessary, by using the **Stop** button.</span></span>  
  
 <span data-ttu-id="98f35-122">**Report**</span><span class="sxs-lookup"><span data-stu-id="98f35-122">**Report**</span></span>  
 <span data-ttu-id="98f35-123">Consente di visualizzare un report dei risultati, salvarlo in un file, copiarlo negli Appunti o inviarlo tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="98f35-123">View a report of the results, save the report to a file, copy the report to the clipboard, or send the report by e-mail.</span></span>  
  
  
