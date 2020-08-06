---
title: Genera script SQL (oggetti di replica) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.generatesqlscript.f1
helpviewer_keywords:
- Generate SQL Script dialog box
ms.assetid: b7ccc34e-1c22-44b8-8eb5-f6423af3164e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 31a4b318eb3a4c0e5d9f79f43efdcf97c42957f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624593"
---
# <a name="generate-sql-script-replication-objects"></a><span data-ttu-id="e96c2-102">Genera script SQL (oggetti di replica)</span><span class="sxs-lookup"><span data-stu-id="e96c2-102">Generate SQL Script (Replication Objects)</span></span>
  <span data-ttu-id="e96c2-103">In uno script di replica sono incluse le stored procedure di sistema [!INCLUDE[tsql](../../includes/tsql-md.md)] necessarie per l'implementazione dei componenti di replica selezionati per lo script, ad esempio una pubblicazione o una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="e96c2-103">A replication script contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures necessary to implement the replication components scripted, such as a publication or subscription.</span></span> <span data-ttu-id="e96c2-104">Gli script di tutti i componenti di replica inclusi in una topologia devono essere creati come parte di un piano di ripristino di emergenza. Gli script possono inoltre essere utilizzati per automatizzare attività ripetitive.</span><span class="sxs-lookup"><span data-stu-id="e96c2-104">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="e96c2-105">Sono disponibili due finestre di dialogo per lo script di oggetti di replica:</span><span class="sxs-lookup"><span data-stu-id="e96c2-105">Replication offers two dialog boxes for scripting replication objects:</span></span>  
  
-   <span data-ttu-id="e96c2-106">**Genera script SQL**, disponibile dal menu di scelta rapida della cartella **Replica** e da tutte le sottocartelle in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e96c2-106">**Generate SQL Script**, which is available from the context menu of the **Replication** folder and all subfolders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="e96c2-107">Questa finestra di dialogo consente di creare lo script di tutti gli oggetti di replica in un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e96c2-107">This dialog box allows you to script all replication objects on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="e96c2-108">**Genera script SQL \<ObjectName>** , disponibile nel menu di scelta rapida associato a pubblicazioni e sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="e96c2-108">**Generate SQL Script \<ObjectName>**, which is available from the context menu for publications and subscriptions.</span></span> <span data-ttu-id="e96c2-109">Questa finestra di dialogo consente di creare lo script di singoli oggetti.</span><span class="sxs-lookup"><span data-stu-id="e96c2-109">This dialog box allows you to script individual objects.</span></span>  
  
 <span data-ttu-id="e96c2-110">Queste finestre di dialogo consentono di creare lo script di oggetti in una singola istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ma non di stabilire connessioni ad altre istanze per generare lo script degli oggetti correlati.</span><span class="sxs-lookup"><span data-stu-id="e96c2-110">These dialog boxes script objects on a single instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they do not connect to other instances to script related objects.</span></span>  
  
