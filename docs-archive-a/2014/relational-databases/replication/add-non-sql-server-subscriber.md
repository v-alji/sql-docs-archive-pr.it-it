---
title: Aggiungere un Sottoscrittore non SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.addnonsqlsubscriber.f1
ms.assetid: 21beeaa0-4b9e-48da-be63-1b9ff14e03d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e36d048b11fcc71b27ab0ab2ee815b0284187c4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629371"
---
# <a name="add-non-sql-server-subscriber"></a><span data-ttu-id="9ffe9-102">Aggiungi Sottoscrittore non SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ffe9-102">Add Non-SQL Server Subscriber</span></span>
  <span data-ttu-id="9ffe9-103">La replica supporta la creazione di sottoscrizioni push delle pubblicazioni transazionali e snapshot per i Sottoscrittori Oracle e IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="9ffe9-103">Replication supports creating push subscriptions to snapshot and transactional publications for Oracle and IBM DB2 Subscribers.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9ffe9-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9ffe9-104">Options</span></span>  
 <span data-ttu-id="9ffe9-105">**Tipo di Sottoscrittore da aggiungere**</span><span class="sxs-lookup"><span data-stu-id="9ffe9-105">**Type of Subscriber to add**</span></span>  
 <span data-ttu-id="9ffe9-106">Consente di selezionare un Sottoscrittore Oracle o IBM DB2.</span><span class="sxs-lookup"><span data-stu-id="9ffe9-106">Select an Oracle Subscriber or IBM DB2 Subscriber.</span></span> <span data-ttu-id="9ffe9-107">Per altre informazioni sul supporto per tali Sottoscrittori, vedere [Sottoscrittori non SQL Server](non-sql/non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="9ffe9-107">For more information about support for these Subscribers, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
 <span data-ttu-id="9ffe9-108">**Nome origine dati**</span><span class="sxs-lookup"><span data-stu-id="9ffe9-108">**Data source name**</span></span>  
 <span data-ttu-id="9ffe9-109">Nome utilizzato per individuare il database in rete.</span><span class="sxs-lookup"><span data-stu-id="9ffe9-109">The name used to locate the database on a network.</span></span> <span data-ttu-id="9ffe9-110">La replica genera una stringa di connessione per il database utilizzando il nome dell'origine dei dati in combinazione con l'account di accesso, la password e le eventuali opzioni di connessione specificate nella pagina **Sicurezza agente di distribuzione** di questa procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="9ffe9-110">Replication produces a connection string for the database using the data source name, combined with the login, password, and any connection options you specify in the **Distribution Agent Security** page in this wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ffe9-111">Il nome dell'origine dei dati e la stringa di connessione non vengono convalidati da [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finché l'agente di distribuzione non tenta di inizializzare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="9ffe9-111">The data source name and connection string are not validated by [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until the Distribution Agent attempts to initialize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ffe9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ffe9-112">See Also</span></span>  
 <span data-ttu-id="9ffe9-113">[Creare una sottoscrizione per un Sottoscrittore non SQL Server](create-a-subscription-for-a-non-sql-server-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="9ffe9-113">[Create a Subscription for a Non-SQL Server Subscriber](create-a-subscription-for-a-non-sql-server-subscriber.md) </span></span>  
 <span data-ttu-id="9ffe9-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="9ffe9-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="9ffe9-115">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="9ffe9-115">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
