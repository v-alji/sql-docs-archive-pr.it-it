---
title: "Attività 14: aggiunta dell'attività Esegui SQL al flusso di controllo per eseguire la stored procedure per MDS | Microsoft Docs"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 9a5d1b52-d505-4e6f-8a89-569329c094e2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: da8e80b25706c40e749fc364baeb578681e76b42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714840"
---
# <a name="task-14-adding-execute-sql-task-to-control-flow-to-run-the-stored-procedure-for-mds"></a><span data-ttu-id="1b4d8-102">Attività 14: Attività dell'attività Esegui SQL al flusso di controllo per eseguire la stored procedure per MDS</span><span class="sxs-lookup"><span data-stu-id="1b4d8-102">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>
  <span data-ttu-id="1b4d8-103">Dopo il caricamento dei dati nelle tabelle di staging MDS, eseguire una stored procedure associata alla tabella in questione per caricare i dati di staging nelle tabelle appropriate del database MDS.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-103">After loading data into the staging tables of MDS, you run a stored procedure associated with that table to load the data from staging into the appropriate tables in the MDS database.</span></span> <span data-ttu-id="1b4d8-104">In questa stored procedure sono inclusi due parametri obbligatori che è necessario passare: LogFlag e VersionName.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-104">This stored procedure has two required parameters that you need to pass: LogFlag and VersionName.</span></span> <span data-ttu-id="1b4d8-105">Il parametro LogFlag specifica se le transazioni vengono registrate durante il processo di gestione temporanea, mentre il parametro VersionName rappresenta la versione del modello.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-105">LogFlag specifies whether transactions are logged during the staging process and VersionName represents the version of the model.</span></span> <span data-ttu-id="1b4d8-106">Per ulteriori informazioni, vedere l'argomento [stored procedure](https://msdn.microsoft.com/library/hh231028.aspx) di gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-106">See [Staged Stored Procedure](https://msdn.microsoft.com/library/hh231028.aspx) topic for more details.</span></span>

 <span data-ttu-id="1b4d8-107">In questa attività viene aggiunta Attività Esegui SQL al flusso di controllo per richiamare la stored procedure in modo da caricare i dati di gestione temporanea nelle tabelle MDS appropriate.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-107">In this task, you add the Execute SQL Task to the control flow to invoke the stored procedure to load the staged data into appropriate MDS tables.</span></span>

1.  <span data-ttu-id="1b4d8-108">Passare ora alla scheda **flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="1b4d8-108">Now, switch to the **Control Flow** tab.</span></span>

2.  <span data-ttu-id="1b4d8-109">Trascinare l' **attività Esegui SQL** dalla **casella degli strumenti SSIS** alla scheda **flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="1b4d8-109">Drag-drop **Execute SQL Task** from the **SSIS Toolbox** to the **Control Flow** tab.</span></span>

3.  <span data-ttu-id="1b4d8-110">Fare clic con il pulsante destro del mouse su **attività Esegui SQL** nella scheda **flusso di controllo** e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-110">Right-click **Execute SQL Task** in the **Control Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="1b4d8-111">Digitare **trigger stored procedure per caricare i dati in MDS** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-111">Type **Trigger Stored Procedure to Load Data into MDS** and press **ENTER**.</span></span>

4.  <span data-ttu-id="1b4d8-112">Connettere **Ricevi, Pulisci, abbina e cura i dati fornitore** per **attivare la stored procedure per caricare i dati** usando il connettore verde.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-112">Connect **Receive, Cleanse, Match, and Curate Supplier Data** to **Trigger Stored Procedure to Load Data** using the green connector.</span></span>

     <span data-ttu-id="1b4d8-113">![Connessione all'attività Esegui SQL](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Connessione all'attività Esegui SQL")</span><span class="sxs-lookup"><span data-stu-id="1b4d8-113">![Connect to Execute SQL Task](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-01.jpg "Connect to Execute SQL Task")</span></span>

5.  <span data-ttu-id="1b4d8-114">Usando la finestra **variabili** aggiungere due nuove variabili con le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-114">Using the **Variables** window, add two new variables with the following settings.</span></span> <span data-ttu-id="1b4d8-115">Se non viene visualizzata la finestra **variabili** , fare clic su **SSIS** sulla barra dei menu e fare clic su **variabili**.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-115">If you do not see the **Variables** window, click **SSIS** on the menu bar and click **Variables**.</span></span>

    |<span data-ttu-id="1b4d8-116">Nome</span><span class="sxs-lookup"><span data-stu-id="1b4d8-116">Name</span></span>|<span data-ttu-id="1b4d8-117">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1b4d8-117">Data Type</span></span>|<span data-ttu-id="1b4d8-118">Valore</span><span class="sxs-lookup"><span data-stu-id="1b4d8-118">Value</span></span>|
    |----------|---------------|-----------|
    |<span data-ttu-id="1b4d8-119">LogFlag</span><span class="sxs-lookup"><span data-stu-id="1b4d8-119">LogFlag</span></span>|<span data-ttu-id="1b4d8-120">Int32</span><span class="sxs-lookup"><span data-stu-id="1b4d8-120">Int32</span></span>|<span data-ttu-id="1b4d8-121">1</span><span class="sxs-lookup"><span data-stu-id="1b4d8-121">1</span></span>|
    |<span data-ttu-id="1b4d8-122">VersionName</span><span class="sxs-lookup"><span data-stu-id="1b4d8-122">VersionName</span></span>|<span data-ttu-id="1b4d8-123">string</span><span class="sxs-lookup"><span data-stu-id="1b4d8-123">String</span></span>|<span data-ttu-id="1b4d8-124">VERSION_1</span><span class="sxs-lookup"><span data-stu-id="1b4d8-124">VERSION_1</span></span>|

     <span data-ttu-id="1b4d8-125">![Finestra Variabili SSIS](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "Finestra Variabili SSIS")</span><span class="sxs-lookup"><span data-stu-id="1b4d8-125">![SSIS Variables Window](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-02.jpg "SSIS Variables Window")</span></span>

6.  <span data-ttu-id="1b4d8-126">Fare doppio clic su **trigger stored procedure per caricare i dati in MDS**.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-126">Double-click **Trigger Stored Procedure to Load Data into MDS**.</span></span>

7.  <span data-ttu-id="1b4d8-127">Nella finestra di dialogo **Editor attività Esegui SQL** selezionare **(locale). MDS** (o **localhost). MDS**) per la **connessione**.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-127">In the **Execute SQL Task Editor** dialog box, select **(local).MDS** (or **localhost.MDS**) for **Connection**.</span></span>

8.  <span data-ttu-id="1b4d8-128">Digitare **exec [STG]. [ udp_Supplier_Leaf]?,?,?**</span><span class="sxs-lookup"><span data-stu-id="1b4d8-128">Type **EXEC [stg].[udp_Supplier_Leaf] ?, ?, ?**</span></span> <span data-ttu-id="1b4d8-129">per l' **istruzione SQL**.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-129">for **SQL Statement**.</span></span> <span data-ttu-id="1b4d8-130">Per verificare il nome, utilizzare SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-130">You can verify the name by using SQL Server Management Studio.</span></span>

     <span data-ttu-id="1b4d8-131">![Finestra di dialogo Editor Esegui SQL - Impostazioni generali](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Finestra di dialogo Editor Esegui SQL - Impostazioni generali")</span><span class="sxs-lookup"><span data-stu-id="1b4d8-131">![Execute SQL Editor Dialog Box - General Settings](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-03.jpg "Execute SQL Editor Dialog Box - General Settings")</span></span>

9. <span data-ttu-id="1b4d8-132">Fare clic su **Mapping parametri** dal menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-132">Click **Parameter Mapping** from the menu on left.</span></span>

10. <span data-ttu-id="1b4d8-133">Nella pagina **Mapping parametri** fare clic su **Aggiungi** per aggiungere un mapping.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-133">In the **Parameter Mapping** page, click **Add** to add a mapping.</span></span> <span data-ttu-id="1b4d8-134">Ingrandire la finestra e ridimensionare le colonne in modo da visualizzare correttamente i valori negli elenchi a discesa.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-134">Maximize the window and resize columns so that you can see values in drop-down lists properly.</span></span>

11. <span data-ttu-id="1b4d8-135">Selezionare **User:: VersionName** dall'elenco a discesa per il nome della **variabile**.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-135">Select **User::VersionName** from the drop-down list for the **Variable Name**.</span></span>

12. <span data-ttu-id="1b4d8-136">Selezionare **nvarchar** per **tipo di dati**.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-136">Select **NVARCHAR** for **Data Type**.</span></span>

13. <span data-ttu-id="1b4d8-137">Digitare **0** (zero) per **nome parametro**.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-137">Type **0** (zero) for **Parameter Name**.</span></span>

14. <span data-ttu-id="1b4d8-138">Ripetere i quattro passaggi precedenti per aggiungere altre due variabili.</span><span class="sxs-lookup"><span data-stu-id="1b4d8-138">Repeat the previous four steps to add two more variables.</span></span>

    |<span data-ttu-id="1b4d8-139">Nome variabile</span><span class="sxs-lookup"><span data-stu-id="1b4d8-139">Variable Name</span></span>|<span data-ttu-id="1b4d8-140">Tipo di dati (importante)</span><span class="sxs-lookup"><span data-stu-id="1b4d8-140">Data Type (important)</span></span>|<span data-ttu-id="1b4d8-141">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="1b4d8-141">Parameter Name</span></span>|
    |-------------------|-----------------------------|--------------------|
    |<span data-ttu-id="1b4d8-142">User::LogFlag</span><span class="sxs-lookup"><span data-stu-id="1b4d8-142">User::LogFlag</span></span>|<span data-ttu-id="1b4d8-143">LONG</span><span class="sxs-lookup"><span data-stu-id="1b4d8-143">LONG</span></span>|<span data-ttu-id="1b4d8-144">1</span><span class="sxs-lookup"><span data-stu-id="1b4d8-144">1</span></span>|
    |<span data-ttu-id="1b4d8-145">User::BatchTag</span><span class="sxs-lookup"><span data-stu-id="1b4d8-145">User::BatchTag</span></span>|<span data-ttu-id="1b4d8-146">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="1b4d8-146">NVARCHAR</span></span>|<span data-ttu-id="1b4d8-147">2</span><span class="sxs-lookup"><span data-stu-id="1b4d8-147">2</span></span>|

     <span data-ttu-id="1b4d8-148">![Editor attività Esegui SQL - Mapping parametri](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Editor attività Esegui SQL - Mapping parametri")</span><span class="sxs-lookup"><span data-stu-id="1b4d8-148">![Execute SQL Task Editor - Parameter Mapping](../../2014/tutorials/media/et-addingesqltasktocftorunthespformds-04.jpg "Execute SQL Task Editor - Parameter Mapping")</span></span>

15. <span data-ttu-id="1b4d8-149">Fare clic su **OK** per chiudere la finestra di dialogo **Editor SQL Esegui** .</span><span class="sxs-lookup"><span data-stu-id="1b4d8-149">Click **OK** to close the **Execute SQL Editor** dialog box.</span></span>

## <a name="next-step"></a><span data-ttu-id="1b4d8-150">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="1b4d8-150">Next Step</span></span>
 [<span data-ttu-id="1b4d8-151">Attività 15: Compilazione ed esecuzione del progetto SSIS</span><span class="sxs-lookup"><span data-stu-id="1b4d8-151">Task 15: Building and Running the SSIS Project</span></span>](../../2014/tutorials/task-15-building-and-running-the-ssis-project.md)


