---
title: Proprietà della memoria condivisa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- shared memory [SQL Server]
ms.assetid: dc1704da-eacd-4d26-b529-c996f958ca4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6275215afdb6de3aa134dbffe74aa22b9e7b6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636976"
---
# <a name="shared-memory-properties"></a><span data-ttu-id="6fe18-102">Proprietà Shared Memory</span><span class="sxs-lookup"><span data-stu-id="6fe18-102">Shared Memory Properties</span></span>
  <span data-ttu-id="6fe18-103">Usare la pagina **Protocollo**nella finestra di dialogo **Proprietà Shared Memory** per abilitare o disabilitare il protocollo Shared Memory.</span><span class="sxs-lookup"><span data-stu-id="6fe18-103">Use the **Protocol**page on the **Shared Memory Properties** dialog box to enable or disable the shared memory protocol.</span></span> <span data-ttu-id="6fe18-104">Shared Memory è il protocollo più semplice da utilizzare e non richiede la configurazione di impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6fe18-104">Shared memory is the simplest protocol to use and has no configurable settings.</span></span> <span data-ttu-id="6fe18-105">Poiché i client che usano questo protocollo possono connettersi solo a un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eseguita sullo stesso computer, Shared Memory non è adatto per la maggior parte delle attività del database.</span><span class="sxs-lookup"><span data-stu-id="6fe18-105">Because clients using the shared memory protocol can only connect to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance running on the same computer, it is not useful for most database activity.</span></span> <span data-ttu-id="6fe18-106">Utilizzare il protocollo Shared Memory per la risoluzione dei problemi quando si sospetta che gli altri protocolli siano configurati in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="6fe18-106">Use the shared memory protocol for troubleshooting when you suspect the other protocols are configured incorrectly.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6fe18-107">deve essere riavviato per abilitare o disabilitare il protocollo.</span><span class="sxs-lookup"><span data-stu-id="6fe18-107">must be restarted to enable or disable the protocol.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6fe18-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6fe18-108">Options</span></span>  
 <span data-ttu-id="6fe18-109">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="6fe18-109">**Enabled**</span></span>  
 <span data-ttu-id="6fe18-110">I valori possibili sono **Sì** e **No**.</span><span class="sxs-lookup"><span data-stu-id="6fe18-110">Possible values are **Yes** and **No**.</span></span> <span data-ttu-id="6fe18-111">Il protocollo Shared Memory è attivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6fe18-111">The shared memory protocol is enabled by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe18-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fe18-112">See Also</span></span>  
 <span data-ttu-id="6fe18-113">[Scelta di un protocollo di rete](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="6fe18-113">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="6fe18-114">Creazione di una stringa di connessione valida mediante il protocollo di memoria condivisa</span><span class="sxs-lookup"><span data-stu-id="6fe18-114">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
  
