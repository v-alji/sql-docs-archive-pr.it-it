---
title: Configurare le proprietà di un agente di raccolta dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollectionprop.advanced.f1
- sql12.swb.dc.datacollectionprop.general.f1
ms.assetid: cf98f57d-5a6d-4bc3-bf10-783e460fc63d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05172c2c831ec649269512a625be069cdc67047a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718251"
---
# <a name="configure-properties-of-a-data-collector"></a><span data-ttu-id="1d347-102">Configurare le proprietà di un agente di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="1d347-102">Configure Properties of a Data Collector</span></span>
  <span data-ttu-id="1d347-103">In questo argomento viene descritto come configurare le proprietà di un agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="1d347-103">This topic discusses how you can configure the properties of a data collector.</span></span>  
  
## <a name="data-collection-properties-general-tab"></a><span data-ttu-id="1d347-104">Proprietà raccolta dati (scheda Generale)</span><span class="sxs-lookup"><span data-stu-id="1d347-104">Data Collection Properties (General Tab)</span></span>  
 <span data-ttu-id="1d347-105">Utilizzare questa pagina per configurare le impostazioni per il data warehouse di gestione e specificare la posizione di archiviazione dei dati raccolti prima del caricamento nel data warehouse.</span><span class="sxs-lookup"><span data-stu-id="1d347-105">Use this page to configure settings for the management data warehouse and specify where collected data should be stored before it is uploaded to the data warehouse.</span></span>  
  
 <span data-ttu-id="1d347-106">**Abilita raccolta dati**</span><span class="sxs-lookup"><span data-stu-id="1d347-106">**Enable Data Collection**</span></span>  
 <span data-ttu-id="1d347-107">Selezionare questa opzione per abilitare la raccolta dei dati.</span><span class="sxs-lookup"><span data-stu-id="1d347-107">Select to enable data collection.</span></span> <span data-ttu-id="1d347-108">Questa impostazione equivale all'esecuzione della stored procedure sp_syscollector_enable_collector.</span><span class="sxs-lookup"><span data-stu-id="1d347-108">This has the same effect as running the sp_syscollector_enable_collector stored procedure.</span></span> <span data-ttu-id="1d347-109">La deselezione di questa casella di controllo disabilita la raccolta dei dati ed equivale all'esecuzione della stored procedure sp_syscollector_disable_collector.</span><span class="sxs-lookup"><span data-stu-id="1d347-109">Clearing this check box disables data collection and has the same effect as running the sp_syscollector_disable_collector stored procedure.</span></span>  
  
 <span data-ttu-id="1d347-110">**Server**</span><span class="sxs-lookup"><span data-stu-id="1d347-110">**Server**</span></span>  
 <span data-ttu-id="1d347-111">Visualizza il nome del server che ospiterà il data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="1d347-111">Displays the name of the server that will host the management data warehouse</span></span>  
  
 <span data-ttu-id="1d347-112">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="1d347-112">**Database name**</span></span>  
 <span data-ttu-id="1d347-113">Visualizza il nome del database relazionale utilizzato per il data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="1d347-113">Displays the name of the relational database that is used for the management data warehouse.</span></span>  
  
 <span data-ttu-id="1d347-114">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="1d347-114">**Test Connection**</span></span>  
 <span data-ttu-id="1d347-115">Consente di testare la connessione al **Server** specificato utilizzando le informazioni fornite durante la configurazione della raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="1d347-115">Test the connection to the specified **Server** using information provided when data collection is configured.</span></span>  
  
 <span data-ttu-id="1d347-116">**Directory cache**</span><span class="sxs-lookup"><span data-stu-id="1d347-116">**Cache directory**</span></span>  
 <span data-ttu-id="1d347-117">Specifica la directory in cui vengono archiviati i dati raccolti nel sistema prima di essere caricati nel data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="1d347-117">Specifies the directory where collected data is stored on the system collecting the data before it is uploaded to the management data warehouse.</span></span> <span data-ttu-id="1d347-118">Se la **Directory cache** non è specificata, l'agente di raccolta dati tenta di individuare le variabili di ambiente % TEMP% e % TMP% e utilizza una di queste posizioni come percorso predefinito per l'archiviazione temporanea.</span><span class="sxs-lookup"><span data-stu-id="1d347-118">If **Cache directory** is not specified, the data collector attempts to locate the %TEMP% and %TMP% environment variables and use one these locations as the default location for temporary storage.</span></span> <span data-ttu-id="1d347-119">Se queste variabili di ambiente non sono configurate, si verifica un errore e viene chiesto di creare una directory della cache.</span><span class="sxs-lookup"><span data-stu-id="1d347-119">If these environment variables are not configured, an error occurs and you are prompted to create a cache directory.</span></span>  
  
## <a name="data-collection-properties-advanced-tab"></a><span data-ttu-id="1d347-120">Proprietà raccolta dati (scheda Avanzate)</span><span class="sxs-lookup"><span data-stu-id="1d347-120">Data Collection Properties (Advanced Tab)</span></span>  
 <span data-ttu-id="1d347-121">Utilizzare questa pagina per configurare le impostazioni relative ai tentativi per la connessione al data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="1d347-121">Use this page to configure the retry settings for the connection to the management data warehouse.</span></span>  
  
 <span data-ttu-id="1d347-122">**Numero di tentativi se il caricamento ha esito negativo**</span><span class="sxs-lookup"><span data-stu-id="1d347-122">**Number of times to retry if upload fails**</span></span>  
 <span data-ttu-id="1d347-123">Consente di specificare il numero di volte in cui è possibile ritentare l'esecuzione di un caricamento non riuscito nel data warehouse di gestione.</span><span class="sxs-lookup"><span data-stu-id="1d347-123">Specifies the number of times to retry an upload to the management data warehouse if an upload fails.</span></span> <span data-ttu-id="1d347-124">Il valore predefinito è 1.</span><span class="sxs-lookup"><span data-stu-id="1d347-124">The default is 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d347-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d347-125">See Also</span></span>  
 <span data-ttu-id="1d347-126">[Gestire raccolta dati](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="1d347-126">[Manage Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="1d347-127">Configurazione del data warehouse di gestione &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1d347-127">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
