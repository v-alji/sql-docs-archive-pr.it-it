---
title: Finestra di dialogo Editor trasformazione pulizia DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssdqs.designer.cleansing.f1
- SQL12.SSDQS.DESIGNER.DQCONNECTION.F1
ms.assetid: 07e79641-71ee-45d0-a9ba-ed6f9f68f333
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e97cd138bb17ce3cfe476496e5bc576875728224
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624270"
---
# <a name="dqs-cleansing-transformation-editor-dialog-box"></a><span data-ttu-id="85544-102">Finestra di dialogo Editor trasformazione DQS Cleansing</span><span class="sxs-lookup"><span data-stu-id="85544-102">DQS Cleansing Transformation Editor Dialog Box</span></span>
  <span data-ttu-id="85544-103">Usare la finestra di dialogo **Editor trasformazione DQS Cleansing** per correggere dati usando Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="85544-103">Use the **DQS Cleansing Transformation Editor** dialog box to correct data using Data Quality Services (DQS).</span></span> <span data-ttu-id="85544-104">Per altre informazioni, vedere [Concetti di Data Quality Services](../../2014/data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="85544-104">For more information, see [Data Quality Services Concepts](../../2014/data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="85544-105">Per altre informazioni sulla trasformazione, vedere [Trasformazione DQS Cleansing](data-flow/transformations/dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="85544-105">To learn more about the transformation, see [DQS Cleansing Transformation](data-flow/transformations/dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="85544-106">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="85544-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="85544-107">Aprire Editor trasformazione DQS Cleansing</span><span class="sxs-lookup"><span data-stu-id="85544-107">Open the DQS Cleansing Transformation Editor</span></span>](#open)  
  
-   [<span data-ttu-id="85544-108">Impostare le opzioni nella scheda Gestione connessione</span><span class="sxs-lookup"><span data-stu-id="85544-108">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="85544-109">Impostare le opzioni nella scheda Mapping</span><span class="sxs-lookup"><span data-stu-id="85544-109">Set options on the Mapping tab</span></span>](#mapping)  
  
-   [<span data-ttu-id="85544-110">Impostare le opzioni nella scheda Avanzate</span><span class="sxs-lookup"><span data-stu-id="85544-110">Set options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="85544-111">Impostare le opzioni nella finestra di dialogo Gestione connessione DQS Cleansing</span><span class="sxs-lookup"><span data-stu-id="85544-111">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>](#manager)  
  
##  <a name="open-the-dqs-cleansing-transformation-editor"></a><a name="open"></a><span data-ttu-id="85544-112">Aprire l'Editor trasformazione DQS cleaning</span><span class="sxs-lookup"><span data-stu-id="85544-112">Open the DQS Cleansing Transformation Editor</span></span>  
  
1.  <span data-ttu-id="85544-113">Aggiungere la trasformazione DQS Cleansing al pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85544-113">Add the DQS Cleansing Transformation to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="85544-114">Fare clic con il pulsante destro del mouse sul componente e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="85544-114">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a> <span data-ttu-id="85544-115">Impostare le opzioni nella scheda Gestione connessione</span><span class="sxs-lookup"><span data-stu-id="85544-115">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="85544-116">**Gestione connessione Data Quality**</span><span class="sxs-lookup"><span data-stu-id="85544-116">**Data quality connection manager**</span></span>  
 <span data-ttu-id="85544-117">Consente di selezionare una gestione connessione DQS esistente nell'elenco oppure di crearne una facendo clic sul pulsante **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="85544-117">Select an existing DQS connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="85544-118">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="85544-118">**New**</span></span>  
 <span data-ttu-id="85544-119">Consente di creare una nuova gestione connessione usando la finestra di dialogo **Gestione connessione DQS Cleansing** .</span><span class="sxs-lookup"><span data-stu-id="85544-119">Create a new connection manager by using the **DQS Cleansing Connection Manager** dialog box.</span></span> <span data-ttu-id="85544-120">Per altre informazioni, vedere [Impostare le opzioni nella finestra di dialogo Gestione connessione DQS Cleansing](#manager).</span><span class="sxs-lookup"><span data-stu-id="85544-120">See [Set the options in the DQS Cleansing Connection Manager dialog box](#manager)</span></span>  
  
 <span data-ttu-id="85544-121">**Data Quality Knowledge Base**</span><span class="sxs-lookup"><span data-stu-id="85544-121">**Data Quality Knowledge Base**</span></span>  
 <span data-ttu-id="85544-122">Selezionare una Knowledge Base DQS esistente per l'origine dati connessa.</span><span class="sxs-lookup"><span data-stu-id="85544-122">Select an existing DQS knowledge base for the connected data source.</span></span> <span data-ttu-id="85544-123">Per altre informazioni sulla Knowledge Base DQS, vedere [Knowledge Base e domini DQS](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="85544-123">For more information about the DQS knowledge base, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="85544-124">**Crittografa connessione**</span><span class="sxs-lookup"><span data-stu-id="85544-124">**Encrypt connection**</span></span>  
 <span data-ttu-id="85544-125">consente di specificare se crittografare la connessione, per crittografare il trasferimento dei dati tra il server DQS e [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="85544-125">specify whether to encrypt the connection, in order to encrypt the data transfer between the DQS Server and [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="85544-126">**Domini disponibili**</span><span class="sxs-lookup"><span data-stu-id="85544-126">**Available domains**</span></span>  
 <span data-ttu-id="85544-127">Consente di elencare i domini disponibili per la Knowledge Base selezionata.</span><span class="sxs-lookup"><span data-stu-id="85544-127">Lists the available domains for the selected knowledge base.</span></span> <span data-ttu-id="85544-128">Esistono due tipi di domini, cioè singoli e composti. In questi ultimi sono contenuti due o più domini singoli.</span><span class="sxs-lookup"><span data-stu-id="85544-128">There are two types of domains: single domains, and composite domains that contain two or more single domains.</span></span>  
  
 <span data-ttu-id="85544-129">Per informazioni su come eseguire il mapping di colonne a domini composti, vedere [Eseguire il mapping delle colonne ai domini compositi](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="85544-129">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="85544-130">Per altre informazioni sui domini, vedere [Knowledge Base e domini DQS](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="85544-130">For more information about domains, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="85544-131">**Configura output errori**</span><span class="sxs-lookup"><span data-stu-id="85544-131">**Configure Error Output**</span></span>  
 <span data-ttu-id="85544-132">Consente di specificare come gestire gli errori a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="85544-132">Specify how to handle row-level errors.</span></span> <span data-ttu-id="85544-133">Possono verificarsi degli errori quando la trasformazione corregge i dati dall'origine dati connessa, a causa di valori di dati o vincoli di convalida non previsti.</span><span class="sxs-lookup"><span data-stu-id="85544-133">Errors can occur when the transformation corrects data from the connected data source, due to unexpected data values or validation constraints.</span></span>  
  
 <span data-ttu-id="85544-134">Di seguito sono riportati i valori validi:</span><span class="sxs-lookup"><span data-stu-id="85544-134">The following are the valid values:</span></span>  
  
-   <span data-ttu-id="85544-135">**Interrompi componente**: indica che la trasformazione ha esito negativo e che i dati di input non vengono inseriti nel database Data Quality Services.</span><span class="sxs-lookup"><span data-stu-id="85544-135">**Fail Component**, which indicates that the transformation fails and the input data is not inserted into the Data Quality Services database.</span></span> <span data-ttu-id="85544-136">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="85544-136">This is the default value.</span></span>  
  
-   <span data-ttu-id="85544-137">**Reindirizza riga**: indica che i dati di input non vengono inseriti nel database di Data Quality Services e che vengono reindirizzati all'output degli errori.</span><span class="sxs-lookup"><span data-stu-id="85544-137">**Redirect Row**, which indicates that the input data is not inserted into the Data Quality Services database and is redirected to the error output.</span></span>  
  
##  <a name="set-options-on-the-mapping-tab"></a><a name="mapping"></a><span data-ttu-id="85544-138">Impostare le opzioni nella scheda mapping</span><span class="sxs-lookup"><span data-stu-id="85544-138">Set options on the Mapping tab</span></span>  
 <span data-ttu-id="85544-139">Per informazioni su come eseguire il mapping di colonne a domini composti, vedere [Eseguire il mapping delle colonne ai domini compositi](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="85544-139">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="85544-140">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="85544-140">**Available Input Columns**</span></span>  
 <span data-ttu-id="85544-141">Elenca le colonne dall'origine dati connessa.</span><span class="sxs-lookup"><span data-stu-id="85544-141">Lists the columns from the connected data source.</span></span> <span data-ttu-id="85544-142">Selezionare una o più colonne contenenti i dati che si desidera correggere.</span><span class="sxs-lookup"><span data-stu-id="85544-142">Select one or more columns that contain data that you want to correct.</span></span>  
  
 <span data-ttu-id="85544-143">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="85544-143">**Input Column**</span></span>  
 <span data-ttu-id="85544-144">Elenca una colonna di input selezionata nell'area **Colonne di input disponibili** .</span><span class="sxs-lookup"><span data-stu-id="85544-144">Lists an input column that you selected in the **Available Input Columns** area.</span></span>  
  
 <span data-ttu-id="85544-145">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="85544-145">**Domain**</span></span>  
 <span data-ttu-id="85544-146">Consente di selezionare un dominio di cui si desidera eseguire il mapping alle colonne di input.</span><span class="sxs-lookup"><span data-stu-id="85544-146">Select a domain to map to the input column.</span></span>  
  
 <span data-ttu-id="85544-147">**Alias di origine**</span><span class="sxs-lookup"><span data-stu-id="85544-147">**Source Alias**</span></span>  
 <span data-ttu-id="85544-148">Consente di visualizzare la colonna di origine contenente il valore della colonna originale.</span><span class="sxs-lookup"><span data-stu-id="85544-148">Lists the source column that contains the original column value.</span></span>  
  
 <span data-ttu-id="85544-149">Fare clic all'interno del campo per modificare il nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="85544-149">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="85544-150">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="85544-150">**Output Alias**</span></span>  
 <span data-ttu-id="85544-151">Consente di visualizzare la colonna che viene restituita da **Trasformazione DQS Cleansing**.</span><span class="sxs-lookup"><span data-stu-id="85544-151">Lists the column that is outputted by the **DQS Cleansing Transformation**.</span></span> <span data-ttu-id="85544-152">La colonna contiene il valore della colonna originale o il valore corretto.</span><span class="sxs-lookup"><span data-stu-id="85544-152">The column contains the original column value or the corrected value.</span></span>  
  
 <span data-ttu-id="85544-153">Fare clic all'interno del campo per modificare il nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="85544-153">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="85544-154">**Alias di stato**</span><span class="sxs-lookup"><span data-stu-id="85544-154">**Status Alias**</span></span>  
 <span data-ttu-id="85544-155">Consente di visualizzare la colonna contenente le informazioni sullo stato per i dati corretti.</span><span class="sxs-lookup"><span data-stu-id="85544-155">Lists the column that contains status information for the corrected data.</span></span> <span data-ttu-id="85544-156">Fare clic all'interno del campo per modificare il nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="85544-156">Click in the field to modify the column name.</span></span>  
  
##  <a name="set-options-on-the-advanced-tab"></a><a name="advanced"></a><span data-ttu-id="85544-157">Impostare le opzioni nella scheda Avanzate</span><span class="sxs-lookup"><span data-stu-id="85544-157">Set options on the Advanced tab</span></span>  
 <span data-ttu-id="85544-158">**Standardizzare output**</span><span class="sxs-lookup"><span data-stu-id="85544-158">**Standardize output**</span></span>  
 <span data-ttu-id="85544-159">Consente di specificare se restituire i dati nel formato standardizzato basato sul formato di output definito per i domini.</span><span class="sxs-lookup"><span data-stu-id="85544-159">Indicate whether to output the data in the standardized format based on the output format defined for domains.</span></span> <span data-ttu-id="85544-160">Per altre informazioni sul formato standardizzato, vedere [Pulizia dei dati](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="85544-160">For more information about standardized format, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="85544-161">**Fiducia**</span><span class="sxs-lookup"><span data-stu-id="85544-161">**Confidence**</span></span>  
 <span data-ttu-id="85544-162">Consente di specificare se includere il livello di confidenza per i dati corretti.</span><span class="sxs-lookup"><span data-stu-id="85544-162">Indicate whether to include the confidence level for corrected data.</span></span> <span data-ttu-id="85544-163">Il livello di confidenza indica il livello di certezza di DQS in relazione a correzione o suggerimento.</span><span class="sxs-lookup"><span data-stu-id="85544-163">The confidence level indicates the extend of certainty of DQS for the correction or suggestion.</span></span> <span data-ttu-id="85544-164">Per altre informazioni sui livelli di confidenza, vedere [Pulizia dei dati](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="85544-164">For more information about confidence levels, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="85544-165">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="85544-165">**Reason**</span></span>  
 <span data-ttu-id="85544-166">Consente di specificare se includere il motivo per la correzione dei dati.</span><span class="sxs-lookup"><span data-stu-id="85544-166">Indicate whether to include the reason for the data correction.</span></span>  
  
 <span data-ttu-id="85544-167">**Dati accodati**</span><span class="sxs-lookup"><span data-stu-id="85544-167">**Appended Data**</span></span>  
 <span data-ttu-id="85544-168">Consente di specificare se restituire dati aggiuntivi ricevuti da un provider di dati di riferimento esistente.</span><span class="sxs-lookup"><span data-stu-id="85544-168">Indicate whether to output additional data that is received from an existing reference data provider.</span></span> <span data-ttu-id="85544-169">Per altre informazioni, vedere [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="85544-169">For more information, see [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span></span>  
  
 <span data-ttu-id="85544-170">**Schema dati accodati**</span><span class="sxs-lookup"><span data-stu-id="85544-170">**Appended Data Schema**</span></span>  
 <span data-ttu-id="85544-171">Consente di specificare se restituire lo schema dati.</span><span class="sxs-lookup"><span data-stu-id="85544-171">Indicate whether to output the data schema.</span></span> <span data-ttu-id="85544-172">Per ulteriori informazioni, vedere [la pagina relativa alla connessione di un dominio o un dominio composito ai dati di riferimento](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span><span class="sxs-lookup"><span data-stu-id="85544-172">For more information, see [Attach a Domain or Composite Domain to Reference Data](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span></span>  
  
##  <a name="set-the-options-in-the-dqs-cleansing-connection-manager-dialog-box"></a><a name="manager"></a><span data-ttu-id="85544-173">Impostare le opzioni nella finestra di dialogo Gestione connessione DQS cleaning</span><span class="sxs-lookup"><span data-stu-id="85544-173">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>  
 <span data-ttu-id="85544-174">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="85544-174">**Server name**</span></span>  
 <span data-ttu-id="85544-175">Selezionare o digitare il nome del server DQS a cui si desidera connettersi.</span><span class="sxs-lookup"><span data-stu-id="85544-175">Select or type the name of the DQS server that you want to connect to.</span></span> <span data-ttu-id="85544-176">Per altre informazioni sul server, vedere [Amministrazione DQS](../../2014/data-quality-services/dqs-administration.md).</span><span class="sxs-lookup"><span data-stu-id="85544-176">For more information about the server, see [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span></span>  
  
 <span data-ttu-id="85544-177">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="85544-177">**Test Connection**</span></span>  
 <span data-ttu-id="85544-178">Fare clic per verificare che la connessione specificata sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="85544-178">Click to confirm that the connection that you specified is viable.</span></span>  
  
 <span data-ttu-id="85544-179">È anche possibile aprire la finestra di dialogo **Gestione connessione DQS Cleansing** dall'area relativa alle connessioni eseguendo queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="85544-179">You can also open the **DQS Cleansing Connection Manager** dialog box from the connections area, by doing the following:</span></span>  
  
1.  <span data-ttu-id="85544-180">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], aprire un progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="85544-180">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or create a new one.</span></span>  
  
2.  <span data-ttu-id="85544-181">Fare clic con il pulsante destro sull'area relativa alle connessioni, scegliere **Nuova connessione**e quindi fare clic su **DQS**.</span><span class="sxs-lookup"><span data-stu-id="85544-181">Right-click in the connections area, click **New Connection**, and then click **DQS**.</span></span>  
  
3.  <span data-ttu-id="85544-182">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="85544-182">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85544-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85544-183">See Also</span></span>  
 [<span data-ttu-id="85544-184">Applicazione delle regole relative alla qualità dei dati all'origine dati</span><span class="sxs-lookup"><span data-stu-id="85544-184">Apply Data Quality Rules to Data Source</span></span>](data-flow/transformations/apply-data-quality-rules-to-data-source.md)  
  
  
