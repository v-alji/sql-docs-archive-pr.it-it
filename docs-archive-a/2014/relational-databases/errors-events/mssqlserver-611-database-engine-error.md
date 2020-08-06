---
title: MSSQLSERVER_611 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 611 (Database Engine error)
ms.assetid: ac6a213f-5c38-44ad-bc85-a62863786614
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f0caa1c218e8b80059c0c97aac652da7db870af3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637362"
---
# <a name="mssqlserver_611"></a><span data-ttu-id="4058b-102">MSSQLSERVER_611</span><span class="sxs-lookup"><span data-stu-id="4058b-102">MSSQLSERVER_611</span></span>
    
## <a name="details"></a><span data-ttu-id="4058b-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4058b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4058b-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="4058b-104">Product Name</span></span>|<span data-ttu-id="4058b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4058b-105">SQL Server</span></span>|  
|<span data-ttu-id="4058b-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="4058b-106">Event ID</span></span>|<span data-ttu-id="4058b-107">611</span><span class="sxs-lookup"><span data-stu-id="4058b-107">611</span></span>|  
|<span data-ttu-id="4058b-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="4058b-108">Event Source</span></span>|<span data-ttu-id="4058b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4058b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4058b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4058b-110">Component</span></span>|<span data-ttu-id="4058b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4058b-111">SQLEngine</span></span>|  
|<span data-ttu-id="4058b-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="4058b-112">Symbolic Name</span></span>|<span data-ttu-id="4058b-113">VAR_SIZE_TOO_BIG</span><span class="sxs-lookup"><span data-stu-id="4058b-113">VAR_SIZE_TOO_BIG</span></span>|  
|<span data-ttu-id="4058b-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="4058b-114">Message Text</span></span>|<span data-ttu-id="4058b-115">Impossibile inserire o aggiornare una riga perché le dimensioni di colonna variabili totali, incluso l'overhead, superano il limite di %d byte.</span><span class="sxs-lookup"><span data-stu-id="4058b-115">Cannot insert or update a row because total variable column size, including overhead, is %d bytes more than the limit.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4058b-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="4058b-116">Explanation</span></span>  
 <span data-ttu-id="4058b-117">Le dimensioni di colonna variabili totali sono maggiori del limite consentito dallo schema.</span><span class="sxs-lookup"><span data-stu-id="4058b-117">The maximum variable column size is more than that allowed by the schema.</span></span> <span data-ttu-id="4058b-118">L'errore 611 viene restituito quando la colonna variabili supera il limite nel case fisso, se il formato di archiviazione vardecimal è abilitato, o quando le dimensioni della colonna variabili superano il limite consentito in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] per un record di dati compresso.</span><span class="sxs-lookup"><span data-stu-id="4058b-118">Error 611 is returned when the variable column is over the limit in the fixed case when vardecimal storage format is enabled, or when the variable column size is over the limit allowed in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] for a compressed data record.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4058b-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="4058b-119">User Action</span></span>  
 <span data-ttu-id="4058b-120">Ridurre le dimensioni del record.</span><span class="sxs-lookup"><span data-stu-id="4058b-120">Reduce the size of the record.</span></span>  
  
  
