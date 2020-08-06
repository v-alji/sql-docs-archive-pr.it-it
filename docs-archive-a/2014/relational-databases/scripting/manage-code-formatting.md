---
title: Gestione della formattazione del codice
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- indenting code [SQL Server]
- displaying URLs
- code formatting [SQL Server Management Studio]
- collapsing text
- formats [SQL Server], code formatting in SQL Server Management Studio
- hiding text
- formats [SQL Server]
- text [SQL Server], code formats
- automatic indentation
- converting text to lower case
- Query Editor [SQL Server Management Studio], managing code formats
- URL displayed in code [SQL Server Management Studio]
- converting text to upper case
- text [SQL Server]
- unindenting code
ms.assetid: ddbac4d2-6bdc-4467-a352-e869ec880eed
author: rothja
ms.author: jroth
ms.openlocfilehash: 873848c8aee575b47f7a3d8c31d8392cba5ed12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637734"
---
# <a name="manage-code-formatting"></a><span data-ttu-id="aa104-102">Gestione della formattazione del codice</span><span class="sxs-lookup"><span data-stu-id="aa104-102">Manage Code Formatting</span></span>
  <span data-ttu-id="aa104-103">L'editor consente di formattare il codice con rientri, testo nascosto, URL e così via.</span><span class="sxs-lookup"><span data-stu-id="aa104-103">With the Editor you can format your code with indenting, hidden text, URLs, and so forth.</span></span> <span data-ttu-id="aa104-104">È inoltre possibile formattare il codice automaticamente durante la digitazione tramite la funzionalità intelligente per la gestione dei rientri.</span><span class="sxs-lookup"><span data-stu-id="aa104-104">You can also auto-format your code as you type by using Smart Indenting.</span></span>  
  
## <a name="indenting"></a><span data-ttu-id="aa104-105">Stili rientri</span><span class="sxs-lookup"><span data-stu-id="aa104-105">Indenting</span></span>  
 <span data-ttu-id="aa104-106">È possibile scegliere tra tre diversi stili di rientro del testo.</span><span class="sxs-lookup"><span data-stu-id="aa104-106">You can choose three different styles of text indenting.</span></span> <span data-ttu-id="aa104-107">È inoltre possibile specificare il numero di spazi di ogni singolo rientro o tabulazione e se per il rientro l'editor deve utilizzare tabulazioni o spazi.</span><span class="sxs-lookup"><span data-stu-id="aa104-107">You can also specify how many spaces compose a single indentation or tab, and whether the Editor uses tabs or space characters when indenting.</span></span>  
  
#### <a name="to-choose-an-indenting-style"></a><span data-ttu-id="aa104-108">Per scegliere uno stile di rientro</span><span class="sxs-lookup"><span data-stu-id="aa104-108">To choose an indenting style</span></span>  
  
