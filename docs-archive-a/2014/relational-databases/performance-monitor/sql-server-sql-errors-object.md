---
title: Oggetto SQL Errors di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- SQL Errors object
- SQLServer:SQL Errors
ms.assetid: 6e5273ca-29cb-4618-88a2-70b9b8d6cf76
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 11bfb728e79b4fc175fb8a2fe16c9f1662a205ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713076"
---
# <a name="sql-server-sql-errors-object"></a><span data-ttu-id="9edc3-102">Oggetto Errori SQL di SQL Server</span><span class="sxs-lookup"><span data-stu-id="9edc3-102">SQL Server, SQL Errors Object</span></span>
  <span data-ttu-id="9edc3-103">L'oggetto **SQLServer:Errori SQL** di Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] include contatori che consentono di monitorare **Errori SQL**.</span><span class="sxs-lookup"><span data-stu-id="9edc3-103">The **SQLServer:SQL Errors** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides counters to monitor **SQL Errors**.</span></span>  
  
 <span data-ttu-id="9edc3-104">Nella tabella seguente vengono descritti i contatori dell'oggetto **SQL Errors** di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9edc3-104">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **SQL Errors** counters.</span></span>  
  
|<span data-ttu-id="9edc3-105">Contatori dell'oggetto Errori SQL di SQLServer</span><span class="sxs-lookup"><span data-stu-id="9edc3-105">SQL Server SQL Errors counters</span></span>|<span data-ttu-id="9edc3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9edc3-106">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="9edc3-107">**Errori/sec**</span><span class="sxs-lookup"><span data-stu-id="9edc3-107">**Errors/sec**</span></span>|<span data-ttu-id="9edc3-108">Numero di errori/sec</span><span class="sxs-lookup"><span data-stu-id="9edc3-108">Number of errors/sec.</span></span>|  
  
 <span data-ttu-id="9edc3-109">Per ogni contatore nell'oggetto sono disponibili le istanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="9edc3-109">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="9edc3-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="9edc3-110">Item</span></span>|<span data-ttu-id="9edc3-111">Definizione</span><span class="sxs-lookup"><span data-stu-id="9edc3-111">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="9edc3-112">**_Total**</span><span class="sxs-lookup"><span data-stu-id="9edc3-112">**_Total**</span></span>|<span data-ttu-id="9edc3-113">Informazioni relative a tutti gli errori.</span><span class="sxs-lookup"><span data-stu-id="9edc3-113">Information for all errors.</span></span>|  
|<span data-ttu-id="9edc3-114">**DB Offline Errors**</span><span class="sxs-lookup"><span data-stu-id="9edc3-114">**DB Offline Errors**</span></span>|<span data-ttu-id="9edc3-115">Tiene traccia degli errori gravi che obbligano [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a impostare il database corrente come offline.</span><span class="sxs-lookup"><span data-stu-id="9edc3-115">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to take the current database offline.</span></span>|  
|<span data-ttu-id="9edc3-116">**Info Errors**</span><span class="sxs-lookup"><span data-stu-id="9edc3-116">**Info Errors**</span></span>|<span data-ttu-id="9edc3-117">Informazioni relative a messaggi di errore di tipo informativo che non provocano errori.</span><span class="sxs-lookup"><span data-stu-id="9edc3-117">Information related to error messages that provide information to users but do not cause errors.</span></span>|  
|<span data-ttu-id="9edc3-118">**Kill Connection Errors**</span><span class="sxs-lookup"><span data-stu-id="9edc3-118">**Kill Connection Errors**</span></span>|<span data-ttu-id="9edc3-119">Tiene traccia degli errori gravi che obbligano [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a terminare la connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="9edc3-119">Tracks severe errors that cause [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to kill the current connection.</span></span>|  
|<span data-ttu-id="9edc3-120">**User Errors**</span><span class="sxs-lookup"><span data-stu-id="9edc3-120">**User Errors**</span></span>|<span data-ttu-id="9edc3-121">Informazioni sugli errori dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9edc3-121">Information about user errors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9edc3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9edc3-122">See Also</span></span>  
 [<span data-ttu-id="9edc3-123">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="9edc3-123">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
