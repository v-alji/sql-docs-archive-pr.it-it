---
title: Configurazione nodi cluster (completa) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 64174d54-edee-49b8-9b43-039574bf2ca1
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cc1f8ce4574580746e20c478b23e40485c3e6ecc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628207"
---
# <a name="cluster-node-configuration-complete"></a><span data-ttu-id="90c40-102">Configurazione nodi cluster (completa)</span><span class="sxs-lookup"><span data-stu-id="90c40-102">Cluster Node Configuration (Complete)</span></span>
  <span data-ttu-id="90c40-103">Utilizzare la pagina Configurazione nodi cluster (completa) per specificare un'istanza esistente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che è stato preparato per clustering. Per installare o aggiornare un cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è necessario eseguire il programma di installazione su ogni nodo del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="90c40-103">Use the Cluster Node Configuration (Complete) page to specify an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that has been prepared for clustering.To install or upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you must run the Setup program on each node of the failover cluster.</span></span> <span data-ttu-id="90c40-104">Per aggiungere un nodo a un cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esistente, è necessario eseguire il programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel nodo che deve essere aggiunto all'istanza del cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90c40-104">To add a node to an existing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you must run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup on the node that is to be added to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="90c40-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="90c40-105">Options</span></span>  
 <span data-ttu-id="90c40-106">Dalle caselle a discesa:</span><span class="sxs-lookup"><span data-stu-id="90c40-106">From the drop-down boxes:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="90c40-107">Nome istanza: selezionare il nome dell'istanza per il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="90c40-107">instance name - Select the instance name for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
-   <span data-ttu-id="90c40-108">Nome del nodo: questo campo è già popolato con il nome del computer in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in esecuzione il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="90c40-108">Name of this node - This field is pre-populated with the computer name where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program is running.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="90c40-109">Nome di rete del cluster di failover: questo campo non è già popolato.</span><span class="sxs-lookup"><span data-stu-id="90c40-109">Failover Cluster Network Name - This field is not pre-populated.</span></span> <span data-ttu-id="90c40-110">Specificare il nome di rete della nuova istanza del cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90c40-110">Specify the network name for the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance.</span></span> <span data-ttu-id="90c40-111">Si tratta del nome che identifica l'istanza del cluster di failover nella rete.</span><span class="sxs-lookup"><span data-stu-id="90c40-111">This is the name that identifies the failover cluster instance on the network.</span></span>  
  
  
