---
title: 'Esercitazione: Creare un report grafico rapido offline (Generatore report) | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports, creating
- tutorials, getting started
- creating reports
ms.assetid: 6b1db67a-cf75-494c-b70c-09f1e6a8d414
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 51a9e648550a0108f47e3d93d75267ab0c1c24f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626527"
---
# <a name="tutorial-create-a-quick-chart-report-offline-report-builder"></a><span data-ttu-id="e46e4-102">Esercitazione: Creare un report grafico rapido offline (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="e46e4-102">Tutorial: Create a Quick Chart Report Offline (Report Builder)</span></span>
  <span data-ttu-id="e46e4-103">In questa esercitazione verrà creato un grafico a torta utilizzando una procedura guidata e verranno quindi apportate alcune modifiche allo scopo di illustrare le potenzialità offerte all'utente.</span><span class="sxs-lookup"><span data-stu-id="e46e4-103">In this tutorial, you'll create a pie chart by using a wizard, and then you'll modify it a little, just to get an idea of what's possible.</span></span> <span data-ttu-id="e46e4-104">È possibile eseguire questa esercitazione in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="e46e4-104">You can do this tutorial two different ways.</span></span> <span data-ttu-id="e46e4-105">Entrambi i metodi hanno lo stesso risultato, ovvero un grafico a torta simile a quello illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="e46e4-105">Both methods have the same outcome-a pie chart like the one in the following illustration:</span></span>

 <span data-ttu-id="e46e4-106">!["Primo grafico a torta" nella visualizzazione Esegui](../media/rs-my1stpierunview.gif "Primo grafico a torta in Run View")</span><span class="sxs-lookup"><span data-stu-id="e46e4-106">!["My First Pie Chart" in Run view](../media/rs-my1stpierunview.gif "My First Pie Chart in Run view")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e46e4-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e46e4-107">Prerequisites</span></span>
 <span data-ttu-id="e46e4-108">Se si utilizzano dati XML o una query [!INCLUDE[tsql](../../../includes/tsql-md.md)], è necessario avere accesso a Generatore report di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e46e4-108">Whether you use XML data or a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, you need to have access to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder.</span></span> <span data-ttu-id="e46e4-109">È possibile eseguire la versione autonoma o la versione ClickOnce disponibile in Gestione report o in un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e46e4-109">You can run the stand-alone version or the ClickOnce version available from Report Manager or a SharePoint site.</span></span> <span data-ttu-id="e46e4-110">Per le versioni ClickOnce, l'unica differenza riguarda il primo passaggio, ovvero l'apertura di Generatore report.</span><span class="sxs-lookup"><span data-stu-id="e46e4-110">Only the first step, how to open Report Builder, is different for ClickOnce versions.</span></span> <span data-ttu-id="e46e4-111">Per ulteriori informazioni, vedere [installazione, disinstallazione e supporto Generatore report](../install-uninstall-and-report-builder-support.md).</span><span class="sxs-lookup"><span data-stu-id="e46e4-111">For more information, see [Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md).</span></span>

##  <a name="two-ways-to-do-this-tutorial"></a><a name="TwoWays"></a><span data-ttu-id="e46e4-112">Due modi per eseguire questa esercitazione</span><span class="sxs-lookup"><span data-stu-id="e46e4-112">Two Ways To Do This Tutorial</span></span>

