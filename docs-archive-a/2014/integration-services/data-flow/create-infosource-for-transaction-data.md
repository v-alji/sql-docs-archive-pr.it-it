---
title: Crea InfoSource per dati transazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ab5f23e2-cd4e-4507-83d9-ac5ef721c171
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e3a60bb93da17e79087982473e92c35fa0856d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712236"
---
# <a name="create-infosource-for-transaction-data"></a><span data-ttu-id="84bb9-102">Crea InfoSource per dati transazione</span><span class="sxs-lookup"><span data-stu-id="84bb9-102">Create InfoSource for Transaction Data</span></span>
  <span data-ttu-id="84bb9-103">Usare la finestra di dialogo **Crea InfoSource per dati transazione** per creare un nuovo InfoSource per i dati della transazione nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="84bb9-103">Use the **Create InfoSource for Transaction Data** dialog box to create a new InfoSource for transaction data in the SAP Netweaver BW system.</span></span>  
  
 <span data-ttu-id="84bb9-104">È possibile aprire la finestra di dialogo **Crea InfoSource per dati transazione** dalla pagina **Gestione connessione** dell' **Editor destinazione SAP BW**.</span><span class="sxs-lookup"><span data-stu-id="84bb9-104">You can open the **Create InfoSource for Transaction Data** dialog box from the **Connection Manager** page of the **SAP BW Destination Editor**.</span></span> <span data-ttu-id="84bb9-105">Per ulteriori informazioni sulla destinazione SAP BW, vedere [SAP BW Destination](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="84bb9-105">To learn more about the SAP BW destination, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="84bb9-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="84bb9-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="84bb9-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="84bb9-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="84bb9-108">**Per aprire la finestra di dialogo Crea InfoSource per dati transazione**</span><span class="sxs-lookup"><span data-stu-id="84bb9-108">**To open the Create InfoSource for Transaction Data dialog box**</span></span>  
  
1.  <span data-ttu-id="84bb9-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="84bb9-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="84bb9-110">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="84bb9-110">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="84bb9-111">Nell' **Editor destinazione SAP BW**fare clic su **Gestione connessione** per aprire la pagina **Gestione connessione** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="84bb9-111">In the **SAP BW Destination Editor**, click **Connection Manager** to open the **Connection Manager** page of the editor.</span></span>  
  
4.  <span data-ttu-id="84bb9-112">Nella casella di gruppo **Crea oggetti SAP BW** della pagina **Gestione connessione** selezionare **InfoSource**, quindi fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="84bb9-112">On the **Connection Manager** page, in the **Create SAP BW Objects** group box, select **InfoSource**, and then click **Create**.</span></span>  
  
5.  <span data-ttu-id="84bb9-113">Nella finestra di dialogo **Crea InfoSource** selezionare **Dati transazione**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="84bb9-113">In the **Create InfoSource** dialog box, select **Transaction data**, and then click **OK**.</span></span>  
  
## <a name="general-options"></a><span data-ttu-id="84bb9-114">Opzioni generali</span><span class="sxs-lookup"><span data-stu-id="84bb9-114">General Options</span></span>  
 <span data-ttu-id="84bb9-115">**Nome InfoSource**</span><span class="sxs-lookup"><span data-stu-id="84bb9-115">**InfoSource name**</span></span>  
 <span data-ttu-id="84bb9-116">Immettere un nome per il nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="84bb9-116">Enter a name for the new InfoSource.</span></span>  
  
 <span data-ttu-id="84bb9-117">**Descrizione breve**</span><span class="sxs-lookup"><span data-stu-id="84bb9-117">**Short description**</span></span>  
 <span data-ttu-id="84bb9-118">Immettere una breve descrizione per il nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="84bb9-118">Enter a short description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="84bb9-119">**Descrizione lunga**</span><span class="sxs-lookup"><span data-stu-id="84bb9-119">**Long description**</span></span>  
 <span data-ttu-id="84bb9-120">Immettere una descrizione lunga per il nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="84bb9-120">Enter a long description for the new InfoSource.</span></span>  
  
 <span data-ttu-id="84bb9-121">**Sistema di origine**</span><span class="sxs-lookup"><span data-stu-id="84bb9-121">**Source system**</span></span>  
 <span data-ttu-id="84bb9-122">Selezionare il sistema di origine associato all'InfoSource.</span><span class="sxs-lookup"><span data-stu-id="84bb9-122">Select the source system associated with the InfoSource.</span></span>  
  
 <span data-ttu-id="84bb9-123">**Salva e attiva**</span><span class="sxs-lookup"><span data-stu-id="84bb9-123">**Save & Activate**</span></span>  
 <span data-ttu-id="84bb9-124">Salvare e attivare il nuovo InfoSource.</span><span class="sxs-lookup"><span data-stu-id="84bb9-124">Save and activate the new InfoSource.</span></span>  
  
