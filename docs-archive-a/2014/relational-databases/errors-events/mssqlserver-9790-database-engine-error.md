---
title: MSSQLSERVER_9790 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9790 (Database Engine error)
ms.assetid: 83fd379f-5deb-4f97-8cb4-282e3d3fed94
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d6d065d4a0e841da3b5ecb84f902df17dcfd60c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627739"
---
# <a name="mssqlserver_9790"></a><span data-ttu-id="faebf-102">MSSQLSERVER_9790</span><span class="sxs-lookup"><span data-stu-id="faebf-102">MSSQLSERVER_9790</span></span>
    
## <a name="details"></a><span data-ttu-id="faebf-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="faebf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="faebf-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="faebf-104">Product Name</span></span>|<span data-ttu-id="faebf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="faebf-105">SQL Server</span></span>|  
|<span data-ttu-id="faebf-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="faebf-106">Event ID</span></span>|<span data-ttu-id="faebf-107">9790</span><span class="sxs-lookup"><span data-stu-id="faebf-107">9790</span></span>|  
|<span data-ttu-id="faebf-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="faebf-108">Event Source</span></span>|<span data-ttu-id="faebf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="faebf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="faebf-110">Componente</span><span class="sxs-lookup"><span data-stu-id="faebf-110">Component</span></span>|<span data-ttu-id="faebf-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="faebf-111">SQLEngine</span></span>|  
|<span data-ttu-id="faebf-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="faebf-112">Symbolic Name</span></span>|<span data-ttu-id="faebf-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span><span class="sxs-lookup"><span data-stu-id="faebf-113">SB3_XMIT_ERROR_ENTRANCE_BROKER_SINGLE_USER</span></span>|  
|<span data-ttu-id="faebf-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="faebf-114">Message Text</span></span>|<span data-ttu-id="faebf-115">Impossibile eseguire il routing del messaggio in arrivo.</span><span class="sxs-lookup"><span data-stu-id="faebf-115">Unable to route the incoming message.</span></span> <span data-ttu-id="faebf-116">Il database di sistema MSDB contenente le informazioni di routing è in modalità utente singolo.</span><span class="sxs-lookup"><span data-stu-id="faebf-116">The system database MSDB containing routing information is in SINGLE USER mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="faebf-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="faebf-117">Explanation</span></span>  
 <span data-ttu-id="faebf-118">Si è verificato un errore durante il tentativo di classificare un messaggio ricevuto fuori collegamento poiché il database MSDB è in modalità utente singolo.</span><span class="sxs-lookup"><span data-stu-id="faebf-118">An error occurred while trying to classify a message received off the wire because the MSDB database was in Single User mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="faebf-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="faebf-119">User Action</span></span>  
 <span data-ttu-id="faebf-120">Impostare MSDB sulla modalità MULTI USER con il comando ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="faebf-120">Change MSDB to be in MULTI USER mode with the ALTER DATABASE command.</span></span>  
  
  
