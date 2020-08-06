---
title: Opzioni di configurazione del server access check cache | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- access check cache option
- access check cache bucket count
- access check cache quota
ms.assetid: 0a992ea8-3ec6-4a4d-97b5-460ae7326247
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: feed895eeb7b11b4c41c51c4c26859a1057d2733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623492"
---
# <a name="access-check-cache-server-configuration-options"></a><span data-ttu-id="738f7-102">Opzioni di configurazione del server access check cache</span><span class="sxs-lookup"><span data-stu-id="738f7-102">access check cache Server Configuration Options</span></span>
<span data-ttu-id="738f7-103">Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]accede agli oggetti di database, il controllo dell'accesso viene memorizzato nella cache in una struttura interna denominata **cache dei risultati del controllo dell'accesso**.</span><span class="sxs-lookup"><span data-stu-id="738f7-103">When database objects are accessed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the access check is cached in an internal structure called the **access check result cache**.</span></span> 
  
<span data-ttu-id="738f7-104">L'opzione **Conteggio bucket cache controllo di accesso** controlla il numero di bucket di hash usati per la cache dei risultati di controllo accesso.</span><span class="sxs-lookup"><span data-stu-id="738f7-104">The **access check cache bucket count** option controls the number of hash buckets that are used for the access check result cache.</span></span> 

<span data-ttu-id="738f7-105">L'opzione **Quota della cache controllo di accesso** controlla il numero di voci archiviate nella cache dei risultati di controllo accesso.</span><span class="sxs-lookup"><span data-stu-id="738f7-105">The **access check cache quota** option controls the number of entries that are stored in the access check result cache.</span></span> <span data-ttu-id="738f7-106">Quando viene raggiunto il numero massimo di voci, le voci meno recenti vengono rimosse dalla cache dei risultati di controllo accesso.</span><span class="sxs-lookup"><span data-stu-id="738f7-106">When the maximum number of entries is reached, the oldest entries are removed from the access check result cache.</span></span>
  
<span data-ttu-id="738f7-107">Il valore predefinito 0 indica che le opzioni vengono gestite da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="738f7-107">The default values of 0 indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is managing these options.</span></span> <span data-ttu-id="738f7-108">Da [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] a, i valori predefiniti vengono convertiti nelle configurazioni interne seguenti:</span><span class="sxs-lookup"><span data-stu-id="738f7-108">From [!INCLUDE[ssKatmai](../../includes/ssKatmai-md.md)] through [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], the default values translate to the following internal configurations:</span></span>
-   <span data-ttu-id="738f7-109">Per Access check cache bucket count, il valore 0 imposta un valore predefinito di 256 bucket per l'architettura x86 e 2.048 bucket per le architetture x64 e IA-64.</span><span class="sxs-lookup"><span data-stu-id="738f7-109">For access check cache bucket count, the value 0 sets a default value of 256 buckets for x86 architecture, and 2,048 buckets for x64 and IA-64 architectures.</span></span>
-   <span data-ttu-id="738f7-110">Per Access check cache quota, il valore 0 imposta un valore predefinito di 1.024 voci per l'architettura x86 e 28.192.048 bucket per le architetture x64 e IA-64.</span><span class="sxs-lookup"><span data-stu-id="738f7-110">For access check cache quota, the value 0 sets a default value of 1,024 entries for x86 architecture, and 28,192,048 buckets for x64 and IA-64 architectures.</span></span>

<span data-ttu-id="738f7-111">Raramente la modifica di tali opzioni consente di ottenere prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="738f7-111">In rare circumstances, performance can be improved by changing these options.</span></span> <span data-ttu-id="738f7-112">Ad esempio, è possibile ridurre le dimensioni della cache dei risultati di controllo accesso se viene usata una quantità eccessiva di memoria.</span><span class="sxs-lookup"><span data-stu-id="738f7-112">For example, you may want to reduce the size of the access check result cache if too much memory is used.</span></span> <span data-ttu-id="738f7-113">Oppure è possibile aumentare le dimensioni della cache dei risultati di controllo accesso se si riscontra un utilizzo elevato della CPU quando le autorizzazioni vengono ricalcolate.</span><span class="sxs-lookup"><span data-stu-id="738f7-113">Or, you may want to increase the size of the access check result cache if you experience high CPU usage when permissions are recalculated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="738f7-114">È consigliabile modificare le opzioni solo se suggerito dal Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="738f7-114">Microsoft recommends only changing these options when directed by Microsoft Customer Support Services.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="738f7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="738f7-115">See Also</span></span>  
 <span data-ttu-id="738f7-116">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="738f7-116">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="738f7-117">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="738f7-117">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
