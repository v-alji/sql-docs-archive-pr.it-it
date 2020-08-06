---
title: Filtrare i dati pubblicati per la replica di tipo merge | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication [SQL Server replication], filtering published data
- replication [SQL Server], filtering published data
ms.assetid: 46c5023d-7a3b-4455-becc-e159fcb5d6c4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ad9ad45a64f57a6bef8255373180ea943af9893f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623206"
---
# <a name="filter-published-data-for-merge-replication"></a><span data-ttu-id="644f5-102">Filtro dei dati pubblicati per la replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="644f5-102">Filter Published Data for Merge Replication</span></span>
  <span data-ttu-id="644f5-103">Oltre ai filtri di riga e di colonna statici che è possibile definire con altri tipi di replica, la replica di tipo merge offre filtri di riga con parametri e filtri join.</span><span class="sxs-lookup"><span data-stu-id="644f5-103">In addition to the static row filters and column filters you can define with other types of replication, merge replication offers parameterized row filters and join filters.</span></span> <span data-ttu-id="644f5-104">Per altre informazioni sui filtri di riga e di colonna statici, vedere [Filtrare i dati pubblicati](../publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="644f5-104">For more information about static row filters and column filters, see [Filter Published Data](../publish/filter-published-data.md).</span></span>  
  
 <span data-ttu-id="644f5-105">La replica di tipo merge viene utilizzata in molte applicazioni che supportano gli utenti mobili. Tali applicazioni hanno in genere un gran numero di sottoscrizioni ognuna delle quali riceve un set di dati univoco.</span><span class="sxs-lookup"><span data-stu-id="644f5-105">Merge replication is used in many applications that support mobile users; these applications usually have a large number of subscriptions with each subscription receiving a unique data set.</span></span> <span data-ttu-id="644f5-106">I filtri con parametri combinati con i filtri join consentono a un amministratore di impostare una pubblicazione (o un numero limitato di pubblicazioni) e di fornire set di dati diversi agli utenti, riducendo l'overhead di gestione introdotto con la creazione di più pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="644f5-106">Parameterized filters combined with join filters allow an administrator to set up one publication (or at most a small number of publications) and yet provide different data sets to users, reducing the management overhead introduced by creating multiple publications.</span></span>  
  
-   <span data-ttu-id="644f5-107">I filtri con parametri consentono l'invio di partizioni diverse di dati a Sottoscrittori diversi senza richiedere la creazione di più pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="644f5-107">Parameterized filters allow different partitions of data to be sent to different Subscribers without requiring multiple publications to be created.</span></span> <span data-ttu-id="644f5-108">Ad esempio, è possibile filtrare una tabella in modo che i dati di uno specifico rappresentante vengano replicati solo a tale rappresentante.</span><span class="sxs-lookup"><span data-stu-id="644f5-108">For example, a table can be filtered so that data for a given sales representative is replicated only to that representative.</span></span> <span data-ttu-id="644f5-109">I filtri con parametri hanno una varietà di opzioni che consentono di personalizzare il filtraggio per ottimizzare le prestazioni e adattarsi ai dati e ai requisiti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="644f5-109">Parameterized filters have a variety of options that allow you to tailor filtering to optimize performance and best match your data and application requirements.</span></span> <span data-ttu-id="644f5-110">Per altre informazioni sui filtri di riga con parametri, vedere [Filtri di riga con parametri](parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="644f5-110">For more information, see [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span></span>  
  
-   <span data-ttu-id="644f5-111">I filtri join sono utilizzati insieme ai filtri con parametri per estendere il filtraggio alle tabelle correlate e possono essere utilizzati anche insieme ai filtri statici.</span><span class="sxs-lookup"><span data-stu-id="644f5-111">Join filters are typically used in conjunction with parameterized filters to extend filtering to related tables (they can also be used in conjunction with static filters).</span></span> <span data-ttu-id="644f5-112">Ad esempio, il rappresentante in genere dispone di dati in altre tabelle, ad esempio le tabelle relative a clienti e ordini.</span><span class="sxs-lookup"><span data-stu-id="644f5-112">For example, the sales representative typically has data in other tables such as customer and order tables.</span></span> <span data-ttu-id="644f5-113">Questi dati possono essere filtrati in modo che il rappresentante riceva solo i dati relativi ai clienti e ai rispettivi ordini.</span><span class="sxs-lookup"><span data-stu-id="644f5-113">This data can be filtered so the sales representative receives only the data on her customers and her customers' orders.</span></span> <span data-ttu-id="644f5-114">Per altre informazioni, vedere [Join Filters](join-filters.md).</span><span class="sxs-lookup"><span data-stu-id="644f5-114">For more information, see [Join Filters](join-filters.md).</span></span>  
  
 <span data-ttu-id="644f5-115">In un filtro non deve essere inclusa la colonna `rowguidcol` utilizzata dalla replica per identificare le righe.</span><span class="sxs-lookup"><span data-stu-id="644f5-115">A filter must not include the `rowguidcol` used by replication to identify rows.</span></span> <span data-ttu-id="644f5-116">Per impostazione predefinita, si tratta della colonna aggiunta al momento dell'impostazione della replica di tipo merge ed è denominata **rowguid**.</span><span class="sxs-lookup"><span data-stu-id="644f5-116">By default this is the column added at the time you set up merge replication and is named **rowguid**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="644f5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="644f5-117">See Also</span></span>  
 [<span data-ttu-id="644f5-118">Pubblicare dati e oggetti di database</span><span class="sxs-lookup"><span data-stu-id="644f5-118">Publish Data and Database Objects</span></span>](../publish/publish-data-and-database-objects.md)  
  
  
