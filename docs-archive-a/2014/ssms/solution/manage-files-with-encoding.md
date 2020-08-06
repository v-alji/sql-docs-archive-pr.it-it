---
title: Gestire file con codifica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- files [SQL Server Management Studio]
- encoding [SQL Server Management Studio]
- files [SQL Server Management Studio], encoding
ms.assetid: 919544c9-59f0-4cc6-bb2a-f1ad671eb74b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9b0aaa123001fed3f6ad42ea9d642e4007e2640f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638205"
---
# <a name="manage-files-with-encoding"></a><span data-ttu-id="ced29-102">Gestione di file con codifica</span><span class="sxs-lookup"><span data-stu-id="ced29-102">Manage Files with Encoding</span></span>
  <span data-ttu-id="ced29-103">Per facilitare la visualizzazione del codice in una lingua e in una piattaforma particolari, è possibile associare a un file una particolare codifica dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="ced29-103">To facilitate the display of your code in a particular language and on a particular platform, you can associate a particular character encoding with a file.</span></span>  
  
## <a name="opening-files"></a><span data-ttu-id="ced29-104">Apertura di file</span><span class="sxs-lookup"><span data-stu-id="ced29-104">Opening Files</span></span>  
 <span data-ttu-id="ced29-105">È possibile scegliere l'editor da utilizzare per modificare il file.</span><span class="sxs-lookup"><span data-stu-id="ced29-105">You can choose the editor you want to use to edit the file.</span></span>  
  
#### <a name="to-open-a-file-with-a-specific-editor"></a><span data-ttu-id="ced29-106">Per aprire un file con un editor specifico</span><span class="sxs-lookup"><span data-stu-id="ced29-106">To open a file with a specific editor</span></span>  
  
1.  <span data-ttu-id="ced29-107">Scegliere **Apri** dal menu **File**e quindi fare clic su **File**.</span><span class="sxs-lookup"><span data-stu-id="ced29-107">On the **File** menu, point to **Open**, and then click **File**.</span></span>  
  
2.  <span data-ttu-id="ced29-108">Nella finestra di dialogo **Apri file** selezionare il nome del file.</span><span class="sxs-lookup"><span data-stu-id="ced29-108">In the **Open File** dialog box, select the file name.</span></span>  
  
3.  <span data-ttu-id="ced29-109">Fare clic sulla freccia accanto al pulsante **Apri** e quindi scegliere**Apri con** dal menu visualizzato.</span><span class="sxs-lookup"><span data-stu-id="ced29-109">Click the arrow next to the **Open** button, and then click**Open With** from the menu that appears.</span></span>  
  
4.  <span data-ttu-id="ced29-110">Selezionare un editor dall'elenco **Selezionare un programma dall'elenco** e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="ced29-110">In the **Select a program to open** list, select an editor, and then click **Open**.</span></span> <span data-ttu-id="ced29-111">Per aprire il file con una particolare codifica, selezionare un editor che supporti questa funzionalità, ad esempio Editor di query SQL con codifica o Editor XML con codifica.</span><span class="sxs-lookup"><span data-stu-id="ced29-111">To open the file with a particular encoding, select an editor with encoding support, such as SQL Query Editor with Encoding or XML Editor with Encoding.</span></span>  
  
## <a name="saving-files"></a><span data-ttu-id="ced29-112">Salvataggio di file</span><span class="sxs-lookup"><span data-stu-id="ced29-112">Saving Files</span></span>  
 <span data-ttu-id="ced29-113">È inoltre possibile salvare il codice con una codifica Unicode o una tabella codici diversa per supportare diverse lingue, ad esempio quelle dell'Europa occidentale o orientale.</span><span class="sxs-lookup"><span data-stu-id="ced29-113">You can also save your code with a Unicode encoding or a different code page to support various languages, such as Western European or Eastern European.</span></span> <span data-ttu-id="ced29-114">Per facilitare la visualizzazione del codice nella lingua scelta, è possibile associare a un file una codifica dei caratteri e un tipo di terminazione riga particolari per supportare un dato sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ced29-114">You can associate a particular character encoding with a file to facilitate the display of your code in that language, as well as a line-ending type to support a particular operating system.</span></span> <span data-ttu-id="ced29-115">Alcuni caratteri, se utilizzati nei nomi di file, possono essere salvati solo con codifica Unicode.</span><span class="sxs-lookup"><span data-stu-id="ced29-115">Also, some characters, when used in file names, cannot be saved unless they are saved with Unicode encoding.</span></span>  
  