1.  <span data-ttu-id="aa104-109">Scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="aa104-109">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="aa104-110">Fare clic su **Editor di testo**.</span><span class="sxs-lookup"><span data-stu-id="aa104-110">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="aa104-111">Selezionare la cartella **Tutti i linguaggi** per impostare i rientri per tutti i linguaggi.</span><span class="sxs-lookup"><span data-stu-id="aa104-111">Click the folder, and select **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="aa104-112">Fare clic su **Tabulazioni**.</span><span class="sxs-lookup"><span data-stu-id="aa104-112">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="aa104-113">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa104-113">Click one of the following options:</span></span>  
  
    -   <span data-ttu-id="aa104-114">**Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="aa104-114">**None**.</span></span> <span data-ttu-id="aa104-115">Il cursore si porta all'inizio della riga successiva.</span><span class="sxs-lookup"><span data-stu-id="aa104-115">The cursor goes to the beginning of the next line.</span></span>  
  
    -   <span data-ttu-id="aa104-116">**Blocco**.</span><span class="sxs-lookup"><span data-stu-id="aa104-116">**Block**.</span></span> <span data-ttu-id="aa104-117">Il cursore allinea la riga successiva con quella precedente.</span><span class="sxs-lookup"><span data-stu-id="aa104-117">The cursor aligns the next line with the previous line.</span></span>  
  
    -   <span data-ttu-id="aa104-118">**Intelligenti** (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="aa104-118">**Smart** (Default).</span></span> <span data-ttu-id="aa104-119">Il servizio di linguaggio determina lo stile di rientro appropriato da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="aa104-119">The language service determines the appropriate indenting style to use.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aa104-120">Non tutte le opzioni di rientro sono disponibili per tutti i linguaggi.</span><span class="sxs-lookup"><span data-stu-id="aa104-120">Some languages do not offer all three indenting options.</span></span>  
  
#### <a name="to-change-indent-tab-settings"></a><span data-ttu-id="aa104-121">Per modificare le impostazioni di tabulazione dei rientri</span><span class="sxs-lookup"><span data-stu-id="aa104-121">To change indent tab settings</span></span>  
  
1.  <span data-ttu-id="aa104-122">Scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="aa104-122">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="aa104-123">Fare clic su **Editor di testo**.</span><span class="sxs-lookup"><span data-stu-id="aa104-123">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="aa104-124">Selezionare la cartella **Tutti i linguaggi** per impostare i rientri per tutti i linguaggi.</span><span class="sxs-lookup"><span data-stu-id="aa104-124">Select the folder for **All Languages** to set indenting for all languages.</span></span>  
  
4.  <span data-ttu-id="aa104-125">Fare clic su **Tabulazioni**.</span><span class="sxs-lookup"><span data-stu-id="aa104-125">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="aa104-126">Per specificare i caratteri per tabulazioni e rientri, fare clic su **Mantieni tabulazioni**.</span><span class="sxs-lookup"><span data-stu-id="aa104-126">To specify tab characters for tab and indent operations, click **Keep tabs**.</span></span> <span data-ttu-id="aa104-127">Per specificare spazi, selezionare **Inserisci spazi**.</span><span class="sxs-lookup"><span data-stu-id="aa104-127">To specify space characters, select **Insert spaces**.</span></span>  
  
     <span data-ttu-id="aa104-128">Se si seleziona **Inserisci spazi**, immettere il numero di spazi per ogni tabulazione o rientro rispettivamente in **Dimensione tabulazione** o **Dimensione rientro**.</span><span class="sxs-lookup"><span data-stu-id="aa104-128">If you select **Insert Spaces**, enter the number of space characters each tab or indent represents under **Tab Size** or **Indent Size**, respectively.</span></span>  
  
#### <a name="to-indent-code"></a><span data-ttu-id="aa104-129">Per rientrare il codice</span><span class="sxs-lookup"><span data-stu-id="aa104-129">To indent code</span></span>  
  
1.  <span data-ttu-id="aa104-130">Selezionare il testo che si desidera rientrare.</span><span class="sxs-lookup"><span data-stu-id="aa104-130">Select the text you want to indent.</span></span>  
  
2.  <span data-ttu-id="aa104-131">Premere TAB o fare clic sul pulsante **Rientra** sulla barra degli strumenti Standard.</span><span class="sxs-lookup"><span data-stu-id="aa104-131">Press TAB, or click the **Indent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-unindent-code"></a><span data-ttu-id="aa104-132">Per ridurre il rientro del codice</span><span class="sxs-lookup"><span data-stu-id="aa104-132">To unindent code</span></span>  
  
1.  <span data-ttu-id="aa104-133">Selezionare il testo a cui applicare la riduzione del rientro.</span><span class="sxs-lookup"><span data-stu-id="aa104-133">Select the text you want to unindent.</span></span>  
  
2.  <span data-ttu-id="aa104-134">Premere MAIUSC+TAB, oppure fare clic sul pulsante **Riduci rientro** sulla barra degli strumenti Standard.</span><span class="sxs-lookup"><span data-stu-id="aa104-134">Press SHIFT+TAB, or click the **Unindent** button on the Standard toolbar.</span></span>  
  
#### <a name="to-automatically-indent-all-of-your-code"></a><span data-ttu-id="aa104-135">Per rientrare automaticamente tutto il codice</span><span class="sxs-lookup"><span data-stu-id="aa104-135">To automatically indent all of your code</span></span>  
  
1.  <span data-ttu-id="aa104-136">Scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="aa104-136">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="aa104-137">Fare clic su **Editor di testo**.</span><span class="sxs-lookup"><span data-stu-id="aa104-137">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="aa104-138">Fare clic su **Tutti i linguaggi**.</span><span class="sxs-lookup"><span data-stu-id="aa104-138">Click **All Languages**.</span></span>  
  
4.  <span data-ttu-id="aa104-139">Fare clic su **Tabulazioni**.</span><span class="sxs-lookup"><span data-stu-id="aa104-139">Click **Tabs**.</span></span>  
  
5.  <span data-ttu-id="aa104-140">Scegliere **Intelligenti**.</span><span class="sxs-lookup"><span data-stu-id="aa104-140">Click **Smart**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa104-141">L'opzione **Intelligenti** non è disponibile per tutti i linguaggi.</span><span class="sxs-lookup"><span data-stu-id="aa104-141">The **Smart** option is not available for some languages.</span></span>  
  
#### <a name="to-convert-white-space-to-tabs"></a><span data-ttu-id="aa104-142">Per convertire gli spazi vuoti in tabulazioni</span><span class="sxs-lookup"><span data-stu-id="aa104-142">To convert white space to tabs</span></span>  
  
1.  <span data-ttu-id="aa104-143">Selezionare il testo in cui si desidera convertire lo spazio vuoto in tabulazioni.</span><span class="sxs-lookup"><span data-stu-id="aa104-143">Select the text whose white space you want to convert to tabs.</span></span>  
  
2.  <span data-ttu-id="aa104-144">Scegliere **Avanzate** dal menu **Modifica**e quindi fare clic su **Inserisci tabulazione**.</span><span class="sxs-lookup"><span data-stu-id="aa104-144">On the **Edit** menu, point to **Advanced**, and click **Tabify Selection**.</span></span>  
  
#### <a name="to-convert-tabs-to-spaces"></a><span data-ttu-id="aa104-145">Per convertire le tabulazioni in spazi</span><span class="sxs-lookup"><span data-stu-id="aa104-145">To convert tabs to spaces</span></span>  
  
1.  <span data-ttu-id="aa104-146">Selezionare il testo in cui si desidera convertire le tabulazioni in spazi.</span><span class="sxs-lookup"><span data-stu-id="aa104-146">Select the text whose tabs you want to convert to spaces.</span></span>  
  
2.  <span data-ttu-id="aa104-147">Scegliere **Avanzate** dal menu **Modifica**e quindi fare clic su **Rimuovi tabulazione**.</span><span class="sxs-lookup"><span data-stu-id="aa104-147">On the **Edit** menu, point to **Advanced**, and click **Untabify Selection**.</span></span>  
  
 <span data-ttu-id="aa104-148">Il comportamento di questi comandi dipende dalle impostazioni di tabulazione nella finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="aa104-148">The behavior of these commands depends on the tab settings in the **Options** dialog box.</span></span> <span data-ttu-id="aa104-149">Se, ad esempio, l'impostazione di tabulazione è 4, **Inserisci tabulazione** comporta la creazione di una tabulazione ogni 4 spazi contigui, mentre **Rimuovi tabulazione** comporta la creazione di 4 spazi per ogni tabulazione.</span><span class="sxs-lookup"><span data-stu-id="aa104-149">For example, if the tab setting is 4, **Tabify Selection** creates a tab for every 4 contiguous spaces, and **Untabify Selection** creates 4 spaces for every tab.</span></span>  
  
## <a name="converting-text-to-upper-and-lower-case"></a><span data-ttu-id="aa104-150">Conversione del testo in lettere maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="aa104-150">Converting Text to Upper and Lower Case</span></span>  
 <span data-ttu-id="aa104-151">Sono previsti dei comandi per convertire un testo in tutte lettere maiuscole o minuscole.</span><span class="sxs-lookup"><span data-stu-id="aa104-151">You can use commands to convert text to all uppercase or lower case.</span></span>  
  
#### <a name="to-switch-text-to-upper-or-lower-case"></a><span data-ttu-id="aa104-152">Per convertire un testo in lettere maiuscole o minuscole</span><span class="sxs-lookup"><span data-stu-id="aa104-152">To switch text to upper or lower case</span></span>  
  
1.  <span data-ttu-id="aa104-153">Selezionare il testo che si desidera convertire.</span><span class="sxs-lookup"><span data-stu-id="aa104-153">Select the text you want to convert.</span></span>  
  
2.  <span data-ttu-id="aa104-154">Per convertirlo in lettere maiuscole, premere CTRL+MAIUSC+U, oppure scegliere **Maiuscole** dal sottomenu **Avanzate** del menu **Modifica** .</span><span class="sxs-lookup"><span data-stu-id="aa104-154">To convert text to uppercase, press CTRL+SHIFT+U, or click **Make Uppercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
3.  <span data-ttu-id="aa104-155">Per convertirlo in lettere minuscole, premere CTRL+MAIUSC+L, oppure scegliere **Minuscole** dal sottomenu **Avanzate** del menu **Modifica** .</span><span class="sxs-lookup"><span data-stu-id="aa104-155">To convert text to lowercase, press CTRL+SHIFT+L, or click **Make Lowercase** on the **Advanced** submenu of the **Edit** menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa104-156">Per un elenco completo dei tasti di scelta rapida, vedere [Tasti di scelta rapida di SQL Server Management Studio](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span><span class="sxs-lookup"><span data-stu-id="aa104-156">For a complete list of keyboard shortcut keys, see [SQL Server Management Studio Keyboard Shortcuts](../../ssms/sql-server-management-studio-keyboard-shortcuts.md).</span></span>  
  
## <a name="displaying-and-linking-to-urls"></a><span data-ttu-id="aa104-157">Visualizzazione e collegamenti agli URL</span><span class="sxs-lookup"><span data-stu-id="aa104-157">Displaying and Linking to URLs</span></span>  
 <span data-ttu-id="aa104-158">All'interno del codice è possibile creare e visualizzare URL selezionabili.</span><span class="sxs-lookup"><span data-stu-id="aa104-158">You can create and display clickable URLs in your code.</span></span> <span data-ttu-id="aa104-159">Per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="aa104-159">By default, the URLs:</span></span>  
  
-   <span data-ttu-id="aa104-160">Gli URL sono sottolineati.</span><span class="sxs-lookup"><span data-stu-id="aa104-160">Are underlined.</span></span>  
  
-   <span data-ttu-id="aa104-161">Il puntatore del mouse si trasforma in una mano quando viene spostato su di essi.</span><span class="sxs-lookup"><span data-stu-id="aa104-161">Change the mouse pointer to a hand when you move over them.</span></span>  
  
-   <span data-ttu-id="aa104-162">Se l'URL è valido, viene aperto quando si fa clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="aa104-162">Open the URL when clicked, if the URL is valid.</span></span>  
  
#### <a name="to-display-a-clickable-url"></a><span data-ttu-id="aa104-163">Per visualizzare un URL selezionabile</span><span class="sxs-lookup"><span data-stu-id="aa104-163">To display a clickable URL</span></span>  
  
1.  <span data-ttu-id="aa104-164">Scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="aa104-164">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="aa104-165">Fare clic su **Editor di testo**.</span><span class="sxs-lookup"><span data-stu-id="aa104-165">Click **Text Editor**.</span></span>  
  
3.  <span data-ttu-id="aa104-166">Per modificare l'opzione per un solo linguaggio, fare clic sulla cartella corrispondente e quindi scegliere **Generale**.</span><span class="sxs-lookup"><span data-stu-id="aa104-166">To change the option for only one language, click that language folder and then click **General**.</span></span> <span data-ttu-id="aa104-167">Per modificarla per tutti i linguaggi, fare clic su **Tutti i linguaggi** e quindi scegliere **Generale**.</span><span class="sxs-lookup"><span data-stu-id="aa104-167">To change the option for all languages, click **All Languages** and then click **General**.</span></span>  
  
4.  <span data-ttu-id="aa104-168">Selezionare **Consenti navigazione URL con clic singolo**.</span><span class="sxs-lookup"><span data-stu-id="aa104-168">Select **Enable single-click URL navigation**.</span></span>  
  
  
