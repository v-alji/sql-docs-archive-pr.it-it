---
title: Crea nuovo InfoObject | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 3587a633-1c0b-4d63-a22a-6b2b93923c3a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 022f2d1e3fe10ae037ea379a02a18845b3a36107
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636824"
---
# <a name="create-new-infoobject"></a><span data-ttu-id="97864-102">Crea nuovo InfoObject</span><span class="sxs-lookup"><span data-stu-id="97864-102">Create New InfoObject</span></span>
  <span data-ttu-id="97864-103">Usare la finestra di dialogo **Crea nuovo InfoObject** per creare un nuovo InfoObject nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="97864-103">Use the **Create New InfoObject** dialog box to create a new InfoObject in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="97864-104">È possibile aprire la finestra di dialogo **Crea InfoObject** dalla pagina **Gestione connessione** dell' **Editor destinazione SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="97864-104">You can open the **Create InfoObject** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="97864-105">Per ulteriori informazioni sulla destinazione SAP BW, vedere [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="97864-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="97864-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="97864-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="97864-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="97864-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="97864-108">**Per aprire la finestra di dialogo Crea nuovo InfoObject**</span><span class="sxs-lookup"><span data-stu-id="97864-108">**To open the Create New InfoObject dialog box**</span></span>  
  
1.  <span data-ttu-id="97864-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="97864-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="97864-110">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="97864-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="97864-111">Nell' **Editor destinazione SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="97864-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="97864-112">Nella casella di gruppo **Crea oggetti SAP BW** della pagina **Gestione connessione** eseguire una delle operazioni seguenti per creare un InfoObject:</span><span class="sxs-lookup"><span data-stu-id="97864-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, do one of the following steps to create an InfoObject:</span></span>  
  
    1.  <span data-ttu-id="97864-113">Per creare un InfoObject direttamente, selezionare **InfoObject**e quindi fare clic su **Crea** per aprire la finestra di dialogo **Crea nuovo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="97864-113">To create an InfoObject directly, select **InfoObject**, and then click **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
    2.  <span data-ttu-id="97864-114">Per creare un InfoObject durante la creazione di un InfoCube, selezionare **InfoCube**e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="97864-114">To create an InfoObject while creating an InfoCube, select **InfoCube**, and then click **Create**.</span></span> <span data-ttu-id="97864-115">Nella finestra di dialogo **Crea InfoCube per dati transazione** , nella colonna **IObject** di una delle righe dell'elenco selezionare **Crea** per aprire la finestra di dialogo **Crea nuovo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="97864-115">In the **Create InfoCube for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="97864-116">Ogni riga della tabella rappresenta una colonna nel flusso di dati del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="97864-116">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    3.  <span data-ttu-id="97864-117">Per creare un InfoObject durante la creazione di un InfoSource per dati transazionali, selezionare **InfoSource**e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="97864-117">To create an InfoObject while creating an InfoSouce for transactional data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="97864-118">Nella finestra di dialogo **Crea InfoSource** selezionare **Dati transazione**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="97864-118">In the **Create InfoSource** dialog box, select **Transaction Data**, and then click **OK**.</span></span> <span data-ttu-id="97864-119">Nella finestra di dialogo **Crea InfoSource per dati transazione** , nella colonna **IObject** di una delle righe dell'elenco selezionare **Crea** per aprire la finestra di dialogo **Crea nuovo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="97864-119">In the **Create InfoSource for Transaction Data** dialog box, in the **IObject** column for one of the rows in the list, select **Create** to open the **Create New InfoObject** dialog box.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="97864-120">Ogni riga della tabella rappresenta una colonna nel flusso di dati del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="97864-120">Each row in the table represents a column in the data flow of the package.</span></span>  
  
    4.  <span data-ttu-id="97864-121">Per creare un InfoObject durante la creazione di un InfoSource per dati master, selezionare **InfoSource**e quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="97864-121">To create an InfoObject while creating an InfoSource for master data, select **InfoSource**, and then click **Create**.</span></span> <span data-ttu-id="97864-122">Nella finestra di dialogo **Crea InfoSource** selezionare **Dati master**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="97864-122">In the **Create InfoSource** dialog box, select **Master Data**, and then click **OK**.</span></span> <span data-ttu-id="97864-123">Nella finestra di dialogo **Crea InfoSource per dati master** , fare clic su **Nuovo** per aprire la finestra di dialogo **Crea nuovo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="97864-123">In the **Create InfoSource for Master Data** dialog box, click **New** to open the **Create New InfoObject** dialog box.</span></span>  
  
 <span data-ttu-id="97864-124">È anche possibile aprire la finestra di dialogo **Crea nuovo InfoObject** facendo clic su **Nuovo** nella sezione **Attributi** della finestra di dialogo **Crea nuovo InfoObject** .</span><span class="sxs-lookup"><span data-stu-id="97864-124">You can also open the **Create New InfoObject** dialog box by clicking **New** in the **Attributes** section of the **Create New InfoObject** dialog box.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="97864-125">Opzioni generali</span><span class="sxs-lookup"><span data-stu-id="97864-125">General Options</span></span>  
 <span data-ttu-id="97864-126">**Caratteristica**</span><span class="sxs-lookup"><span data-stu-id="97864-126">**Characteristic**</span></span>  
 <span data-ttu-id="97864-127">Creare un InfoObject che rappresenti i dati di dimensione.</span><span class="sxs-lookup"><span data-stu-id="97864-127">Create an InfoObject that represents dimension data.</span></span>  
  
 <span data-ttu-id="97864-128">**Cifra chiave**</span><span class="sxs-lookup"><span data-stu-id="97864-128">**Key figure**</span></span>  
 <span data-ttu-id="97864-129">Creare un InfoObject che rappresenti i dati delle tabelle dei fatti.</span><span class="sxs-lookup"><span data-stu-id="97864-129">Create an InfoObject that represents fact data.</span></span>  
  
 <span data-ttu-id="97864-130">**Nome InfoObject**</span><span class="sxs-lookup"><span data-stu-id="97864-130">**InfoObject name**</span></span>  
 <span data-ttu-id="97864-131">Immettere un nome per l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="97864-131">Enter a name for the InfoObject.</span></span>  
  
 <span data-ttu-id="97864-132">**Descrizione breve**</span><span class="sxs-lookup"><span data-stu-id="97864-132">**Short description**</span></span>  
 <span data-ttu-id="97864-133">Immettere una breve descrizione per l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="97864-133">Enter a short description for the InfoObject.</span></span>  
  
 <span data-ttu-id="97864-134">**Descrizione lunga**</span><span class="sxs-lookup"><span data-stu-id="97864-134">**Long description**</span></span>  
 <span data-ttu-id="97864-135">Immettere una descrizione lunga per l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="97864-135">Enter a long description for the InfoObject.</span></span>  
  
 <span data-ttu-id="97864-136">**Con dati master**</span><span class="sxs-lookup"><span data-stu-id="97864-136">**Has master data**</span></span>  
 <span data-ttu-id="97864-137">Indicare che l'InfoObject contiene dati master sotto forma di attributi, testo o gerarchie.</span><span class="sxs-lookup"><span data-stu-id="97864-137">Indicate that the InfoObject contains master data in the form of attributes, texts, or hierarchies.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97864-138">Selezionare questa opzione se l'InfoObject rappresenta i dati di dimensione e se è stata selezionata l'opzione **Caratteristica** .</span><span class="sxs-lookup"><span data-stu-id="97864-138">Select this option if the InfoObject represents dimensional data and you have selected the **Characteristic** option.</span></span>  
  
 <span data-ttu-id="97864-139">**Consenti caratteri minuscoli**</span><span class="sxs-lookup"><span data-stu-id="97864-139">**Allow lower-case characters**</span></span>  
 <span data-ttu-id="97864-140">Sono consentiti i caratteri minuscoli nei dati dell'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="97864-140">Allow lower-case characters in the InfoObject data.</span></span>  
  
 <span data-ttu-id="97864-141">**Salva e attiva**</span><span class="sxs-lookup"><span data-stu-id="97864-141">**Save & Activate**</span></span>  
 <span data-ttu-id="97864-142">Salva e attiva il nuovo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="97864-142">Save and active the new InfoObject.</span></span>  
  
