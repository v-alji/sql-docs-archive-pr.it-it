---
title: Personalizza (pagina Comandi) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.vs.customizecom.f1
ms.assetid: c8965f2c-51d9-437d-a6f3-8ac2075ede6b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 684fb9a6266fafae00b9881eb64a3642e6c98c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717208"
---
# <a name="customize-commands-page"></a><span data-ttu-id="a08a3-102">Personalizza (pagina Comandi)</span><span class="sxs-lookup"><span data-stu-id="a08a3-102">Customize (Commands Page)</span></span>
  <span data-ttu-id="a08a3-103">Questa finestra di dialogo consente di aggiungere e rimuovere i comandi sulle barre degli strumenti e nei menu, nonché di modificare le immagini utilizzate per i pulsanti della barra degli strumenti o per i comandi di menu.</span><span class="sxs-lookup"><span data-stu-id="a08a3-103">This dialog box enables you to add and remove commands on toolbars and menus as well as change the images used for toolbar buttons or menu commands.</span></span> <span data-ttu-id="a08a3-104">Per accedere alla pagina **Comandi** , scegliere **Personalizza** dal menu **Strumenti** e quindi fare clic su **Comandi**.</span><span class="sxs-lookup"><span data-stu-id="a08a3-104">You can access the **Commands** page by clicking **Customize** on the **Tools** menu and then clicking **Commands**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a08a3-105">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a08a3-105">UI element list</span></span>  
 <span data-ttu-id="a08a3-106">**Categories** (Categorie)</span><span class="sxs-lookup"><span data-stu-id="a08a3-106">**Categories**</span></span>  
 <span data-ttu-id="a08a3-107">Consente di specificare il set di comandi visualizzati nella casella di riepilogo **Comandi** .</span><span class="sxs-lookup"><span data-stu-id="a08a3-107">Specifies the set of commands that are displayed in the **Commands** list box.</span></span> <span data-ttu-id="a08a3-108">Le categorie dei comandi si basano sui titoli di menu assegnati dagli strumenti e dalle finestre di progettazione attualmente supportati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a08a3-108">The categories of commands are based on menu titles provided by the tools and designers that the environment is currently supporting.</span></span> <span data-ttu-id="a08a3-109">Poiché questo elenco di titoli è dinamico, è possibile che l'ordine delle categorie e dei titoli di menu cambi in base agli strumenti e alla finestra di progettazione, nonché alle personalizzazioni apportate a questi elementi.</span><span class="sxs-lookup"><span data-stu-id="a08a3-109">This list of titles is dynamic so that the order of categories and the menu titles change, depending on the tools and the designer, as well as any customizations made to them.</span></span> <span data-ttu-id="a08a3-110">È pertanto possibile che due menu associati a due finestre di progettazione diverse abbiano lo stesso nome e che quindi lo stesso titolo venga visualizzato due volte, anche se corrisponde a due set di comandi diversi.</span><span class="sxs-lookup"><span data-stu-id="a08a3-110">Therefore, it is possible for two menus from different designers to have the same name, so the same title can appear twice but offer different command sets.</span></span>  
  
 <span data-ttu-id="a08a3-111">**Comandi**</span><span class="sxs-lookup"><span data-stu-id="a08a3-111">**Commands**</span></span>  
 <span data-ttu-id="a08a3-112">Consente di visualizzare i comandi e le relative immagini in base alla categoria selezionata.</span><span class="sxs-lookup"><span data-stu-id="a08a3-112">Displays the commands and command images based on the category you selected.</span></span> <span data-ttu-id="a08a3-113">È possibile trascinare un comando sulla barra degli strumenti che si desidera personalizzare.</span><span class="sxs-lookup"><span data-stu-id="a08a3-113">You can drag a command onto the toolbar you want to customize.</span></span>  
  
 <span data-ttu-id="a08a3-114">**Modifica selezione**</span><span class="sxs-lookup"><span data-stu-id="a08a3-114">**Modify Selection**</span></span>  
 <span data-ttu-id="a08a3-115">Consente di visualizzare un elenco di comandi che possono essere utilizzati per personalizzare la visualizzazione del pulsante sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="a08a3-115">Displays a list of commands you can use to customize the display of the button on the toolbar.</span></span> <span data-ttu-id="a08a3-116">È ad esempio possibile modificare l'immagine o i tasti di scelta rapida, nonché specificare se visualizzare una stringa di testo anziché un'immagine per il comando.</span><span class="sxs-lookup"><span data-stu-id="a08a3-116">For example, you can change the image or accelerator keys, as well as specify whether to display text instead of an image for the command.</span></span> <span data-ttu-id="a08a3-117">Questo pulsante diventa disponibile dopo la selezione di un pulsante di comando sulla barra degli strumenti che si desidera personalizzare.</span><span class="sxs-lookup"><span data-stu-id="a08a3-117">This button is available after you select a command button on a toolbar you want to customize.</span></span>  
  
 <span data-ttu-id="a08a3-118">**Ridisponi comandi**</span><span class="sxs-lookup"><span data-stu-id="a08a3-118">**Rearrange Commands**</span></span>  
 <span data-ttu-id="a08a3-119">Consente di visualizzare la finestra di dialogo **Ridisponi comandi** , che può essere usata per rinominare, aggiungere e rimuovere i comandi dai menu e dalle barre degli strumenti, nonché per modificare il loro ordine e le immagini dei comandi e dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="a08a3-119">Displays the **Rearrange Commands** dialog box, which allows you to rename, reorder, add, and remove commands on menus and toolbars as well as change button and command images.</span></span>  
  
 <span data-ttu-id="a08a3-120">**Tastiera**</span><span class="sxs-lookup"><span data-stu-id="a08a3-120">**Keyboard**</span></span>  
 <span data-ttu-id="a08a3-121">Consente di visualizzare la pagina **Tastiera** della finestra di dialogo **Opzioni** , in cui è possibile specificare le combinazioni di tasti di scelta rapida per i comandi.</span><span class="sxs-lookup"><span data-stu-id="a08a3-121">Displays the **Keyboard** page of the **Options** dialog box so you can specify shortcut key combinations for commands.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08a3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a08a3-122">See Also</span></span>  
 [<span data-ttu-id="a08a3-123">Personalizzare i menu e i tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="a08a3-123">Customize Menus and Shortcut Keys</span></span>](../customize-menus-and-shortcut-keys.md)  
