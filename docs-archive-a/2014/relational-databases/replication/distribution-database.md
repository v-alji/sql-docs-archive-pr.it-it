---
title: Database di distribuzione | Microsoft Docs
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.distributiondatabase.f1
ms.assetid: 5b42a083-7a11-41d8-9e3f-320c7c907237
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d98a80be52ae77cbdaf1581a5b3397f9d11af4fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624628"
---
# <a name="distribution-database"></a><span data-ttu-id="714fc-102">Database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="714fc-102">Distribution Database</span></span>
  <span data-ttu-id="714fc-103">Nel database di distribuzione vengono archiviati i metadati e i dati di cronologia relativi a tutti i tipi di replica, nonché le transazioni per la replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="714fc-103">The distribution database stores metadata and history data for all types of replication, and transactions for transactional replication.</span></span>  
  
 <span data-ttu-id="714fc-104">In molti casi, è sufficiente un singolo database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="714fc-104">In many cases, a single distribution database is sufficient.</span></span> <span data-ttu-id="714fc-105">Tuttavia, nel caso in cui più server di pubblicazione utilizzino un unico server di distribuzione, valutare l'opportunità di creare un database di distribuzione per ogni server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="714fc-105">However, if multiple Publishers use a single Distributor, consider creating a distribution database for each Publisher.</span></span> <span data-ttu-id="714fc-106">in modo da garantire che il flusso di dati di ogni database di distribuzione risulti distinto.</span><span class="sxs-lookup"><span data-stu-id="714fc-106">Doing so ensures that the data flowing through each distribution database is distinct.</span></span> <span data-ttu-id="714fc-107">È possibile specificare un database di distribuzione per il server di distribuzione utilizzando la Configurazione guidata distribuzione.</span><span class="sxs-lookup"><span data-stu-id="714fc-107">You can specify one distribution database for the Distributor using the Configure Distribution Wizard.</span></span> <span data-ttu-id="714fc-108">Se necessario, specificare database di distribuzione aggiuntivi nella finestra di dialogo **Proprietà server di distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="714fc-108">If necessary, specify additional distribution databases in the **Distributor Properties** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="714fc-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="714fc-109">Options</span></span>  
 <span data-ttu-id="714fc-110">**Nome database di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="714fc-110">**Distribution database name**</span></span>  
 <span data-ttu-id="714fc-111">Consente di immettere un nome per il database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="714fc-111">Enter a name for the distribution database.</span></span> <span data-ttu-id="714fc-112">Il nome predefinito del database di distribuzione è 'distribution'.</span><span class="sxs-lookup"><span data-stu-id="714fc-112">The default name for the distribution database is 'distribution'.</span></span> <span data-ttu-id="714fc-113">Se si specifica un nome, questo può avere una lunghezza massima di 128 caratteri, deve essere univoco nell'ambito di un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e conforme alle regole per gli identificatori.</span><span class="sxs-lookup"><span data-stu-id="714fc-113">If you specify a name, the name can be a maximum of 128 characters, must be unique within an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and must conform to the rules for identifiers.</span></span> <span data-ttu-id="714fc-114">Per altre informazioni, vedere [Identificatori del database](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="714fc-114">For more information, see [Database Identifiers](../databases/database-identifiers.md).</span></span>  
  
 <span data-ttu-id="714fc-115">**Cartella per il file del database di distribuzione** e **Cartella per il file di log del database di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="714fc-115">**Folder for the distribution database file** and **Folder for the distribution database log file**</span></span>  
 <span data-ttu-id="714fc-116">Immettere il percorso del database di distribuzione e dei file di log.</span><span class="sxs-lookup"><span data-stu-id="714fc-116">Enter the path for the distribution database and log files.</span></span> <span data-ttu-id="714fc-117">I percorsi devono fare riferimento a dischi locali del server di distribuzione e iniziare con una lettera di unità locale seguita da due punti, ad esempio C:.</span><span class="sxs-lookup"><span data-stu-id="714fc-117">Paths must refer to disks that are local to the Distributor and begin with a local drive letter and colon (for example, C:).</span></span> <span data-ttu-id="714fc-118">Le lettere di unità mappate e i percorsi di rete non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="714fc-118">Mapped drive letters and network paths are not valid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="714fc-119">è possibile ridurre il tempo necessario per la scrittura di transazioni e ottenere un miglioramento delle prestazioni della replica inserendo il log di distribuzione in un'unità disco distinta da quella del database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="714fc-119">You can decrease the time it takes to write transactions and improve the performance of replication by placing the distribution database log on a separate disk drive from the distribution database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714fc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="714fc-120">See Also</span></span>  
 <span data-ttu-id="714fc-121">[Configura distribuzione](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="714fc-121">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="714fc-122">[Configurare la pubblicazione e la distribuzione](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="714fc-122">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 [<span data-ttu-id="714fc-123">Visualizzare e modificare le proprietà del server di pubblicazione e del database di distribuzione</span><span class="sxs-lookup"><span data-stu-id="714fc-123">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)  
  
  