#### <a name="to-save-a-file-with-a-different-encoding-or-line-ending-type"></a><span data-ttu-id="ced29-116">Per salvare un file con una codifica o un tipo di terminazione riga diversi</span><span class="sxs-lookup"><span data-stu-id="ced29-116">To save a file with a different encoding or line ending type</span></span>  
  
1.  <span data-ttu-id="ced29-117">Scegliere **Apri** dal menu **Salva \<filename> File**.</span><span class="sxs-lookup"><span data-stu-id="ced29-117">On the **File** menu, click **Save \<filename> As**.</span></span>  
  
2.  <span data-ttu-id="ced29-118">Nella finestra di dialogo **Salva file con nome** espandere il pulsante **Salva** e quindi fare clic su **Salva con codifica**.</span><span class="sxs-lookup"><span data-stu-id="ced29-118">In the **Save File As** dialog, expand the **Save** button, and then click **Save with Encoding**.</span></span>  
  
3.  <span data-ttu-id="ced29-119">Nella finestra di dialogo **Opzioni di salvataggio avanzate** selezionare la codifica desiderata dall'elenco **Codifica** .</span><span class="sxs-lookup"><span data-stu-id="ced29-119">In the **Advanced Save Options** dialog box, select the encoding you want from the **Encoding** list.</span></span>  
  
4.  <span data-ttu-id="ced29-120">Dall'elenco **Terminazioni riga**selezionare il tipo di terminazione riga desiderato.</span><span class="sxs-lookup"><span data-stu-id="ced29-120">From the **Line Endings**list, select the type of line ending you want.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ced29-121">Se il file viene salvato con codifica Unicode, è necessario archiviarlo in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe come file binario in quanto Visual SourceSafe non supporta l'unione, il confronto e la visualizzazione delle differenze tra i file salvati come Unicode.</span><span class="sxs-lookup"><span data-stu-id="ced29-121">If you save your file your file with Unicode encoding, the file should be checked into [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual SourceSafe as a binary file because Visual SourceSafe does not support merging, comparing, and showing differences between files that are saved as Unicode.</span></span>  
  
 <span data-ttu-id="ced29-122">Se si utilizza Visual SourceSafe per archiviare i file con ANSI, UTF8 o Unicode, tenere presenti le limitazioni seguenti per ognuno di essi:</span><span class="sxs-lookup"><span data-stu-id="ced29-122">If you are using Visual SourceSafe to store files with ANSI, UTF8, or Unicode, be aware of the following limitations for each:</span></span>  
  
-   <span data-ttu-id="ced29-123">Nei file ANSI sono ammessi solo i caratteri supportati nella tabella codici corrente, con conseguenti limitazioni per l'uso internazionale.</span><span class="sxs-lookup"><span data-stu-id="ced29-123">ANSI files allow only characters that are supported in the current code page, which limits international use.</span></span>  
  
-   <span data-ttu-id="ced29-124">Nei file Unicode non è possibile utilizzare funzionalità di estrazione condivisa, controllo delle differenze o di unione in quanto questi file sono gestiti come file binari.</span><span class="sxs-lookup"><span data-stu-id="ced29-124">Unicode files cannot use shared checkout, difference checking, or merging functionality because they are handled as binary files.</span></span> <span data-ttu-id="ced29-125">È possibile utilizzare questo formato nei file internazionali.</span><span class="sxs-lookup"><span data-stu-id="ced29-125">You can use this format in international files.</span></span>  
  
-   <span data-ttu-id="ced29-126">Non è possibile utilizzare in sicurezza file UTF8 con Visual SourceSafe perché durante l'archiviazione, l'estrazione, il controllo delle differenze e l'unione vengono apportate modifiche che causano problemi per gli editor di questo tipo di file.</span><span class="sxs-lookup"><span data-stu-id="ced29-126">UTF8 files do not work safely with Visual SourceSafe because changes that cause problems for UTF8 file editors are made during check in, check out, difference checking, and merging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced29-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ced29-127">See Also</span></span>  
 <span data-ttu-id="ced29-128">[File per la gestione di soluzioni e progetti](files-that-manage-solutions-and-projects.md) </span><span class="sxs-lookup"><span data-stu-id="ced29-128">[Files That Manage Solutions and Projects](files-that-manage-solutions-and-projects.md) </span></span>  
 [<span data-ttu-id="ced29-129">Associazione di estensioni di file a un editor di codice</span><span class="sxs-lookup"><span data-stu-id="ced29-129">Associate File Extensions to a Code Editor</span></span>](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md)  
  
  
