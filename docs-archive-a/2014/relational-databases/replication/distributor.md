---
title: Database di distribuzione | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.selectdistributor.f1
ms.assetid: 787f0e9c-09dd-438a-bc04-5b8f99c127b8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c601a540088b5cd9d7a2033510a5cf9b83c3170e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624616"
---
# <a name="distributor"></a><span data-ttu-id="d14ed-102">Database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="d14ed-102">Distributor</span></span>
  <span data-ttu-id="d14ed-103">La pagina **Server di distribuzione** viene visualizzata nella Configurazione guidata distribuzione e nella Creazione guidata nuova pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="d14ed-103">The **Distributor** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="d14ed-104">Il server di distribuzione è il server che contiene il database di distribuzione e che gestisce l'archiviazione dei metadati e dei dati di cronologia per tutti i tipi di replica.</span><span class="sxs-lookup"><span data-stu-id="d14ed-104">The Distributor is a server that contains the distribution database and stores metadata and history data for all types of replication.</span></span> <span data-ttu-id="d14ed-105">Il server di distribuzione gestisce inoltre l'archiviazione delle transazioni per la replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="d14ed-105">The Distributor also stores transactions for transactional replication.</span></span> <span data-ttu-id="d14ed-106">Il server di distribuzione può corrispondere al server di pubblicazione (server di distribuzione locale) o essere un server distinto (server di distribuzione remoto).</span><span class="sxs-lookup"><span data-stu-id="d14ed-106">The Distributor can be the same server as the Publisher (a local Distributor) or it can be a separate server from the Publisher (a remote Distributor).</span></span> <span data-ttu-id="d14ed-107">Il ruolo del server di distribuzione varia in base al tipo di replica implementato.</span><span class="sxs-lookup"><span data-stu-id="d14ed-107">The role of the Distributor varies, depending on which type of replication you implement.</span></span> <span data-ttu-id="d14ed-108">In generale, il ruolo del server di distribuzione è più rilevante per la replica transazionale rispetto a quanto non lo sia per la replica di tipo merge e snapshot.</span><span class="sxs-lookup"><span data-stu-id="d14ed-108">In general, its role is much greater for transactional replication than it is for merge replication and snapshot replication.</span></span> <span data-ttu-id="d14ed-109">La replica di tipo merge e la replica snapshot utilizzano normalmente un server di distribuzione locale, mentre la replica transazionale in sistemi sottoposti a un utilizzo particolarmente intensivo possono trarre vantaggio dall'utilizzo di un server di distribuzione remoto.</span><span class="sxs-lookup"><span data-stu-id="d14ed-109">Merge and snapshot replication typically use a local Distributor, but transactional replication on a very busy system can benefit from using a remote Distributor.</span></span>  
  
 <span data-ttu-id="d14ed-110">Il server di distribuzione utilizza le risorse aggiuntive seguenti nel server in cui è installato:</span><span class="sxs-lookup"><span data-stu-id="d14ed-110">The Distributor uses these additional resources on the server where it is located:</span></span>  
  
-   <span data-ttu-id="d14ed-111">Maggiore spazio su disco se i file di snapshot per la pubblicazione sono archiviati al suo interno, così come avviene normalmente.</span><span class="sxs-lookup"><span data-stu-id="d14ed-111">Additional disk space if the snapshot files for the publication are stored on it (which they typically are).</span></span>  
  
-   <span data-ttu-id="d14ed-112">Maggiore spazio su disco per l'archiviazione del database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d14ed-112">Additional disk space to store the distribution database.</span></span>  
  
-   <span data-ttu-id="d14ed-113">Maggior utilizzo del processore da parte degli agenti di replica per le sottoscrizioni push in esecuzione nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d14ed-113">Additional processor usage by replication agents for push subscriptions running on the Distributor.</span></span>  
  
 <span data-ttu-id="d14ed-114">Nel server selezionato come server di distribuzione devono essere disponibili spazio su disco e capacità del processore sufficienti per il supporto delle attività di replica e di altre eventuali operazioni basate su tale server.</span><span class="sxs-lookup"><span data-stu-id="d14ed-114">The server you select as the Distributor should have adequate disk space and processor power to support replication and any other activities on that server.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d14ed-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d14ed-115">Options</span></span>  
 <span data-ttu-id="d14ed-116">**'\<ServerName>' fungerà da database di distribuzione per se stesso. Verranno creati un database di distribuzione e un log**</span><span class="sxs-lookup"><span data-stu-id="d14ed-116">**'\<ServerName>' will act as its own Distributor; SQL Server will create a distribution database and log**</span></span>  
 <span data-ttu-id="d14ed-117">Selezionare questa opzione per configurare il server a cui si è connessi come server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d14ed-117">Select this option to configure the server you are connected to as a Distributor.</span></span>  
  
 <span data-ttu-id="d14ed-118">**Usa il server seguente come server di distribuzione (nota: il server selezionato deve essere già stato configurato come server di distribuzione)**</span><span class="sxs-lookup"><span data-stu-id="d14ed-118">**Use the following server as the Distributor (Note: the server you select must already be configured as a Distributor)**</span></span>  
 <span data-ttu-id="d14ed-119">Selezionare questa opzione e quindi fare clic sul nome di un server elencato per configurare un altro server come server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d14ed-119">Select this option and then click on the name of a server below to configure another server as the Distributor.</span></span>  
  
 <span data-ttu-id="d14ed-120">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="d14ed-120">**Add**</span></span>  
 <span data-ttu-id="d14ed-121">Se il server che si desidera utilizzare non è elencato come server di distribuzione, fare clic su **Aggiungi** per identificare il server e aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="d14ed-121">If the server you want to use as a Distributor is not listed, click **Add** to identify the server and add it to the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d14ed-122">Per utilizzare un server remoto come server di distribuzione è necessario che il server remoto sia già stato configurato come server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d14ed-122">To use a remote server as the Distributor, the remote server must already be configured as a Distributor.</span></span> <span data-ttu-id="d14ed-123">Il server sul quale è in esecuzione la procedura guidata deve essere stato abilitato come server di pubblicazione nel server di distribuzione specifico.</span><span class="sxs-lookup"><span data-stu-id="d14ed-123">The server against which this wizard is running must be enabled as a Publisher on that Distributor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14ed-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d14ed-124">See Also</span></span>  
 <span data-ttu-id="d14ed-125">[Configura distribuzione](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="d14ed-125">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="d14ed-126">Configurare la pubblicazione e la distribuzione</span><span class="sxs-lookup"><span data-stu-id="d14ed-126">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
  
