---
title: 'Esercitazione: Introduzione alle espressioni | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d05ef4c-5f91-48b2-8795-f0a201a0b3cc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62a815800dba0730052eb812124d4561d031d0e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722427"
---
# <a name="tutorial-introducing-expressions"></a><span data-ttu-id="c1a89-102">Esercitazione: Introduzione alle espressioni</span><span class="sxs-lookup"><span data-stu-id="c1a89-102">Tutorial: Introducing Expressions</span></span>
  <span data-ttu-id="c1a89-103">Le espressioni consentono di creare report potenti e flessibili.</span><span class="sxs-lookup"><span data-stu-id="c1a89-103">Expressions help you create powerful and flexible reports.</span></span> <span data-ttu-id="c1a89-104">In questa esercitazione verrà illustrato come creare e implementare espressioni in cui vengono utilizzati operatori e funzioni comuni.</span><span class="sxs-lookup"><span data-stu-id="c1a89-104">This tutorial teaches you to create and implement expressions that use common functions and operators.</span></span> <span data-ttu-id="c1a89-105">Si utilizzerà la finestra di dialogo **espressione** per scrivere espressioni che concatenano i valori dei nomi, ricercare valori in un set di dati separato, visualizzare immagini diverse in base ai valori dei campi e così via.</span><span class="sxs-lookup"><span data-stu-id="c1a89-105">You will use the **Expression** dialog box to write expressions that concatenate name values, look up values in a separate dataset, display different pictures based on field values, and so on.</span></span>  
  
 <span data-ttu-id="c1a89-106">Il report è a barre con righe alternate in bianco e in un altro colore</span><span class="sxs-lookup"><span data-stu-id="c1a89-106">The report is a barred report with alternating row colors in white and a color.</span></span> <span data-ttu-id="c1a89-107">che può essere selezionato tramite un parametro incluso nel report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-107">The report includes a parameter for selecting the color of the non-white rows.</span></span>  
  
 <span data-ttu-id="c1a89-108">Nell'immagine seguente viene illustrato un report simile a quello che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="c1a89-108">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="c1a89-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span><span class="sxs-lookup"><span data-stu-id="c1a89-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="c1a89-110">Cosa si apprenderà</span><span class="sxs-lookup"><span data-stu-id="c1a89-110">What You Will Learn</span></span>  
 <span data-ttu-id="c1a89-111">In questa esercitazione verranno illustrate le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1a89-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="c1a89-112">Creare un report tabella e un set di dati dalla Creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="c1a89-112">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="c1a89-113">Aggiornare i nomi predefiniti dell'origine dati e del set di dati</span><span class="sxs-lookup"><span data-stu-id="c1a89-113">Update Default Names of the Data Source and Dataset</span></span>](#UpdateNames)  
  
