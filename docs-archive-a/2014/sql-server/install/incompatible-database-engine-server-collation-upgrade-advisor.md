---
title: Regole di confronto di motore di database server incompatibili (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f499d6-2c90-49eb-a5b3-0bb5b7faaa3b
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b6ce0555bdf5a878e56d87a8bd55b5ce6c4b2649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637040"
---
# <a name="incompatible-database-engine-server-collation-upgrade-advisor"></a><span data-ttu-id="fbcc5-102">Regole di confronto del server del motore di database incompatibili (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="fbcc5-102">Incompatible Database Engine Server Collation (Upgrade Advisor)</span></span>
  <span data-ttu-id="fbcc5-103">È stata rilevata l' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] utilizzo di un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configurata per l'utilizzo di regole di confronto del server incompatibili.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-103">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
||  
|-|  
|<span data-ttu-id="fbcc5-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità SharePoint di.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="fbcc5-105">Componente</span><span class="sxs-lookup"><span data-stu-id="fbcc5-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="fbcc5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbcc5-106">Description</span></span>  
 <span data-ttu-id="fbcc5-107">È stata rilevata l' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] utilizzo di un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configurata per l'utilizzo di regole di confronto del server incompatibili.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-107">Upgrade Advisor detected [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is using an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that is configured to use an incompatible server collation.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="fbcc5-108">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] modalità SharePoint viene utilizzata l'architettura dei servizi condivisi di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-108">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode utilizes the SharePoint shared services architecture.</span></span> <span data-ttu-id="fbcc5-109">In SharePoint non viene supportato [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configurato per la distinzione tra maiuscole e minuscole o per regole di confronto del server o per regole di confronto del server binarie.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-109">SharePoint does not support [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configured for case sensitive or server collations or binary server collations.</span></span> <span data-ttu-id="fbcc5-110">Le regole di confronto incompatibili includono regole di confronto che per impostazione predefinita supportano la distinzione tra maiuscole e minuscole o che sono binarie e regole di confronto di base che per impostazione predefinita sono compatibili ma sono state configurate con alcune delle designazioni delle regole di confronto seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbcc5-110">Incompatible collations include collations that are by default case sensitive or binary and a base collation that by default is compatible but has been configured with any of the following collation designators:</span></span>  
  
-   <span data-ttu-id="fbcc5-111">**Binario**</span><span class="sxs-lookup"><span data-stu-id="fbcc5-111">**Binary**</span></span>  
  
-   <span data-ttu-id="fbcc5-112">**Distinzione maiuscole/minuscole**</span><span class="sxs-lookup"><span data-stu-id="fbcc5-112">**Case-sensitive**</span></span>  
  
-   <span data-ttu-id="fbcc5-113">**Punto di codice binario**</span><span class="sxs-lookup"><span data-stu-id="fbcc5-113">**Binary-codepoint**</span></span>  
  
 <span data-ttu-id="fbcc5-114">Poiché le regole di confronto del server [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] correnti sono incompatibili, l'aggiornamento è bloccato.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-114">Because the current [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation is incompatible, upgrade is blocked.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="fbcc5-115">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="fbcc5-115">Corrective Action</span></span>  
 <span data-ttu-id="fbcc5-116">La proprietà delle regole di confronto del server [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-116">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] server collation property cannot be changed.</span></span> <span data-ttu-id="fbcc5-117">Non sarà possibile completare un aggiornamento di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fbcc5-117">You will not be able to complete an upgrade of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="fbcc5-118">Sarà necessario eseguire la migrazione dell'installazione [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] a un nuovo server che sta utilizzando regole di confronto del server compatibili.</span><span class="sxs-lookup"><span data-stu-id="fbcc5-118">You will need to migrate your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation to a new server which is using a compatible server collation.</span></span> <span data-ttu-id="fbcc5-119">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbcc5-119">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="fbcc5-120">Eseguire l'aggiornamento e la migrazione di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fbcc5-120">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=233227)  
  
-   [<span data-ttu-id="fbcc5-121">Selezione delle regole di confronto di SQL Server</span><span class="sxs-lookup"><span data-stu-id="fbcc5-121">Selecting a SQL Server Collation</span></span>](https://go.microsoft.com/fwlink/?LinkId=233226)  
  
  
