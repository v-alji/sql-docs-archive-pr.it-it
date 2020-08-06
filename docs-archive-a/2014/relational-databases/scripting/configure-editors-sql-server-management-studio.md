---
title: Configurare gli editor
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e7c7a8ef-f561-4258-a7b6-c445dba69f87
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e94cdbcd310814081e146e3fd0dbe75260d1240
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716223"
---
# <a name="configure-editors-sql-server-management-studio"></a><span data-ttu-id="b040a-102">Configurazione di editor (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b040a-102">Configure Editors (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b040a-103">È possibile personalizzare il funzionamento degli editor di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] configurando le apposite opzioni.</span><span class="sxs-lookup"><span data-stu-id="b040a-103">You can customize the operation of the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] editors by configuring the options for each editor.</span></span>  
  
## <a name="settng-editor-options"></a><span data-ttu-id="b040a-104">Impostazione delle opzioni degli editor</span><span class="sxs-lookup"><span data-stu-id="b040a-104">Settng Editor Options</span></span>  
 <span data-ttu-id="b040a-105">È possibile impostare la maggior parte delle opzioni degli editor scegliendo **Opzioni** dal menu **Strumenti** per visualizzare la finestra di dialogo **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="b040a-105">Most of the editor options are set by using the **Tools** menu and selecting **Options...** to display an **Options** dialog.</span></span> <span data-ttu-id="b040a-106">Nella finestra di dialogo **Opzioni** , aprire il nodo **Editor di testo** nel riquadro sinistro per impostare le opzioni di modifica di codice e testo.</span><span class="sxs-lookup"><span data-stu-id="b040a-106">In the **Options** dialog, open the **Text Editor** node in the left pane to set code and text editing options.</span></span> <span data-ttu-id="b040a-107">I nodi in Editor di testo si applicano a editor specifici:</span><span class="sxs-lookup"><span data-stu-id="b040a-107">The nodes under Text Editor apply to specific editors:</span></span>  
  
1.  <span data-ttu-id="b040a-108">**Tutte le lingue**: le opzioni impostate in questo nodo si applicano a tutti gli editor di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b040a-108">**All Languages** - options set using this node apply to all of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] editors.</span></span> <span data-ttu-id="b040a-109">È possibile ignorare queste impostazioni utilizzando gli altri nodi che consentono di configurare opzioni diverse per un editor specifico.</span><span class="sxs-lookup"><span data-stu-id="b040a-109">You can override these settings by using the other nodes to set different options for a specific editor.</span></span>  
  
2.  <span data-ttu-id="b040a-110">**Testo normale**: le opzioni impostate in questo nodo si applicano agli editor di testo, MDX e DMX.</span><span class="sxs-lookup"><span data-stu-id="b040a-110">**Plain Text** - options set using this node apply to the MDX, DMX, and text editors.</span></span>  
  
3.  <span data-ttu-id="b040a-111">**Transact-SQL**: le opzioni impostate in questo nodo si applicano all'editor di query del motore di database.</span><span class="sxs-lookup"><span data-stu-id="b040a-111">**Transact-SQL** - options set using this node apply to the Database Engine Query Editor.</span></span>  
  
4.  <span data-ttu-id="b040a-112">**XML**: le opzioni impostate in questo nodo si applicano all'editor XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="b040a-112">**XML** - options set using this node apply to the XML for Analysis editor.</span></span>  
  
 <span data-ttu-id="b040a-113">Aprire i nodi **Esecuzione query** o **Risultati query** per personalizzare l'esecuzione di query e la modalità di visualizzazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="b040a-113">Open the **Query Execution** or **Query Results** nodes to customize the execution of queries and how the results are displayed.</span></span>  
  
## <a name="editor-configuration-tasks"></a><span data-ttu-id="b040a-114">Attività di configurazione degli editor</span><span class="sxs-lookup"><span data-stu-id="b040a-114">Editor Configuration Tasks</span></span>  
  
|<span data-ttu-id="b040a-115">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="b040a-115">Task Description</span></span>|<span data-ttu-id="b040a-116">Argomento</span><span class="sxs-lookup"><span data-stu-id="b040a-116">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="b040a-117">Descrive come specificare che un editor deve essere aperto facendo doppio clic su un file con un'estensione specificata in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="b040a-117">Describes how to specify that an editor be opened by double-clicking on a file with a specified extension in Windows Explorer.</span></span>|[<span data-ttu-id="b040a-118">Associare estensioni di file a un editor di codice</span><span class="sxs-lookup"><span data-stu-id="b040a-118">Associate File Extensions to a Code Editor</span></span>](associate-file-extensions-to-a-code-editor.md)|  
|<span data-ttu-id="b040a-119">Descrive come personalizzare i tipi di carattere per rendere più leggibili codice e testo.</span><span class="sxs-lookup"><span data-stu-id="b040a-119">Describes how to customize fonts to make code and text more readable.</span></span>|[<span data-ttu-id="b040a-120">Modificare lo stile, le dimensioni e il colore del carattere</span><span class="sxs-lookup"><span data-stu-id="b040a-120">Change Font Color, Size, and Style</span></span>](change-font-color-size-and-style.md)|  
|<span data-ttu-id="b040a-121">Descrive come visualizzare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="b040a-121">Describes how to view properties.</span></span>|[<span data-ttu-id="b040a-122">Usare la finestra Proprietà in Management Studio</span><span class="sxs-lookup"><span data-stu-id="b040a-122">Use the Properties Window in Management Studio</span></span>](use-the-properties-window-in-management-studio.md)|  
|<span data-ttu-id="b040a-123">Percorso delle pagine della Guida per le finestre di dialogo delle opzioni degli editor.</span><span class="sxs-lookup"><span data-stu-id="b040a-123">Location of the F1 help pages for the editor options dialogs.</span></span>|[<span data-ttu-id="b040a-124">Guida sensibile al contesto relativa alle pagine di Opzioni query</span><span class="sxs-lookup"><span data-stu-id="b040a-124">Query Options Pages F1 Help</span></span>](../../database-engine/query-options-pages-f1-help.md)|  
  
  
