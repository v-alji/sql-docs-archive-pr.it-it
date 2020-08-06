---
title: MSSQLSERVER_17130 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17130 (Database Engine error)
ms.assetid: 7ce6afca-221d-402f-89df-da7e74a339a8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b63be325273e4df33d837ec1548ed46701323977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715356"
---
# <a name="mssqlserver_17130"></a><span data-ttu-id="8a956-102">MSSQLSERVER_17130</span><span class="sxs-lookup"><span data-stu-id="8a956-102">MSSQLSERVER_17130</span></span>
    
## <a name="details"></a><span data-ttu-id="8a956-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8a956-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a956-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="8a956-104">Product Name</span></span>|<span data-ttu-id="8a956-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8a956-105">SQL Server</span></span>|  
|<span data-ttu-id="8a956-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="8a956-106">Event ID</span></span>|<span data-ttu-id="8a956-107">17130</span><span class="sxs-lookup"><span data-stu-id="8a956-107">17130</span></span>|  
|<span data-ttu-id="8a956-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="8a956-108">Event Source</span></span>|<span data-ttu-id="8a956-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8a956-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8a956-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8a956-110">Component</span></span>|<span data-ttu-id="8a956-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8a956-111">SQLEngine</span></span>|  
|<span data-ttu-id="8a956-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="8a956-112">Symbolic Name</span></span>|<span data-ttu-id="8a956-113">INIT_NOLOCKSPACE</span><span class="sxs-lookup"><span data-stu-id="8a956-113">INIT_NOLOCKSPACE</span></span>|  
|<span data-ttu-id="8a956-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="8a956-114">Message Text</span></span>|<span data-ttu-id="8a956-115">Memoria insufficiente per il numero configurato di blocchi.</span><span class="sxs-lookup"><span data-stu-id="8a956-115">Not enough memory for the configured number of locks.</span></span> <span data-ttu-id="8a956-116">Verrà tentato l'avvio con una tabella hash di blocchi più piccola, con possibili conseguenze sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8a956-116">Attempting to start with a smaller lock hash table, which may impact performance.</span></span> <span data-ttu-id="8a956-117">Per configurare più memoria per questa istanza del Motore di database, contattare l'amministratore.</span><span class="sxs-lookup"><span data-stu-id="8a956-117">Contact the database administrator to configure more memory for this instance of the Database Engine.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8a956-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8a956-118">Explanation</span></span>  
 <span data-ttu-id="8a956-119">Memoria insufficiente per le dimensioni desiderate della tabella hash di Gestione blocchi.</span><span class="sxs-lookup"><span data-stu-id="8a956-119">Not enough memory for the desired lock manager hash table size.</span></span>  <span data-ttu-id="8a956-120">Verrà eseguito un tentativo di allocare una tabella hash di dimensioni minori.</span><span class="sxs-lookup"><span data-stu-id="8a956-120">An attempt will be made to allocate a smaller hash table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8a956-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="8a956-121">User Action</span></span>  
 <span data-ttu-id="8a956-122">Verificare i parametri di configurazione della memoria del server (min server memory/max server memory) e il numero di richieste di memoria</span><span class="sxs-lookup"><span data-stu-id="8a956-122">Check server memory configuration parameters (min/max server memory), check for memory pressures.</span></span> <span data-ttu-id="8a956-123">e fornire una quantità maggiore di memoria a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8a956-123">Provide SQL Server more memory.</span></span>  
  
  
