---
title: MSSQLSERVER_21893 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21893 (Database Engine error)
ms.assetid: 1ab1195a-fe2a-4e06-b871-b177b6bea1fe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 92479d7727ac2300d6a60d02492667d99a69b022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635647"
---
# <a name="mssqlserver_21893"></a><span data-ttu-id="5dff8-102">MSSQLSERVER_21893</span><span class="sxs-lookup"><span data-stu-id="5dff8-102">MSSQLSERVER_21893</span></span>
    
## <a name="details"></a><span data-ttu-id="5dff8-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5dff8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5dff8-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="5dff8-104">Product Name</span></span>|<span data-ttu-id="5dff8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5dff8-105">SQL Server</span></span>|  
|<span data-ttu-id="5dff8-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="5dff8-106">Event ID</span></span>|<span data-ttu-id="5dff8-107">21893</span><span class="sxs-lookup"><span data-stu-id="5dff8-107">21893</span></span>|  
|<span data-ttu-id="5dff8-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="5dff8-108">Event Source</span></span>|<span data-ttu-id="5dff8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5dff8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5dff8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5dff8-110">Component</span></span>|<span data-ttu-id="5dff8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5dff8-111">SQLEngine</span></span>|  
|<span data-ttu-id="5dff8-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="5dff8-112">Symbolic Name</span></span>|<span data-ttu-id="5dff8-113">SQLErrorNum21893</span><span class="sxs-lookup"><span data-stu-id="5dff8-113">SQLErrorNum21893</span></span>|  
|<span data-ttu-id="5dff8-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5dff8-114">Message Text</span></span>|<span data-ttu-id="5dff8-115">I sottoscrittori (%s) del server di pubblicazione originale '%s' non sembrano server remoti per il server di pubblicazione reindirizzato '%s.'</span><span class="sxs-lookup"><span data-stu-id="5dff8-115">The subscribers ( %s ) of original publisher '%s' do not appear as remote servers at redirected publisher '%s'.</span></span> <span data-ttu-id="5dff8-116">Eseguire `sp_addlinkedserver` nel server di pubblicazione reindirizzato per aggiungere questi sottoscrittori come server remoti.</span><span class="sxs-lookup"><span data-stu-id="5dff8-116">Run `sp_addlinkedserver` at the redirected publisher to add these subscribers as remote servers .</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5dff8-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5dff8-117">Explanation</span></span>  
 <span data-ttu-id="5dff8-118">`sp_validate_redirected_publisher`Nel  vengono utilizzate le tabelle di metadati della sottoscrizione del database del server di pubblicazione sul server remoto per identificare i sottoscrittori associati e viene verificato che vi siano voci associate in master.dbo.sysservers per i sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="5dff8-118">`sp_validate_redirected_publisher` uses the subscription metadata tables of the publisher database at the remote server to identify its associated subscribers and verifies that there are associated entries in master.dbo.sysservers for the subscribers.</span></span> <span data-ttu-id="5dff8-119">Questo errore viene restituito se uno dei sottoscrittori identificato non è presente.</span><span class="sxs-lookup"><span data-stu-id="5dff8-119">This error is returned if any of the identified subscribers are not present.</span></span>  
  
 <span data-ttu-id="5dff8-120">Questo errore non è considerato un errore irreversibile.</span><span class="sxs-lookup"><span data-stu-id="5dff8-120">This error is not considered a fatal error.</span></span> <span data-ttu-id="5dff8-121">Gli agenti che rilevano questo errore lo registreranno come messaggio di errore informativo ma non termineranno, poiché un errore, per avere voci del sottoscrittore appropriate sul nuovo server di pubblicazione, ha un impatto limitato sulla replica.</span><span class="sxs-lookup"><span data-stu-id="5dff8-121">Agents encountering this error will log the error as informational but will not terminate, since a failure to have appropriate subscriber entries at the new publisher has limited impact on replication.</span></span> <span data-ttu-id="5dff8-122">Senza una voce adatta per un Sottoscrittore in sysservers, è possibile che alcune attività di gestione delle sottoscrizioni non riescano se vengono eseguite tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dff8-122">Without an appropriate entry for a subscriber in sysservers, some subscription management activities may fail when executed through [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="5dff8-123">Tuttavia, è possibile eseguire queste stesse attività correttamente eseguendo in modo esplicito le stored procedure di gestione.</span><span class="sxs-lookup"><span data-stu-id="5dff8-123">However, these same activities can be successfully performed by executing the management stored procedures explicitly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5dff8-124">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="5dff8-124">User Action</span></span>  
 <span data-ttu-id="5dff8-125">Eseguire `sp_addlinkedserver` sul server di pubblicazione reindirizzato per tutti i sottoscrittori identificati per aggiungerli come server remoti.</span><span class="sxs-lookup"><span data-stu-id="5dff8-125">Run `sp_addlinkedserver` at the redirected publisher for each of the identified subscribers to add them as remote servers.</span></span> <span data-ttu-id="5dff8-126">Quindi, eseguire `sp_serveroption` per impostare il bit del sottoscrittore per il server.</span><span class="sxs-lookup"><span data-stu-id="5dff8-126">Then, run `sp_serveroption` to set the subscriber bit for the server.</span></span>  
  
  
