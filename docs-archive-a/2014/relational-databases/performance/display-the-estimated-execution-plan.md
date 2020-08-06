---
title: Visualizzare il piano di esecuzione stimato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- zoom [SQL Server]
- estimated execution plan [SQL Server]
- displaying execution plans
- viewing execution plans
- execution plans [SQL Server], displaying
- customizing execution plan display [SQL Server]
- modifying execution plan display
- custom zoom [SQL Server]
ms.assetid: e94aa576-4c0c-4c54-ad05-6c3432cc615b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79c0972661d40eb9e359cf43f7a1f0b1b2ae4b0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714212"
---
# <a name="display-the-estimated-execution-plan"></a><span data-ttu-id="a2dc5-102">Visualizzazione del piano di esecuzione stimato</span><span class="sxs-lookup"><span data-stu-id="a2dc5-102">Display the Estimated Execution Plan</span></span>
  <span data-ttu-id="a2dc5-103">In questo argomento viene descritta la procedura per generare rappresentazioni grafiche di piani di esecuzione stimati mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2dc5-103">This topic describes how to generate graphical estimated execution plans by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a2dc5-104">Quando si generano piani di esecuzione stimati, le query o i batch [!INCLUDE[tsql](../../includes/tsql-md.md)] non vengono eseguiti.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-104">When estimated execution plans are generated, the [!INCLUDE[tsql](../../includes/tsql-md.md)] queries or batches do not execute.</span></span> <span data-ttu-id="a2dc5-105">Nel piano di esecuzione generato vengono invece visualizzate le query che verrebbero utilizzate con maggiore probabilità da [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in caso di effettiva esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-105">Instead, the execution plan that is generated displays the query execution plan that [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] would most probably use if the queries were actually executed.</span></span>  
  
 <span data-ttu-id="a2dc5-106">Per utilizzare questa funzionalità, è necessario che gli utenti dispongano delle autorizzazioni appropriate relative all'esecuzione delle query [!INCLUDE[tsql](../../includes/tsql-md.md)] per le quali verrà generato un piano di esecuzione grafico, nonché dell'autorizzazione SHOWPLAN per tutti i database a cui fa riferimento la query.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-106">To use this feature, users must have the appropriate permissions to execute the [!INCLUDE[tsql](../../includes/tsql-md.md)] query for which a graphical execution plan is being generated, and they must be granted the SHOWPLAN permission for all databases referenced by the query.</span></span>  
  
### <a name="to-display-the-estimated-execution-plan-for-a-query"></a><span data-ttu-id="a2dc5-107">Per visualizzare il piano di esecuzione stimato di una query</span><span class="sxs-lookup"><span data-stu-id="a2dc5-107">To display the estimated execution plan for a query</span></span>  
  
1.  <span data-ttu-id="a2dc5-108">Scegliere **Query del Motore di database**nella barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-108">On the toolbar, click **Database Engine Query**.</span></span> <span data-ttu-id="a2dc5-109">Per aprire una query esistente e visualizzare il piano di esecuzione stimato, è inoltre possibile fare clic sul pulsante **Apri file** della barra degli strumenti e individuare la query.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-109">You can also open an existing query and display the estimated execution plan by clicking the **Open File** toolbar button and locating the existing query.</span></span>  
  
2.  <span data-ttu-id="a2dc5-110">Immettere la query di cui si desidera visualizzare il piano di esecuzione stimato.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-110">Enter the query for which you would like to display the estimated execution plan.</span></span>  
  
3.  <span data-ttu-id="a2dc5-111">Scegliere **Visualizza piano di esecuzione stimato** dal menu **Query** oppure fare clic sul pulsante **Visualizza piano di esecuzione stimato** della barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-111">On the **Query** menu, click **Display Estimated Execution Plan** or click the **Display Estimated Execution Plan** toolbar button.</span></span> <span data-ttu-id="a2dc5-112">Il piano di esecuzione stimato verrà visualizzato nel riquadro Risultati della scheda **Piano di esecuzione** .</span><span class="sxs-lookup"><span data-stu-id="a2dc5-112">The estimated execution plan is displayed on the **Execution Plan** tab in the results pane.</span></span> <span data-ttu-id="a2dc5-113">Per visualizzare informazioni aggiuntive, posizionare il mouse sulle icone degli operatori logici e fisici e visualizzare la descrizione e le proprietà dell'operatore nella descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-113">To view additional information, pause the mouse over the logical and physical operator icons and view the description and properties of the operator in the displayed ToolTip.</span></span> <span data-ttu-id="a2dc5-114">In alternativa, è possibile visualizzare le proprietà dell'operatore nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-114">Alternatively, you can view operator properties in the Properties window.</span></span> <span data-ttu-id="a2dc5-115">Se tale finestra non è visibile, fare clic con il pulsante destro del mouse su un operatore e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-115">If Properties is not visible, right-click an operator and click **Properties**.</span></span> <span data-ttu-id="a2dc5-116">Selezionare un operatore e visualizzare le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-116">Select an operator to view its properties.</span></span>  
  
4.  <span data-ttu-id="a2dc5-117">Per modificare la visualizzazione del piano di esecuzione, fare clic con il pulsante destro del mouse sul piano di esecuzione e scegliere **Zoom avanti**, **Zoom indietro**, **Personalizza zoom**o **Adatta alla finestra**.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-117">To alter the display of the execution plan, right-click the execution plan and select **Zoom In**, **Zoom Out**, **Custom Zoom**, or **Zoom to Fit**.</span></span> <span data-ttu-id="a2dc5-118">**Zoom avanti** e **Zoom indietro** consentono rispettivamente di ingrandire o ridurre il piano di esecuzione in base a valori di percentuale predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-118">**Zoom In** and **Zoom Out** allow you to magnify or reduce the execution plan by fixed amounts.</span></span> <span data-ttu-id="a2dc5-119">**Personalizza zoom** consente di definire un ingrandimento personalizzato per la visualizzazione, ad esempio 80 percento.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-119">**Custom Zoom** allows you to define your own display magnification, such as zooming at 80 percent.</span></span> <span data-ttu-id="a2dc5-120">**Adatta alla finestra** consente di ingrandire il piano di esecuzione per adattarlo al riquadro Risultati.</span><span class="sxs-lookup"><span data-stu-id="a2dc5-120">**Zoom to Fit** magnifies the execution plan to fit the result pane.</span></span>  
  
  
