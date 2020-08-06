---
title: Connetti al server (Oracle) - Proprietà connessione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.connectionprops.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 1bb7396f-cbb2-4f88-b82b-543287ed4172
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c76a3058283a098357701a44de48efff917acd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624081"
---
# <a name="connect-to-server-oracle-connection-properties"></a><span data-ttu-id="9bbd6-102">Connetti al server (Oracle) - Proprietà connessione</span><span class="sxs-lookup"><span data-stu-id="9bbd6-102">Connect to Server (Oracle), Connection Properties</span></span>
  <span data-ttu-id="9bbd6-103">Utilizzare la scheda **Proprietà connessione** della finestra di dialogo **Connetti al server** per specificare un'opzione di pubblicazione, ovvero **Gateway** o **Completa**.</span><span class="sxs-lookup"><span data-stu-id="9bbd6-103">Use the **Connection Properties** tab of the **Connect to Server** dialog box to specify a publishing option of **Gateway** or **Complete**.</span></span> <span data-ttu-id="9bbd6-104">Dopo aver identificato un server di pubblicazione, questa opzione può essere modificata solo eliminando e riconfigurando il server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="9bbd6-104">After a Publisher is identified, this option cannot be changed without dropping and reconfiguring the Publisher.</span></span> <span data-ttu-id="9bbd6-105">Per altre informazioni, vedere [Configurare un server di pubblicazione Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="9bbd6-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9bbd6-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9bbd6-106">Options</span></span>  
 <span data-ttu-id="9bbd6-107">**Tipo di autore**</span><span class="sxs-lookup"><span data-stu-id="9bbd6-107">**Publisher type**</span></span>  
 <span data-ttu-id="9bbd6-108">Selezionare **Gateway** o **Completa**.</span><span class="sxs-lookup"><span data-stu-id="9bbd6-108">Select **Gateway** or **Complete**.</span></span> <span data-ttu-id="9bbd6-109">L'opzione **Completa** è progettata per offrire pubblicazioni snapshot e transazionali con il set completo di caratteristiche supportate per la pubblicazione Oracle.</span><span class="sxs-lookup"><span data-stu-id="9bbd6-109">The **Complete** option is designed to provide snapshot and transactional publications with the complete set of supported features for Oracle publishing.</span></span> <span data-ttu-id="9bbd6-110">L'opzione **Gateway** consente l'ottimizzazione della progettazione specifica per migliorare le prestazioni per i casi in cui la replica funge da gateway tra i sistemi.</span><span class="sxs-lookup"><span data-stu-id="9bbd6-110">The **Gateway** option provides specific design optimizations to improve performance for cases where replication serves as a gateway between systems.</span></span> <span data-ttu-id="9bbd6-111">Non è possibile utilizzare l'opzione **Gateway** se si intende pubblicare la stessa tabella in più pubblicazioni transazionali.</span><span class="sxs-lookup"><span data-stu-id="9bbd6-111">The **Gateway** option cannot be used if you plan to publish the same table in multiple transactional publications.</span></span> <span data-ttu-id="9bbd6-112">Se si seleziona **Gateway**, una tabella può essere presente al massimo in una pubblicazione transazionale e in un numero qualsiasi di pubblicazioni snapshot.</span><span class="sxs-lookup"><span data-stu-id="9bbd6-112">A table can appear in at most one transactional publication and any number of snapshot publications if you select **Gateway**.</span></span>  
  
 <span data-ttu-id="9bbd6-113">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="9bbd6-113">**Timeouts**</span></span>  
 <span data-ttu-id="9bbd6-114">Specificare per quanto tempo il server di distribuzione [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve tentare di stabilire la connessione al server di pubblicazione Oracle prima che si verifichi un timeout.</span><span class="sxs-lookup"><span data-stu-id="9bbd6-114">Specify how long the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor should attempt to connect to the Oracle Publisher before a timeout error occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bbd6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bbd6-115">See Also</span></span>  
 <span data-ttu-id="9bbd6-116">[Glossario dei termini per la pubblicazione Oracle](non-sql/glossary-of-terms-for-oracle-publishing.md) </span><span class="sxs-lookup"><span data-stu-id="9bbd6-116">[Glossary of Terms for Oracle Publishing](non-sql/glossary-of-terms-for-oracle-publishing.md) </span></span>  
 [<span data-ttu-id="9bbd6-117">Ottimizzazione delle prestazioni per i server di pubblicazione Oracle</span><span class="sxs-lookup"><span data-stu-id="9bbd6-117">Performance Tuning for Oracle Publishers</span></span>](non-sql/performance-tuning-for-oracle-publishers.md)  
  
  