## <a name="infosource-transfer-structure-options"></a><span data-ttu-id="84bb9-125">Opzioni della struttura di trasferimento di InfoSource</span><span class="sxs-lookup"><span data-stu-id="84bb9-125">InfoSource Transfer Structure Options</span></span>  
 <span data-ttu-id="84bb9-126">La struttura di trasferimento di InfoSource consente di associare le colonne del flusso di dati agli InfoSource.</span><span class="sxs-lookup"><span data-stu-id="84bb9-126">The InfoSource transfer structure lets you associate data flow columns to InfoSources.</span></span>  
  
 <span data-ttu-id="84bb9-127">**PipelineElement**</span><span class="sxs-lookup"><span data-stu-id="84bb9-127">**PipelineElement**</span></span>  
 <span data-ttu-id="84bb9-128">Visualizza la colonna nell'output del flusso di dati connesso alla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="84bb9-128">Displays the column in the output of the data flow that is connected to the SAP BW destination.</span></span>  
  
 <span data-ttu-id="84bb9-129">**PipelineDataType**</span><span class="sxs-lookup"><span data-stu-id="84bb9-129">**PipelineDataType**</span></span>  
 <span data-ttu-id="84bb9-130">Visualizza il tipo di dati [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] della colonna del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="84bb9-130">Displays the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type of the data flow column.</span></span>  
  
 <span data-ttu-id="84bb9-131">**Iobject - Ricerca**</span><span class="sxs-lookup"><span data-stu-id="84bb9-131">**Iobject - Search**</span></span>  
 <span data-ttu-id="84bb9-132">Associare un InfoObject esistente alla colonna del flusso di dati nella riga corrente.</span><span class="sxs-lookup"><span data-stu-id="84bb9-132">Associate an existing InfoObject to the data flow column in the current row.</span></span> <span data-ttu-id="84bb9-133">Per effettuare questa associazione, fare clic su **Cerca**e quindi usare la finestra di dialogo **Cerca InfoObject** per selezionare l'InfoObject esistente.</span><span class="sxs-lookup"><span data-stu-id="84bb9-133">To make this association, click **Search**, and then use the **Look Up InfoObject** dialog box to select the existing InfoObject.</span></span> <span data-ttu-id="84bb9-134">Per altre informazioni su questa finestra di dialogo, vedere [Cerca InfoObject](look-up-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="84bb9-134">For more information about this dialog box, see [Look Up InfoObject](look-up-infoobject.md).</span></span>  
  
 <span data-ttu-id="84bb9-135">Dopo aver selezionato un InfoObject esistente, le colonne **InfoObject** e **Tipo** vengono popolate dal componente con i valori selezionati.</span><span class="sxs-lookup"><span data-stu-id="84bb9-135">After you select an existing InfoObject, the component populates the **InfoObject** and **Type** columns with the selected values.</span></span>  
  
 <span data-ttu-id="84bb9-136">**Iobject - Nuovo**</span><span class="sxs-lookup"><span data-stu-id="84bb9-136">**Iobject - New**</span></span>  
 <span data-ttu-id="84bb9-137">Creare un nuovo InfoObject e associarlo alla colonna del flusso di dati nella riga corrente.</span><span class="sxs-lookup"><span data-stu-id="84bb9-137">Create a new InfoObject and associate this new InfoObect to the data flow column in the current row.</span></span> <span data-ttu-id="84bb9-138">Per creare il nuovo InfoObject, fare clic su **Nuovo**quindi usare la finestra di dialogo **Crea nuovo InfoObject** per creare l'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="84bb9-138">To create the new InfoObject, click **New**, and then use the **Create New InfoObject** dialog box to create the InfoObject.</span></span> <span data-ttu-id="84bb9-139">Per altre informazioni su questa finestra di dialogo, vedere [Crea nuovo InfoObject](create-new-infoobject.md).</span><span class="sxs-lookup"><span data-stu-id="84bb9-139">For more information about this dialog box, see [Create New InfoObject](create-new-infoobject.md).</span></span>  
  
 <span data-ttu-id="84bb9-140">Dopo aver creato un nuovo InfoObject, le colonne **InfoObject** e **Tipo** vengono popolate dal componente con i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="84bb9-140">After you create a new InfoObject, the component populates the **InfoObject** and **Type** columns with the new values.</span></span>  
  
 <span data-ttu-id="84bb9-141">**Iobject - Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="84bb9-141">**Iobject - Remove**</span></span>  
 <span data-ttu-id="84bb9-142">Rimuovere l'associazione tra l'InfoObject e la colonna del flusso di dati per la riga corrente.</span><span class="sxs-lookup"><span data-stu-id="84bb9-142">Remove the association between the InfoObject and the data flow column for the current row.</span></span> <span data-ttu-id="84bb9-143">Per rimuovere l'associazione, scegliere **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="84bb9-143">To remove this association, click **Remove**.</span></span>  
  
 <span data-ttu-id="84bb9-144">**InfoObject**</span><span class="sxs-lookup"><span data-stu-id="84bb9-144">**InfoObject**</span></span>  
 <span data-ttu-id="84bb9-145">Visualizza il nome dell'InfoObject associato alla colonna del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="84bb9-145">Displays the name of the InfoObject that is associated with the data flow column.</span></span>  
  
 <span data-ttu-id="84bb9-146">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="84bb9-146">**Type**</span></span>  
 <span data-ttu-id="84bb9-147">Visualizza il tipo dell'InfoObject associato alla colonna del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="84bb9-147">Displays the type of the InfoObject that is associated with the data flow column.</span></span> <span data-ttu-id="84bb9-148">Nella tabella seguente sono elencati i valori possibili per il tipo.</span><span class="sxs-lookup"><span data-stu-id="84bb9-148">The following table lists the possible values for the type.</span></span>  
  