## <a name="generate-sql-script-options"></a><span data-ttu-id="e96c2-111">Opzioni Genera script SQL</span><span class="sxs-lookup"><span data-stu-id="e96c2-111">Generate SQL Script Options</span></span>  
 <span data-ttu-id="e96c2-112">**Proprietà server di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="e96c2-112">**Distributor properties**</span></span>  
 <span data-ttu-id="e96c2-113">Selezionare questa opzione per creare script di stored procedure che consentano di attivare o disabilitare il server di distribuzione, aggiungere o eliminare i server di pubblicazione associati a quello di distribuzione e creare o rimuovere il database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e96c2-113">Select to script stored procedures to: enable or disable the Distributor; add or drop Publishers associated with the Distributor; and create or drop the distribution database.</span></span>  
  
 <span data-ttu-id="e96c2-114">**Pubblicazioni nelle origini dei dati seguenti**</span><span class="sxs-lookup"><span data-stu-id="e96c2-114">**Publications in the following data sources**</span></span>  
 <span data-ttu-id="e96c2-115">Selezionare questa opzione per creare script di stored procedure che consentano di attivare o disabilitare la pubblicazione e creare o eliminare pubblicazioni, articoli, sottoscrizioni push e processi di replica.</span><span class="sxs-lookup"><span data-stu-id="e96c2-115">Select to script stored procedures to: enable or disable publishing; and create or drop publications, articles, push subscriptions, and replication jobs.</span></span>  
  
 <span data-ttu-id="e96c2-116">**Sottoscrizioni nelle origini dei dati seguenti**</span><span class="sxs-lookup"><span data-stu-id="e96c2-116">**Subscriptions in the following data sources**</span></span>  
 <span data-ttu-id="e96c2-117">Selezionare questa opzione per creare lo script di stored procedure che consentano di creare o eliminare sottoscrizioni pull e processi di replica.</span><span class="sxs-lookup"><span data-stu-id="e96c2-117">Select to script stored procedures to create or drop pull subscriptions and replication jobs.</span></span>  
  
 <span data-ttu-id="e96c2-118">**Per creare o attivare i componenti** e **Per rimuovere o disabilitare i componenti**</span><span class="sxs-lookup"><span data-stu-id="e96c2-118">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="e96c2-119">Specificare se nello script devono essere inclusi i comandi per la creazione o la rimozione di un oggetto di replica.</span><span class="sxs-lookup"><span data-stu-id="e96c2-119">Specify whether the script should include commands for creating or dropping a replication object.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="e96c2-120">consiglia di utilizzare questa finestra di dialogo per creare un set di script che consenta di attivare e disabilitare i componenti.</span><span class="sxs-lookup"><span data-stu-id="e96c2-120">recommends that you use the dialog box to create a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="e96c2-121">**Processi di replica**</span><span class="sxs-lookup"><span data-stu-id="e96c2-121">**Replication jobs**</span></span>  
 <span data-ttu-id="e96c2-122">Selezionare questa opzione per creare lo script dei processi di replica oltre a quello delle chiamate di stored procedure.</span><span class="sxs-lookup"><span data-stu-id="e96c2-122">Select to script replication jobs in addition to stored procedure calls.</span></span> <span data-ttu-id="e96c2-123">Questa opzione è disponibile solo quando si crea lo script da un server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e96c2-123">This option is available only when scripting from a Distributor.</span></span>  
  
 <span data-ttu-id="e96c2-124">Le stored procedure di replica creano i processi necessari al momento dell'esecuzione e non è pertanto necessario selezionare l'opzione.</span><span class="sxs-lookup"><span data-stu-id="e96c2-124">Replication stored procedures create the necessary jobs when they are executed, so it is not required to select this option.</span></span> <span data-ttu-id="e96c2-125">Può tuttavia risultare utile disporre di un record dei processi creati in caso sia necessario ricreare un singolo processo.</span><span class="sxs-lookup"><span data-stu-id="e96c2-125">However, it can be useful to have a record of the jobs created in case an individual job must be recreated.</span></span>  
  
## <a name="generate-sql-script-objectname-options"></a><span data-ttu-id="e96c2-126">Opzioni di Genera script SQL - \<ObjectName></span><span class="sxs-lookup"><span data-stu-id="e96c2-126">Generate SQL Script \<ObjectName> Options</span></span>  
 <span data-ttu-id="e96c2-127">**Per creare o attivare i componenti** e **Per rimuovere o disabilitare i componenti**</span><span class="sxs-lookup"><span data-stu-id="e96c2-127">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="e96c2-128">Specificare se nello script devono essere inclusi i comandi per la creazione o la rimozione di un oggetto di replica.</span><span class="sxs-lookup"><span data-stu-id="e96c2-128">Specify whether the script should include commands for creating or dropping a replication object.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="e96c2-129">consiglia di utilizzare la finestra di dialogo, creando un set di script che consenta di attivare e disabilitare i componenti.</span><span class="sxs-lookup"><span data-stu-id="e96c2-129">recommends that you use the dialog box, creating a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="e96c2-130">**Processi di replica**</span><span class="sxs-lookup"><span data-stu-id="e96c2-130">**Replication jobs**</span></span>  
 <span data-ttu-id="e96c2-131">Questa opzione è disponibile solo dalla finestra di dialogo **Genera script SQL** .</span><span class="sxs-lookup"><span data-stu-id="e96c2-131">This option is available only from the **Generate SQL Script** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e96c2-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e96c2-132">See Also</span></span>  
 [<span data-ttu-id="e96c2-133">Creazione di script di replica</span><span class="sxs-lookup"><span data-stu-id="e96c2-133">Scripting Replication</span></span>](scripting-replication.md)  
  
  
