---
title: Editor destinazione file non elaborato (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledestinationcolumns.f1
ms.assetid: 37f61d0b-1269-42ee-94ab-011cbaac63e9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a89d8ca46805a23fd03465ed40428081499dccb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713275"
---
# <a name="raw-file-destination-editor-columns-page"></a><span data-ttu-id="bbde3-102">Editor destinazione file non elaborato (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="bbde3-102">Raw File Destination Editor (Columns Page)</span></span>
  <span data-ttu-id="bbde3-103">Utilizzare l'Editor destinazione file non elaborato per configurare la destinazione file non elaborato in modo da scrivere dati non elaborati in un file.</span><span class="sxs-lookup"><span data-stu-id="bbde3-103">Use the Raw File Destination Editor to configure the Raw File destination to write raw data to a file.</span></span>  
  
 <span data-ttu-id="bbde3-104">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="bbde3-104">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="bbde3-105">Aprire l'Editor destinazione file non elaborato</span><span class="sxs-lookup"><span data-stu-id="bbde3-105">Open the Raw File Destination Editor</span></span>](#open)  
  
-   [<span data-ttu-id="bbde3-106">Impostare le opzioni nella scheda Gestione connessione</span><span class="sxs-lookup"><span data-stu-id="bbde3-106">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="bbde3-107">Impostare le opzioni nella scheda Colonne</span><span class="sxs-lookup"><span data-stu-id="bbde3-107">Set options on the Columns tab</span></span>](#mapping)  
  
##  <a name="open-the-raw-file-destination-editor"></a><a name="open"></a> <span data-ttu-id="bbde3-108">Aprire l'Editor destinazione file non elaborato</span><span class="sxs-lookup"><span data-stu-id="bbde3-108">Open the Raw File Destination Editor</span></span>  
  
1.  <span data-ttu-id="bbde3-109">Aggiungere la destinazione file non elaborato in un pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbde3-109">Add the Raw File destination to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="bbde3-110">Fare clic con il pulsante destro del mouse sul componente e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="bbde3-110">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a> <span data-ttu-id="bbde3-111">Impostare le opzioni nella scheda Gestione connessione</span><span class="sxs-lookup"><span data-stu-id="bbde3-111">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="bbde3-112">**Modalità di accesso**</span><span class="sxs-lookup"><span data-stu-id="bbde3-112">**Access mode**</span></span>  
 <span data-ttu-id="bbde3-113">Selezionare come il nome file viene specificato.</span><span class="sxs-lookup"><span data-stu-id="bbde3-113">Select how the file name is specified.</span></span> <span data-ttu-id="bbde3-114">Selezionare **Nome file** per immettere direttamente il nome file e il percorso o **Nome file da variabile** per specificare una variabile che contiene il nome file.</span><span class="sxs-lookup"><span data-stu-id="bbde3-114">Select **File name** to enter the file name and path directly, of **File name from variable** to specify a variable that contains the file name.</span></span>  
  
 <span data-ttu-id="bbde3-115">**Nome file** o **Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="bbde3-115">**File name** or **Variable name**</span></span>  
 <span data-ttu-id="bbde3-116">Immettere il nome e il percorso del file non elaborato o selezionare la variabile contenente il nome file.</span><span class="sxs-lookup"><span data-stu-id="bbde3-116">Enter the name and path of the raw file, or select the variable that contains the file name.</span></span>  
  
 <span data-ttu-id="bbde3-117">**Opzione scrittura**</span><span class="sxs-lookup"><span data-stu-id="bbde3-117">**Write option**</span></span>  
 <span data-ttu-id="bbde3-118">Selezionare il metodo utilizzato per creare e scrivere nel file.</span><span class="sxs-lookup"><span data-stu-id="bbde3-118">Select the method used to create and write to the file.</span></span>  
  
 <span data-ttu-id="bbde3-119">**Generare file non elaborato iniziale**</span><span class="sxs-lookup"><span data-stu-id="bbde3-119">**Generate initial raw file**</span></span>  
 <span data-ttu-id="bbde3-120">Fare clic sul pulsante per generare un file non elaborato vuoto contenente solo le colonne (file di soli metadati) senza dover eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="bbde3-120">Click the button to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="bbde3-121">È possibile puntare l'origine file non elaborato al file di soli metadati.</span><span class="sxs-lookup"><span data-stu-id="bbde3-121">You can point the Raw File source to the metadata-only file.</span></span>  
  
 <span data-ttu-id="bbde3-122">Quando si fa clic sul pulsante, viene visualizzato un elenco delle colonne.</span><span class="sxs-lookup"><span data-stu-id="bbde3-122">When you click the button, a list of the columns appears.</span></span> <span data-ttu-id="bbde3-123">È possibile fare clic su Annulla e modificare le colonne o fare clic su OK per procedere con la creazione del file.</span><span class="sxs-lookup"><span data-stu-id="bbde3-123">You can click cancel and modify the columns or click OK to proceed with creating the file.</span></span>  
  
##  <a name="set-options-on-the-columns-tab"></a><a name="mapping"></a><span data-ttu-id="bbde3-124">Impostare le opzioni nella scheda colonne</span><span class="sxs-lookup"><span data-stu-id="bbde3-124">Set options on the Columns tab</span></span>  
 <span data-ttu-id="bbde3-125">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="bbde3-125">**Available Input Columns**</span></span>  
 <span data-ttu-id="bbde3-126">Selezionare uno o più colonne di input per scrivere nel file non elaborato.</span><span class="sxs-lookup"><span data-stu-id="bbde3-126">Select one or more input columns to write to the raw file.</span></span>  
  
 <span data-ttu-id="bbde3-127">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="bbde3-127">**Input Column**</span></span>  
 <span data-ttu-id="bbde3-128">Una colonna di input viene aggiunta automaticamente a questa tabella quando la si seleziona in **Colonne di input disponibili**o è possibile selezionare direttamente la colonna di input in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="bbde3-128">An input column is automatically added to this table when you select it under **Available Input Columns**, or you can select the input column directly in this table.</span></span>  
  
 <span data-ttu-id="bbde3-129">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="bbde3-129">**Output Alias**</span></span>  
 <span data-ttu-id="bbde3-130">Specificare un nome alternativo da utilizzare per la colonna di output.</span><span class="sxs-lookup"><span data-stu-id="bbde3-130">Specify an alternate name to use for the output column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbde3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbde3-131">See Also</span></span>  
 [<span data-ttu-id="bbde3-132">Destinazione file non elaborato</span><span class="sxs-lookup"><span data-stu-id="bbde3-132">Raw File Destination</span></span>](data-flow/raw-file-destination.md)  
  
  