|<span data-ttu-id="84bb9-149">valore</span><span class="sxs-lookup"><span data-stu-id="84bb9-149">Value</span></span>|<span data-ttu-id="84bb9-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84bb9-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="84bb9-151">CHA</span><span class="sxs-lookup"><span data-stu-id="84bb9-151">CHA</span></span>|<span data-ttu-id="84bb9-152">Caratteristiche</span><span class="sxs-lookup"><span data-stu-id="84bb9-152">Characteristics</span></span>|  
|<span data-ttu-id="84bb9-153">UNI</span><span class="sxs-lookup"><span data-stu-id="84bb9-153">UNI</span></span>|<span data-ttu-id="84bb9-154">Unità</span><span class="sxs-lookup"><span data-stu-id="84bb9-154">Units</span></span>|  
|<span data-ttu-id="84bb9-155">KYF</span><span class="sxs-lookup"><span data-stu-id="84bb9-155">KYF</span></span>|<span data-ttu-id="84bb9-156">Cifre chiave</span><span class="sxs-lookup"><span data-stu-id="84bb9-156">Key figures</span></span>|  
|<span data-ttu-id="84bb9-157">TIM</span><span class="sxs-lookup"><span data-stu-id="84bb9-157">TIM</span></span>|<span data-ttu-id="84bb9-158">Caratteristiche ora</span><span class="sxs-lookup"><span data-stu-id="84bb9-158">Time characteristics</span></span>|  
  
 <span data-ttu-id="84bb9-159">**Campo unità**</span><span class="sxs-lookup"><span data-stu-id="84bb9-159">**Unit Field**</span></span>  
 <span data-ttu-id="84bb9-160">Specificare le unità che verranno utilizzate dall'InfoObject.</span><span class="sxs-lookup"><span data-stu-id="84bb9-160">Specify the units that the InfoObject will use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84bb9-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84bb9-161">See Also</span></span>  
 <span data-ttu-id="84bb9-162">[Crea InfoSource](create-infosource.md) </span><span class="sxs-lookup"><span data-stu-id="84bb9-162">[Create InfoSource](create-infosource.md) </span></span>  
 [<span data-ttu-id="84bb9-163">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="84bb9-163">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
