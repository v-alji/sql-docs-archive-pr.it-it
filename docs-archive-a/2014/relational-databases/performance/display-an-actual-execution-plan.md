---
title: Visualizzare un piano di esecuzione effettivo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- displaying execution plans
- actual execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
ms.assetid: 9e583a18-5f4a-4054-bfe1-4b2a76630db6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f384e2d2752b7601fbb46b8ee7f7b56a2615651c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714224"
---
# <a name="display-an-actual-execution-plan"></a><span data-ttu-id="f9ff6-102">Visualizzazione di un piano di esecuzione effettivo</span><span class="sxs-lookup"><span data-stu-id="f9ff6-102">Display an Actual Execution Plan</span></span>
  <span data-ttu-id="f9ff6-103">In questo argomento viene descritto come generare piani di esecuzione grafici effettivi utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9ff6-103">This topic describes how to generate actual graphical execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="f9ff6-104">Alla generazione di piani di esecuzione effettivi vengono eseguite le query o i batch di comandi [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f9ff6-104">When actual execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches execute.</span></span> <span data-ttu-id="f9ff6-105">Il piano di esecuzione generato visualizza il piano di esecuzione query effettivo utilizzato da [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] per eseguire le query.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-105">The execution plan that is generated displays the actual query execution plan that the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses to execute the queries.</span></span>  
  
 <span data-ttu-id="f9ff6-106">Per utilizzare questa funzionalità, gli utenti devono disporre delle autorizzazioni appropriate per eseguire le query [!INCLUDE[tsql](../../includes/tsql-md.md)] per le quali viene generato un piano di esecuzione grafico e dell'autorizzazione SHOWPLAN per tutti i database a cui fa riferimento la query.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-include-an-execution-plan-for-a-query-during-execution"></a><span data-ttu-id="f9ff6-107">Per includere un piano di esecuzione per una query durante l'esecuzione</span><span class="sxs-lookup"><span data-stu-id="f9ff6-107">To include an execution plan for a query during execution</span></span>  
  
1.  <span data-ttu-id="f9ff6-108">Scegliere [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query del motore di database **nella barra degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-108">On the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="f9ff6-109">Per aprire una query esistente e visualizzare il piano di esecuzione stimato, è inoltre possibile fare clic sul pulsante **Apri file** della barra degli strumenti e individuare la query.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="f9ff6-110">Immettere la query per quale si desidera visualizzare il piano di esecuzione effettivo.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-110">Enter the query for which you would like to display the actual execution plan.</span></span>  
  
3.  <span data-ttu-id="f9ff6-111">Scegliere **Includi piano di esecuzione effettivo** dal menu **query** oppure fare clic sul pulsante della barra degli strumenti **Includi piano di esecuzione effettivo** .</span><span class="sxs-lookup"><span data-stu-id="f9ff6-111">On the **Query** menu, click **Include Actual Execution Plan** or click the **Include Actual Execution Plan** toolbar button</span></span>  
  
4.  <span data-ttu-id="f9ff6-112">Fare clic sul pulsante della barra degli strumenti **Esegui** per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-112">Execute the query by clicking the **Execute** toolbar button.</span></span> <span data-ttu-id="f9ff6-113">Il piano usato da Query Optimizer viene visualizzato nella scheda **Piano di esecuzione** del riquadro dei risultati.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-113">The plan used by the query optimizer is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="f9ff6-114">Posizionando il puntatore del mouse sugli operatori logici e fisici è possibile visualizzare una descrizione comando contenente la descrizione e le proprietà degli operatori.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-114">Pause the mouse over the logical and physical operators to view the description and properties of the operators in the displayed ToolTip.</span></span>  
  
     <span data-ttu-id="f9ff6-115">In alternativa, è possibile visualizzare le proprietà dell'operatore nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-115">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="f9ff6-116">Se la finestra Proprietà non è visibile, fare clic con il pulsante destro del mouse su un operatore e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-116">If Properties is not visible, right-click an operator and select **Properties**.</span></span> <span data-ttu-id="f9ff6-117">Selezionare un operatore e visualizzare le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-117">Select an operator to view its properties.</span></span>  
  
5.  <span data-ttu-id="f9ff6-118">È possibile modificare la visualizzazione del piano di esecuzione facendo clic con il pulsante destro del mouse sul piano di esecuzione e scegliendo **Zoom avanti**, **Zoom indietro**, **Personalizza zoom**oppure **Adatta alla finestra**.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-118">You can alter the display of the execution plan by right-clicking the execution plan and selecting **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="f9ff6-119">Le opzioni**Zoom avanti** e **Zoom indietro** consentono rispettivamente di ingrandire e rimpicciolire il piano di esecuzione, mentre **Personalizza zoom** consente di definire un fattore di zoom personalizzato, ad esempio 80 percento.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-119">**Zoom In** and **Zoom Out** allow you to zoom in or out on the execution plan, while **Custom Zoom** allows you to define your own zoom, such as zooming at 80 percent.</span></span> <span data-ttu-id="f9ff6-120">**Adatta alla finestra** consente di ingrandire il piano di esecuzione per adattarlo al riquadro Risultati.</span><span class="sxs-lookup"><span data-stu-id="f9ff6-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
