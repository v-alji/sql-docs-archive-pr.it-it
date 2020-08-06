---
title: Crea InfoCube per dati transazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 673cea01-a260-4fce-a1a0-f73839289805
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a20fe051cfdd3e6afe285279996fcf696a83c21b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712252"
---
# <a name="create-infocube-for-transaction-data"></a><span data-ttu-id="da7bb-102">Crea InfoCube per dati transazione</span><span class="sxs-lookup"><span data-stu-id="da7bb-102">Create InfoCube for Transaction Data</span></span>
  <span data-ttu-id="da7bb-103">Usare la finestra di dialogo **Crea InfoCube per dati transazione** per creare un nuovo InfoCube per i dati della transazione nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="da7bb-103">Use the **Create InfoCube for Transaction Data** dialog box to create a new InfoCube for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="da7bb-104">È possibile aprire la finestra di dialogo **Crea InfoCube per dati transazione** dalla pagina **Gestione connessione** dell' **Editor destinazione SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="da7bb-104">You can open the **Create InfoCube for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="da7bb-105">Per ulteriori informazioni sulla destinazione SAP BW, vedere [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="da7bb-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="da7bb-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="da7bb-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="da7bb-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="da7bb-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="da7bb-108">**Per aprire la finestra di dialogo Crea InfoCube per dati transazione.**</span><span class="sxs-lookup"><span data-stu-id="da7bb-108">**To open the Create InfoCube for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="da7bb-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="da7bb-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="da7bb-110">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="da7bb-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="da7bb-111">Nell' **Editor destinazione SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="da7bb-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="da7bb-112">Nella casella di gruppo **Crea oggetti SAP BW** della pagina **Gestione connessione** selezionare **InfoCube**, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="da7bb-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoCube**, and then click **Create**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="da7bb-113">Opzioni generali</span><span class="sxs-lookup"><span data-stu-id="da7bb-113">General Options</span></span>  
 <span data-ttu-id="da7bb-114">**Nome InfoCube**</span><span class="sxs-lookup"><span data-stu-id="da7bb-114">**InfoCube name**</span></span>  
 <span data-ttu-id="da7bb-115">Immettere un nome per il nuovo InfoCube.</span><span class="sxs-lookup"><span data-stu-id="da7bb-115">Enter a name for the new InfoCube.</span></span>  
  
 <span data-ttu-id="da7bb-116">**Descrizione lunga**</span><span class="sxs-lookup"><span data-stu-id="da7bb-116">**Long description**</span></span>  
 <span data-ttu-id="da7bb-117">Immettere una descrizione per il nuovo InfoCube.</span><span class="sxs-lookup"><span data-stu-id="da7bb-117">Enter a description for the new InfoCube.</span></span>  
  
 <span data-ttu-id="da7bb-118">**Salva e attiva**</span><span class="sxs-lookup"><span data-stu-id="da7bb-118">**Save & Activate**</span></span>  
 <span data-ttu-id="da7bb-119">Salvare e attivare il nuovo InfoCube.</span><span class="sxs-lookup"><span data-stu-id="da7bb-119">Save and activate the new InfoCube.</span></span>  
  
## <a name="infocube-transfer-structure-options"></a><span data-ttu-id="da7bb-120">Opzioni della struttura di trasferimento di InfoCube</span><span class="sxs-lookup"><span data-stu-id="da7bb-120">InfoCube Transfer Structure Options</span></span>  
 <span data-ttu-id="da7bb-121">La sezione della struttura di trasferimento di InfoCube consente di associare le colonne del flusso di dati agli InfoObject.</span><span class="sxs-lookup"><span data-stu-id="da7bb-121">The InfoCube transfer structure section lets you associate data flow columns to InfoObjects.</span></span>  
  
 <span data-ttu-id="da7bb-122">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="da7bb-122">**PipelineElement**</span></span>  
 <span data-ttu-id="da7bb-123">Visualizza la colonna nell'output del flusso di dati connesso alla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="da7bb-123">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="da7bb-124">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="da7bb-124">**PipelineDataType**</span></span>  
 <span data-ttu-id="da7bb-125">Visualizza il tipo di dati della colonna del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="da7bb-125">Displays the data type of the data flow column.</span></span>  
  
 <span data-ttu-id="da7bb-126">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="da7bb-126">**InfoObject**</span></span>  
 <span data-ttu-id="da7bb-127">Visualizza il nome dell'InfoObject associato alla colonna del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="da7bb-127">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="da7bb-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="da7bb-128">**Type**</span></span>  
 <span data-ttu-id="da7bb-129">Visualizza il tipo dell'InfoObject associato alla colonna del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="da7bb-129">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="da7bb-130">Nella tabella seguente sono elencati i valori possibili per il tipo.</span><span class="sxs-lookup"><span data-stu-id="da7bb-130">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="da7bb-131">valore</span><span class="sxs-lookup"><span data-stu-id="da7bb-131">Value</span></span>|<span data-ttu-id="da7bb-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da7bb-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="da7bb-133">CHA</span><span class="sxs-lookup"><span data-stu-id="da7bb-133">CHA</span></span>|<span data-ttu-id="da7bb-134">Caratteristiche</span><span class="sxs-lookup"><span data-stu-id="da7bb-134">Characteristics</span></span>|  
