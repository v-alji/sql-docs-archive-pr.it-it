---
title: Editor destinazione file non elaborato (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledestinationconnectionmanager.f1
ms.assetid: a0ec9643-3b44-4467-b855-f45ae4794f7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a693591921a5669eb9bc8160f0be076ab4d6869b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713272"
---
# <a name="raw-file-destination-editor-connection-manager-page"></a><span data-ttu-id="00f5f-102">Editor destinazione file non elaborato (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="00f5f-102">Raw File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="00f5f-103">Utilizzare l'Editor destinazione file non elaborato per configurare la destinazione file non elaborato in modo da scrivere dati non elaborati in un file.</span><span class="sxs-lookup"><span data-stu-id="00f5f-103">Use the Raw File Destination Editor to configure the Raw File destination to write raw data to a file.</span></span>  
  
 <span data-ttu-id="00f5f-104">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="00f5f-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="00f5f-105">Aprire l'Editor destinazione file non elaborato</span><span class="sxs-lookup"><span data-stu-id="00f5f-105">Open the Raw File Destination Editor</span></span>](#open)  
  
-   [<span data-ttu-id="00f5f-106">Impostare le opzioni nella scheda Gestione connessione</span><span class="sxs-lookup"><span data-stu-id="00f5f-106">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="00f5f-107">Impostare le opzioni nella scheda Colonne</span><span class="sxs-lookup"><span data-stu-id="00f5f-107">Set options on the Columns tab</span></span>](#mapping)  
  
##  <a name="open-the-raw-file-destination-editor"></a><a name="open"></a> <span data-ttu-id="00f5f-108">Aprire l'Editor destinazione file non elaborato</span><span class="sxs-lookup"><span data-stu-id="00f5f-108">Open the Raw File Destination Editor</span></span>  
  
1.  <span data-ttu-id="00f5f-109">Aggiungere la destinazione file non elaborato in un pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00f5f-109">Add the Raw File destination to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="00f5f-110">Fare clic con il pulsante destro del mouse sul componente e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="00f5f-110">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a> <span data-ttu-id="00f5f-111">Impostare le opzioni nella scheda Gestione connessione</span><span class="sxs-lookup"><span data-stu-id="00f5f-111">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="00f5f-112">**Modalità di accesso**</span><span class="sxs-lookup"><span data-stu-id="00f5f-112">**Access mode**</span></span>  
 <span data-ttu-id="00f5f-113">Selezionare come il nome file viene specificato.</span><span class="sxs-lookup"><span data-stu-id="00f5f-113">Select how the file name is specified.</span></span> <span data-ttu-id="00f5f-114">Selezionare **Nome file** per immettere direttamente il nome file e il percorso o **Nome file da variabile** per specificare una variabile che contiene il nome file.</span><span class="sxs-lookup"><span data-stu-id="00f5f-114">Select **File name** to enter the file name and path directly, of **File name from variable** to specify a variable that contains the file name.</span></span>  
  
 <span data-ttu-id="00f5f-115">**Nome file** o **Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="00f5f-115">**File name** or **Variable name**</span></span>  
 <span data-ttu-id="00f5f-116">Immettere il nome e il percorso del file non elaborato o selezionare la variabile contenente il nome file.</span><span class="sxs-lookup"><span data-stu-id="00f5f-116">Enter the name and path of the raw file, or select the variable that contains the file name.</span></span>  
  
 <span data-ttu-id="00f5f-117">**Opzione scrittura**</span><span class="sxs-lookup"><span data-stu-id="00f5f-117">**Write option**</span></span>  
 <span data-ttu-id="00f5f-118">Selezionare il metodo utilizzato per creare e scrivere nel file.</span><span class="sxs-lookup"><span data-stu-id="00f5f-118">Select the method used to create and write to the file.</span></span>  
  
 <span data-ttu-id="00f5f-119">**Generare file non elaborato iniziale**</span><span class="sxs-lookup"><span data-stu-id="00f5f-119">**Generate initial raw file**</span></span>  
 <span data-ttu-id="00f5f-120">Fare clic sul pulsante per generare un file non elaborato vuoto contenente solo le colonne (file di soli metadati) senza dover eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="00f5f-120">Click the button to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="00f5f-121">Nel file sono contenute le colonne selezionate nella pagina **Colonne** di **Editor destinazione file non elaborato**.</span><span class="sxs-lookup"><span data-stu-id="00f5f-121">The file contains the columns that you selected on the **Columns** page of the **Raw File Destination Editor**.</span></span> <span data-ttu-id="00f5f-122">È possibile puntare l'origine file non elaborato a questo file di soli metadati.</span><span class="sxs-lookup"><span data-stu-id="00f5f-122">You can point the Raw File source to this metadata-only file.</span></span>  
  
 <span data-ttu-id="00f5f-123">Quando si fa clic su **Genera file non elaborato iniziale**, viene visualizzata una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="00f5f-123">When you click **Generate initial raw file**, a message box appears.</span></span> <span data-ttu-id="00f5f-124">Fare clic su **OK** per procedere con la creazione del file.</span><span class="sxs-lookup"><span data-stu-id="00f5f-124">Click **OK** to proceed with creating the file.</span></span> <span data-ttu-id="00f5f-125">Fare clic su **Annulla** per selezionare un elenco diverso di colonne nella pagina **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="00f5f-125">Click **Cancel** to select a different list of columns on the **Columns** page.</span></span>  
  
##  <a name="set-options-on-the-columns-tab"></a><a name="mapping"></a><span data-ttu-id="00f5f-126">Impostare le opzioni nella scheda colonne</span><span class="sxs-lookup"><span data-stu-id="00f5f-126">Set options on the Columns tab</span></span>  
 <span data-ttu-id="00f5f-127">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="00f5f-127">**Available Input Columns**</span></span>  
 <span data-ttu-id="00f5f-128">Selezionare uno o più colonne di input per scrivere nel file non elaborato.</span><span class="sxs-lookup"><span data-stu-id="00f5f-128">Select one or more input columns to write to the raw file.</span></span>  
  
 <span data-ttu-id="00f5f-129">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="00f5f-129">**Input Column**</span></span>  
 <span data-ttu-id="00f5f-130">Una colonna di input viene aggiunta automaticamente a questa tabella quando la si seleziona in **Colonne di input disponibili**o è possibile selezionare direttamente la colonna di input in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="00f5f-130">An input column is automatically added to this table when you select it under **Available Input Columns**, or you can select the input column directly in this table.</span></span>  
  
 <span data-ttu-id="00f5f-131">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="00f5f-131">**Output Alias**</span></span>  
 <span data-ttu-id="00f5f-132">Specificare un nome alternativo da utilizzare per la colonna di output.</span><span class="sxs-lookup"><span data-stu-id="00f5f-132">Specify an alternate name to use for the output column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00f5f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00f5f-133">See Also</span></span>  
 [<span data-ttu-id="00f5f-134">Destinazione file non elaborato</span><span class="sxs-lookup"><span data-stu-id="00f5f-134">Raw File Destination</span></span>](data-flow/raw-file-destination.md)  
  
  