## <a name="data-type-options"></a><span data-ttu-id="97864-143">Opzioni per i tipi di dati</span><span class="sxs-lookup"><span data-stu-id="97864-143">Data Type Options</span></span>  
 <span data-ttu-id="97864-144">**CHAR - Stringa di caratteri**</span><span class="sxs-lookup"><span data-stu-id="97864-144">**CHAR - Character String**</span></span>  
 <span data-ttu-id="97864-145">Indica che l'InfoObject contiene dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="97864-145">Indicates that the InfoObject contains character data.</span></span>  
  
 <span data-ttu-id="97864-146">**NUMC - Stringa numerica**</span><span class="sxs-lookup"><span data-stu-id="97864-146">**NUMC - Numeric String**</span></span>  
 <span data-ttu-id="97864-147">Indica che l'InfoObject contiene dati numerici.</span><span class="sxs-lookup"><span data-stu-id="97864-147">Indicates that the InfoObject contains numeric data.</span></span>  
  
 <span data-ttu-id="97864-148">**DATS - Data (AAAAMMGG)**</span><span class="sxs-lookup"><span data-stu-id="97864-148">**DATS - Date (YYYYMMDD)**</span></span>  
 <span data-ttu-id="97864-149">Indica che l'InfoObject contiene dati di data.</span><span class="sxs-lookup"><span data-stu-id="97864-149">Indicates that the InfoObject contains date data.</span></span>  
  
 <span data-ttu-id="97864-150">**TIMS - Ora (HHMMSS)**</span><span class="sxs-lookup"><span data-stu-id="97864-150">**TIMS - Time (HHMMSS)**</span></span>  
 <span data-ttu-id="97864-151">Indica che l'InfoObject contiene dati orari.</span><span class="sxs-lookup"><span data-stu-id="97864-151">Indicates that the InfoObject contains time data.</span></span>  
  
 <span data-ttu-id="97864-152">**Lunghezza**</span><span class="sxs-lookup"><span data-stu-id="97864-152">**Length**</span></span>  
 <span data-ttu-id="97864-153">Immettere la lunghezza dei dati.</span><span class="sxs-lookup"><span data-stu-id="97864-153">Enter the length of the data.</span></span>  
  
