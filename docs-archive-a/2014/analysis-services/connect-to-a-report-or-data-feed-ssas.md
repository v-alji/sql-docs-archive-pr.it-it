---
title: Connettersi a un report o a un feed di dati (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connreportdatafeed.f1
ms.assetid: e0ccfb0b-e646-4de8-b7da-f88c986c96e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76dd51c32d13e64b0368267ba7ac66aa6d76a784
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625718"
---
# <a name="connect-to-a-report-or-data-feed-ssas"></a><span data-ttu-id="e921f-102">Connettersi a un report o a un feed di dati (SSAS)</span><span class="sxs-lookup"><span data-stu-id="e921f-102">Connect to a Report or Data Feed (SSAS)</span></span>
  <span data-ttu-id="e921f-103">Questa pagina dell' **Importazione guidata tabella** consente di connettersi a un feed di dati.</span><span class="sxs-lookup"><span data-stu-id="e921f-103">This page of the **Table Import Wizard** enables you to connect to a data feed.</span></span> <span data-ttu-id="e921f-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="e921f-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
## <a name="from-a-report"></a><span data-ttu-id="e921f-105">Da un report</span><span class="sxs-lookup"><span data-stu-id="e921f-105">From a Report</span></span>  
 <span data-ttu-id="e921f-106">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="e921f-106">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="e921f-107">Digitare un nome descrittivo per la connessione al feed di dati.</span><span class="sxs-lookup"><span data-stu-id="e921f-107">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="e921f-108">**Percorso report**</span><span class="sxs-lookup"><span data-stu-id="e921f-108">**Report Path**</span></span>  
 <span data-ttu-id="e921f-109">Elenca l'URL per un report di SQL Server Reporting Services che genera feed di dati.</span><span class="sxs-lookup"><span data-stu-id="e921f-109">Lists the URL for a SQL Server Reporting Services report that generates data feeds.</span></span> <span data-ttu-id="e921f-110">Fare clic su **Sfoglia** per specificare l'URL per il report.</span><span class="sxs-lookup"><span data-stu-id="e921f-110">Click **Browse** to specify the URL for the report.</span></span>  
  
 <span data-ttu-id="e921f-111">Fare clic su **Visualizza report** per visualizzare il report.</span><span class="sxs-lookup"><span data-stu-id="e921f-111">Click **View Report** to display the report.</span></span>  
  
 <span data-ttu-id="e921f-112">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="e921f-112">**Browse**</span></span>  
 <span data-ttu-id="e921f-113">Passare al percorso in cui è disponibile un report.</span><span class="sxs-lookup"><span data-stu-id="e921f-113">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="e921f-114">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="e921f-114">**Advanced**</span></span>  
 <span data-ttu-id="e921f-115">Impostare altre proprietà relative alla connessione tramite la finestra di dialogo **Impostazione delle proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="e921f-115">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="e921f-116">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="e921f-116">**Test Connection**</span></span>  
 <span data-ttu-id="e921f-117">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="e921f-117">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="e921f-118">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="e921f-118">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-an-azure-datamarket-dataset"></a><span data-ttu-id="e921f-119">Da un set di dati di Azure DataMarket</span><span class="sxs-lookup"><span data-stu-id="e921f-119">From an Azure DataMarket Dataset</span></span>  
 <span data-ttu-id="e921f-120">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="e921f-120">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="e921f-121">Digitare un nome descrittivo per la connessione al feed di dati.</span><span class="sxs-lookup"><span data-stu-id="e921f-121">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="e921f-122">**URL feed di dati**</span><span class="sxs-lookup"><span data-stu-id="e921f-122">**Data Feed URL**</span></span>  
 <span data-ttu-id="e921f-123">Digitare il percorso completo di un documento di servizio Atom (estensione atomsvc o atom) o l'URL per un solo feed di dati oppure fare clic su **Sfoglia** per selezionare un documento di servizio Atom.</span><span class="sxs-lookup"><span data-stu-id="e921f-123">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="e921f-124">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="e921f-124">**Browse**</span></span>  
 <span data-ttu-id="e921f-125">Passare al percorso in cui è disponibile un report.</span><span class="sxs-lookup"><span data-stu-id="e921f-125">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="e921f-126">Fare clic su **Visualizza set di dati disponibili di DataMarket Azure** per visualizzare i set di dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="e921f-126">Click **View available Azure DataMarket datasets** to display available datasets.</span></span>  
  
 <span data-ttu-id="e921f-127">**Chiave dell'account**</span><span class="sxs-lookup"><span data-stu-id="e921f-127">**Account key**</span></span>  
 <span data-ttu-id="e921f-128">Specificare la chiave dell'account usata per accedere alle sottoscrizioni del set di dati di Azure Marketplace.</span><span class="sxs-lookup"><span data-stu-id="e921f-128">Specify the account key used to access your Azure Marketplace dataset subscriptions.</span></span>  
  
 <span data-ttu-id="e921f-129">**Trovare**</span><span class="sxs-lookup"><span data-stu-id="e921f-129">**Find**</span></span>  
 <span data-ttu-id="e921f-130">Individuare una chiave di account associata a un account di Windows Live.</span><span class="sxs-lookup"><span data-stu-id="e921f-130">Locate an account key associated with a Windows Live account.</span></span>  
  
 <span data-ttu-id="e921f-131">**Salva chiave account**</span><span class="sxs-lookup"><span data-stu-id="e921f-131">**Save my account key**</span></span>  
 <span data-ttu-id="e921f-132">Salvare la chiave di account (crittografata) con la connessione dati.</span><span class="sxs-lookup"><span data-stu-id="e921f-132">Saves the account key (encrypted) with the data connection.</span></span>  
  
 <span data-ttu-id="e921f-133">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="e921f-133">**Advanced**</span></span>  
 <span data-ttu-id="e921f-134">Impostare altre proprietà relative alla connessione tramite la finestra di dialogo **Impostazione delle proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="e921f-134">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="e921f-135">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="e921f-135">**Test Connection**</span></span>  
 <span data-ttu-id="e921f-136">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="e921f-136">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="e921f-137">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="e921f-137">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-other-feeds"></a><span data-ttu-id="e921f-138">Dagli altri feed</span><span class="sxs-lookup"><span data-stu-id="e921f-138">From Other Feeds</span></span>  
 <span data-ttu-id="e921f-139">**Nome descrittivo connessione**</span><span class="sxs-lookup"><span data-stu-id="e921f-139">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="e921f-140">Digitare un nome descrittivo per la connessione al feed di dati.</span><span class="sxs-lookup"><span data-stu-id="e921f-140">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="e921f-141">**URL feed di dati**</span><span class="sxs-lookup"><span data-stu-id="e921f-141">**Data Feed URL**</span></span>  
 <span data-ttu-id="e921f-142">Digitare il percorso completo di un documento di servizio Atom (estensione atomsvc o atom) o l'URL per un solo feed di dati oppure fare clic su **Sfoglia** per selezionare un documento di servizio Atom.</span><span class="sxs-lookup"><span data-stu-id="e921f-142">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="e921f-143">Fare clic su **Includi sempre +++tutte le colonne di feed** per specificare se importare tutte le colonne di feed di dati.</span><span class="sxs-lookup"><span data-stu-id="e921f-143">Click **Include all feed columns** to specify whether all the data feed columns are imported.</span></span>  
  
 <span data-ttu-id="e921f-144">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="e921f-144">**Browse**</span></span>  
 <span data-ttu-id="e921f-145">Passare al percorso in cui è disponibile un feed di dati.</span><span class="sxs-lookup"><span data-stu-id="e921f-145">Navigate to a location where a data feed is available.</span></span>  
  
 <span data-ttu-id="e921f-146">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="e921f-146">**Advanced**</span></span>  
 <span data-ttu-id="e921f-147">Per impostare ulteriori proprietà della connessione, utilizzare la finestra di dialogo **Imposta proprietà avanzate** .</span><span class="sxs-lookup"><span data-stu-id="e921f-147">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="e921f-148">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="e921f-148">**Test Connection**</span></span>  
 <span data-ttu-id="e921f-149">Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="e921f-149">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="e921f-150">Viene visualizzato un messaggio che indica se la connessione è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="e921f-150">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