3.  [<span data-ttu-id="c1a89-114">Visualizzare il nome, l'iniziale e il cognome</span><span class="sxs-lookup"><span data-stu-id="c1a89-114">Display First Name, Initial, and Last Name</span></span>](#Concatenate)  
  
4.  [<span data-ttu-id="c1a89-115">Utilizzare immagini per visualizzare il sesso</span><span class="sxs-lookup"><span data-stu-id="c1a89-115">Use Images to Display Gender</span></span>](#Gender)  
  
5.  [<span data-ttu-id="c1a89-116">Cercare il nome CountryRegion</span><span class="sxs-lookup"><span data-stu-id="c1a89-116">Look Up CountryRegion Name</span></span>](#Lookup)  
  
6.  [<span data-ttu-id="c1a89-117">Contare i giorni dall'ultimo acquisto</span><span class="sxs-lookup"><span data-stu-id="c1a89-117">Count Days Since Last Purchase</span></span>](#Count)  
  
7.  [<span data-ttu-id="c1a89-118">Utilizzare un indicatore per mostrare il confronto vendite</span><span class="sxs-lookup"><span data-stu-id="c1a89-118">Use an Indicator to Show Sales Comparison</span></span>](#Indicator)  
  
8.  [<span data-ttu-id="c1a89-119">Rendere il report un report "barra verde"</span><span class="sxs-lookup"><span data-stu-id="c1a89-119">Make the Report a "Green Bar" Report</span></span>](#GreenBar)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="c1a89-120">Altri passaggi facoltativi</span><span class="sxs-lookup"><span data-stu-id="c1a89-120">Other Optional Steps</span></span>  
  
-   [<span data-ttu-id="c1a89-121">Formattare la colonna della data</span><span class="sxs-lookup"><span data-stu-id="c1a89-121">Format Date Column</span></span>](#DateFormat)  
  
-   [<span data-ttu-id="c1a89-122">Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="c1a89-122">Add a Report Title</span></span>](#Title)  
  
-   [<span data-ttu-id="c1a89-123">Salva il report</span><span class="sxs-lookup"><span data-stu-id="c1a89-123">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="c1a89-124">Tempo previsto per il completamento di questa esercitazione: 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="c1a89-124">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1a89-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1a89-125">Requirements</span></span>  
 <span data-ttu-id="c1a89-126">Per informazioni sui requisiti, vedere [Prerequisiti per le esercitazioni &#40;Generatore report&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="c1a89-126">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="c1a89-127">1. creare un report tabella e un set di dati dalla creazione guidata tabella o matrice</span><span class="sxs-lookup"><span data-stu-id="c1a89-127">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="c1a89-128">Creare un report tabella, un'origine dati e un set di dati.</span><span class="sxs-lookup"><span data-stu-id="c1a89-128">Create a table report, a data source, and a dataset.</span></span> <span data-ttu-id="c1a89-129">Durante la disposizione della tabella verranno inclusi solo pochi campi.</span><span class="sxs-lookup"><span data-stu-id="c1a89-129">When you lay out the table, you will include only a few fields.</span></span> <span data-ttu-id="c1a89-130">Dopo aver completato la procedura guidata, si aggiungeranno manualmente colonne.</span><span class="sxs-lookup"><span data-stu-id="c1a89-130">After you complete the wizard you will manually add columns.</span></span> <span data-ttu-id="c1a89-131">La procedura guidata consente di disporre la tabella e di applicare uno stile facilmente.</span><span class="sxs-lookup"><span data-stu-id="c1a89-131">The wizard makes it easy for you to lay out the table and apply a style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1a89-132">Nella query di questa esercitazione sono contenuti i valori dei dati in modo che non sia necessaria un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="c1a89-132">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="c1a89-133">Tale condizione rende tuttavia la query piuttosto lunga.</span><span class="sxs-lookup"><span data-stu-id="c1a89-133">This makes the query quite long.</span></span> <span data-ttu-id="c1a89-134">In una query di un ambiente aziendale non sarebbe incluso alcun dato.</span><span class="sxs-lookup"><span data-stu-id="c1a89-134">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="c1a89-135">Questo esempio è solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="c1a89-135">This is for learning purposes only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1a89-136">In questa esercitazione, i passaggi per la procedura guidata sono consolidati in un'unica procedura.</span><span class="sxs-lookup"><span data-stu-id="c1a89-136">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="c1a89-137">Per istruzioni dettagliate su come selezionare un server di report, come scegliere un'origine dati e come creare un set di dati, vedere la prima esercitazione di questa serie: [Esercitazione: Creazione di un report tabella semplice &#40;Generatore report&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c1a89-137">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
#### <a name="to-create-a-new-table-report"></a><span data-ttu-id="c1a89-138">Per creare un nuovo report tabella</span><span class="sxs-lookup"><span data-stu-id="c1a89-138">To create a new table report</span></span>  
  
1.  <span data-ttu-id="c1a89-139">Fare clic sul pulsante **Start**, scegliere **programmi**, fare clic su [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Generatore report**e quindi su **Generatore report**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-139">Click **Start**, point to **Programs**, click [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="c1a89-140">Verrà visualizzata la finestra di dialogo **Introduzione** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-140">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1a89-141">Se la finestra di dialogo **Introduzione** non viene visualizzata, dal pulsante **Generatore report** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-141">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1a89-142">Se si preferisce utilizzare la versione ClickOnce di Generatore report, aprire Gestione report e fare clic su **Generatore report**oppure accedere a un sito di SharePoint in cui sono abilitati i tipi di contenuto di Reporting Services, ad esempio i report, quindi fare clic su **Generatore report report** dal menu **nuovo documento** nella scheda **documenti** di una raccolta documenti condivisa.</span><span class="sxs-lookup"><span data-stu-id="c1a89-142">If you prefer using the ClickOnce version of Report Builder, open Report Manager and click **Report Builder**, or go to a SharePoint site on which Reporting Services content types such as reports are enabled and click **Report Builder Report** on the **New Document** menu on the **Documents** tab of a shared documents library.</span></span>  
  
2.  <span data-ttu-id="c1a89-143">Nel riquadro sinistro verificare che sia selezionata l'opzione **Nuovo report** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-143">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="c1a89-144">Nel riquadro destro fare clic su **Creazione guidata tabella o matrice**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-144">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="c1a89-145">Nella pagina **Scegliere un set di dati** fare clic su **Crea un set di dati**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-145">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="c1a89-146">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="c1a89-147">Nella pagina **Scegliere una connessione a un'origine dei dati** selezionare un'origine dati che sia del tipo **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-147">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="c1a89-148">Selezionare un'origine dati dall'elenco o passare al server di report per selezionarne una.</span><span class="sxs-lookup"><span data-stu-id="c1a89-148">Select a data source from the list or browse to the report server to select one.</span></span>  
  
7.  <span data-ttu-id="c1a89-149">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-149">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="c1a89-150">Nella pagina **Progetta query** fare clic su **Modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-150">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="c1a89-151">Incollare la query seguente nel relativo riquadro:</span><span class="sxs-lookup"><span data-stu-id="c1a89-151">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Lauren' AS FirstName,'Johnson' AS LastName, 'American Samoa' AS StateProvince, 1 AS CountryRegionID,'Unknown' AS Gender, CAST(9996.60 AS money) AS YTDPurchase, CAST('2010-6-10' AS date) AS LastPurchase  
    UNION SELECT'Warren' AS FirstName, 'Pal' AS LastName, 'New South Wales' AS StateProvince, 2 AS CountryRegionID, 'Male' AS Gender, CAST(5747.25 AS money) AS YTDPurchase, CAST('2010-7-3' AS date) AS LastPurchase  
    UNION SELECT 'Fernando' AS FirstName, 'Ross' AS LastName, 'Alberta' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(9248.15 AS money) AS YTDPurchase, CAST('2010-10-17' AS date) AS LastPurchase  
    UNION SELECT 'Rob' AS FirstName, 'Caron' AS LastName, 'Northwest Territories' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(742.50 AS money) AS YTDPurchase, CAST('2010-4-29' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Bailey' AS LastName, 'British Columbia' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(1147.50 AS money) AS YTDPurchase, CAST('2010-6-15' AS date) AS LastPurchase  
    UNION SELECT  'Bridget' AS FirstName, 'She' AS LastName, 'Hamburg' AS StateProvince, 4 AS CountryRegionID, 'Female' AS Gender, CAST(7497.30 AS money) AS YTDPurchase, CAST('2010-5-10' AS date) AS LastPurchase  
    UNION SELECT 'Alexander' AS FirstName, 'Martin' AS LastName, 'Saxony' AS StateProvince, 4 AS CountryRegionID, 'Male' AS Gender, CAST(2997.60 AS money) AS YTDPurchase, CAST('2010-11-19' AS date) AS LastPurchase  
    UNION SELECT 'Yolanda' AS FirstName, 'Sharma' AS LastName ,'Micronesia' AS StateProvince, 5 AS CountryRegionID, 'Female' AS Gender, CAST(3247.95 AS money) AS YTDPurchase, CAST('2010-8-23' AS date) AS LastPurchase  
    UNION SELECT 'Marc' AS FirstName, 'Zimmerman' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1200.00 AS money) AS YTDPurchase, CAST('2010-11-16' AS date) AS LastPurchase  
    UNION SELECT 'Katherine' AS FirstName, 'Abel' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Female' AS Gender, CAST(2025.00 AS money) AS YTDPurchase, CAST('2010-12-1' AS date) AS LastPurchase  
    UNION SELECT 'Nicolas' as FirstName, 'Anand' AS LastName, 'Seine (Paris)' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1425.00 AS money) AS YTDPurchase, CAST('2010-12-11' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Peters' AS LastName, 'England' AS StateProvince, 12 AS CountryRegionID, 'Male' AS Gender, CAST(887.50 AS money) AS YTDPurchase, CAST('2010-8-15' AS date) AS LastPurchase  
    UNION SELECT 'Alison' AS FirstName, 'Nath' AS LastName, 'Alaska' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(607.50 AS money) AS YTDPurchase, CAST('2010-10-13' AS date) AS LastPurchase  
    UNION SELECT 'Grace' AS FirstName, 'Patterson' AS LastName, 'Kansas' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(1215.00 AS money) AS YTDPurchase, CAST('2010-10-18' AS date) AS LastPurchase  
    UNION SELECT 'Bobby' AS FirstName, 'Sanchez' AS LastName, 'North Dakota' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(6191.00 AS money) AS YTDPurchase, CAST('2010-9-17' AS date) AS LastPurchase  
    UNION SELECT 'Charles' AS FirstName, 'Reed' AS LastName, 'Nebraska' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8772.00 AS money) AS YTDPurchase, CAST('2010-8-27' AS date) AS LastPurchase  
    UNION SELECT 'Orlando' AS FirstName, 'Romeo' AS LastName, 'Texas' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8578.00 AS money) AS YTDPurchase, CAST('2010-7-29' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    ```  
  
     <span data-ttu-id="c1a89-152">Nella query vengono specificati nomi di colonne tra cui data di nascita, nome, cognome, stato o provincia, identificatore di paese/regione, sesso e acquisti da inizio anno.</span><span class="sxs-lookup"><span data-stu-id="c1a89-152">The query specifies column names that include a birth date, first name, last name, state or province, country/region identifier, gender, and year-to-date purchases.</span></span>  
  
10. <span data-ttu-id="c1a89-153">Sulla barra degli strumenti Progettazione query fare clic su **Esegui** (**!**).</span><span class="sxs-lookup"><span data-stu-id="c1a89-153">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="c1a89-154">Nel set di risultati vengono visualizzate 20 righe di dati e sono incluse le colonne seguenti: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase e LastPurchase.</span><span class="sxs-lookup"><span data-stu-id="c1a89-154">The result set displays 20 rows of data and includes the following columns: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase, and LastPurchase.</span></span>  
  
11. <span data-ttu-id="c1a89-155">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-155">Click **Next**.</span></span>  
  
12. <span data-ttu-id="c1a89-156">Nella pagina **Disponi campi** trascinare i campi seguenti nell'ordine specificato, dall'elenco **Campi disponibili** all'elenco **Valori** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-156">On the **Arrange fields** page, drag the following fields, in the specified order, from the **Available Fields** list to the **Values** list.</span></span>  
  
    -   <span data-ttu-id="c1a89-157">StateProvince</span><span class="sxs-lookup"><span data-stu-id="c1a89-157">StateProvince</span></span>  
  
    -   <span data-ttu-id="c1a89-158">CountryRegionID</span><span class="sxs-lookup"><span data-stu-id="c1a89-158">CountryRegionID</span></span>  
  
    -   <span data-ttu-id="c1a89-159">LastPurchase</span><span class="sxs-lookup"><span data-stu-id="c1a89-159">LastPurchase</span></span>  
  
    -   <span data-ttu-id="c1a89-160">YTDPurchase</span><span class="sxs-lookup"><span data-stu-id="c1a89-160">YTDPurchase</span></span>  
  
     <span data-ttu-id="c1a89-161">Dal momento che in CountryRegionID e YTDPurchase sono contenuti dati numerici, per impostazione predefinita a tali campi viene applicata l'aggregazione SUM.</span><span class="sxs-lookup"><span data-stu-id="c1a89-161">Because the CountryRegionID and YTDPurchase contain numeric data, the SUM aggregate is applied to them by default.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1a89-162">I campi FirstName e LastName non sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="c1a89-162">The FirstName and LastName fields are not included.</span></span> <span data-ttu-id="c1a89-163">Verranno aggiunti in un passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="c1a89-163">You will add them in a later step.</span></span>  
  
13. <span data-ttu-id="c1a89-164">Nell'elenco **valori** fare clic con il pulsante destro del mouse `CountryRegionID` e scegliere l'opzione **Sum** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-164">In the **Values** list, right-click `CountryRegionID` and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="c1a89-165">Al campo CountryRegionID non viene più applicata la somma.</span><span class="sxs-lookup"><span data-stu-id="c1a89-165">Sum is no longer applied to CountryRegionID.</span></span>  
  
14. <span data-ttu-id="c1a89-166">Nell'elenco **Valori** fare clic con il pulsante destro del mouse su **YTDPurchase** e sull'opzione **Somma** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-166">In the **Values** list, right-click **YTDPurchase** and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="c1a89-167">Al campo YTDPurchase non viene più applicata la somma.</span><span class="sxs-lookup"><span data-stu-id="c1a89-167">Sum is no longer applied to YTDPurchase.</span></span>  
  
15. <span data-ttu-id="c1a89-168">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-168">Click **Next**.</span></span>  
  
16. <span data-ttu-id="c1a89-169">Nella pagina **Scegliere il layout** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-169">On the **Choose the layout** page, click **Next**.</span></span>  
  
17. <span data-ttu-id="c1a89-170">Nella pagina **scegliere uno stile** fare clic su **Slate**, quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-170">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
##  <a name="2-update-default-names-of-the-data-source-and-dataset"></a><a name="UpdateNames"></a><span data-ttu-id="c1a89-171">2. aggiornare i nomi predefiniti dell'origine dati e del set di dati</span><span class="sxs-lookup"><span data-stu-id="c1a89-171">2. Update Default Names of the Data Source and Dataset</span></span>  
  
#### <a name="to-update-the-default-name-of-the-data-source"></a><span data-ttu-id="c1a89-172">Per aggiornare il nome predefinito dell'origine dati</span><span class="sxs-lookup"><span data-stu-id="c1a89-172">To update the default name of the data source</span></span>  
  
1.  <span data-ttu-id="c1a89-173">Nel riquadro Dati report espandere **Origini dati**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-173">In the Report Data pane, expand **Data Sources**.</span></span>  
  
2.  <span data-ttu-id="c1a89-174">Fare clic con il pulsante destro del mouse su **DataSource1** e scegliere **Proprietà origine dati.**</span><span class="sxs-lookup"><span data-stu-id="c1a89-174">Right-click **DataSource1** and click **Data Source Properties.**</span></span>  
  
3.  <span data-ttu-id="c1a89-175">Nella casella **Nome** digitare **ExpressionsDataSource**</span><span class="sxs-lookup"><span data-stu-id="c1a89-175">In the **Name** box, type **ExpressionsDataSource**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-update-the-default-name-of-the-dataset"></a><span data-ttu-id="c1a89-176">Per aggiornare il nome predefinito del set di dati</span><span class="sxs-lookup"><span data-stu-id="c1a89-176">To update the default name of the dataset</span></span>  
  
1.  <span data-ttu-id="c1a89-177">Nel riquadro Dati report espandere **Set di dati**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-177">In the Report Data pane, expand **Datasets**.</span></span>  
  
2.  <span data-ttu-id="c1a89-178">Fare clic con il pulsante destro del mouse su **DataSet1** e scegliere **Proprietà set di dati.**</span><span class="sxs-lookup"><span data-stu-id="c1a89-178">Right-click **DataSet1** and click **Dataset Properties.**</span></span>  
  
3.  <span data-ttu-id="c1a89-179">Nella casella **Nome** digitare **Expressions**</span><span class="sxs-lookup"><span data-stu-id="c1a89-179">In the **Name** box, type **Expressions**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="3-display-first-name-initial-and-last-name"></a><a name="Concatenate"></a><span data-ttu-id="c1a89-180">3. visualizzare il nome, l'iniziale e il cognome</span><span class="sxs-lookup"><span data-stu-id="c1a89-180">3. Display First Name, Initial, and Last Name</span></span>  
 <span data-ttu-id="c1a89-181">Usare la funzione **Left** e l'operatore di **concatenazione**(**&**) in un'espressione tramite cui viene restituito un nome con un'iniziale e un cognome.</span><span class="sxs-lookup"><span data-stu-id="c1a89-181">Use the **Left** function and the **Concatenate** (**&**) operator in an expression that evaluates to a name that includes an initial and a last name.</span></span> <span data-ttu-id="c1a89-182">È possibile compilare l'espressione passaggio dopo passaggio oppure andare avanti nella procedura e copiare e incollare l'espressione dall'esercitazione nella finestra di dialogo **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-182">You can build the expression step by step or skip ahead in the procedure and copy/paste the expression from the tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the-name-column"></a><span data-ttu-id="c1a89-183">Per aggiungere la colonna Name</span><span class="sxs-lookup"><span data-stu-id="c1a89-183">To add the Name column</span></span>  
  
1.  <span data-ttu-id="c1a89-184">Fare clic con il pulsante destro del mouse sulla colonna **StateProvince** , scegliere **Inserisci colonna**e fare clic su **A sinistra**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-184">Right-click the **StateProvince** column, point to **Insert Column**, and then click **Left**.</span></span>  
  
     <span data-ttu-id="c1a89-185">Una nuova colonna verrà aggiunta a sinistra della colonna **StateProvince** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-185">A new column is added to the left of the **StateProvince** column.</span></span>  
  
2.  <span data-ttu-id="c1a89-186">Fare clic sul titolo della nuova colonna e digitare **Name**</span><span class="sxs-lookup"><span data-stu-id="c1a89-186">Click the title of the new column and type **Name**</span></span>  
  
3.  <span data-ttu-id="c1a89-187">Fare clic con il pulsante destro del mouse sulla cella di dati per la colonna **Name** e scegliere **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-187">Right-click the data cell for the **Name** column and click **Expression**.</span></span>  
  
4.  <span data-ttu-id="c1a89-188">Nella finestra di dialogo **Espressione** espandere **Funzioni comuni**e fare clic su **Text**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-188">In the **Expression** dialog box, expand **Common Functions**, and then click **Text**.</span></span>  
  
5.  <span data-ttu-id="c1a89-189">Nell'elenco **Elemento** fare doppio clic su **Left**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-189">In the **Item** list, double-click **Left**.</span></span>  
  
     <span data-ttu-id="c1a89-190">La funzione **Left** viene aggiunta all'espressione.</span><span class="sxs-lookup"><span data-stu-id="c1a89-190">The **Left** function is added to the expression.</span></span>  
  
6.  <span data-ttu-id="c1a89-191">Nell'elenco **Categoria** fare clic su **Fields (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-191">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="c1a89-192">Nell'elenco **Valori** fare doppio clic su **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-192">In the **Values** list, double-click **FirstName**.</span></span>  
  
8.  <span data-ttu-id="c1a89-193">Digitare **, 1)**</span><span class="sxs-lookup"><span data-stu-id="c1a89-193">Type **, 1)**</span></span>  
  
     <span data-ttu-id="c1a89-194">Questa espressione consente di estrarre un carattere dal valore **FirstName** , a partire da sinistra.</span><span class="sxs-lookup"><span data-stu-id="c1a89-194">This expression extracts one character from the **FirstName** value, counting from the left.</span></span>  
  
9. <span data-ttu-id="c1a89-195">Digitare **&" "&**</span><span class="sxs-lookup"><span data-stu-id="c1a89-195">Type **&" "&**</span></span>  
  
10. <span data-ttu-id="c1a89-196">Nell'elenco **Valori** fare doppio clic su **LastName**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-196">In the **Values** list, double-click **LastName**.</span></span>  
  
     <span data-ttu-id="c1a89-197">L'espressione completa è: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span><span class="sxs-lookup"><span data-stu-id="c1a89-197">The completed expression: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="c1a89-198">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-198">Click **Run** to preview the report.</span></span>  
  
##  <a name="4-use-images-to-display-gender"></a><a name="Gender"></a><span data-ttu-id="c1a89-199">4. utilizzare le immagini per visualizzare il sesso</span><span class="sxs-lookup"><span data-stu-id="c1a89-199">4. Use Images to Display Gender</span></span>  
 <span data-ttu-id="c1a89-200">Utilizzare immagini per visualizzare il sesso di una persona e identificare i valori sconosciuti relativi al sesso utilizzando una terza immagine.</span><span class="sxs-lookup"><span data-stu-id="c1a89-200">Use images to show the gender of a person, and identify unknown gender values by using a third image.</span></span> <span data-ttu-id="c1a89-201">Si aggiungeranno al report tre immagini nascoste e una nuova colonna per visualizzare le immagini, quindi si stabilirà l'immagine che verrà visualizzata nella colonna in base al valore del campo Gender.</span><span class="sxs-lookup"><span data-stu-id="c1a89-201">You will add to the report three hidden images and a new column to display the images, and then determine the image that appears in the column based on the value of the Gender field.</span></span>  
  
 <span data-ttu-id="c1a89-202">Per applicare un colore alla cella della tabella in cui è contenuta l'immagine durante la creazione di un report a barre, verrà aggiunto un rettangolo in cui verrà inserita successivamente l'immagine.</span><span class="sxs-lookup"><span data-stu-id="c1a89-202">To apply a color to the table cell that contains the image when you make the report a barred report, you will add a rectangle and then add the image to the rectangle.</span></span> <span data-ttu-id="c1a89-203">È necessario utilizzare un rettangolo perché consente, a differenza di un'immagine, l'applicazione di un colore di sfondo.</span><span class="sxs-lookup"><span data-stu-id="c1a89-203">You need to use a rectangle because you can apply a background color to a rectangle, but not to an image.</span></span>  
  
 <span data-ttu-id="c1a89-204">Nell'esercitazione vengono utilizzate immagini che vengono installate con Windows, ma è possibile utilizzare qualsiasi immagine disponibile.</span><span class="sxs-lookup"><span data-stu-id="c1a89-204">The tutorial uses images that are installed with Windows, but you can use any images available to you.</span></span> <span data-ttu-id="c1a89-205">Verranno utilizzate immagini incorporate che non è necessario siano installate nel computer locale o nel server di report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-205">You will use embedded images, and they do not need to be installed on your local computer or the report server.</span></span>  
  
#### <a name="to-add-images-to-the-report-body"></a><span data-ttu-id="c1a89-206">Per aggiungere immagini al corpo del report</span><span class="sxs-lookup"><span data-stu-id="c1a89-206">To add images to the report body</span></span>  
  
1.  <span data-ttu-id="c1a89-207">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="c1a89-207">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c1a89-208">Nella scheda **Inserisci** della barra multifunzione selezionare **Immagine** e fare clic nel corpo del report, sotto la tabella.</span><span class="sxs-lookup"><span data-stu-id="c1a89-208">On the **Insert** tab of the ribbon, click **Image** and then click in the report body, below the table.</span></span>  
  
     <span data-ttu-id="c1a89-209">Verrà visualizzata la finestra di dialogo **Proprietà immagine**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-209">The **Image Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c1a89-210">Fare clic su **Importa** e passare a C:\Users\Public\Immagini pubbliche\Immagini campione.</span><span class="sxs-lookup"><span data-stu-id="c1a89-210">Click **Import** and navigate to C:\Users\Public\Public Pictures\Sample Pictures.</span></span>  
  
4.  <span data-ttu-id="c1a89-211">Fare clic sul file Penguins.JPG e scegliere **Apri**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-211">Click Penguins.JPG and click **Open**.</span></span>  
  
     <span data-ttu-id="c1a89-212">Nella finestra di dialogo **Proprietà immagine** fare clic su **Visibilità** e scegliere l'opzione **Nascondi**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-212">In the **Image Properties** dialog box, click **Visibility** and then click the **Hide** option.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c1a89-213">Ripetere i passaggi da 2 a 5, ma scegliere il file Koala.JPG.</span><span class="sxs-lookup"><span data-stu-id="c1a89-213">Repeat steps 2 through 5, but choose Koala.JPG.</span></span>  
  
7.  <span data-ttu-id="c1a89-214">Ripetere i passaggi da 2 a 5, ma scegliere il file Tulips.JPG.</span><span class="sxs-lookup"><span data-stu-id="c1a89-214">Repeat steps 2 through 5, but choose Tulips.JPG.</span></span>  
  
#### <a name="to-add-the-gender-column"></a><span data-ttu-id="c1a89-215">Per aggiungere la colonna Gender</span><span class="sxs-lookup"><span data-stu-id="c1a89-215">To add the Gender column</span></span>  
  
1.  <span data-ttu-id="c1a89-216">Fare clic con il pulsante destro del mouse sulla colonna **Name**, scegliere **Inserisci colonna** e fare clic su **A destra**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-216">Right-click the **Name** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="c1a89-217">Una nuova colonna verrà aggiunta a destra della colonna **Name**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-217">A new column is added to the right of the **Name** column.</span></span>  
  
2.  <span data-ttu-id="c1a89-218">Fare clic sul titolo della nuova colonna e digitare **Gender**</span><span class="sxs-lookup"><span data-stu-id="c1a89-218">Click the title of the new column and type **Gender**</span></span>  
  
#### <a name="to-add-a-rectangle"></a><span data-ttu-id="c1a89-219">Per aggiungere un rettangolo</span><span class="sxs-lookup"><span data-stu-id="c1a89-219">To add a rectangle</span></span>  
  
-   <span data-ttu-id="c1a89-220">Nella scheda **Inserisci** della barra multifunzione selezionare **Rettangolo** e fare clic nella cella di dati della colonna **Gender**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-220">On the **Insert** tab of the ribbon, click **Rectangle** and then click in the data cell of the **Gender** column.</span></span>  
  
     <span data-ttu-id="c1a89-221">Verrà aggiunto un rettangolo alla cella.</span><span class="sxs-lookup"><span data-stu-id="c1a89-221">A rectangle is added to the cell.</span></span>  
  
#### <a name="to-add-an-image-to-the-rectangle"></a><span data-ttu-id="c1a89-222">Per aggiungere un'immagine al rettangolo</span><span class="sxs-lookup"><span data-stu-id="c1a89-222">To add an image to the rectangle</span></span>  
  
1.  <span data-ttu-id="c1a89-223">Fare clic con il pulsante destro del mouse nel rettangolo, scegliere **Inserisci** e fare clic su **Immagine**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-223">Right-click in the rectangle, point to **Insert**, and then click **Image**.</span></span>  
  
2.  <span data-ttu-id="c1a89-224">Nella finestra di dialogo **Proprietà immagine** fare clic sulla freccia a discesa accanto a **Usare questa immagine** e selezionare una delle immagini aggiunte, ad esempio Penguins.JPG.</span><span class="sxs-lookup"><span data-stu-id="c1a89-224">In the **Image Properties** dialog box, click the down arrow beside **Use this image**, and select one of the images you added, for example, Penguins.JPG.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-use-images-to-show-gender"></a><span data-ttu-id="c1a89-225">Per utilizzare immagini per mostrare il sesso</span><span class="sxs-lookup"><span data-stu-id="c1a89-225">To use images to show gender</span></span>  
  
1.  <span data-ttu-id="c1a89-226">Fare clic con il pulsante destro del mouse sull'immagine nella cella di dati nella colonna **Gender** e scegliere **Proprietà immagine**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-226">Right-click the image in the data cell in the **Gender** column and click **Image Properties**.</span></span>  
  
2.  <span data-ttu-id="c1a89-227">Nella finestra di dialogo **Proprietà immagine** fare clic sul pulsante dell'espressione **fx** accanto alla casella di testo **Usare questa immagine**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-227">In the **Image Properties** dialog box, click the expression **fx** button next to the **Use this image** text box.</span></span>  
  
3.  <span data-ttu-id="c1a89-228">Nella finestra di dialogo **Espressione** espandere **Funzioni comuni** e fare clic su **Program Flow**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-228">In the **Expression** dialog box, expand **Common Functions** and click **Program Flow**.</span></span>  
  
4.  <span data-ttu-id="c1a89-229">Nell'elenco **Elemento** fare doppio clic su **Switch**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-229">In the **Item** list, double-click **Switch**.</span></span>  
  
5.  <span data-ttu-id="c1a89-230">Nell'elenco **Categoria** fare clic su **Fields (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-230">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="c1a89-231">Nell'elenco **Valori** fare doppio clic su **Gender**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-231">In the **Values** list, double-click **Gender**.</span></span>  
  
7.  <span data-ttu-id="c1a89-232">Digitare **="Male", "Koala",**</span><span class="sxs-lookup"><span data-stu-id="c1a89-232">Type **="Male", "Koala",**</span></span>  
  
8.  <span data-ttu-id="c1a89-233">Nell'elenco **Valori** fare doppio clic su **Gender**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-233">In the **Values** list, double-click **Gender**.</span></span>  
  
9. <span data-ttu-id="c1a89-234">Digitare **="Female", "Penguins",**</span><span class="sxs-lookup"><span data-stu-id="c1a89-234">Type **="Female", "Penguins",**</span></span>  
  
10. <span data-ttu-id="c1a89-235">Nell'elenco **Valori** fare doppio clic su **Gender**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-235">In the **Values** list, double-click **Gender**.</span></span>  
  
11. <span data-ttu-id="c1a89-236">Digitare **="Unknown", "Tulips")**</span><span class="sxs-lookup"><span data-stu-id="c1a89-236">Type **="Unknown", "Tulips")**</span></span>  
  
     <span data-ttu-id="c1a89-237">L'espressione completa è: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span><span class="sxs-lookup"><span data-stu-id="c1a89-237">The completed expression: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="c1a89-238">Scegliere di nuovo **OK** per chiudere la finestra di dialogo **Proprietà immagine**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-238">Click **OK** again to close the **Image Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="c1a89-239">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-239">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-look-up-countryregion-name"></a><a name="Lookup"></a><span data-ttu-id="c1a89-240">5. cercare il nome CountryRegion</span><span class="sxs-lookup"><span data-stu-id="c1a89-240">5. Look Up CountryRegion Name</span></span>  
 <span data-ttu-id="c1a89-241">Creare il set di dati CountryRegion e usare la funzione **Lookup** per visualizzare il nome di un paese o di una regione anziché il relativo identificatore.</span><span class="sxs-lookup"><span data-stu-id="c1a89-241">Create the CountryRegion dataset and use the **Lookup** function to display the name of a country/region instead of the identifier of the country/region.</span></span>  
  
#### <a name="to-create-the-countryregion-dataset"></a><span data-ttu-id="c1a89-242">Per creare un set di dati CountryRegion</span><span class="sxs-lookup"><span data-stu-id="c1a89-242">To create the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="c1a89-243">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="c1a89-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c1a89-244">Nel riquadro dei dati del report fare clic su **nuovo** , quindi su **set**di dati.</span><span class="sxs-lookup"><span data-stu-id="c1a89-244">In the Report Data pane, click **New** and then click **Dataset**.</span></span>  
  
3.  <span data-ttu-id="c1a89-245">Fare clic su **Usare un set di dati incorporato nel report**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-245">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="c1a89-246">Selezionare ExpressionsDataSource nell'elenco **Origine dati** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-246">In the **Data source** list, select ExpressionsDataSource.</span></span>  
  
5.  <span data-ttu-id="c1a89-247">Nella casella **Nome** digitare **CountryRegion**</span><span class="sxs-lookup"><span data-stu-id="c1a89-247">In the **Name** box, type **CountryRegion**</span></span>  
  
6.  <span data-ttu-id="c1a89-248">Verificare che sia selezionato il tipo di query **Testo** e fare clic su **Progettazione query**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-248">Verify that the **Text** query type is selected and click **Query Designer**.</span></span>  
  
7.  <span data-ttu-id="c1a89-249">Fare clic su **Modifica come testo**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-249">Click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="c1a89-250">Copiare e incollare la query seguente nel relativo riquadro:</span><span class="sxs-lookup"><span data-stu-id="c1a89-250">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 1 AS ID, 'American Samoa' AS CountryRegion  
    UNION SELECT 2 AS CountryRegionID, 'Australia' AS CountryRegion  
    UNION SELECT 3 AS ID, 'Canada' AS CountryRegion  
    UNION SELECT 4 AS ID, 'Germany' AS CountryRegion  
    UNION SELECT 5 AS ID, 'Micronesia' AS CountryRegion  
    UNION SELECT 6 AS ID, 'France' AS CountryRegion  
    UNION SELECT 7 AS ID, 'United States' AS CountryRegion  
    UNION SELECT 8 AS ID, 'Brazil' AS CountryRegion  
    UNION SELECT 9 AS ID, 'Mexico' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Japan' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Australia' AS CountryRegion  
    UNION SELECT 12 AS ID, 'United Kingdom' AS CountryRegion  
    ```  
  
9. <span data-ttu-id="c1a89-251">Fare clic su **Esegui** (**!**) per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="c1a89-251">Click **Run** (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="c1a89-252">I risultati query sono i nomi e gli identificatori di paesi.</span><span class="sxs-lookup"><span data-stu-id="c1a89-252">The query results are the country/region identifiers and names.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="c1a89-253">Scegliere di nuovo **OK** per chiudere la finestra di dialogo **Proprietà set di dati** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-253">Click **OK** again to close the **Dataset Properties** dialog box.</span></span>  
  
#### <a name="to-look-up-values-in-the-countryregion-dataset"></a><span data-ttu-id="c1a89-254">Per cercare valori nel set di dati CountryRegion</span><span class="sxs-lookup"><span data-stu-id="c1a89-254">To look up values in the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="c1a89-255">Fare clic sul titolo della colonna **Country Region ID** ed eliminare il testo ID.</span><span class="sxs-lookup"><span data-stu-id="c1a89-255">Click the **Country Region ID** column title and delete the text: ID.</span></span>  
  
2.  <span data-ttu-id="c1a89-256">Fare clic con il pulsante destro del mouse sulla cella di dati per la colonna **Country Region** e scegliere **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-256">Right-click the data cell for the **Country Region** column and click **Expression**.</span></span>  
  
3.  <span data-ttu-id="c1a89-257">Eliminare l'espressione eccetto il segno iniziale di uguale (=).</span><span class="sxs-lookup"><span data-stu-id="c1a89-257">Delete the expression except the initial equal (=) sign.</span></span>  
  
     <span data-ttu-id="c1a89-258">L'espressione rimanente è: `=`</span><span class="sxs-lookup"><span data-stu-id="c1a89-258">The remaining expression is: `=`</span></span>  
  
4.  <span data-ttu-id="c1a89-259">Nella finestra di dialogo **Espressione** espandere **Funzioni comuni** e fare clic su **Miscellaneous**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-259">In the **Expression** dialog box, expand **Common Functions** and click **Miscellaneous**.</span></span>  
  
5.  <span data-ttu-id="c1a89-260">Nell'elenco **Elemento** fare doppio clic su **Lookup**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-260">In the **Item** list, double-click **Lookup**.</span></span>  
  
6.  <span data-ttu-id="c1a89-261">Nell'elenco **Categoria** fare clic su **Fields (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-261">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="c1a89-262">Nell'elenco **valori** fare doppio clic su `CountryRegionID` .</span><span class="sxs-lookup"><span data-stu-id="c1a89-262">In the **Values** list, double-click `CountryRegionID`.</span></span>  
  
8.  <span data-ttu-id="c1a89-263">Se il cursore non si trova già subito dopo `CountryRegionID.Value`, posizionarlo in tale punto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-263">If the cursor is not already immediately after `CountryRegionID.Value`, place it there.</span></span>  
  
9. <span data-ttu-id="c1a89-264">Eliminare la parentesi chiusa e digitare **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**</span><span class="sxs-lookup"><span data-stu-id="c1a89-264">Delete the right parenthesis and then type **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**</span></span>  
  
     <span data-ttu-id="c1a89-265">L'espressione completa è: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span><span class="sxs-lookup"><span data-stu-id="c1a89-265">The completed expression: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span></span>  
  
     <span data-ttu-id="c1a89-266">La sintassi della funzione **Lookup** consente di specificare una ricerca tra CountryRegionID e ID nel set di dati CountryRegion tramite cui viene restituito il valore CountryRegion, che si trova anche nel set di dati CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="c1a89-266">The syntax of the **Lookup** function specifies a lookup between CountryRegionID and ID in the CountryRegion dataset that returns the CountryRegion value, which is also in the CountryRegion dataset.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="c1a89-267">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-267">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-count-days-since-last-purchase"></a><a name="Count"></a><span data-ttu-id="c1a89-268">6. contare i giorni dall'ultimo acquisto</span><span class="sxs-lookup"><span data-stu-id="c1a89-268">6. Count Days Since Last Purchase</span></span>  
 <span data-ttu-id="c1a89-269">Aggiungere una colonna e quindi usare la funzione **Now** o la `ExecutionTime` variabile globale incorporata per calcolare il numero di giorni trascorsi dall'ultimo acquisto di una persona.</span><span class="sxs-lookup"><span data-stu-id="c1a89-269">Add a column and then use the **Now** function or the `ExecutionTime` built-in global variable to calculate the number of days from today since a person's last purchases.</span></span>  
  
#### <a name="to-add-the-days-ago-column"></a><span data-ttu-id="c1a89-270">Per aggiungere la colonna Days Ago</span><span class="sxs-lookup"><span data-stu-id="c1a89-270">To add the Days Ago column</span></span>  
  
1.  <span data-ttu-id="c1a89-271">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="c1a89-271">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c1a89-272">Fare clic con il pulsante destro del mouse sulla colonna **Last Purchase** , scegliere **Inserisci colonna**e fare clic su **A destra**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-272">Right-click the **Last Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="c1a89-273">Una nuova colonna verrà aggiunta a destra della colonna **Last Purchase** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-273">A new column is added to the right of the **Last Purchase** column.</span></span>  
  
3.  <span data-ttu-id="c1a89-274">Nell'intestazione di colonna digitare **Days Ago**</span><span class="sxs-lookup"><span data-stu-id="c1a89-274">In the column header, type **Days Ago**</span></span>  
  
4.  <span data-ttu-id="c1a89-275">Fare clic con il pulsante destro del mouse sulla cella di dati per la colonna **Days Ago** e scegliere **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-275">Right-click the data cell for the **Days Ago** column and click **Expression**.</span></span>  
  
5.  <span data-ttu-id="c1a89-276">Nella finestra di dialogo **Espressione** espandere **Funzioni comuni** e fare clic su **Date & Time**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-276">In the **Expression** dialog box, expand **Common Functions**, and then click **Date & Time**.</span></span>  
  
6.  <span data-ttu-id="c1a89-277">Nell'elenco **Elemento** fare doppio clic su **DateDiff**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-277">In the **Item** list, double-click **DateDiff**.</span></span>  
  
7.  <span data-ttu-id="c1a89-278">Se il cursore non si trova già subito dopo `DateDiff(`, posizionarlo in tale punto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-278">If the cursor is not already immediately after `DateDiff(`, place it there.</span></span>  
  
8.  <span data-ttu-id="c1a89-279">Digitare **"d",**</span><span class="sxs-lookup"><span data-stu-id="c1a89-279">Type **"d",**</span></span>  
  
9. <span data-ttu-id="c1a89-280">Nell'elenco **Categoria** fare clic su **Fields (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-280">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
10. <span data-ttu-id="c1a89-281">Nell'elenco **Valori** fare doppio clic su **LastPurchase**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-281">In the **Values** list, double-click **LastPurchase**.</span></span>  
  
11. <span data-ttu-id="c1a89-282">Se il cursore non si trova già subito dopo `Fields!LastPurchase.Value`, posizionarlo in tale punto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-282">If the cursor is not already immediately after `Fields!LastPurchase.Value`, place it there.</span></span>  
  
12. <span data-ttu-id="c1a89-283">Digitare **,**</span><span class="sxs-lookup"><span data-stu-id="c1a89-283">Type **,**</span></span>  
  
13. <span data-ttu-id="c1a89-284">Nell' elenco **Categoria**, fare di nuovo clic su **Date & Time**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-284">In the **Category** list, click **Date & Time** again.</span></span>  
  
14. <span data-ttu-id="c1a89-285">Nell'elenco **Elemento** fare doppio clic su **Now**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-285">In the **Item** list, double-click **Now**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="c1a89-286">Nei report di produzione non è consigliabile usare la funzione **Now** in espressioni valutate più volte quando si esegue il rendering del report, ad esempio nelle righe di dettaglio di un report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-286">In production reports you should not use the **Now** function in expressions that are evaluated multiple times as the report renders (for example, in the detail rows of a report).</span></span> <span data-ttu-id="c1a89-287">Il valore di **Now** cambia da riga a riga e i valori diversi influiscono sui risultati della valutazione delle espressioni, generando risultati leggermente incoerenti.</span><span class="sxs-lookup"><span data-stu-id="c1a89-287">The value of **Now** changes from row to row and the different values affect the evaluation results of expressions, which leads to results that are subtly inconsistent.</span></span> <span data-ttu-id="c1a89-288">È consigliabile invece ricorrere alla variabile globale `ExecutionTime` di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1a89-288">Instead, you should use the `ExecutionTime` global variable that [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides.</span></span>  
  
15. <span data-ttu-id="c1a89-289">Se il cursore non si trova già subito dopo `Now(`, posizionarlo in tale punto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-289">If the cursor is not already immediately after `Now(`, place it there.</span></span>  
  
16. <span data-ttu-id="c1a89-290">Eliminare la parentesi aperta e digitare **)**</span><span class="sxs-lookup"><span data-stu-id="c1a89-290">Delete the left parenthesis and then type **)**</span></span>  
  
     <span data-ttu-id="c1a89-291">L'espressione completa è: `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span><span class="sxs-lookup"><span data-stu-id="c1a89-291">The completed expression: `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span></span>  
  
17. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="7-use-an-indicator-to-show-sales-comparison"></a><a name="Indicator"></a><span data-ttu-id="c1a89-292">7. utilizzare un indicatore per mostrare il confronto delle vendite</span><span class="sxs-lookup"><span data-stu-id="c1a89-292">7. Use an Indicator to Show Sales Comparison</span></span>  
 <span data-ttu-id="c1a89-293">Aggiungere una nuova colonna e usare un indicatore per indicare se gli acquisti da inizio anno (YTD) di una persona sono al di sopra o al di sotto degli acquisti YTD medi.</span><span class="sxs-lookup"><span data-stu-id="c1a89-293">Add a new column and use an indicator to show whether a person's year-to-date (YTD) purchases are above or below the average YTD purchases.</span></span> <span data-ttu-id="c1a89-294">La funzione **Round** consente di rimuovere i decimali dai valori.</span><span class="sxs-lookup"><span data-stu-id="c1a89-294">The **Round** function removes decimals from values.</span></span>  
  
 <span data-ttu-id="c1a89-295">Per la configurazione dell'indicatore e dei relativi stati sono necessari numerosi passaggi.</span><span class="sxs-lookup"><span data-stu-id="c1a89-295">The configuration of the indicator and its states requires many steps.</span></span> <span data-ttu-id="c1a89-296">Se si desidera, nella procedura "per configurare l'indicatore", è possibile ignorare e copiare e incollare le espressioni complete da questa esercitazione nella finestra di dialogo **espressione** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-296">If you want to, in the "To configure the indicator" procedure, you can skip ahead and copy/paste the completed expressions from this tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the--or---avg-sales-column"></a><span data-ttu-id="c1a89-297">Per aggiungere la colonna + or - AVG Sales</span><span class="sxs-lookup"><span data-stu-id="c1a89-297">To add the + or - AVG Sales column</span></span>  
  
1.  <span data-ttu-id="c1a89-298">Fare clic con il pulsante destro del mouse sulla colonna **YTD Purchase** , scegliere **Inserisci colonna**e fare clic su **A destra**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-298">Right-click the **YTD Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="c1a89-299">Una nuova colonna verrà aggiunta a destra della colonna **YTD Purchase** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-299">A new column is added to the right of the **YTD Purchase** column.</span></span>  
  
2.  <span data-ttu-id="c1a89-300">Fare clic sul titolo della nuova colonna e digitare **+ or - AVG Sales**</span><span class="sxs-lookup"><span data-stu-id="c1a89-300">Click the title of the column and type **+ or - AVG Sales**</span></span>  
  
#### <a name="to-add-an-indicator"></a><span data-ttu-id="c1a89-301">Per aggiungere un indicatore</span><span class="sxs-lookup"><span data-stu-id="c1a89-301">To add an indicator</span></span>  
  
1.  <span data-ttu-id="c1a89-302">Nella scheda **Inserisci** della barra multifunzione selezionare **Indicatore** e fare clic nella cella di dati della colonna **+ or - AVG Sales**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-302">On the **Insert** tab of the ribbon, click **Indicator**, and then click the data cell for the **+ or - AVG Sales** column.</span></span>  
  
     <span data-ttu-id="c1a89-303">Verrà visualizzata la finestra di dialogo **Seleziona tipo indicatore** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-303">The **Select Indicator Type** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c1a89-304">Nel gruppo **Direzionale** di set di icone selezionare il set di tre frecce grigie.</span><span class="sxs-lookup"><span data-stu-id="c1a89-304">In the **Directional** group of icon sets, click the set of three gray arrows.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-configure-the-indicator"></a><span data-ttu-id="c1a89-305">Per configurare l'indicatore</span><span class="sxs-lookup"><span data-stu-id="c1a89-305">To configure the indicator</span></span>  
  
1.  <span data-ttu-id="c1a89-306">Fare clic con il pulsante destro del mouse sull'indicatore, selezionare **Proprietà indicatore**e scegliere **Valore e stati**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-306">Right-click the indicator, click **Indicator Properties**, and then click **Value and States**.</span></span>  
  
2.  <span data-ttu-id="c1a89-307">Fare clic sul pulsante dell'espressione **fx** accanto alla casella di testo **Valore** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-307">Click the expression **fx** button next to the **Value** text box.</span></span>  
  
3.  <span data-ttu-id="c1a89-308">Nella finestra di dialogo **Espressione** espandere **Funzioni comuni**e fare clic su **Math**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-308">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
4.  <span data-ttu-id="c1a89-309">Nell'elenco **Elemento** fare doppio clic su **Round**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-309">In the **Item** list, double-click **Round**.</span></span>  
  
5.  <span data-ttu-id="c1a89-310">Nell'elenco **Categoria** fare clic su **Fields (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-310">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="c1a89-311">Nell'elenco **Valori** fare doppio clic su **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-311">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
7.  <span data-ttu-id="c1a89-312">Se il cursore non si trova già subito dopo `Fields!YTDPurchase.Value`, posizionarlo in tale punto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-312">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
8.  <span data-ttu-id="c1a89-313">Tipo**-**</span><span class="sxs-lookup"><span data-stu-id="c1a89-313">Type  **-**</span></span>  
  
9. <span data-ttu-id="c1a89-314">Espandere di nuovo **Funzioni comuni** e fare clic su **Aggregate**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-314">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
10. <span data-ttu-id="c1a89-315">Nell'elenco **Elemento** fare doppio clic su **Avg**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-315">In the **Item** list, double-click **Avg**.</span></span>  
  
11. <span data-ttu-id="c1a89-316">Nell'elenco **Categoria** fare clic su **Fields (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-316">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
12. <span data-ttu-id="c1a89-317">Nell'elenco **Valori** fare doppio clic su **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-317">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
13. <span data-ttu-id="c1a89-318">Se il cursore non si trova già subito dopo `Fields!YTDPurchase.Value`, posizionarlo in tale punto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-318">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
14. <span data-ttu-id="c1a89-319">Digitare **, "Expressions"))**</span><span class="sxs-lookup"><span data-stu-id="c1a89-319">Type **, "Expressions"))**</span></span>  
  
     <span data-ttu-id="c1a89-320">L'espressione completa è: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span><span class="sxs-lookup"><span data-stu-id="c1a89-320">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span></span>  
  
15. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
16. <span data-ttu-id="c1a89-321">Nella casella **Unità di misura stati** selezionare **Numerico**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-321">In the **States Measurement Unit** box, select **Numeric**.</span></span>  
  
17. <span data-ttu-id="c1a89-322">Nella riga con la freccia rivolta verso il basso fare clic sul pulsante **fx** a destra della casella di testo per il valore **Iniziale** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-322">In the row with the down-pointing arrow, click the **fx** button to the right of the text box for the **Start** value.</span></span>  
  
18. <span data-ttu-id="c1a89-323">Nella finestra di dialogo **Espressione** espandere **Funzioni comuni**e fare clic su **Math**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-323">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
19. <span data-ttu-id="c1a89-324">Nell'elenco **Elemento** fare doppio clic su **Round**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-324">In the **Item** list, double-click **Round**.</span></span>  
  
20. <span data-ttu-id="c1a89-325">Nell'elenco **Categoria** fare clic su **Fields (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-325">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
21. <span data-ttu-id="c1a89-326">Nell'elenco **Valori** fare doppio clic su **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-326">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
22. <span data-ttu-id="c1a89-327">Se il cursore non si trova già subito dopo `Fields!YTDPurchase.Value`, posizionarlo in tale punto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-327">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="c1a89-328">Tipo**-**</span><span class="sxs-lookup"><span data-stu-id="c1a89-328">Type  **-**</span></span>  
  
24. <span data-ttu-id="c1a89-329">Espandere di nuovo **Funzioni comuni** e fare clic su **Aggregate**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-329">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
25. <span data-ttu-id="c1a89-330">Nell'elenco **Elemento** fare doppio clic su **Avg**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-330">In the **Item** list, double-click **Avg**.</span></span>  
  
26. <span data-ttu-id="c1a89-331">Nell'elenco **Categoria** fare clic su **Fields (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-331">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
27. <span data-ttu-id="c1a89-332">Nell'elenco **Valori** fare doppio clic su **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-332">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
28. <span data-ttu-id="c1a89-333">Se il cursore non si trova già subito dopo `Fields!YTDPurchase.Value`, posizionarlo in tale punto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-333">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
29. <span data-ttu-id="c1a89-334">Digitare **, "Expressions")) < 0**</span><span class="sxs-lookup"><span data-stu-id="c1a89-334">Type **, "Expressions")) < 0**</span></span>  
  
     <span data-ttu-id="c1a89-335">L'espressione completa è: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span><span class="sxs-lookup"><span data-stu-id="c1a89-335">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span></span>  
  
30. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
31. <span data-ttu-id="c1a89-336">Nella casella di testo per il valore **Finale** digitare **0**</span><span class="sxs-lookup"><span data-stu-id="c1a89-336">In the text box for the **End** value, type **0**</span></span>  
  
32. <span data-ttu-id="c1a89-337">Fare clic sulla riga con la freccia orizzontale e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-337">Click the row with the horizontal-pointing arrow and click **Delete**.</span></span>  
  
33. <span data-ttu-id="c1a89-338">Nella riga con la freccia rivolta verso l'alto, nella casella **Inizio** digitare **0**</span><span class="sxs-lookup"><span data-stu-id="c1a89-338">In the row with the up-pointing arrow, in the **Start** box, type **0**</span></span>  
  
34. <span data-ttu-id="c1a89-339">Fare clic sul pulsante **fx** a destra della casella di testo per il valore **Finale** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-339">Click the **fx** button to the right of the text box for the **End** value.</span></span>  
  
35. <span data-ttu-id="c1a89-340">Nella finestra di dialogo **espressione** creare l'espressione:`=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span><span class="sxs-lookup"><span data-stu-id="c1a89-340">In the **Expression** dialog box, create the expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span></span>  
  
36. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
37. <span data-ttu-id="c1a89-341">Scegliere di nuovo **OK** per chiudere la finestra di dialogo **Proprietà indicatore** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-341">Click **OK** again to close the **Indicator properties** dialog box.</span></span>  
  
38. <span data-ttu-id="c1a89-342">Fare clic su **Esegui** per visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-342">Click **Run** to preview the report.</span></span>  
  
##  <a name="8-make-the-report-a-green-bar-report"></a><a name="GreenBar"></a><span data-ttu-id="c1a89-343">8. rendere il report un report "barra verde"</span><span class="sxs-lookup"><span data-stu-id="c1a89-343">8. Make the Report a "Green Bar" Report</span></span>  
 <span data-ttu-id="c1a89-344">Utilizzare un parametro per specificare il colore da applicare alle righe alternate nel report, rendendolo a barre.</span><span class="sxs-lookup"><span data-stu-id="c1a89-344">Use a parameter to specify the color to apply to alternating rows in the report, making it a barred report.</span></span>  
  
#### <a name="to-add-a-parameter"></a><span data-ttu-id="c1a89-345">Per aggiungere un parametro</span><span class="sxs-lookup"><span data-stu-id="c1a89-345">To add a parameter</span></span>  
  
1.  <span data-ttu-id="c1a89-346">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="c1a89-346">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c1a89-347">Nel riquadro **Dati report** fare clic con il pulsante destro del mouse su **Parametri** e scegliere **Aggiungi parametro**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-347">In the **Report Data** pane, right-click **Parameters** and click **Add Parameter**.</span></span>  
  
     <span data-ttu-id="c1a89-348">Verrà visualizzata la finestra di dialogo **Proprietà parametri report** .</span><span class="sxs-lookup"><span data-stu-id="c1a89-348">The **Report Parameter Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c1a89-349">In **Messaggio di richiesta**digitare **Choose color**</span><span class="sxs-lookup"><span data-stu-id="c1a89-349">In **Prompt**, type **Choose color**</span></span>  
  
4.  <span data-ttu-id="c1a89-350">Nella casella **Nome**digitare **RowColor**</span><span class="sxs-lookup"><span data-stu-id="c1a89-350">In **Name**, type **RowColor**</span></span>  
  
5.  <span data-ttu-id="c1a89-351">Nel riquadro di sinistra scegliere **Valori disponibili**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-351">In the left pane, click **Available Values**.</span></span>  
  
6.  <span data-ttu-id="c1a89-352">Fare clic su **Imposta valori**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-352">Click **Specify values**.</span></span>  
  
7.  <span data-ttu-id="c1a89-353">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-353">Click **Add**.</span></span>  
  
8.  <span data-ttu-id="c1a89-354">Nella casella **Etichetta** digitare: **Yellow**</span><span class="sxs-lookup"><span data-stu-id="c1a89-354">In the **Label** box, type: **Yellow**</span></span>  
  
9. <span data-ttu-id="c1a89-355">Nella casella **Valore** digitare **Yellow**</span><span class="sxs-lookup"><span data-stu-id="c1a89-355">In the **Value** box, type **Yellow**</span></span>  
  
10. <span data-ttu-id="c1a89-356">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-356">Click **Add**.</span></span>  
  
11. <span data-ttu-id="c1a89-357">Nella casella **Etichetta** digitare **Green**</span><span class="sxs-lookup"><span data-stu-id="c1a89-357">In the **Label** box, type **Green**</span></span>  
  
12. <span data-ttu-id="c1a89-358">Nella casella **Valore** digitare **PaleGreen**</span><span class="sxs-lookup"><span data-stu-id="c1a89-358">In the **Value** box, type **PaleGreen**</span></span>  
  
13. <span data-ttu-id="c1a89-359">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-359">Click **Add**.</span></span>  
  
14. <span data-ttu-id="c1a89-360">Nella casella **Etichetta** digitare **Blue**</span><span class="sxs-lookup"><span data-stu-id="c1a89-360">In the **Label** box, type **Blue**</span></span>  
  
15. <span data-ttu-id="c1a89-361">Nella casella **Valore** digitare **LightBlue**</span><span class="sxs-lookup"><span data-stu-id="c1a89-361">In the **Value** box, type **LightBlue**</span></span>  
  
16. <span data-ttu-id="c1a89-362">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-362">Click **Add**.</span></span>  
  
17. <span data-ttu-id="c1a89-363">Nella casella **Etichetta** digitare **Pink**</span><span class="sxs-lookup"><span data-stu-id="c1a89-363">In the **Label** box, type **Pink**</span></span>  
  
18. <span data-ttu-id="c1a89-364">Nella casella **Valore** digitare **Pink**</span><span class="sxs-lookup"><span data-stu-id="c1a89-364">In the **Value** box, type **Pink**</span></span>  
  
19. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-apply-alternating-colors-to-detail-rows"></a><span data-ttu-id="c1a89-365">Per applicare colori alternati alle righe di dettaglio</span><span class="sxs-lookup"><span data-stu-id="c1a89-365">To apply alternating colors to detail rows</span></span>  
  
1.  <span data-ttu-id="c1a89-366">Fare clic sulla scheda **Visualizza** sulla barra multifunzione e verificare che l'opzione **Proprietà** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="c1a89-366">Click the **View** tab on the ribbon and verify that **Properties** is selected.</span></span>  
  
2.  <span data-ttu-id="c1a89-367">Fare clic sulla cella di dati per la colonna **Name** e premere MAIUSC.</span><span class="sxs-lookup"><span data-stu-id="c1a89-367">Click the data cell for the **Name** column and press the Shift key.</span></span>  
  
3.  <span data-ttu-id="c1a89-368">Fare clic sulle altre celle nella riga singolarmente.</span><span class="sxs-lookup"><span data-stu-id="c1a89-368">One by one, click the other cells in the row.</span></span>  
  
4.  <span data-ttu-id="c1a89-369">Nel riquadro Proprietà fare clic su **BackgroundColor**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-369">In the Properties pane, click **BackgroundColor**.</span></span>  
  
     <span data-ttu-id="c1a89-370">Se le proprietà nel riquadro Proprietà sono elencate per categoria, **BackgroundColor** sarà disponibile nella categoria **Fill**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-370">If your Properties pane lists properties by category, you will find the **BackgroundColor** under the **Fill** category.</span></span>  
  
5.  <span data-ttu-id="c1a89-371">Fare clic sulla freccia a discesa e scegliere **Espressione**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-371">Click the down arrow and then click **Expression**.</span></span>  
  
6.  <span data-ttu-id="c1a89-372">Nella finestra di dialogo **Espressione** espandere **Funzioni comuni**e fare clic su **Program Flow**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-372">In the **Expression** dialog box, expand **Common Functions**, and then click **Program Flow**.</span></span>  
  
7.  <span data-ttu-id="c1a89-373">Nell'elenco **Elemento** fare doppio clic su **IIf**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-373">In the **Item** list, double-click **IIf**.</span></span>  
  
8.  <span data-ttu-id="c1a89-374">Espandere **Funzioni comuni** e fare clic su **Aggregate**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-374">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
9. <span data-ttu-id="c1a89-375">Nell'elenco **Elemento** fare doppio clic su **RunningValue**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-375">In the **Item** list, double-click **RunningValue**.</span></span>  
  
10. <span data-ttu-id="c1a89-376">Nell'elenco **Categoria** fare clic su **Fields (Expressions)**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-376">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
11. <span data-ttu-id="c1a89-377">Nell'elenco **Valori** fare doppio clic su **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-377">In the **Values** list, double-click **FirstName**.</span></span>  
  
12. <span data-ttu-id="c1a89-378">Se il cursore non si trova già subito dopo `Fields!FirstName.Value`, posizionarlo in tale punto e digitare **,**</span><span class="sxs-lookup"><span data-stu-id="c1a89-378">If the cursor is not already immediately after `Fields!FirstName.Value`, place it there and type **,**</span></span>  
  
13. <span data-ttu-id="c1a89-379">Espandere **Funzioni comuni** e fare clic su **Aggregate**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-379">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
14. <span data-ttu-id="c1a89-380">Nell'elenco **Elemento** fare doppio clic su **Count**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-380">In the **Item** list, double-click **Count**.</span></span>  
  
15. <span data-ttu-id="c1a89-381">Se il cursore non si trova già subito dopo `Count(`, posizionarlo in tale punto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-381">If the cursor is not already immediately after `Count(`, place it there.</span></span>  
  
16. <span data-ttu-id="c1a89-382">Eliminare la parentesi aperta e digitare **, "Expressions")**</span><span class="sxs-lookup"><span data-stu-id="c1a89-382">Delete the left parenthesis and then type **,"Expressions")**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1a89-383">Expressions è il nome del set di dati in cui contare le righe di dati.</span><span class="sxs-lookup"><span data-stu-id="c1a89-383">Expressions is the name of the dataset in which to count data rows.</span></span>  
  