## <a name="text-options"></a><span data-ttu-id="97864-154">Opzioni di testo</span><span class="sxs-lookup"><span data-stu-id="97864-154">Text Options</span></span>  
 <span data-ttu-id="97864-155">**Con testi**</span><span class="sxs-lookup"><span data-stu-id="97864-155">**With Texts**</span></span>  
 <span data-ttu-id="97864-156">Indica che l'InfoObject contiene testi.</span><span class="sxs-lookup"><span data-stu-id="97864-156">Indicate that the InfoObject contains texts.</span></span>  
  
 <span data-ttu-id="97864-157">**Testo breve**</span><span class="sxs-lookup"><span data-stu-id="97864-157">**Short Text**</span></span>  
 <span data-ttu-id="97864-158">Indica che l'InfoObject contiene testi brevi.</span><span class="sxs-lookup"><span data-stu-id="97864-158">Indicates that the InfoObject contains short texts.</span></span>  
  
 <span data-ttu-id="97864-159">**Testo medio**</span><span class="sxs-lookup"><span data-stu-id="97864-159">**Medium Text**</span></span>  
 <span data-ttu-id="97864-160">Indica che l'InfoObject contiene testi medi.</span><span class="sxs-lookup"><span data-stu-id="97864-160">Indicates that the InfoObject contains medium texts.</span></span>  
  
 <span data-ttu-id="97864-161">**Testo lungo**</span><span class="sxs-lookup"><span data-stu-id="97864-161">**Long Text**</span></span>  
 <span data-ttu-id="97864-162">Indica che l'InfoObject contiene testi lunghi.</span><span class="sxs-lookup"><span data-stu-id="97864-162">Indicates that the InfoObject contains long texts.</span></span>  
  
 <span data-ttu-id="97864-163">**Testo dipendente dalla lingua**</span><span class="sxs-lookup"><span data-stu-id="97864-163">**Text Language-Dependent**</span></span>  
 <span data-ttu-id="97864-164">Indica che i testi sono dipendenti dalla lingua.</span><span class="sxs-lookup"><span data-stu-id="97864-164">Indicates that the texts are language-dependent.</span></span>  
  
 <span data-ttu-id="97864-165">**Testo dipendente dall'ora**</span><span class="sxs-lookup"><span data-stu-id="97864-165">**Text Time-Dependent**</span></span>  
 <span data-ttu-id="97864-166">Indica che i testi sono dipendenti dall'ora.</span><span class="sxs-lookup"><span data-stu-id="97864-166">Indicates that the texts are time-dependent.</span></span>  
  
