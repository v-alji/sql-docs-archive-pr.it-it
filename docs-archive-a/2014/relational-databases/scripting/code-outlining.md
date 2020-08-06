---
title: Struttura del codice
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Query Editor [SQL Server Management Studio], outlining code
- Query Editor [SQL Server Management Studio], hiding code
ms.assetid: 556c7dfe-7bc8-4cab-a36f-2b753a05d3f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 0a142ca8fbdcdfcfbfd1b71de06c0b0fd4c5339c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627162"
---
# <a name="code-outlining"></a><span data-ttu-id="c5a8f-102">Struttura del codice</span><span class="sxs-lookup"><span data-stu-id="c5a8f-102">Code Outlining</span></span>
  <span data-ttu-id="c5a8f-103">La modalità struttura negli editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] consente di nascondere in modo selettivo il codice quando si modificano query.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-103">You can use the outlining feature in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] query editors to selectively hide code when you edit queries.</span></span> <span data-ttu-id="c5a8f-104">In questo modo è possibile visualizzare più facilmente il codice utilizzato, soprattutto in file di query di dimensioni elevate.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-104">This enables you to more easily view the code you are working on, especially in large query files.</span></span>

## <a name="outlining-overview"></a><span data-ttu-id="c5a8f-105">Panoramica sulla struttura</span><span class="sxs-lookup"><span data-stu-id="c5a8f-105">Outlining Overview</span></span>
 <span data-ttu-id="c5a8f-106">Per impostazione predefinita, quando si apre una finestra dell'editor di query tutto il codice è visibile.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-106">By default, all code is visible when you open a query editor window.</span></span> <span data-ttu-id="c5a8f-107">È possibile comprimere alcune aree del codice per nasconderne la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-107">Regions of the code can be collapsed to hide it from view.</span></span> <span data-ttu-id="c5a8f-108">In una riga verticale sul bordo sinistro della finestra dell'editor viene utilizzato un quadrato con un segno meno (-) per identificare l'inizio di ogni area di codice comprimibile.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-108">A vertical line on the left edge of the editor window uses a square with a minus sign (-) to identify the start of each collapsible code region.</span></span> <span data-ttu-id="c5a8f-109">Quando si fa clic sul segno meno, il testo dell'area del codice viene sostituito con una casella che contiene tre punti (...) e il segno meno viene modificato in un segno più (+).</span><span class="sxs-lookup"><span data-stu-id="c5a8f-109">When you click a minus sign, the text of the code region is replaced with a box that contains three periods (...), and the minus sign changes to a plus sign (+).</span></span> <span data-ttu-id="c5a8f-110">Quando si fa clic sul segno più, il codice compresso viene visualizzato e il segno più viene modificato in un segno meno.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-110">When you click a plus sign, the collapsed code appears and the plus sign changes to a minus sign.</span></span> <span data-ttu-id="c5a8f-111">Quando si sposta il puntatore su una casella in cui sono presenti i tre punti, viene visualizzata una descrizione di comando in cui viene mostrato il codice contenuto nella sezione compressa.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-111">When you move the pointer over a box that has three periods, a tooltip appears that shows the code in the collapsed section.</span></span>

## <a name="system-outline-regions"></a><span data-ttu-id="c5a8f-112">Aree della struttura di sistema</span><span class="sxs-lookup"><span data-stu-id="c5a8f-112">System Outline Regions</span></span>
 <span data-ttu-id="c5a8f-113">Ogni editor di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] genera un set di aree della struttura predefinite stabilite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-113">Each [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] editor generates a set of default, system-defined outline regions.</span></span>

 <span data-ttu-id="c5a8f-114">Gli editor del codice MDX e DMX creano aree della struttura per ogni istruzione su più righe.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-114">The MDX and DMX code editors create outline regions for each multiline statement.</span></span> <span data-ttu-id="c5a8f-115">Questo è l'unico livello di struttura supportata da tali editor.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-115">This is the only level of outlining that these editors support.</span></span>