17. <span data-ttu-id="c1a89-384">Espandere **Operatori** e fare clic su **Aritmetici**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-384">Expand **Operators** and click **Arithmetic**.</span></span>  
  
18. <span data-ttu-id="c1a89-385">Nell'elenco **Elemento** fare doppio clic su **Mod**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-385">In the **Item** list, double-click **Mod**.</span></span>  
  
19. <span data-ttu-id="c1a89-386">Se il cursore non si trova già subito dopo `Mod`, posizionarlo in tale punto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-386">If the cursor is not already immediately after `Mod`, place it there.</span></span>  
  
20. <span data-ttu-id="c1a89-387">Digitare **2 =0,**</span><span class="sxs-lookup"><span data-stu-id="c1a89-387">Type  **2 =0,**</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c1a89-388">Assicurarsi di includere uno spazio prima di digitare il numero 2.</span><span class="sxs-lookup"><span data-stu-id="c1a89-388">Be sure you include a space before you type the number 2.</span></span>  
  
21. <span data-ttu-id="c1a89-389">Fare clic su **Parametri** e nell'elenco **Valori** fare doppio clic su **RowColor**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-389">Click **Parameters** and in the **Values** list, double-click **RowColor**.</span></span>  
  
22. <span data-ttu-id="c1a89-390">Se il cursore non si trova già subito dopo `Parameters!RowColor.Value`, posizionarlo in tale punto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-390">If the cursor is not already immediately after `Parameters!RowColor.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="c1a89-391">Digitare **, "white")**</span><span class="sxs-lookup"><span data-stu-id="c1a89-391">Type **, "White")**</span></span>  
  
     <span data-ttu-id="c1a89-392">L'espressione completa è: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span><span class="sxs-lookup"><span data-stu-id="c1a89-392">The completed expression: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span></span>  
  
24. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="run-the-report"></a><span data-ttu-id="c1a89-393">Eseguire il report</span><span class="sxs-lookup"><span data-stu-id="c1a89-393">Run the Report</span></span>  
  
1.  <span data-ttu-id="c1a89-394">Se non è visualizzata la scheda **Home** fare clic su **Home** per tornare alla visualizzazione della struttura.</span><span class="sxs-lookup"><span data-stu-id="c1a89-394">If not on the **Home** tab, click **Home** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c1a89-395">Fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-395">Click **Run**.</span></span>  
  
3.  <span data-ttu-id="c1a89-396">Nell'elenco a discesa **Scegli colore** selezionare il colore delle barre che non sono bianche nel report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-396">In the **Choose color** drop-down list, select the color of the non-white bars on the report.</span></span>  
  
4.  <span data-ttu-id="c1a89-397">Fare clic su **Visualizza rapporto**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-397">Click **View Report**.</span></span>  
  
     <span data-ttu-id="c1a89-398">Viene eseguito il rendering del report e nelle righe alternate verrà visualizzato lo sfondo scelto.</span><span class="sxs-lookup"><span data-stu-id="c1a89-398">The report renders and alternating rows have the background that you chose.</span></span>  
  
##  <a name="optional-format-date-column"></a><a name="DateFormat"></a><span data-ttu-id="c1a89-399">opzionale Formattare la colonna della data</span><span class="sxs-lookup"><span data-stu-id="c1a89-399">(optional) Format Date Column</span></span>  
 <span data-ttu-id="c1a89-400">Formattare la colonna **Last Purchase** in cui sono contenute le date.</span><span class="sxs-lookup"><span data-stu-id="c1a89-400">Format the **Last Purchase** column, which contains dates.</span></span>  
  
