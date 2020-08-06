---
title: Impostazione del layout e delle opzioni dello strumento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 43e97ce0-97bc-4a27-9485-5bbeb7190b85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 96d853a85b8ee4d451c55d7ea59af3755887be22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719217"
---
# <a name="setting-tool-options-and-layout"></a><span data-ttu-id="6c065-102">Impostazione del layout e delle opzioni dello strumento</span><span class="sxs-lookup"><span data-stu-id="6c065-102">Setting Tool Options and Layout</span></span>
  <span data-ttu-id="6c065-103">All'avvio è possibile impostare nella maniera più appropriata alla modalità di utilizzo le opzioni che configurano l'interfaccia utente grafica (GUI) dello strumento Ottimizzazione guidata motore di database, il carattere utilizzato e altre funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6c065-103">You can set options that configure what the Database Engine Tuning Advisor graphical user interface (GUI) displays on startup, the font it uses, and other tool functionality to best support how you use it.</span></span> <span data-ttu-id="6c065-104">Le procedure contenute in questa pagina illustrano le opzioni che è possibile impostare e in che modo impostarle.</span><span class="sxs-lookup"><span data-stu-id="6c065-104">The practices on this page familiarize you with the options you can set, and how to set them.</span></span>  
  
### <a name="set-the-tool-options"></a><span data-ttu-id="6c065-105">Impostazione delle opzioni dello strumento</span><span class="sxs-lookup"><span data-stu-id="6c065-105">Set the tool options</span></span>  
  
1.  <span data-ttu-id="6c065-106">Avviare lo strumento Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="6c065-106">Start the Database Engine Tuning Advisor.</span></span> <span data-ttu-id="6c065-107">Scegliere **Programmi** dal menu **Start**di Windows, selezionare [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], poi **Strumenti per le prestazioni**e fare clic su **Ottimizzazione guidata motore di database**.</span><span class="sxs-lookup"><span data-stu-id="6c065-107">On the Windows **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and click **Database Engine Tuning Advisor**.</span></span>  
  
2.  <span data-ttu-id="6c065-108">Scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="6c065-108">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="6c065-109">Nella finestra di dialogo **Opzioni** visualizzare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c065-109">In the **Options** dialog box, view the following options:</span></span>  
  
    -   <span data-ttu-id="6c065-110">Espandere l'elenco **All'avvio** per mostrare le visualizzazioni possibili all'avvio di Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="6c065-110">Expand the **On startup** list to view what Database Engine Tuning Advisor can display when it is started.</span></span> <span data-ttu-id="6c065-111">Per impostazione predefinita, è selezionata l'opzione **Mostra una nuova sessione** .</span><span class="sxs-lookup"><span data-stu-id="6c065-111">By default, **Show a new session** is selected.</span></span>  
  
    -   <span data-ttu-id="6c065-112">Fare clic su **modifica carattere** per visualizzare i tipi di carattere che è possibile scegliere per gli elenchi di database e tabelle nella scheda **generale** . I tipi di carattere scelti per questa opzione vengono utilizzati anche nei report e nelle griglie Ottimizzazione guidata motore di database raccomandazione dopo aver eseguito l'ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="6c065-112">Click **Change Font** to see what fonts you can choose for the lists of databases and tables on the **General** tab. The fonts you choose for this option also are used in Database Engine Tuning Advisor recommendation grids and reports after you have performed tuning.</span></span> <span data-ttu-id="6c065-113">Per impostazione predefinita, Ottimizzazione guidata motore di database utilizza i caratteri di sistema.</span><span class="sxs-lookup"><span data-stu-id="6c065-113">By default, Database Engine Tuning Advisor uses system fonts.</span></span>  
  
    -   <span data-ttu-id="6c065-114">È possibile impostare **Numero di elementi negli elenchi degli ultimi elementi utilizzati** tra **1** e **10**.</span><span class="sxs-lookup"><span data-stu-id="6c065-114">The **Number of items in most recently used lists** can be set between **1** and **10**.</span></span> <span data-ttu-id="6c065-115">In tal modo viene impostato il numero massimo di elementi visualizzati quando si sceglie **Sessioni recenti** o **File recenti** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="6c065-115">This sets the maximum number of items in the lists displayed by clicking **Recent Sessions** or **Recent Files** on the **File** menu.</span></span> <span data-ttu-id="6c065-116">Per impostazione predefinita, questa opzione è impostata su **4**.</span><span class="sxs-lookup"><span data-stu-id="6c065-116">By default, this option is set to **4**.</span></span>  
  
    -   <span data-ttu-id="6c065-117">Quando l'opzione **Memorizza le ultime opzioni di ottimizzazione specificate** è selezionata, per impostazione predefinita, per la sessione di ottimizzazione successiva, lo strumento Ottimizzazione guidata motore di database usa le opzioni specificate per l'ultima sessione.</span><span class="sxs-lookup"><span data-stu-id="6c065-117">When **Remember my last tuning options** is checked, by default Database Engine Tuning Advisor uses the tuning options you specified for your last tuning session for the next tuning session.</span></span> <span data-ttu-id="6c065-118">Deselezionare questa casella di controllo per utilizzare le opzioni di ottimizzazione predefinite di Ottimizzazione guidata motore di database.</span><span class="sxs-lookup"><span data-stu-id="6c065-118">Clear this check box to use Database Engine Tuning Advisor tuning option defaults.</span></span> <span data-ttu-id="6c065-119">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6c065-119">By default, this option is selected.</span></span>  
  
    -   <span data-ttu-id="6c065-120">Per impostazione predefinita, l'opzione **Chiedi conferma prima di eliminare definitivamente le sessioni** è selezionata per evitare l'eliminazione accidentale di sessioni di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="6c065-120">By default, **Ask before permanently deleting sessions** is checked to avoid accidentally deleting tuning sessions.</span></span>  
  
    -   <span data-ttu-id="6c065-121">Per impostazione predefinita, l'opzione **Chiedi conferma prima di arrestare l'analisi della sessione** è selezionata, per evitare l'arresto accidentale di una sessione di ottimizzazione prima che Ottimizzazione guidata motore di database abbia concluso l'analisi di un carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6c065-121">By default, **Ask before stopping session analysis** is checked to avoid accidentally stopping a tuning session before Database Engine Tuning Advisor has finished analyzing a workload.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="6c065-122">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="6c065-122">Next Lesson</span></span>  
 [<span data-ttu-id="6c065-123">Lezione 2: Uso di Ottimizzazione guidata motore di database</span><span class="sxs-lookup"><span data-stu-id="6c065-123">Lesson 2: Using Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
