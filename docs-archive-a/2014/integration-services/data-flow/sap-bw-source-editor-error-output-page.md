---
title: Editor origine SAP BW (pagina Output degli errori) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b6e23b0c-949a-46d1-8424-4dc3d9035e79
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1a4ad2d02d3f5ec5c1a786019e18fa01665fdc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712215"
---
# <a name="sap-bw-source-editor-error-output-page"></a><span data-ttu-id="cffdd-102">Editor origine SAP BW (pagina Output degli errori)</span><span class="sxs-lookup"><span data-stu-id="cffdd-102">SAP BW Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="cffdd-103">Utilizzare la pagina **Output degli errori** della finestra di dialogo **Editor origine SAP BW** per selezionare le opzioni di gestione degli errori e impostare le proprietà delle colonne di output degli errori.</span><span class="sxs-lookup"><span data-stu-id="cffdd-103">Use the **Error Output** page of the **SAP BW Source Editor** to select error handling options and to set properties on error output columns.</span></span>  
  
 <span data-ttu-id="cffdd-104">Per altre informazioni sul componente di origine SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vedere [Origine SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="cffdd-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cffdd-105">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="cffdd-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="cffdd-106">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="cffdd-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cffdd-107">L'estrazione di dati da SAP Netweaver BW richiede licenze SAP aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="cffdd-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="cffdd-108">Contattare SAP per verificare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="cffdd-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="cffdd-109">**Per aprire la pagina Output errori**</span><span class="sxs-lookup"><span data-stu-id="cffdd-109">**To open the Error Output page**</span></span>  
  
1.  <span data-ttu-id="cffdd-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene l'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="cffdd-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="cffdd-111">Nella scheda **Flusso di dati** fare doppio clic sull'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="cffdd-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="cffdd-112">Nell' **Editor origine SAP BW**fare clic su **Output degli errori** per aprire la pagina **Output degli errori** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="cffdd-112">In the **SAP BW Source Editor**, click **Error Output** to open the **Error Output** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cffdd-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cffdd-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cffdd-114">Se non si conoscono tutti i valori richiesti per configurare l'origine, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="cffdd-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="cffdd-115">**Input o output**</span><span class="sxs-lookup"><span data-stu-id="cffdd-115">**Input or Output**</span></span>  
 <span data-ttu-id="cffdd-116">Consente di visualizzare il nome dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="cffdd-116">View the name of the data source.</span></span>  
  
 <span data-ttu-id="cffdd-117">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="cffdd-117">**Column**</span></span>  
 <span data-ttu-id="cffdd-118">Visualizzare le colonne esterne (di origine) selezionate nella pagina **Colonne** della finestra di dialogo **Editor origine SAP BW** .</span><span class="sxs-lookup"><span data-stu-id="cffdd-118">View the external (source) columns that you selected on the **Columns** page of the **SAP BW Source Editor** dialog box.</span></span> <span data-ttu-id="cffdd-119">Per altre informazioni su questa finestra di dialogo, vedere [Editor origine SAP BW &#40;pagina Colonne&#41;](sap-bw-source-editor-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="cffdd-119">For more information about this dialog box, see [SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md).</span></span>  
  
 <span data-ttu-id="cffdd-120">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="cffdd-120">**Error**</span></span>  
 <span data-ttu-id="cffdd-121">Specificare quale operazione dovrà essere eseguita dal componente di origine SAP BW in caso di errore: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="cffdd-121">Specify what the SAP BW source component should do when there is an error: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="cffdd-122">**Troncamento**</span><span class="sxs-lookup"><span data-stu-id="cffdd-122">**Truncation**</span></span>  
 <span data-ttu-id="cffdd-123">Specificare quale operazione dovrà essere eseguita dal componente di origine SAP BW in caso di troncamento: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="cffdd-123">Specify what the SAP BW source component should do when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="cffdd-124">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cffdd-124">**Description**</span></span>  
 <span data-ttu-id="cffdd-125">Consente di visualizzare la descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="cffdd-125">View the description of the error.</span></span>  
  
 <span data-ttu-id="cffdd-126">**Imposta questo valore nelle celle selezionate**</span><span class="sxs-lookup"><span data-stu-id="cffdd-126">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="cffdd-127">Specificare l'azione che dovrà essere eseguita dal componente di origine SAP BW su tutte le celle selezionate in caso di errore o troncamento: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="cffdd-127">Specify what the SAP BW source component should do to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="cffdd-128">**Applica**</span><span class="sxs-lookup"><span data-stu-id="cffdd-128">**Apply**</span></span>  
 <span data-ttu-id="cffdd-129">Consente di applicare l'opzione di gestione degli errori alle celle selezionate.</span><span class="sxs-lookup"><span data-stu-id="cffdd-129">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cffdd-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cffdd-130">See Also</span></span>  
 <span data-ttu-id="cffdd-131">[Editor origine SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="cffdd-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="cffdd-132">[Editor origine SAP BW &#40;pagina Colonne&#41;](sap-bw-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="cffdd-132">[SAP BW Source Editor &#40;Columns Page&#41;](sap-bw-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="cffdd-133">[Editor origine SAP BW &#40;pagina Avanzate&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="cffdd-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="cffdd-134">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="cffdd-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
