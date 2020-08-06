---
title: MSSQLSERVER_7901 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7901 (Database Engine error)
ms.assetid: 2d0d19b9-947b-4474-9ff8-7e03019ab93d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fae6e55cbe7170f795aff85400da2c5cdaef780a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628717"
---
# <a name="mssqlserver_7901"></a><span data-ttu-id="b20f0-102">MSSQLSERVER_7901</span><span class="sxs-lookup"><span data-stu-id="b20f0-102">MSSQLSERVER_7901</span></span>
    
## <a name="details"></a><span data-ttu-id="b20f0-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b20f0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b20f0-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b20f0-104">Product Name</span></span>|<span data-ttu-id="b20f0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b20f0-105">SQL Server</span></span>|  
|<span data-ttu-id="b20f0-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b20f0-106">Event ID</span></span>|<span data-ttu-id="b20f0-107">7901</span><span class="sxs-lookup"><span data-stu-id="b20f0-107">7901</span></span>|  
|<span data-ttu-id="b20f0-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b20f0-108">Event Source</span></span>|<span data-ttu-id="b20f0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b20f0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b20f0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b20f0-110">Component</span></span>|<span data-ttu-id="b20f0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b20f0-111">SQLEngine</span></span>|  
|<span data-ttu-id="b20f0-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b20f0-112">Symbolic Name</span></span>|<span data-ttu-id="b20f0-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span><span class="sxs-lookup"><span data-stu-id="b20f0-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span></span>|  
|<span data-ttu-id="b20f0-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b20f0-114">Message Text</span></span>|<span data-ttu-id="b20f0-115">L'istruzione di correzione non è stata elaborata.</span><span class="sxs-lookup"><span data-stu-id="b20f0-115">The repair statement was not processed.</span></span> <span data-ttu-id="b20f0-116">Questo livello di correzione non è supportato quando il database è in modalità di emergenza.</span><span class="sxs-lookup"><span data-stu-id="b20f0-116">This level of repair is not supported when the database is in emergency mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b20f0-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b20f0-117">Explanation</span></span>  
 <span data-ttu-id="b20f0-118">Il database è in modalità di emergenza ed è stato specificato un livello di correzione diverso da REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="b20f0-118">The database is in emergency mode and a repair level other than REPAIR_ALLOW_DATA_LOSS has been specified.</span></span> <span data-ttu-id="b20f0-119">Non è possibile implementare correzioni in modalità di emergenza a meno che non venga specificata l'opzione REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="b20f0-119">Repairs cannot be made in emergency mode unless REPAIR_ALLOW_DATA_LOSS is specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b20f0-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b20f0-120">User Action</span></span>  
 <span data-ttu-id="b20f0-121">Eseguire nuovamente il comando e specificare l'opzione REPAIR_ALLOW_DATA_LOSS.</span><span class="sxs-lookup"><span data-stu-id="b20f0-121">Rerun the command and specify the REPAIR_ALLOW_DATA_LOSS option.</span></span>  
  
  