## <a name="attributes-section"></a><span data-ttu-id="97864-167">Sezione Attributi</span><span class="sxs-lookup"><span data-stu-id="97864-167">Attributes Section</span></span>  
 <span data-ttu-id="97864-168">La sezione **Attributi** è costituita da un elenco di attributi per l'InfoObject e dalle opzioni che consentono di aggiungere e rimuovere gli attributi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="97864-168">The **Attributes** section consists of a list of attributes for the InfoObject, and the options that let you add and remove attributes from the list.</span></span>  
  
### <a name="attributes-list"></a><span data-ttu-id="97864-169">Elenco Attributi</span><span class="sxs-lookup"><span data-stu-id="97864-169">Attributes List</span></span>  
 <span data-ttu-id="97864-170">Nell'elenco **Attributi** sono visualizzati gli attributi dell'InfoObject che viene creato.</span><span class="sxs-lookup"><span data-stu-id="97864-170">The **Attributes** list displays the attributes of the InfoObject that you are creating.</span></span> <span data-ttu-id="97864-171">L'elenco **Attributi** presenta le seguenti intestazioni di colonna:</span><span class="sxs-lookup"><span data-stu-id="97864-171">The **Attributes** list has the following column headings:</span></span>  
  
 <span data-ttu-id="97864-172">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="97864-172">**InfoObject**</span></span>  
 <span data-ttu-id="97864-173">Visualizza il nome dell'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="97864-173">View the name of the InfoObject.</span></span>  
  
 <span data-ttu-id="97864-174">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="97864-174">**Description**</span></span>  
 <span data-ttu-id="97864-175">Visualizza la descrizione dell'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="97864-175">View the description of the InfoObject.</span></span>  
  
 <span data-ttu-id="97864-176">**Tipo di InfoObject**</span><span class="sxs-lookup"><span data-stu-id="97864-176">**InfoObject Type**</span></span>  
 <span data-ttu-id="97864-177">Visualizza il tipo dell'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="97864-177">View the type of the InfoObject.</span></span> <span data-ttu-id="97864-178">Nella tabella seguente sono elencati i valori possibili per il tipo.</span><span class="sxs-lookup"><span data-stu-id="97864-178">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="97864-179">valore</span><span class="sxs-lookup"><span data-stu-id="97864-179">Value</span></span>|<span data-ttu-id="97864-180">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97864-180">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="97864-181">CHA</span><span class="sxs-lookup"><span data-stu-id="97864-181">CHA</span></span>|<span data-ttu-id="97864-182">Caratteristiche</span><span class="sxs-lookup"><span data-stu-id="97864-182">Characteristics</span></span>|  