### <a name="analysis-services-xmla-query-editor-regions"></a><span data-ttu-id="c5a8f-116">Aree dell'editor di query XMLA di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c5a8f-116">Analysis Services XMLA Query Editor Regions</span></span>
 <span data-ttu-id="c5a8f-117">L'editor di query XMLA di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] genera un'area della struttura per ogni attributo XML su più righe.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-117">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query Editor generates an outline region for each multiline XML attribute.</span></span> <span data-ttu-id="c5a8f-118">L'editor nidifica le aree della struttura per i tag nidificati.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-118">The editor nests the outline regions for nested tags.</span></span> <span data-ttu-id="c5a8f-119">L'editor XMLA, ad esempio, crea tre aree della struttura per il documento seguente.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-119">For example, the XMLA Editor creates three outline regions for the following document.</span></span>

 <span data-ttu-id="c5a8f-120">![Codice XML in cui è illustrata la struttura](../../database-engine/media/editoutlinexmlfull.gif "Codice XML in cui è illustrata la struttura")</span><span class="sxs-lookup"><span data-stu-id="c5a8f-120">![XML code showing outlining](../../database-engine/media/editoutlinexmlfull.gif "XML code showing outlining")</span></span>

 <span data-ttu-id="c5a8f-121">Quando si fa clic sul segno meno sulla \<InnerTag> riga, solo InnerTag viene compresso, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-121">When you click the minus sign on the \<InnerTag> line, just the InnerTag is collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="c5a8f-122">![Codice XML con il nodo interno nascosto](../../database-engine/media/editoutlinexmlinnercol.gif "Codice XML con il nodo interno nascosto")</span><span class="sxs-lookup"><span data-stu-id="c5a8f-122">![XML code with inner node hidden](../../database-engine/media/editoutlinexmlinnercol.gif "XML code with inner node hidden")</span></span>

 <span data-ttu-id="c5a8f-123">Quando si sposta il puntatore sulla casella in cui sono presenti i tre punti (...), il codice contenuto nell'area compressa viene visualizzato in una descrizione di comando, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-123">When you move the pointer over the box that has the three periods (...), the code in the collapsed region appears in a tooltip, as shown in the following illustration.</span></span>

 <span data-ttu-id="c5a8f-124">![Codice XML con una descrizione comandi in cui è illustrato il codice nascosto](../../database-engine/media/editoutlinexmlmouse.gif "Codice XML con una descrizione comandi in cui è illustrato il codice nascosto")</span><span class="sxs-lookup"><span data-stu-id="c5a8f-124">![XML code with tooltip showing hidden code](../../database-engine/media/editoutlinexmlmouse.gif "XML code with tooltip showing hidden code")</span></span>

 <span data-ttu-id="c5a8f-125">Quando si fa clic sul segno meno sulla \<MiddleTag> riga, MiddleTag e InnerTag vengono compressi, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-125">When you click the minus sign on the \<MiddleTag> line, both the MiddleTag and InnerTag are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="c5a8f-126">![Codice XML con i tag interni e centrali nascosti](../../database-engine/media/editoutlinexmlmiddlecol.gif "Codice XML con i tag interni e centrali nascosti")</span><span class="sxs-lookup"><span data-stu-id="c5a8f-126">![XML code with inner and middle tags hidden](../../database-engine/media/editoutlinexmlmiddlecol.gif "XML code with inner and middle tags hidden")</span></span>

 <span data-ttu-id="c5a8f-127">Quando si fa clic sul segno meno sulla \<OuterTag> riga, vengono compresse tutte e tre le righe, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-127">When you click the minus sign on the \<OuterTag> line, all three lines are collapsed, as shown in the following illustration.</span></span>

 <span data-ttu-id="c5a8f-128">![Codice XML in cui sono illustrati tutti e tre i tag nascosti](../../database-engine/media/editoutlinexmloutercol.gif "Codice XML in cui sono illustrati tutti e tre i tag nascosti")</span><span class="sxs-lookup"><span data-stu-id="c5a8f-128">![XML code showing all three tags hidden](../../database-engine/media/editoutlinexmloutercol.gif "XML code showing all three tags hidden")</span></span>

