---
title: Finestra di dialogo Opzioni Generatore report, impostazioni (Generatore report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10427"
ms.assetid: 423360de-9bed-462e-921f-60a5abab004f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 07bd4a7f9dfe1abd8ab76765cb1ac10ff5227066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626024"
---
# <a name="report-builder-options-dialog-box-settings-report-builder"></a><span data-ttu-id="2d1b5-102">Finestra di dialogo Opzioni Generatore report, Impostazioni (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="2d1b5-102">Report Builder Options Dialog Box, Settings (Report Builder)</span></span>
  <span data-ttu-id="2d1b5-103">Fare clic sul pulsante **Generatore report** , quindi fare clic su **Opzioni** per impostare le opzioni per la visualizzazione dei file e delle connessioni recenti.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-103">Click the **Report Builder** button and then click **Options** to set options for showing recent files and connections.</span></span> <span data-ttu-id="2d1b5-104">È anche possibile modificare il server di report predefinito o aggiungerne uno se tale server non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-104">You can also change the default report server, or add one if you don't have a default.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="2d1b5-105">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2d1b5-105">UI element list</span></span>  
 <span data-ttu-id="2d1b5-106">**Usa questo server di report o sito di SharePoint per impostazione predefinita**</span><span class="sxs-lookup"><span data-stu-id="2d1b5-106">**Use this report server or SharePoint site by default**</span></span>  
 <span data-ttu-id="2d1b5-107">È possibile che l'amministratore abbia configurato questa opzione.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-107">Your administrator may have configured this.</span></span> <span data-ttu-id="2d1b5-108">Il valore può essere un URL ben formato che inizia con http:// o https://.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-108">The value can be a well-formed URL starting with http:// or https://.</span></span> <span data-ttu-id="2d1b5-109">Questa impostazione determina le connessioni all'origine dati che verranno visualizzate per impostazione predefinita nelle procedure guidate Nuova tabella o matrice e Nuovo grafico.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-109">This setting determines which data source connections appear by default in the Table/Matrix and Chart wizards.</span></span> <span data-ttu-id="2d1b5-110">I report verranno inoltre elaborati su questo server e sarà possibile fare riferimento alle risorse dal server.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-110">In addition, your reports will be processed on this server and you can reference resources from this server.</span></span>  
  
 <span data-ttu-id="2d1b5-111">Se si seleziona un altro server di report, potrebbe essere necessario riavviare Generatore report per rendere effettiva la modifica.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-111">If you select a different report server, you may need to restart Report Builder in order for this change to take affect.</span></span>  
  
 <span data-ttu-id="2d1b5-112">**Pubblica parti di report in questa cartella per impostazione predefinita**</span><span class="sxs-lookup"><span data-stu-id="2d1b5-112">**Publish report parts to this folder by default**</span></span>  
 <span data-ttu-id="2d1b5-113">Generatore report consentirà il salvataggio delle parti di report pubblicate in questa cartella.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-113">Report Builder will save report parts that you publish to this folder.</span></span> <span data-ttu-id="2d1b5-114">Se la cartella non esiste ancora e si dispone delle autorizzazioni per la creazione di cartelle nel server di report, verrà creata da Generatore report.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-114">If the folder does not exist yet and you have permissions to create folders on the report server, Report Builder will create this folder.</span></span>  
  
 <span data-ttu-id="2d1b5-115">Non è necessario riavviare Generatore report affinché questa impostazione venga applicata.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-115">You do not need to restart Report Builder for this setting to take effect.</span></span>  
  
 <span data-ttu-id="2d1b5-116">**Mostra questo numero di siti e server recenti**</span><span class="sxs-lookup"><span data-stu-id="2d1b5-116">**Show this number of recent sites and servers**</span></span>  
 <span data-ttu-id="2d1b5-117">Specificare il numero di siti e connessioni recenti da visualizzare nelle finestre di dialogo **Apri report** e **Salva come report** .</span><span class="sxs-lookup"><span data-stu-id="2d1b5-117">Specify the number of recent sites and connections to show in the **Open Report** and **Save As Report** dialog boxes.</span></span>  
  
 <span data-ttu-id="2d1b5-118">**Mostra questo numero di connessioni alle origini dei dati condivise**</span><span class="sxs-lookup"><span data-stu-id="2d1b5-118">**Show this number of recent shared datasets and data source connections**</span></span>  
 <span data-ttu-id="2d1b5-119">Specificare il numero di connessioni a origini dati e set di dati condivisi di recente da visualizzare nella finestra di dialogo **Proprietà set di dati** e nella pagina **Scegliere una connessione a un'origine dei dati** della procedura guidata Aree dati.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-119">Specify the number of recent shared datasets and data source connections to show in the **Dataset Properties** dialog box and the **Choose a connection to a data source** page of the Data Regions Wizard.</span></span>  
  
 <span data-ttu-id="2d1b5-120">**Mostra questo numero di documenti recenti**</span><span class="sxs-lookup"><span data-stu-id="2d1b5-120">**Show this number of recent documents**</span></span>  
 <span data-ttu-id="2d1b5-121">Specificare il numero di documenti recenti da visualizzare quando si fa clic sul pulsante Generatore report.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-121">Specify the number of recent documents to show when you click the Report Builder button.</span></span>  
  
 <span data-ttu-id="2d1b5-122">**Cancella tutti gli elenchi di elementi recenti**</span><span class="sxs-lookup"><span data-stu-id="2d1b5-122">**Clear all recent item lists**</span></span>  
 <span data-ttu-id="2d1b5-123">Cancellare tutti gli elenchi correnti di siti e server, connessioni ai set di dati condivisi e alle origini dati nonché documenti recenti.</span><span class="sxs-lookup"><span data-stu-id="2d1b5-123">Clear the current lists of recent sites and servers, shared datasets, shared data source connections, and documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d1b5-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d1b5-124">See Also</span></span>  
 [<span data-ttu-id="2d1b5-125">Guida di Generatore report per finestre di dialogo, riquadri e procedure guidate</span><span class="sxs-lookup"><span data-stu-id="2d1b5-125">Report Builder Help for Dialog Boxes, Panes, and Wizards</span></span>](../report-builder-help-for-dialog-boxes-panes-and-wizards.md)  
  
  