-   [<span data-ttu-id="e46e4-113">Creare il grafico a torta con dati XML</span><span class="sxs-lookup"><span data-stu-id="e46e4-113">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

-   [<span data-ttu-id="e46e4-114">Creare il grafico a torta con una query Transact-SQL contenente dati</span><span class="sxs-lookup"><span data-stu-id="e46e4-114">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

### <a name="using-xml-data-for-this-tutorial"></a><span data-ttu-id="e46e4-115">Utilizzo di dati XML per l'esercitazione</span><span class="sxs-lookup"><span data-stu-id="e46e4-115">Using XML data for this tutorial</span></span>
 <span data-ttu-id="e46e4-116">È possibile utilizzare dati XML copiandoli da questo argomento e incollandoli nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e46e4-116">You can use XML data that you copy from this topic and paste into the wizard.</span></span> <span data-ttu-id="e46e4-117">Non è necessario essere connessi a un server di report o a un server di report in modalità integrata SharePoint e non è necessario accedere a un'istanza di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e46e4-117">You don't need to be connected to a report server or a report server in SharePoint integrated mode, and you don't need access to an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>

 [<span data-ttu-id="e46e4-118">Creare il grafico a torta con dati XML</span><span class="sxs-lookup"><span data-stu-id="e46e4-118">Create the pie chart with XML data</span></span>](#CreatePieChartXML)

### <a name="using-a-transact-sql-query-that-contains-data-for-this-tutorial"></a><span data-ttu-id="e46e4-119">Utilizzo di una query Transact-SQL contenente dati per l'esercitazione</span><span class="sxs-lookup"><span data-stu-id="e46e4-119">Using a Transact-SQL query that contains data for this tutorial</span></span>
 <span data-ttu-id="e46e4-120">È possibile copiare una query contenente dati da questo argomento e incollarla nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e46e4-120">You can copy a query with data included in it from this topic and paste it into the wizard.</span></span> <span data-ttu-id="e46e4-121">Sarà necessario disporre del nome di un'istanza di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] e di credenziali sufficienti per l'accesso in sola lettura a qualsiasi database.</span><span class="sxs-lookup"><span data-stu-id="e46e4-121">You will need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="e46e4-122">Per la query del set di dati dell'esercitazione vengono utilizzati dati letterali, ma è necessario elaborare la query da un'istanza di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] per restituire i metadati richiesti per un set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="e46e4-122">The dataset query in the tutorial uses literal data, but the query must be processed by an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to return the metadata that is required for a report dataset.</span></span>

 <span data-ttu-id="e46e4-123">Il vantaggio dell'utilizzo della query [!INCLUDE[tsql](../../../includes/tsql-md.md)] è dato dal fatto che in tutte le altre esercitazioni di Generatore report viene utilizzato lo stesso metodo, pertanto durante le altre esercitazioni si conosceranno già le azioni da effettuare.</span><span class="sxs-lookup"><span data-stu-id="e46e4-123">The advantage of using the [!INCLUDE[tsql](../../../includes/tsql-md.md)] query is that all the other Report Builder tutorials use the same method, so when you do the other tutorials, you will already know what to do.</span></span>

 <span data-ttu-id="e46e4-124">Per la query [!INCLUDE[tsql](../../../includes/tsql-md.md)] sono necessari pochi altri prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="e46e4-124">The [!INCLUDE[tsql](../../../includes/tsql-md.md)] query does require a few other prerequisites.</span></span> <span data-ttu-id="e46e4-125">Per altre informazioni, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="e46e4-125">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

 [<span data-ttu-id="e46e4-126">Creare il grafico a torta con una query Transact-SQL contenente dati</span><span class="sxs-lookup"><span data-stu-id="e46e4-126">Create the pie chart with a Transact-SQL query that contains data</span></span>](#CreatePieQueryData)

## <a name="also-in-this-article"></a><span data-ttu-id="e46e4-127">Ulteriore contenuto dell'articolo</span><span class="sxs-lookup"><span data-stu-id="e46e4-127">Also in This Article</span></span>
 [<span data-ttu-id="e46e4-128">Al termine della procedura guidata</span><span class="sxs-lookup"><span data-stu-id="e46e4-128">After You Run the Wizard</span></span>](#AfterWizard)

 [<span data-ttu-id="e46e4-129">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e46e4-129">What's Next</span></span>](#WhatsNext)

##  <a name="creating-the-pie-chart-with-xml-data"></a><a name="CreatePieChartXML"></a><span data-ttu-id="e46e4-130">Creazione del grafico a torta con dati XML</span><span class="sxs-lookup"><span data-stu-id="e46e4-130">Creating the pie chart with XML data</span></span>

#### <a name="to-create-the-pie-chart-with-xml-data"></a><span data-ttu-id="e46e4-131">Per creare il grafico a torta con dati XML</span><span class="sxs-lookup"><span data-stu-id="e46e4-131">To create the pie chart with XML data</span></span>

1.  <span data-ttu-id="e46e4-132">Fare clic sul menu **Start**, scegliere **Programmi**, **Generatore report per Microsoft SQL Server 2012**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

     <span data-ttu-id="e46e4-133">Verrà visualizzata la finestra di dialogo **Introduzione** .</span><span class="sxs-lookup"><span data-stu-id="e46e4-133">The **Getting Started** dialog box appears.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="e46e4-134">Se la finestra di dialogo **Introduzione** non viene visualizzata, dal pulsante **Generatore report** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-134">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>

2.  <span data-ttu-id="e46e4-135">Nel riquadro sinistro verificare che sia selezionata l'opzione **report** .</span><span class="sxs-lookup"><span data-stu-id="e46e4-135">In the left pane, verify that **Report** is selected.</span></span>

3.  <span data-ttu-id="e46e4-136">Nel riquadro destro fare clic su **Creazione guidata grafico**, quindi scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-136">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="e46e4-137">Nella pagina **Scegliere un set di dati** fare clic su **Crea un set di dati**, quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-137">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="e46e4-138">Nella pagina **Scegliere una connessione a un'origine dei dati** fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-138">In the **Choose a connection to a data source** page, click **New**.</span></span>

     <span data-ttu-id="e46e4-139">Verrà visualizzata la finestra di dialogo **Proprietà origine dati** .</span><span class="sxs-lookup"><span data-stu-id="e46e4-139">The **Data Source Properties** dialog box opens.</span></span>

6.  <span data-ttu-id="e46e4-140">È possibile assegnare qualsiasi nome a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e46e4-140">You can name a data source anything you want.</span></span> <span data-ttu-id="e46e4-141">Nella casella **Nome** digitare **Grafico a torta**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-141">In the **Name** box, type **MyPieChart**.</span></span>

7.  <span data-ttu-id="e46e4-142">Nella casella **Seleziona tipo di connessione** fare clic su **XML.**</span><span class="sxs-lookup"><span data-stu-id="e46e4-142">In the **Select connection type** box, click **XML.**</span></span>

8.  <span data-ttu-id="e46e4-143">Fare clic sulla scheda **credenziali** , selezionare **USA utente di Windows corrente. Potrebbe essere richiesta la delega Kerberos**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-143">Click the **Credentials** tab, select **Use current Windows user. Kerberos delegation may be required**, and then click **OK**.</span></span>

9. <span data-ttu-id="e46e4-144">Nella pagina **Scegliere una connessione a un'origine dei dati** fare clic su **Grafico a torta**, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-144">In the **Choose a connection to a data source** page, click **MyPieChart**, and then click **Next**.</span></span>

10. <span data-ttu-id="e46e4-145">Copiare il testo seguente e incollarlo nella casella grande al centro della pagina **Progetta query** .</span><span class="sxs-lookup"><span data-stu-id="e46e4-145">Copy the following text and paste it in the large box in the center of the **Design a query** page.</span></span>

    ```
    <Query>
    <ElementPath>Root /S  {@Sales (Integer)} /C {@FullName} </ElementPath>
    <XmlData>
    <Root>
    <S Sales="150">
      <C FullName="Jae Pak" />
    </S>
    <S Sales="350">
      <C FullName="Jillian  Carson" />
    </S>
    <S Sales="250">
      <C FullName="Linda C Mitchell" />
    </S>
    <S Sales="500">
      <C FullName="Michael Blythe" />
    </S>
    <S Sales="450">
      <C FullName="Ranjit Varkey" />
    </S>
    </Root>
    </XmlData>
    </Query>
    ```

11. <span data-ttu-id="e46e4-146">(Facoltativo) Fare clic sul pulsante Esegui (**!**) per visualizzare i dati su cui si baserà il grafico.</span><span class="sxs-lookup"><span data-stu-id="e46e4-146">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

12. <span data-ttu-id="e46e4-147">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-147">Click **Next**.</span></span>

13. <span data-ttu-id="e46e4-148">Nella pagina **Scegliere un tipo di grafico** fare clic su **Torta**, quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-148">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

14. <span data-ttu-id="e46e4-149">Nella pagina relativa alla **disposizione dei campi del grafico** fare doppio clic sul campo **Vendite** nella casella **Campi disponibili**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-149">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="e46e4-150">Il campo verrà spostato automaticamente nella casella **Valori** perché rappresenta un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="e46e4-150">Note that it automatically moves to the **Values** box, because it is a numerical value.</span></span>

15. <span data-ttu-id="e46e4-151">Trascinare il campo **FullName** dalla casella **Campi disponibili** alla casella **Categorie**. In alternativa è possibile fare doppio clic sul campo per spostarlo nella casella **Categorie**. Al termine fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-151">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

16. <span data-ttu-id="e46e4-152">Per impostazione predefinita, nella pagina **Scegli uno stile** è selezionata l'opzione **oceano** .</span><span class="sxs-lookup"><span data-stu-id="e46e4-152">In the **Choose a style** page, **Ocean** is selected by default.</span></span> <span data-ttu-id="e46e4-153">Fare clic sugli altri stili per visualizzarne l'aspetto.</span><span class="sxs-lookup"><span data-stu-id="e46e4-153">Click the other styles to see what they look like.</span></span>

17. <span data-ttu-id="e46e4-154">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-154">Click **Finish**.</span></span>

     <span data-ttu-id="e46e4-155">Osservare ora il nuovo report grafico a torta nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e46e4-155">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="e46e4-156">Gli elementi visualizzati sono esemplificativi.</span><span class="sxs-lookup"><span data-stu-id="e46e4-156">What you see is representational.</span></span> <span data-ttu-id="e46e4-157">Nella legenda sono riportate le diciture Full Name 1, Full Name 2 e così via, anziché i nomi dei venditori, e le dimensioni delle sezioni della torta non sono precise.</span><span class="sxs-lookup"><span data-stu-id="e46e4-157">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="e46e4-158">L'esempio serve solo per dare un'idea generale dell'aspetto del report.</span><span class="sxs-lookup"><span data-stu-id="e46e4-158">This is just to give you an idea of what your report will look like.</span></span>

18. <span data-ttu-id="e46e4-159">Per visualizzare il grafico a torta effettivo, fare clic su **Esegui** nella scheda **Home** della barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="e46e4-159">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="e46e4-160">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Torna all'inizio](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="e46e4-160">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="creating-the-pie-chart-with-a-tsql-query"></a><a name="CreatePieQueryData"></a> <span data-ttu-id="e46e4-161">Creazione del grafico a torta con una query [!INCLUDE[tsql](../../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e46e4-161">Creating the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query</span></span>

#### <a name="to-create-the-pie-chart-with-a-tsql-query-that-contains-data"></a><span data-ttu-id="e46e4-162">Per creare il grafico a torta con una query [!INCLUDE[tsql](../../../includes/tsql-md.md)] contenente dati</span><span class="sxs-lookup"><span data-stu-id="e46e4-162">To create the pie chart with a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query that contains data</span></span>

1.  <span data-ttu-id="e46e4-163">Fare clic sul menu **Start**, scegliere **Programmi**, **Generatore report per Microsoft SQL Server 2012**e quindi fare clic su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-163">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

2.  <span data-ttu-id="e46e4-164">Nella finestra di dialogo **nuovo report o set di dati** verificare che il **report** sia selezionato nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="e46e4-164">In the **New report or dataset** dialog box, verify that **Report** is selected in the left pane.</span></span>

3.  <span data-ttu-id="e46e4-165">Nel riquadro destro fare clic su **Creazione guidata grafico**, quindi scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-165">In the right pane, click **Chart Wizard**, and then click **Create**.</span></span>

4.  <span data-ttu-id="e46e4-166">Nella pagina **Scegliere un set di dati** fare clic su **Crea un set di dati**, quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-166">In the **Choose a dataset** page, click **Create a dataset**, and then click **Next**.</span></span>

5.  <span data-ttu-id="e46e4-167">Nella pagina **Scegliere una connessione a un'origine dei dati** selezionare un'origine dati esistente o individuare il server di report, quindi selezionare un'origine dati e scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-167">In the **Choose a connection to a data source** page, select an existing data source or browse to the report server and select a data source, and then click **Next**.</span></span> <span data-ttu-id="e46e4-168">Potrebbe essere necessario immettere un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="e46e4-168">You may need to enter a user name and password.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="e46e4-169">L'origine dati scelta non ha importanza purché si disponga delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="e46e4-169">The data source you choose is unimportant, as long as you have adequate permissions.</span></span> <span data-ttu-id="e46e4-170">Non verranno recuperati dati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e46e4-170">You will not be getting data from the data source.</span></span> <span data-ttu-id="e46e4-171">Per altre informazioni, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="e46e4-171">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md).</span></span>

6.  <span data-ttu-id="e46e4-172">Nella pagina **Progetta query** fare clic su **modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-172">On the **Design a Query** page, click **Edit as Text**.</span></span>

7.  <span data-ttu-id="e46e4-173">Incollare la query seguente nel relativo riquadro:</span><span class="sxs-lookup"><span data-stu-id="e46e4-173">Paste the following query into the query pane:</span></span>

    ```
    SELECT 150 AS Sales, 'Jae Pak' AS FullName 
    UNION SELECT 350 AS Sales, 'Jillian Carson' AS FullName 
    UNION SELECT 250 AS Sales, 'Linda C Mitchell' AS FullName 
    UNION SELECT 500 AS Sales, 'Michael Blythe' AS FullName 
    UNION SELECT 450 AS Sales, 'Ranjit Varkey' AS FullName 
    ```

8.  <span data-ttu-id="e46e4-174">(Facoltativo) Fare clic sul pulsante Esegui (**!**) per visualizzare i dati su cui si baserà il grafico.</span><span class="sxs-lookup"><span data-stu-id="e46e4-174">(Optional) Click the Run button (**!**) to see the data your chart will be based on.</span></span>

9. <span data-ttu-id="e46e4-175">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-175">Click **Next**.</span></span>

10. <span data-ttu-id="e46e4-176">Nella pagina **Scegliere un tipo di grafico** fare clic su **Torta**, quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-176">In the **Choose a chart type** page, click **Pie**, and then click **Next**.</span></span>

11. <span data-ttu-id="e46e4-177">Nella pagina relativa alla **disposizione dei campi del grafico** fare doppio clic sul campo **Vendite** nella casella **Campi disponibili**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-177">In the **Arrange chart fields** page, double-click the **Sales** field in the **Available fields** box.</span></span>

     <span data-ttu-id="e46e4-178">Il campo verrà spostato automaticamente nella casella **Valori** perché rappresenta un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="e46e4-178">Note that it automatically moves to the **Values** box, because it's a numerical value.</span></span>

12. <span data-ttu-id="e46e4-179">Trascinare il campo **FullName** dalla casella **Campi disponibili** alla casella **Categorie**. In alternativa è possibile fare doppio clic sul campo per spostarlo nella casella **Categorie**. Al termine fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-179">Drag the **FullName** field from the **Available fields** box to the **Categories** box (or double-click it; it will go to the **Categories** box), and then click **Next**.</span></span>

13. <span data-ttu-id="e46e4-180">Per impostazione predefinita, nella pagina **Scegliere uno stile** è selezionato lo stile Oceano.</span><span class="sxs-lookup"><span data-stu-id="e46e4-180">In the **Choose a style** page, Ocean is selected by default.</span></span> <span data-ttu-id="e46e4-181">Fare clic sugli altri stili per visualizzarne l'aspetto.</span><span class="sxs-lookup"><span data-stu-id="e46e4-181">Click the other styles to see what they look like.</span></span>

14. <span data-ttu-id="e46e4-182">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-182">Click **Finish**.</span></span>

     <span data-ttu-id="e46e4-183">Osservare ora il nuovo report grafico a torta nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e46e4-183">You're now looking at your new pie chart report on the design surface.</span></span> <span data-ttu-id="e46e4-184">Gli elementi visualizzati sono esemplificativi.</span><span class="sxs-lookup"><span data-stu-id="e46e4-184">What you see is representational.</span></span> <span data-ttu-id="e46e4-185">Nella legenda sono riportate le diciture Full Name 1, Full Name 2 e così via, anziché i nomi dei venditori, e le dimensioni delle sezioni della torta non sono precise.</span><span class="sxs-lookup"><span data-stu-id="e46e4-185">The legend reads Full Name 1, Full Name 2, etc., rather than the salespeople's names, and the size of the slices of pie are not accurate.</span></span> <span data-ttu-id="e46e4-186">L'esempio serve solo per dare un'idea generale dell'aspetto del report.</span><span class="sxs-lookup"><span data-stu-id="e46e4-186">This is just to give you an idea of what your report will look like.</span></span>

15. <span data-ttu-id="e46e4-187">Per visualizzare il grafico a torta effettivo, fare clic su **Esegui** nella scheda **Home** della barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="e46e4-187">To see your actual pie chart, click **Run** on the **Home** tab of the Ribbon.</span></span>

 <span data-ttu-id="e46e4-188">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Torna all'inizio](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="e46e4-188">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="after-you-run-the-wizard"></a><a name="AfterWizard"></a><span data-ttu-id="e46e4-189">Dopo l'esecuzione della procedura guidata</span><span class="sxs-lookup"><span data-stu-id="e46e4-189">After You Run the Wizard</span></span>
 <span data-ttu-id="e46e4-190">Dopo aver terminato la creazione del report del grafico a torta, è possibile modificarlo nel modo desiderato.</span><span class="sxs-lookup"><span data-stu-id="e46e4-190">Now that you have your pie chart report, you can play with it.</span></span> <span data-ttu-id="e46e4-191">Nella scheda **Esegui** della barra multifunzione fare clic su **Progettazione**per continuare a modificarlo.</span><span class="sxs-lookup"><span data-stu-id="e46e4-191">On the **Run** tab of the Ribbon, click **Design**, so you can continue modifying it.</span></span>

### <a name="make-the-chart-bigger"></a><span data-ttu-id="e46e4-192">Ingrandire il grafico</span><span class="sxs-lookup"><span data-stu-id="e46e4-192">Make the chart bigger</span></span>
 <span data-ttu-id="e46e4-193">Potrebbe essere necessario ingrandire il grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="e46e4-193">You may want the pie chart to be bigger.</span></span> <span data-ttu-id="e46e4-194">Fare clic sul grafico, ma non sugli elementi in esso contenuti, per selezionarlo e trascinare l'angolo inferiore destro per ridimensionarlo.</span><span class="sxs-lookup"><span data-stu-id="e46e4-194">Click the chart, but not on any element in the chart, to select it and drag the lower-right corner to resize it.</span></span>

### <a name="add-a-report-title"></a><span data-ttu-id="e46e4-195">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="e46e4-195">Add a report title</span></span>
 <span data-ttu-id="e46e4-196">Selezionare le parole **Titolo grafico** nella parte superiore del grafico, quindi digitare un titolo, ad esempio **Grafico a torta - Vendite**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-196">Select the words **Chart title** at the top of the chart, and then type a title, such as **Sales Pie Chart**.</span></span>

### <a name="add-percentages"></a><span data-ttu-id="e46e4-197">Aggiungere percentuali</span><span class="sxs-lookup"><span data-stu-id="e46e4-197">Add percentages</span></span>

##### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="e46e4-198">Per visualizzare valori in percentuale come etichette in un grafico a torta</span><span class="sxs-lookup"><span data-stu-id="e46e4-198">To display percentage values as labels on a pie chart</span></span>

1.  <span data-ttu-id="e46e4-199">Fare clic con il pulsante destro del mouse sul grafico a torta e scegliere **Mostra etichette dati**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-199">Right-click on the pie chart and select **Show Data Labels**.</span></span> <span data-ttu-id="e46e4-200">Le etichette dati dovrebbero apparire in ogni sezione del grafico a torta.</span><span class="sxs-lookup"><span data-stu-id="e46e4-200">The data labels should appear within each slice on the pie chart.</span></span>

2.  <span data-ttu-id="e46e4-201">Fare clic con il pulsante destro del mouse sulle etichette e scegliere **Proprietà etichetta serie**.</span><span class="sxs-lookup"><span data-stu-id="e46e4-201">Right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="e46e4-202">Verrà visualizzata la finestra di dialogo **Proprietà etichetta serie** .</span><span class="sxs-lookup"><span data-stu-id="e46e4-202">The **Series Label Properties** dialog box appears.</span></span>

3.  <span data-ttu-id="e46e4-203">Digitare `#PERCENT{P0}` per l'opzione **dati etichetta** .</span><span class="sxs-lookup"><span data-stu-id="e46e4-203">Type `#PERCENT{P0}` for the **Label data** option.</span></span>

     <span data-ttu-id="e46e4-204">Il testo `{P0}` specifica la percentuale senza cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="e46e4-204">The `{P0}` gives you the percentage without decimal places.</span></span> <span data-ttu-id="e46e4-205">Se si digita solo `#PERCENT`, i numeri avranno due cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="e46e4-205">If you type just `#PERCENT`, your numbers will have two decimal places.</span></span> <span data-ttu-id="e46e4-206">`#PERCENT` è una parola chiave che esegue un calcolo o una funzione. Ne sono disponibili anche diverse altre.</span><span class="sxs-lookup"><span data-stu-id="e46e4-206">`#PERCENT` is a keyword that performs a calculation or function for you; there are many others.</span></span>

 <span data-ttu-id="e46e4-207">Per altre informazioni sulla personalizzazione di etichette e legende dei grafici, vedere [Visualizzare i valori in percentuale in un grafico a torta &#40;Generatore report e SSRS&#41;](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) e [Modificare il testo di un elemento legenda &#40;Generatore report e SSRS&#41;](../report-design/chart-legend-change-item-text-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e46e4-207">For more information about customizing chart labels and legends, see [Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;](../report-design/display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md) and [Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](../report-design/chart-legend-change-item-text-report-builder.md).</span></span>

 <span data-ttu-id="e46e4-208">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Torna all'inizio](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="e46e4-208">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

##  <a name="whats-next"></a><a name="WhatsNext"></a><span data-ttu-id="e46e4-209">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e46e4-209">What's Next?</span></span>
 <span data-ttu-id="e46e4-210">Al termine della creazione del primo report in Generatore report, è possibile provare a eseguire le altre esercitazioni e iniziare a creare report basati su dati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e46e4-210">Now that you have created your first report in Report Builder, you are ready to try the other tutorials and to start creating reports from your own data.</span></span> <span data-ttu-id="e46e4-211">Per eseguire Generatore report, è necessario disporre dell'autorizzazione per accedere alle origini dati, ad esempio i database, con una *stringa di connessione*che connette effettivamente all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e46e4-211">To run Report Builder, you need permission to access your data sources, such as databases, with a *connection string*, which actually connects you to the data source.</span></span> <span data-ttu-id="e46e4-212">L'amministratore di sistema disporrà di queste informazioni e potrà procedere alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="e46e4-212">Your system administrator will have this information and can set you up.</span></span>

 <span data-ttu-id="e46e4-213">Per eseguire le altre esercitazioni, è necessario disporre del nome di un'istanza di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] e di credenziali sufficienti per l'accesso in sola lettura a qualsiasi database.</span><span class="sxs-lookup"><span data-stu-id="e46e4-213">To work through the other tutorials, you need the name of an instance of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] and credentials sufficient for read-only access to any database.</span></span> <span data-ttu-id="e46e4-214">L'amministratore di sistema potrà fornire i dati necessari.</span><span class="sxs-lookup"><span data-stu-id="e46e4-214">Your system administrator can also set that up for you.</span></span>

 <span data-ttu-id="e46e4-215">Per salvare infine i report in un server di report o in un sito di SharePoint integrato con un server di report, è necessario disporre dell'URL e delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="e46e4-215">Finally, to save your reports to a report server or a SharePoint site that is integrated with a report server, you need the URL and permissions.</span></span> <span data-ttu-id="e46e4-216">Tutti i report creati possono essere eseguiti direttamente dal computer, tuttavia quando vengono eseguiti dal server di report o dal sito di SharePoint i report offrono maggiori funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e46e4-216">You can run any report you create directly from your computer, but reports have more functionality when run from the report server or SharePoint site.</span></span> <span data-ttu-id="e46e4-217">Per eseguire i propri report o quelli presenti sul server di report o nel sito di SharePoint in cui vengono pubblicati è necessario disporre delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="e46e4-217">You need permissions to run your reports or others from the report server or SharePoint site where they are published.</span></span> <span data-ttu-id="e46e4-218">Per ottenere l'accesso è necessario rivolgersi all'amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="e46e4-218">Talk to your system administrator to obtain access.</span></span>

 <span data-ttu-id="e46e4-219">Prima di iniziare può essere utile leggere le informazioni su alcuni concetti e termini.</span><span class="sxs-lookup"><span data-stu-id="e46e4-219">It may help to read about some of the concepts and terms before you get started.</span></span> <span data-ttu-id="e46e4-220">Per ulteriori informazioni, vedere [concetti relativi alla creazione di Report &#40;Generatore report e SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e46e4-220">For more information, see [Report Authoring Concepts &#40;Report Builder and SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="e46e4-221">È inoltre consigliabile dedicarsi alla pianificazione prima di creare il primo report.</span><span class="sxs-lookup"><span data-stu-id="e46e4-221">Also, spend some time planning, before you create your first report.</span></span> <span data-ttu-id="e46e4-222">Questa fase preliminare risulterà infatti molto utile.</span><span class="sxs-lookup"><span data-stu-id="e46e4-222">It will be time well spent.</span></span> <span data-ttu-id="e46e4-223">Per ulteriori informazioni, vedere [pianificazione di un Report &#40;Generatore report&#41;](../report-design/planning-a-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e46e4-223">For more information, see [Planning a Report &#40;Report Builder&#41;](../report-design/planning-a-report-report-builder.md).</span></span>

 <span data-ttu-id="e46e4-224">![Icona freccia usata con il collegamento Torna all'inizio](../../2014-toc/media/uparrow16x16.gif "Icona freccia usata con il collegamento Torna all'inizio") [Torna all'inizio](#TwoWays)</span><span class="sxs-lookup"><span data-stu-id="e46e4-224">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Back to Top](#TwoWays)</span></span>

## <a name="see-also"></a><span data-ttu-id="e46e4-225">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e46e4-225">See Also</span></span>
 <span data-ttu-id="e46e4-226">[Esercitazioni &#40;Generatore report&#41;](../report-builder-tutorials.md) [Generatore report in SQL Server 2014](report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="e46e4-226">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder-in-sql-server-2016.md)</span></span>