|<span data-ttu-id="97864-183">KYF</span><span class="sxs-lookup"><span data-stu-id="97864-183">KYF</span></span>|<span data-ttu-id="97864-184">Cifre chiave</span><span class="sxs-lookup"><span data-stu-id="97864-184">Key figures</span></span>|  
|<span data-ttu-id="97864-185">UNI</span><span class="sxs-lookup"><span data-stu-id="97864-185">UNI</span></span>|<span data-ttu-id="97864-186">Unità</span><span class="sxs-lookup"><span data-stu-id="97864-186">Units</span></span>|  
|<span data-ttu-id="97864-187">TIM</span><span class="sxs-lookup"><span data-stu-id="97864-187">TIM</span></span>|<span data-ttu-id="97864-188">Caratteristiche ora</span><span class="sxs-lookup"><span data-stu-id="97864-188">Time characteristics</span></span>|  
  
### <a name="attributes-options"></a><span data-ttu-id="97864-189">Opzioni degli attributi</span><span class="sxs-lookup"><span data-stu-id="97864-189">Attributes Options</span></span>  
 <span data-ttu-id="97864-190">Utilizzare le opzioni seguenti per aggiungere e rimuovere attributi per l'InfoObject che viene creato:</span><span class="sxs-lookup"><span data-stu-id="97864-190">Use the following options to add and remove attributes for the InfoObject that you are creating:</span></span>  
  
 <span data-ttu-id="97864-191">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="97864-191">**Add**</span></span>  
 <span data-ttu-id="97864-192">Aggiungere un InfoObject esistente come attributo.</span><span class="sxs-lookup"><span data-stu-id="97864-192">Add an existing InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="97864-193">Per aggiungere un InfoObject esistente, fare clic su Aggiungi e quindi usare la finestra di dialogo **Cerca InfoObject** per trovare l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="97864-193">To add an existing InfoObject, click Add, and then use the **Look Up InfoObject** dialog box to find the InfoObject.</span></span> <span data-ttu-id="97864-194">Per altre informazioni su questa finestra di dialogo, vedere [Cerca InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="97864-194">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="97864-195">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="97864-195">**New**</span></span>  
 <span data-ttu-id="97864-196">Aggiungere un nuovo InfoObject come attributo.</span><span class="sxs-lookup"><span data-stu-id="97864-196">Add a new InfoObject as an attribute.</span></span>  
  
 <span data-ttu-id="97864-197">Per creare e aggiungere un nuovo InfoObject, fare clic su Nuovo e quindi usare una nuova istanza della finestra di dialogo **Crea nuovo InfoObject** per creare il nuovo InfoObject.</span><span class="sxs-lookup"><span data-stu-id="97864-197">To create and add a new InfoObject, click New, and then use a new instance of the **Create New InfoObject** dialog box to create the new InfoObject.</span></span>  
  
 <span data-ttu-id="97864-198">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="97864-198">**Remove**</span></span>  
 <span data-ttu-id="97864-199">Rimuove l'InfoObject selezionato dall'elenco **Attributi** .</span><span class="sxs-lookup"><span data-stu-id="97864-199">Remove the selected InfoObject from the **Attributes** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97864-200">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97864-200">See Also</span></span>  
 <span data-ttu-id="97864-201">[Crea InfoCube per dati transazione](create-infocube-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="97864-201">[Create InfoCube for Transaction Data](create-infocube-for-transaction-data.md) </span></span>  
 <span data-ttu-id="97864-202">[Crea InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="97864-202">[Create InfoSource](create-infosource.md) </span></span>  
 <span data-ttu-id="97864-203">[Crea InfoSource per dati transazione](create-infosource-for-transaction-data.md) </span><span class="sxs-lookup"><span data-stu-id="97864-203">[Create InfoSource for Transaction Data](create-infosource-for-transaction-data.md) </span></span>  
 <span data-ttu-id="97864-204">[Crea InfoSource per dati master](create-infosource-for-master-data.md) </span><span class="sxs-lookup"><span data-stu-id="97864-204">[Create InfoSource for Master Data](create-infosource-for-master-data.md) </span></span>  
 [<span data-ttu-id="97864-205">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="97864-205">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
