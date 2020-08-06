---
title: La cartella di lavoro contiene una o più query che aggiornano dati esterni. | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aa65c992-eb41-4032-9e11-a9ba871b6a3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b2095e13d6151c68eb4a3507400dfdb1739564
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628016"
---
# <a name="this-workbook-contains-one-or-more-queries-that-refresh-external-data"></a><span data-ttu-id="7167b-103">La cartella di lavoro contiene una o più query che aggiornano dati esterni.</span><span class="sxs-lookup"><span data-stu-id="7167b-103">This workbook contains one or more queries that refresh external data.</span></span>
  <span data-ttu-id="7167b-104">Per le cartelle di lavoro di Excel contenenti dati PowerPivot, in Excel Services viene visualizzato questo avviso quando vengono rilevate le informazioni di connessione e viene richiesto di abilitare o disabilitare le query per questa cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7167b-104">For Excel workbooks that contain PowerPivot data, Excel Services shows this warning when it detects connection information and prompts you to enable or disable queries for this workbook.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7167b-105">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7167b-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7167b-106">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="7167b-106">Product Name</span></span>|<span data-ttu-id="7167b-107">PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="7167b-107">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="7167b-108">Versione prodotto</span><span class="sxs-lookup"><span data-stu-id="7167b-108">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="7167b-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7167b-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="7167b-110">Causa</span><span class="sxs-lookup"><span data-stu-id="7167b-110">Cause</span></span>|<span data-ttu-id="7167b-111">Excel Services è configurato per avvisare in caso di aggiornamento dati.</span><span class="sxs-lookup"><span data-stu-id="7167b-111">Excel Services is configured to warn on data refresh.</span></span>|  
|<span data-ttu-id="7167b-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="7167b-112">Message Text</span></span>|<span data-ttu-id="7167b-113">La cartella di lavoro contiene una o più query che aggiornano dati esterni.</span><span class="sxs-lookup"><span data-stu-id="7167b-113">This workbook contains one or more queries that refresh external data.</span></span> <span data-ttu-id="7167b-114">Un utente malintenzionato potrebbe creare una query per accedere a informazioni riservate e distribuirle ad altri utenti o eseguire altre azioni dannose.</span><span class="sxs-lookup"><span data-stu-id="7167b-114">A malicious user can design a query to access confidential information and distribute it to other users or perform other harmful actions.</span></span><br /><br /> <span data-ttu-id="7167b-115">Se la cartella di lavoro proviene da una fonte attendibile, fare clic su Sì per consentire le query su dati esterni nella cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7167b-115">If you trust the source of this workbook, click Yes to enable queries to external data in this workbook.</span></span> <span data-ttu-id="7167b-116">In caso contrario, fare clic su No in modo che le modifiche non vengano applicate alla cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7167b-116">If you are not sure, click No so that changes are not applied to your workbook.</span></span><br /><br /> <span data-ttu-id="7167b-117">Consentire le query su dati esterni nella cartella di lavoro?</span><span class="sxs-lookup"><span data-stu-id="7167b-117">Do you want to enable queries to external data in this workbook?</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7167b-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="7167b-118">Explanation</span></span>  
 <span data-ttu-id="7167b-119">Le cartelle di lavoro di PowerPivot contengono stringhe di connessione dati incorporate utilizzate da Excel per comunicare con un server PowerPivot esterno che carica e calcola i dati.</span><span class="sxs-lookup"><span data-stu-id="7167b-119">PowerPivot workbooks contain embedded data connection strings that are used by Excel to communicate with an external PowerPivot server that loads and calculates the data.</span></span> <span data-ttu-id="7167b-120">Quando l'avviso in caso di aggiornamento dati è abilitato, Excel Services rileva questa stringa di connessione e avvisa l'utente di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="7167b-120">When warn on data refresh is enabled, Excel Services detects this connection string and warns the user accordingly.</span></span>  
  
 <span data-ttu-id="7167b-121">Per filtrare e sezionare i dati PowerPivot nella cartella di lavoro, le query devono essere abilitate.</span><span class="sxs-lookup"><span data-stu-id="7167b-121">To filter and slice PowerPivot data in the workbook, queries must be enabled.</span></span> <span data-ttu-id="7167b-122">Assicurarsi di abilitare le query solo per le cartelle di lavoro di PowerPivot attendibili.</span><span class="sxs-lookup"><span data-stu-id="7167b-122">Be sure that you enable queries for only those PowerPivot workbooks that you trust.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7167b-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7167b-123">User Action</span></span>  
 <span data-ttu-id="7167b-124">Fare clic su **Sì** per abilitare le query.</span><span class="sxs-lookup"><span data-stu-id="7167b-124">Click **Yes** to enable queries.</span></span>  
  
 <span data-ttu-id="7167b-125">È anche possibile modificare le impostazioni di configurazione in modo da non ricevere più l'avviso in caso di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="7167b-125">You can also change the configuration settings so that warn on refresh no longer occurs:</span></span>  
  
1.  <span data-ttu-id="7167b-126">In Gestione applicazioni di Amministrazione centrale fare clic su **Gestisci applicazioni di servizio**.</span><span class="sxs-lookup"><span data-stu-id="7167b-126">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="7167b-127">Fare clic su **Applicazione Excel Services**.</span><span class="sxs-lookup"><span data-stu-id="7167b-127">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="7167b-128">Fare clic su **Posizione attendibile file**.</span><span class="sxs-lookup"><span data-stu-id="7167b-128">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="7167b-129">Fare clic su **http://** o sul percorso che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="7167b-129">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="7167b-130">In Dati esterni deselezionare la casella di controllo per **Avvisa in caso di aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="7167b-130">In External Data, clear the checkbox for **Warn on data refresh**.</span></span>  
  
6.  <span data-ttu-id="7167b-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7167b-131">Click **OK**.</span></span>  
  
 <span data-ttu-id="7167b-132">In alternativa, è possibile creare un nuovo percorso attendibile per i siti che contengono cartelle di lavoro di PowerPivot, quindi modificare le impostazioni di configurazione solo per questo sito.</span><span class="sxs-lookup"><span data-stu-id="7167b-132">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="7167b-133">Per altre informazioni, vedere [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="7167b-133">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
