---
title: Restituzione di risultati dall'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], status information
- ExecutionValue property
- status information [Integration Services]
- TaskResult property
- SSIS Script task, status information
ms.assetid: ac06805b-c2db-44bd-af5c-5a0debe36dd7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bef3e93644377f715b5ad24e0a53df053197a03a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715567"
---
# <a name="returning-results-from-the-script-task"></a><span data-ttu-id="03f87-102">Risultati restituiti dall'attività Script</span><span class="sxs-lookup"><span data-stu-id="03f87-102">Returning Results from the Script Task</span></span>
  <span data-ttu-id="03f87-103">L'attività Script utilizza la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> e la proprietà facoltativa <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> per restituire informazioni sullo stato al runtime di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] che è possibile utilizzare per determinare il percorso del flusso di lavoro al termine dell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="03f87-103">The Script task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> and the optional <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> properties to return status information to the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime that can be used to determine the path of the workflow after the Script task has finished.</span></span>  
  
## <a name="taskresult"></a><span data-ttu-id="03f87-104">TaskResult</span><span class="sxs-lookup"><span data-stu-id="03f87-104">TaskResult</span></span>  
 <span data-ttu-id="03f87-105">La proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> indica l'esito positivo o negativo dell'attività.</span><span class="sxs-lookup"><span data-stu-id="03f87-105">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> property reports whether the task succeeded or failed.</span></span> <span data-ttu-id="03f87-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="03f87-106">For example:</span></span>  
  
 `Dts.TaskResult = ScriptResults.Success`  
  
## <a name="executionvalue"></a><span data-ttu-id="03f87-107">ExecutionValue</span><span class="sxs-lookup"><span data-stu-id="03f87-107">ExecutionValue</span></span>  
 <span data-ttu-id="03f87-108">La proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> restituisce facoltativamente un oggetto definito dall'utente che quantifica o fornisce ulteriori informazioni sull'esito positivo o negativo dell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="03f87-108">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> property optionally returns a user-defined object that quantifies or provides more information about the success or failure of the Script task.</span></span> <span data-ttu-id="03f87-109">Ad esempio, l'attività FTP utilizza la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> per restituire il numero di file trasferiti.</span><span class="sxs-lookup"><span data-stu-id="03f87-109">For example, the FTP task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> property to return the number of files transferred.</span></span> <span data-ttu-id="03f87-110">L'attività Esegui SQL restituisce il numero di righe interessate dall'attività.</span><span class="sxs-lookup"><span data-stu-id="03f87-110">The Execute SQL task returns the number of rows affected by the task.</span></span> <span data-ttu-id="03f87-111">La proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> può anche essere utilizzata per determinare il percorso del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="03f87-111">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> can also be used to determine the path of the workflow.</span></span> <span data-ttu-id="03f87-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="03f87-112">For example:</span></span>  
  
 `Dim rowsAffected as Integer`  
  
 `...`  
  
 `rowsAffected = 1000`  
  
 `Dts.ExecutionValue = rowsAffected`  
  
<span data-ttu-id="03f87-113">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="03f87-113">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="03f87-114">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="03f87-114">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="03f87-115">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="03f87-115">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="03f87-116">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="03f87-116">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
