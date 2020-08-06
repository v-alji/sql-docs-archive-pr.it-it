---
title: Editor destinazione file flat (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledestadapter.connection.f1
helpviewer_keywords:
- Flat File Destination Editor
ms.assetid: b01571fa-bc19-4742-8eed-ac163172a919
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6997b72851c2b7bfc56445e6ddb01cfe6e9b04cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624856"
---
# <a name="flat-file-destination-editor-connection-manager-page"></a><span data-ttu-id="bb3d4-102">Editor destinazione file flat (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="bb3d4-102">Flat File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="bb3d4-103">Utilizzare la pagina **Gestione connessione** della finestra di dialogo **Editor destinazione file flat** per selezionare la connessione file flat per la destinazione e specificare se eseguire la sovrascrittura o l'accodamento al file di destinazione esistente.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-103">Use the **Connection Manager** page of the **Flat File Destination Editor** dialog box to select the flat file connection for the destination, and to specify whether to overwrite or append to the existing destination file.</span></span> <span data-ttu-id="bb3d4-104">La destinazione file flat scrive dati in un file di testo</span><span class="sxs-lookup"><span data-stu-id="bb3d4-104">The flat file destination writes data to a text file.</span></span> <span data-ttu-id="bb3d4-105">che può essere in formato delimitato, a larghezza fissa o misto, a larghezza fissa con delimitatori di riga oppure non allineato a destra.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-105">This text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="bb3d4-106">Per ulteriori informazioni sulla destinazione file flat, vedere [Flat File Destination](data-flow/flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="bb3d4-106">To learn more about the Flat File destination, see [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bb3d4-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bb3d4-107">Options</span></span>  
 <span data-ttu-id="bb3d4-108">**Gestione connessione file flat**</span><span class="sxs-lookup"><span data-stu-id="bb3d4-108">**Flat File connection manager**</span></span>  
 <span data-ttu-id="bb3d4-109">Usare la casella di riepilogo per selezionare una gestione connessione esistente oppure fare clic su **Nuova**per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-109">Select an existing connection manager by using the list box, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="bb3d4-110">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="bb3d4-110">**New**</span></span>  
 <span data-ttu-id="bb3d4-111">Consente di creare una nuova connessione utilizzando le finestre di dialogo **Formato file flat** e **Editor gestione connessione file flat** .</span><span class="sxs-lookup"><span data-stu-id="bb3d4-111">Create a new connection by using the **Flat File Format** and **Flat File Connection Manager Editor** dialog boxes.</span></span>  
  
 <span data-ttu-id="bb3d4-112">Oltre ai formati file flat standard di larghezza delimitata e fissa e non allineati a destra, la finestra di dialogo **Formato file flat** dispone di una quarta opzione, **Larghezza fissa con delimitatori di riga**.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-112">In addition to the standard flat file formats of delimited, fixed width, and ragged right, the **Flat File Format** dialog box has a fourth option, **Fixed width with row delimiters**.</span></span> <span data-ttu-id="bb3d4-113">Questa opzione rappresenta un caso speciale del formato non allineato a destra nel quale [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] aggiunge una colonna fittizia come colonna finale dei dati.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-113">This option represents a special case of the ragged-right format in which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] adds a dummy column as the final column of data.</span></span> <span data-ttu-id="bb3d4-114">Questa colonna fittizia assicura che la colonna finale abbia una larghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-114">This dummy column ensures that the final column has a fixed width.</span></span>  
  
 <span data-ttu-id="bb3d4-115">L'opzione **Larghezza fissa con delimitatori di riga** non è disponibile in **Editor gestione connessione file flat**.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-115">The **Fixed width with row delimiters** option is not available in the **Flat File Connection Manager Editor**.</span></span> <span data-ttu-id="bb3d4-116">Se necessario, è possibile emulare questa opzione nell'editor.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-116">If necessary, you can emulate this option in the editor.</span></span> <span data-ttu-id="bb3d4-117">Per emulare questa opzione, nella pagina **Generale** dell' **Editor gestione connessione file flat**selezionare **Non allineato a destra**in **Formato**.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-117">To emulate this option, on the **General** page of the **Flat File Connection Manager Editor**, for **Format**, select **Ragged right**.</span></span> <span data-ttu-id="bb3d4-118">Quindi, nella pagina **Avanzate** dell'editor aggiungere una nuova colonna fittizia come colonna finale dei dati.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-118">Then on the **Advanced** page of the editor, add a new dummy column as the final column of data.</span></span>  
  
 <span data-ttu-id="bb3d4-119">**Sovrascrivi dati nel file**</span><span class="sxs-lookup"><span data-stu-id="bb3d4-119">**Overwrite data in the file**</span></span>  
 <span data-ttu-id="bb3d4-120">Consente di indicare se sovrascrivere un file esistente o accodare i dati al file.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-120">Indicate whether to overwrite an existing file, or to append data to it.</span></span>  
  
 <span data-ttu-id="bb3d4-121">**Intestazione**</span><span class="sxs-lookup"><span data-stu-id="bb3d4-121">**Header**</span></span>  
 <span data-ttu-id="bb3d4-122">Consente di digitare un blocco di testo da inserire nel file prima che i dati vengano scritti.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-122">Type a block of text to insert into the file before any data is written.</span></span> <span data-ttu-id="bb3d4-123">Utilizzare questa opzione per includere informazioni aggiuntive, quali le intestazioni delle colonne.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-123">Use this option to include additional information, such as column headings.</span></span>  
  
 <span data-ttu-id="bb3d4-124">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="bb3d4-124">**Preview**</span></span>  
 <span data-ttu-id="bb3d4-125">Consente di visualizzare in anteprima i risultati nella finestra di dialogo **Vista dati** .</span><span class="sxs-lookup"><span data-stu-id="bb3d4-125">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="bb3d4-126">L'anteprima supporta la visualizzazione di un massimo di 200 righe.</span><span class="sxs-lookup"><span data-stu-id="bb3d4-126">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3d4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb3d4-127">See Also</span></span>  
 <span data-ttu-id="bb3d4-128">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bb3d4-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="bb3d4-129">Editor destinazione file flat &#40;pagina Mapping&#41;</span><span class="sxs-lookup"><span data-stu-id="bb3d4-129">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/flat-file-destination-editor-mappings-page.md)  
  
  