### <a name="database-engine-query-editor-regions"></a><span data-ttu-id="c5a8f-129">Aree dell'editor di query del Motore di database</span><span class="sxs-lookup"><span data-stu-id="c5a8f-129">Database Engine Query Editor Regions</span></span>
 <span data-ttu-id="c5a8f-130">L'editor di query del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] genera aree di struttura per ogni elemento presente nella gerarchia seguente:</span><span class="sxs-lookup"><span data-stu-id="c5a8f-130">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor generates outline regions for each element in the following hierarchy:</span></span>

1.  <span data-ttu-id="c5a8f-131">Batch.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-131">Batches.</span></span> <span data-ttu-id="c5a8f-132">Il primo batch è rappresentato dal codice dall'inizio del file fino al primo comando GO o fino alla fine del file nel caso in cui non siano presenti comandi GO.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-132">The first batch is the code from the start of the file to either the first GO command or the end of the file when there are no GO commands.</span></span> <span data-ttu-id="c5a8f-133">Dopo il primo comando GO, è presente un batch da ogni comando GO fino a quello successivo o fino alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-133">After the first GO, there is one batch from each GO command to either the next GO command or the end of the file.</span></span>

2.  <span data-ttu-id="c5a8f-134">Blocchi delimitati dalle parole chiave seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5a8f-134">Blocks delimited by the following keywords:</span></span>

    -   <span data-ttu-id="c5a8f-135">BEGIN - END</span><span class="sxs-lookup"><span data-stu-id="c5a8f-135">BEGIN - END</span></span>

    -   <span data-ttu-id="c5a8f-136">BEGIN TRY - END TRY</span><span class="sxs-lookup"><span data-stu-id="c5a8f-136">BEGIN TRY - END TRY</span></span>

    -   <span data-ttu-id="c5a8f-137">BEGIN CATCH - END CATCH</span><span class="sxs-lookup"><span data-stu-id="c5a8f-137">BEGIN CATCH - END CATCH</span></span>

3.  <span data-ttu-id="c5a8f-138">Istruzioni su più righe.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-138">Multiline statements.</span></span>

 <span data-ttu-id="c5a8f-139">L'editor di query del [!INCLUDE[ssDE](../../../includes/ssde-md.md)] crea ad esempio tre aree della struttura per la query seguente:</span><span class="sxs-lookup"><span data-stu-id="c5a8f-139">For example, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] Query Editor creates three outline regions for the following query:</span></span>

```
CREATE PROCEDURE Sales.SampleProc --Outline region 1
AS
BEGIN --Outline region 2 
  SELECT GETDATE() AS TimeOfQuery;
  SELECT * --Outline region 3
  FROM sys.transmission_queue;
  SELECT @@VERSION;
END;
GO
```

 <span data-ttu-id="c5a8f-140">È possibile fare clic sul segno di meno sulla riga `SELECT *` per comprimere solo l'istruzione `SELECT` specifica.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-140">You can click the minus sign on the `SELECT *` line to collapse just that `SELECT` statement.</span></span> <span data-ttu-id="c5a8f-141">Per comprimere l'intero blocco `BEGIN - END` , fare clic sul segno meno sulla riga `BEGIN` .</span><span class="sxs-lookup"><span data-stu-id="c5a8f-141">To collapse the whole `BEGIN - END` block, click the minus sign on the `BEGIN` line.</span></span> <span data-ttu-id="c5a8f-142">Per comprimere l'intero batch fino al comando `GO` , fare clic sul segno meno sulla riga `CREATE PROCEDURE` .</span><span class="sxs-lookup"><span data-stu-id="c5a8f-142">To collapse the whole batch to the `GO` command, click the minus sign on the `CREATE PROCEDURE` line.</span></span> <span data-ttu-id="c5a8f-143">Non è possibile comprimere la riga `SELECT GETDATE()` o `SELECT @@VERSION` singolarmente poiché ognuna costituisce un'istruzione su un'unica riga e non definisce aree della struttura.</span><span class="sxs-lookup"><span data-stu-id="c5a8f-143">You cannot collapse the `SELECT GETDATE()` or `SELECT @@VERSION` lines individually because they are single line statements and do not get outlining regions.</span></span>