|<span data-ttu-id="da7bb-135">UNI</span><span class="sxs-lookup"><span data-stu-id="da7bb-135">UNI</span></span>|<span data-ttu-id="da7bb-136">Unità</span><span class="sxs-lookup"><span data-stu-id="da7bb-136">Units</span></span>|  
|<span data-ttu-id="da7bb-137">KYF</span><span class="sxs-lookup"><span data-stu-id="da7bb-137">KYF</span></span>|<span data-ttu-id="da7bb-138">Cifre chiave</span><span class="sxs-lookup"><span data-stu-id="da7bb-138">Key figures</span></span>|  
|<span data-ttu-id="da7bb-139">TIM</span><span class="sxs-lookup"><span data-stu-id="da7bb-139">TIM</span></span>|<span data-ttu-id="da7bb-140">Caratteristiche ora</span><span class="sxs-lookup"><span data-stu-id="da7bb-140">Time characteristics</span></span>|  
  
 <span data-ttu-id="da7bb-141">**Iobject - Ricerca**</span><span class="sxs-lookup"><span data-stu-id="da7bb-141">**Iobject - Search**</span></span>  
 <span data-ttu-id="da7bb-142">Associare un InfoObject esistente alla colonna del flusso di dati per la riga corrente.</span><span class="sxs-lookup"><span data-stu-id="da7bb-142">Associate an existing InfoObject to the data flow column for the current row.</span></span> <span data-ttu-id="da7bb-143">Per effettuare questa associazione, fare clic su **Cerca**e quindi usare la finestra di dialogo **Cerca InfoObject** per selezionare l'InfoObject esistente.</span><span class="sxs-lookup"><span data-stu-id="da7bb-143">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="da7bb-144">Per altre informazioni su questa finestra di dialogo, vedere [Cerca InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="da7bb-144">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="da7bb-145">Dopo aver selezionato un InfoObject esistente, le colonne **InfoObject** e **Tipo** vengono popolate dal componente con i valori selezionati.</span><span class="sxs-lookup"><span data-stu-id="da7bb-145">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="da7bb-146">**Iobject - Nuovo**</span><span class="sxs-lookup"><span data-stu-id="da7bb-146">**Iobject - New**</span></span>  
 <span data-ttu-id="da7bb-147">Creare un nuovo InfoObject e associarlo alla colonna del flusso di dati nella riga corrente.</span><span class="sxs-lookup"><span data-stu-id="da7bb-147">Create a new InfoObject and associate this new InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="da7bb-148">Per creare il nuovo InfoObject, fare clic su **Nuovo**quindi usare la finestra di dialogo **Crea nuovo InfoObject** per creare l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="da7bb-148">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="da7bb-149">Per altre informazioni su questa finestra di dialogo, vedere [Crea nuovo InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="da7bb-149">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="da7bb-150">Dopo aver creato un nuovo InfoObject, le colonne **InfoObject** e **Tipo** vengono popolate dal componente con i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="da7bb-150">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="da7bb-151">**Iobject - Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="da7bb-151">**Iobject - Remove**</span></span>  
 <span data-ttu-id="da7bb-152">Rimuovere l'associazione tra l'InfoObject e la colonna del flusso di dati per la riga corrente.</span><span class="sxs-lookup"><span data-stu-id="da7bb-152">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="da7bb-153">Per rimuovere l'associazione, scegliere **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="da7bb-153">To remove this association, click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da7bb-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da7bb-154">See Also</span></span>  
 [<span data-ttu-id="da7bb-155">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="da7bb-155">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
