---
title: Rivedere e generare script di registrazione supplementare | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- scripts
ms.assetid: 5c858ae2-37d6-42e8-a252-7f6ed4e628a7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb735c0ee318ac68d48c71c09fc76ec305eb2552
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626842"
---
# <a name="review-and-generate-supplemental-logging-scripts"></a><span data-ttu-id="08bcf-102">Rivedere e generare script di registrazione supplementare</span><span class="sxs-lookup"><span data-stu-id="08bcf-102">Review and Generate Supplemental Logging Scripts</span></span>
  <span data-ttu-id="08bcf-103">Usare la scheda **Scripts** per eseguire o rieseguire uno script nel database di origine Oracle per la configurazione della registrazione supplementare.</span><span class="sxs-lookup"><span data-stu-id="08bcf-103">Use the **Scripts** tab to run or re-run a script on the Oracle source database that sets up supplemental logging.</span></span>  
  
 <span data-ttu-id="08bcf-104">Prima di eseguire gli script selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="08bcf-104">Before you run the scripts select one of the following:</span></span>  
  
 <span data-ttu-id="08bcf-105">**Include changes in this session**</span><span class="sxs-lookup"><span data-stu-id="08bcf-105">**Include changes in this session**</span></span>  
 <span data-ttu-id="08bcf-106">Selezionare questa opzione per eseguire lo script nelle nuove tabelle aggiunte all'istanza di CDC o in quelle modificate tramite l'editor delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="08bcf-106">Select this to run the script on any new table that was added to the CDC instance or on tables that were changed in any way using the Properties editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="08bcf-107">Se le tabelle dell'istanza di CDC non sono state modificate, lo script di registrazione supplementare Oracle sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="08bcf-107">If no changes were made to the tables in the CDC instance, the Oracle supplemental logging script area will be empty.</span></span>  
  
 <span data-ttu-id="08bcf-108">**Include all tables/capture instances**</span><span class="sxs-lookup"><span data-stu-id="08bcf-108">**Include all tables/capture instances**</span></span>  
 <span data-ttu-id="08bcf-109">Selezionare questa opzione per eseguire lo script in tutte le tabelle e le istanze di acquisizione dell'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="08bcf-109">Select this to run the script on all of the tables and capture instances in the CDC instance.</span></span>  
  
 <span data-ttu-id="08bcf-110">Dopo avere selezionato una di queste opzioni, eseguire lo script di registrazione supplementare.</span><span class="sxs-lookup"><span data-stu-id="08bcf-110">After you select one of these options, run the supplemental logging script.</span></span>  
  
### <a name="to-run-the-supplemental-logging-scripts"></a><span data-ttu-id="08bcf-111">Per eseguire gli script di registrazione supplementare</span><span class="sxs-lookup"><span data-stu-id="08bcf-111">To run the supplemental logging scripts</span></span>  
  
1.  <span data-ttu-id="08bcf-112">Fare clic su **Run Script** per eseguire lo script di registrazione supplementare nelle tabelle definite per l'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="08bcf-112">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="08bcf-113">Tramite questo script verranno scritte tutte le colonne di interesse nei log delle transazioni durante la registrazione delle operazioni UPDATE nelle tabelle acquisite.</span><span class="sxs-lookup"><span data-stu-id="08bcf-113">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="08bcf-114">Lo script viene in genere esaminato ed eseguito da un amministratore di sistema Oracle.</span><span class="sxs-lookup"><span data-stu-id="08bcf-114">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
2.  <span data-ttu-id="08bcf-115">Quando si eseguono gli script di registrazione supplementare, viene visualizzata la finestra di dialogo Oracle Credentials for Running Script in cui immettere un nome utente e una password Oracle validi.</span><span class="sxs-lookup"><span data-stu-id="08bcf-115">When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="08bcf-116">Per informazioni su come fornire le credenziali Oracle appropriate, vedere [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="08bcf-116">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
 <span data-ttu-id="08bcf-117">Se necessario, è anche possibile eseguire gli script manualmente tramite SQL \* Plus.</span><span class="sxs-lookup"><span data-stu-id="08bcf-117">You can also run the scripts manually using SQL \* Plus, if necessary.</span></span>  
  
### <a name="to-run-the-scripts-manually"></a><span data-ttu-id="08bcf-118">Per eseguire gli script manualmente</span><span class="sxs-lookup"><span data-stu-id="08bcf-118">To run the scripts manually</span></span>  
  
1.  <span data-ttu-id="08bcf-119">Scegliere **Copy** per incollare lo script negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="08bcf-119">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="08bcf-120">Aprire SQL\* Plus e accedere alla directory contenente il database di origine Oracle.</span><span class="sxs-lookup"><span data-stu-id="08bcf-120">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="08bcf-121">Incollare lo script in SQL\*Plus per eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="08bcf-121">Paste the script into SQL\*Plus to run it.</span></span>  
  
### <a name="to-save-the-supplemental-logging-script-in-a-text-file"></a><span data-ttu-id="08bcf-122">Per salvare lo script di registrazione supplementare in un file di testo</span><span class="sxs-lookup"><span data-stu-id="08bcf-122">To save the supplemental logging script in a text file</span></span>  
  
1.  <span data-ttu-id="08bcf-123">Scegliere **Save as** e accedere al percorso in cui si desidera salvare il file.</span><span class="sxs-lookup"><span data-stu-id="08bcf-123">Click **Save as** and browse to the location where you want to save the file.</span></span>  
  
2.  <span data-ttu-id="08bcf-124">Assegnare un nome al file e scegliere **Save** per salvarlo.</span><span class="sxs-lookup"><span data-stu-id="08bcf-124">Give the file a name and click **Save** to save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08bcf-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08bcf-125">See Also</span></span>  
 <span data-ttu-id="08bcf-126">[Procedura di modifica delle proprietà dell'istanza di CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="08bcf-126">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="08bcf-127">Credenziali Oracle per l'esecuzione di script</span><span class="sxs-lookup"><span data-stu-id="08bcf-127">Oracle Credentials for Running Script</span></span>](oracle-credentials-for-running-script.md)  
  
  
