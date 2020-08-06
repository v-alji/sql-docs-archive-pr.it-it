---
title: Opzioni (editor di testo-XML-pagina varie) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 1a9509f0-c663-4b31-b396-7f5dc4371651
author: rothja
ms.author: jroth
ms.openlocfilehash: d937368d30122442ccbc40372a6b8e1cabc141e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711008"
---
# <a name="options-text-editor---xml---miscellaneous-page"></a><span data-ttu-id="2cd87-102">Opzioni (Editor di testo - XML - pagina Varie)</span><span class="sxs-lookup"><span data-stu-id="2cd87-102">Options (Text Editor - XML - Miscellaneous Page)</span></span>

<span data-ttu-id="2cd87-103">La finestra di dialogo **Opzioni** consente di modificare le impostazioni del completamento automatico e dello schema per l'editor XML.</span><span class="sxs-lookup"><span data-stu-id="2cd87-103">The **Options** dialog box lets you change the autocompletion and schema settings for the XML Editor.</span></span> <span data-ttu-id="2cd87-104">Per visualizzare queste impostazioni, scegliere **Opzioni** dal menu **Strumenti**, espandere la cartella **Editor di testo** , fare clic su **XML** e quindi su **Varie** .</span><span class="sxs-lookup"><span data-stu-id="2cd87-104">These settings are available when, on the **Tools** menu, you click **Options**, expand the **Text Editor** folder, click **XML** and then click **Miscellaneous** .</span></span>  
  
## <a name="auto-insert"></a><span data-ttu-id="2cd87-105">Inserimento automatico</span><span class="sxs-lookup"><span data-stu-id="2cd87-105">Auto Insert</span></span>  
 <span data-ttu-id="2cd87-106">**Chiudi i tag**</span><span class="sxs-lookup"><span data-stu-id="2cd87-106">**Close tags**</span></span>  
 <span data-ttu-id="2cd87-107">Nell'editor di testo i tag di chiusura vengono aggiunti automaticamente durante la creazione di elementi XML.</span><span class="sxs-lookup"><span data-stu-id="2cd87-107">The Text Editor adds close tags when authoring XML elements.</span></span> <span data-ttu-id="2cd87-108">Se viene selezionato il tag di inizio di un elemento, viene inserito automaticamente il tag di chiusura corrispondente, che include un prefisso di spazio dei nomi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2cd87-108">If an element start tag is selected, the editor inserts the matching close tag, including a matching namespace prefix.</span></span> <span data-ttu-id="2cd87-109">Questa casella di controllo è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2cd87-109">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="2cd87-110">**Virgolette per gli attributi**</span><span class="sxs-lookup"><span data-stu-id="2cd87-110">**Attribute quotes**</span></span>  
 <span data-ttu-id="2cd87-111">Durante la creazione di attributi XML, l'editor inserisce i caratteri `="``"` e posiziona l'accento circonflesso (**^)** all'interno delle virgolette.</span><span class="sxs-lookup"><span data-stu-id="2cd87-111">When authoring XML attributes, the editor inserts the `="``"` characters and positions the caret (**^)** inside the quotation marks.</span></span> <span data-ttu-id="2cd87-112">Questa casella di controllo è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2cd87-112">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="2cd87-113">**Dichiarazioni degli spazi dei nomi**</span><span class="sxs-lookup"><span data-stu-id="2cd87-113">**Namespace declarations**</span></span>  
 <span data-ttu-id="2cd87-114">Vengono inserite automaticamente le dichiarazioni degli spazi dei nomi, se necessarie.</span><span class="sxs-lookup"><span data-stu-id="2cd87-114">The editor automatically inserts namespace declarations wherever they are needed.</span></span> <span data-ttu-id="2cd87-115">Questa casella di controllo è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2cd87-115">This check box is selected by default.</span></span>  
  
 <span data-ttu-id="2cd87-116">**Altri markup (commenti, CDATA)**</span><span class="sxs-lookup"><span data-stu-id="2cd87-116">**Other markup (Comments, CDATA)**</span></span>  
 <span data-ttu-id="2cd87-117">Commenti, CDATA, DOCTYPE, istruzioni di elaborazione e altri markup vengono completati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2cd87-117">Comments, CDATA, DOCTYPE, processing instructions, and other markup is autocompleted.</span></span> <span data-ttu-id="2cd87-118">Questa casella di controllo è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2cd87-118">This check box is selected by default.</span></span>  
  
## <a name="network"></a><span data-ttu-id="2cd87-119">Rete</span><span class="sxs-lookup"><span data-stu-id="2cd87-119">Network</span></span>  
 <span data-ttu-id="2cd87-120">**Scarica automaticamente le DTD e gli schemi**</span><span class="sxs-lookup"><span data-stu-id="2cd87-120">**Automatically download DTDs and schemas**</span></span>  
 <span data-ttu-id="2cd87-121">Gli schemi e le definizioni DTD (Document Type Definitions) vengono scaricati automaticamente da percorsi HTTP.</span><span class="sxs-lookup"><span data-stu-id="2cd87-121">Schemas and document type definitions (DTDs) are automatically downloaded from HTTP locations.</span></span> <span data-ttu-id="2cd87-122">Questa caratteristica utilizza System.Net con il rilevamento automatico del server proxy.</span><span class="sxs-lookup"><span data-stu-id="2cd87-122">This feature uses System.Net with autoproxy server detection enabled.</span></span> <span data-ttu-id="2cd87-123">Questa casella di controllo è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2cd87-123">This check box is selected by default.</span></span>  
  
## <a name="outlining"></a><span data-ttu-id="2cd87-124">struttura</span><span class="sxs-lookup"><span data-stu-id="2cd87-124">Outlining</span></span>  
 <span data-ttu-id="2cd87-125">**Attiva modalità struttura all'apertura dei file**</span><span class="sxs-lookup"><span data-stu-id="2cd87-125">**Enter outlining mode when files open**</span></span>  
 <span data-ttu-id="2cd87-126">Attiva la modalità struttura quando viene aperto un file.</span><span class="sxs-lookup"><span data-stu-id="2cd87-126">Turns on the outlining feature when a file is opened.</span></span> <span data-ttu-id="2cd87-127">Questa casella di controllo è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2cd87-127">This check box is selected by default.</span></span>  
  
## <a name="caching"></a><span data-ttu-id="2cd87-128">Memorizzazione nella cache</span><span class="sxs-lookup"><span data-stu-id="2cd87-128">Caching</span></span>  
 <span data-ttu-id="2cd87-129">**Schemi**</span><span class="sxs-lookup"><span data-stu-id="2cd87-129">**Schemas**</span></span>  
 <span data-ttu-id="2cd87-130">Specifica il percorso della cache degli schemi.</span><span class="sxs-lookup"><span data-stu-id="2cd87-130">Specifies the location of the schema cache.</span></span> <span data-ttu-id="2cd87-131">Se si fa clic sul pulsante Sfoglia viene aperto il percorso della cache degli schemi corrente in una nuova finestra.</span><span class="sxs-lookup"><span data-stu-id="2cd87-131">The Browse button (...) opens the current schema cache location in a new window.</span></span> <span data-ttu-id="2cd87-132">Il percorso predefinito è *\<Management Studio install directory>* \Xml\Schemas.</span><span class="sxs-lookup"><span data-stu-id="2cd87-132">The default location is *\<Management Studio install directory>* \Xml\Schemas.</span></span>  