#### <a name="to-format-date-column"></a><span data-ttu-id="c1a89-401">Per formattare la colonna della data</span><span class="sxs-lookup"><span data-stu-id="c1a89-401">To format date column</span></span>  
  
1.  <span data-ttu-id="c1a89-402">Fare clic su **Progettazione** per tornare alla visualizzazione Struttura.</span><span class="sxs-lookup"><span data-stu-id="c1a89-402">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c1a89-403">Fare clic con il pulsante destro del mouse sulla cella di dati per la colonna **Last Purchase** e fare clic su **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-403">Right-click the data cell for the **Last Purchase** column and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="c1a89-404">Nella finestra di dialogo **Proprietà casella di testo** fare clic su **Numero**, selezionare **Data** e fare clic sul tipo **\*1/31/2000**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-404">In the **Text Box Properties** dialog box, click **Number**, click **Date**, and then click the type **\*1/31/2000**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="c1a89-405">opzionale Aggiungere un titolo al report</span><span class="sxs-lookup"><span data-stu-id="c1a89-405">(optional) Add a Report Title</span></span>  
 <span data-ttu-id="c1a89-406">Aggiungere un titolo al report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-406">Add a title to the report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="c1a89-407">Per aggiungere il titolo di un report</span><span class="sxs-lookup"><span data-stu-id="c1a89-407">To add a report title</span></span>  
  
