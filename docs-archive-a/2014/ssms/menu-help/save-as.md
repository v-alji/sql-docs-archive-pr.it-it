---
title: Salva con nome | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vs.saveas
helpviewer_keywords:
- Save As dialog box
ms.assetid: 61347757-f5a3-481d-8b05-1fed086629b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: e47d9c37371283fc6fba2754896d77b51d26cef0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638210"
---
# <a name="save-as"></a><span data-ttu-id="1599c-102">Save As</span><span class="sxs-lookup"><span data-stu-id="1599c-102">Save As</span></span>
  <span data-ttu-id="1599c-103">Utilizzare questa finestra di dialogo per salvare un'istanza dell'elemento corrente nel percorso e nel formato di file specificati.</span><span class="sxs-lookup"><span data-stu-id="1599c-103">Use this dialog box to save an instance of the current item at a specified location in a specified file format.</span></span> <span data-ttu-id="1599c-104">Per visualizzare questa finestra di dialogo, fare clic su **Salva** *\<file>* **con** nome nel menu **file** (dove *\<file>* è il nome dell'elemento corrente) oppure premere ALT + F, a nell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="1599c-104">To display this dialog box, click **Save** *\<file>* **As** on the **File** menu (where *\<file>* is the name of the current item), or press ALT+F, A in the Code Editor.</span></span>  
  
## <a name="central-panel"></a><span data-ttu-id="1599c-105">Pannello centrale</span><span class="sxs-lookup"><span data-stu-id="1599c-105">Central Panel</span></span>  
 <span data-ttu-id="1599c-106">**Salva in**</span><span class="sxs-lookup"><span data-stu-id="1599c-106">**Save in**</span></span>  
 <span data-ttu-id="1599c-107">Consente di individuare la cartella progetto esistente utilizzando il menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="1599c-107">Locate the existing project folder from this drop-down menu.</span></span> <span data-ttu-id="1599c-108">La selezione di una cartella in questo elenco determina la visualizzazione del contenuto della cartella nel riquadro principale sottostante.</span><span class="sxs-lookup"><span data-stu-id="1599c-108">Selecting a folder from this list displays the contents of the folder in the primary pane below.</span></span>  
  
 <span data-ttu-id="1599c-109">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="1599c-109">**File name**</span></span>  
 <span data-ttu-id="1599c-110">Utilizzare questa opzione per visualizzare il nome del file corrente, modificare il nome del file oppure filtrare i file e le cartelle visualizzati.</span><span class="sxs-lookup"><span data-stu-id="1599c-110">Use this option to view the current file name, change the file name, or filter the files and folders that are displayed.</span></span> <span data-ttu-id="1599c-111">Per filtrare i file e le cartelle visualizzati, immettere un nome di file completo o parziale in base al quale filtrare.</span><span class="sxs-lookup"><span data-stu-id="1599c-111">To filter the files and folders that are displayed, enter a full or partial file name on which to filter.</span></span> <span data-ttu-id="1599c-112">È possibile utilizzare l'asterisco (`*`) come carattere jolly.</span><span class="sxs-lookup"><span data-stu-id="1599c-112">You can use the asterisk (`*`) as a wildcard.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="1599c-113">Per visualizzare file contenuti in percorsi di rete o Web, specificare un URL o un percorso di rete nella casella **Nome file** .</span><span class="sxs-lookup"><span data-stu-id="1599c-113">To display files on Web and network locations, enter a URL or network path in the **File name** box.</span></span> <span data-ttu-id="1599c-114">Ad esempio, se si digita "<http://mywebsite>" vengono visualizzati i file disponibili nel percorso Web "mywebsite", mentre se si digita "\\" vengono visualizzati i file disponibili nel percorso "myshare" del server "myserver".</span><span class="sxs-lookup"><span data-stu-id="1599c-114">For example, "<http://mywebsite>" displays the files available at the "mywebsite" Web location and "\\\myserver\myshare" displays the files available at the "myshare" location on "myserver".</span></span>  
  
 <span data-ttu-id="1599c-115">**Salva come**</span><span class="sxs-lookup"><span data-stu-id="1599c-115">**Save as type**</span></span>  
 <span data-ttu-id="1599c-116">Utilizzare questa opzione per selezionare un nuovo tipo di file per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="1599c-116">Use this option to select a new file type for the selected item.</span></span> <span data-ttu-id="1599c-117">I tipi di file visualizzati comprendono tutti i tipi di file disponibili in cui è possibile convertire l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="1599c-117">The file types displayed include all available file types to which the selected item can be converted.</span></span>  
  
 <span data-ttu-id="1599c-118">**Opzioni di salvataggio avanzate**</span><span class="sxs-lookup"><span data-stu-id="1599c-118">**Advanced Save Options**</span></span>  
 <span data-ttu-id="1599c-119">Per accedere alla **finestra di dialogo Opzioni di salvataggio avanzate**, selezionare il piccolo rettangolo a destra del pulsante **Salva** e fare clic su **Salva con codifica**.</span><span class="sxs-lookup"><span data-stu-id="1599c-119">To access the **Advanced Save Options Dialog Box**, select the small rectangle at the right of the **Save** button and then click **Save with Encoding**.</span></span> <span data-ttu-id="1599c-120">Utilizzare questa finestra di dialogo per specificare una codifica per il file e i caratteri da utilizzare in corrispondenza delle terminazioni riga.</span><span class="sxs-lookup"><span data-stu-id="1599c-120">Use this dialog box to specify an encoding for the file and the characters to use at Line endings.</span></span>  
  
## <a name="left-panel"></a><span data-ttu-id="1599c-121">Pannello sinistro</span><span class="sxs-lookup"><span data-stu-id="1599c-121">Left Panel</span></span>  
 <span data-ttu-id="1599c-122">**Desktop**</span><span class="sxs-lookup"><span data-stu-id="1599c-122">**Desktop**</span></span>  
 <span data-ttu-id="1599c-123">Consente di visualizzare tutti i file e le cartelle presenti sul desktop.</span><span class="sxs-lookup"><span data-stu-id="1599c-123">Displays any files and folders located on the desktop.</span></span>  
  
 <span data-ttu-id="1599c-124">**Progetti**</span><span class="sxs-lookup"><span data-stu-id="1599c-124">**My Projects**</span></span>  
 <span data-ttu-id="1599c-125">Visualizza i file e le cartelle presenti in **Progetti personali** oppure nell'ultimo percorso visitato.</span><span class="sxs-lookup"><span data-stu-id="1599c-125">Displays files and folders at the **My Projects** or the most recently visited location.</span></span>  
  
 <span data-ttu-id="1599c-126">**Risorse del computer**</span><span class="sxs-lookup"><span data-stu-id="1599c-126">**My Computer**</span></span>  
 <span data-ttu-id="1599c-127">Visualizza il percorso **Risorse del computer** .</span><span class="sxs-lookup"><span data-stu-id="1599c-127">Displays the **My Computer** location on your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1599c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1599c-128">See Also</span></span>  
 <span data-ttu-id="1599c-129">[Opzioni di salvataggio avanzate](advanced-save-options.md) </span><span class="sxs-lookup"><span data-stu-id="1599c-129">[Advanced Save Options](advanced-save-options.md) </span></span>  
 [<span data-ttu-id="1599c-130">Gestire file con codifica</span><span class="sxs-lookup"><span data-stu-id="1599c-130">Manage Files with Encoding</span></span>](../solution/manage-files-with-encoding.md)  
  
  