1.  <span data-ttu-id="c1a89-408">Nell'area di progettazione fare clic su **Fare clic per aggiungere il titolo**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-408">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="c1a89-409">Digitare **Sales Comparison Summary** e fare clic all'esterno della casella di testo.</span><span class="sxs-lookup"><span data-stu-id="c1a89-409">Type **Sales Comparison Summary**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="c1a89-410">Fare clic con il pulsante destro del mouse sulla casella di testo che contiene **Sales Comparison Summary** e fare clic su **Proprietà casella di testo**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-410">Right-click the text box that contains **Sales Comparison Summary** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="c1a89-411">Nella finestra di dialogo **Proprietà casella di testo** fare clic su **Carattere**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-411">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="c1a89-412">Nell'elenco **Dimensione** selezionare **18pt**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-412">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="c1a89-413">Nell'elenco **Colore** selezionare **Grigio**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-413">In the **Color** list, select **Gray**.</span></span>  
  
7.  <span data-ttu-id="c1a89-414">Selezionare **Grassetto** e **Corsivo**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-414">Select  **Bold** and  **Italic**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-save-the-report"></a><a name="Save"></a><span data-ttu-id="c1a89-415">opzionale Salva il report</span><span class="sxs-lookup"><span data-stu-id="c1a89-415">(optional) Save the Report</span></span>  
 <span data-ttu-id="c1a89-416">È possibile salvare i report in un server di report, in una raccolta di SharePoint o nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="c1a89-416">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="c1a89-417">Per altre informazioni, vedere [Salvataggio di report &#40;Generatore report&#41;](report-builder/saving-reports-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c1a89-417">For more information, see [Saving Reports &#40;Report Builder&#41;](report-builder/saving-reports-report-builder.md).</span></span>  
  
 <span data-ttu-id="c1a89-418">In questa esercitazione il report verrà salvato in un server di report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-418">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="c1a89-419">Se non si dispone dell'accesso a un server di report, sarà possibile salvare il report nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="c1a89-419">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-to-a-report-server"></a><span data-ttu-id="c1a89-420">Per salvare il report in un server di report</span><span class="sxs-lookup"><span data-stu-id="c1a89-420">To save the report to a report server</span></span>  
  
1.  <span data-ttu-id="c1a89-421">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-421">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="c1a89-422">Fare clic su **Siti e server recenti**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-422">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="c1a89-423">Selezionare o digitare il nome del server di report per il quale si dispone delle autorizzazioni di salvataggio dei report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-423">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="c1a89-424">Verrà visualizzato il messaggio "Connessione al server di report".</span><span class="sxs-lookup"><span data-stu-id="c1a89-424">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="c1a89-425">Al termine della connessione, verrà visualizzato il contenuto della cartella di report specificata dall'amministratore del server di report come posizione predefinita per i report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-425">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="c1a89-426">In **Nome** sostituire il nome predefinito con **Sales Comparison Summary**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-426">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
5.  <span data-ttu-id="c1a89-427">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-427">Click **Save**.</span></span>  
  
 <span data-ttu-id="c1a89-428">Il report verrà salvato sul server di report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-428">The report is saved to the report server.</span></span> <span data-ttu-id="c1a89-429">Il nome del server di report al quale si è connessi verrà visualizzato sulla barra di stato nella parte inferiore della finestra.</span><span class="sxs-lookup"><span data-stu-id="c1a89-429">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-to-your-computer"></a><span data-ttu-id="c1a89-430">Per salvare il report nel computer</span><span class="sxs-lookup"><span data-stu-id="c1a89-430">To save the report to your computer</span></span>  
  
1.  <span data-ttu-id="c1a89-431">Fare clic sul pulsante **Generatore report** , quindi su **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-431">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="c1a89-432">Fare clic su **Desktop**, **Documenti**o **Risorse del computer**, quindi selezionare la cartella in cui si desidera salvare il report.</span><span class="sxs-lookup"><span data-stu-id="c1a89-432">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="c1a89-433">In **Nome** sostituire il nome predefinito con **Sales Comparison Summary**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-433">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
4.  <span data-ttu-id="c1a89-434">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c1a89-434">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a89-435">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1a89-435">See Also</span></span>  
 <span data-ttu-id="c1a89-436">[Espressioni &#40;Generatore report e SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c1a89-436">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c1a89-437">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c1a89-437">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c1a89-438">[Indicatori &#40;Generatore report e SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c1a89-438">[Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c1a89-439">[Immagini, caselle di testo, rettangoli e linee &#40;Generatore report e SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c1a89-439">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c1a89-440">[Tabelle &#40;Generatore report e SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c1a89-440">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c1a89-441">Aggiungere dati a un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c1a89-441">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
