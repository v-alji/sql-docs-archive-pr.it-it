---
title: MSSQLSERVER_8443 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8443 (Database Engine error)
ms.assetid: a3541b9c-b1a8-4280-add1-275f08696b62
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae02cc0d9e5661f4069884c22bf6eea0697bd2d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719955"
---
# <a name="mssqlserver_8443"></a><span data-ttu-id="a3c32-102">MSSQLSERVER_8443</span><span class="sxs-lookup"><span data-stu-id="a3c32-102">MSSQLSERVER_8443</span></span>
    
## <a name="details"></a><span data-ttu-id="a3c32-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a3c32-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3c32-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="a3c32-104">Product Name</span></span>|<span data-ttu-id="a3c32-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3c32-105">SQL Server</span></span>|  
|<span data-ttu-id="a3c32-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="a3c32-106">Event ID</span></span>|<span data-ttu-id="a3c32-107">8443</span><span class="sxs-lookup"><span data-stu-id="a3c32-107">8443</span></span>|  
|<span data-ttu-id="a3c32-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="a3c32-108">Event Source</span></span>|<span data-ttu-id="a3c32-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a3c32-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a3c32-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a3c32-110">Component</span></span>|<span data-ttu-id="a3c32-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a3c32-111">SQLEngine</span></span>|  
|<span data-ttu-id="a3c32-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="a3c32-112">Symbolic Name</span></span>|<span data-ttu-id="a3c32-113">SB_DIALOG_WO_CONV_GROUP</span><span class="sxs-lookup"><span data-stu-id="a3c32-113">SB_DIALOG_WO_CONV_GROUP</span></span>|  
|<span data-ttu-id="a3c32-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a3c32-114">Message Text</span></span>|<span data-ttu-id="a3c32-115">La conversazione con ID '%.\*ls' e Initiator %d fa riferimento al gruppo di conversazione mancante '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="a3c32-115">The conversation with ID '%.\*ls' and initiator %d references a missing conversation group '%.\*ls'.</span></span> <span data-ttu-id="a3c32-116">Eseguire DBCC CHECKDB per analizzare e riparare il database.</span><span class="sxs-lookup"><span data-stu-id="a3c32-116">Run DBCC CHECKDB to analyze and repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3c32-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a3c32-117">Explanation</span></span>  
 <span data-ttu-id="a3c32-118">Il livello di metadati ha restituito NULL per il gruppo di conversazione.</span><span class="sxs-lookup"><span data-stu-id="a3c32-118">The metadata layer returned NULL for the conversation group.</span></span> <span data-ttu-id="a3c32-119">Il database è stato danneggiato in qualche modo.</span><span class="sxs-lookup"><span data-stu-id="a3c32-119">The database has been corrupted in some way.</span></span> <span data-ttu-id="a3c32-120">Una possibile causa di danneggiamento è un errore del disco.</span><span class="sxs-lookup"><span data-stu-id="a3c32-120">One possible source of corruption is a disk error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3c32-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="a3c32-121">User Action</span></span>  
 <span data-ttu-id="a3c32-122">Eseguire DBCC CHECKDB in modalità di correzione per riportare il database in uno stato consistente.</span><span class="sxs-lookup"><span data-stu-id="a3c32-122">Run DBCC CHECKDB in repair mode to bring the database back into a consistent state.</span></span> <span data-ttu-id="a3c32-123">I messaggi potrebbero essere eliminati se necessario per ripristinare la consistenza.</span><span class="sxs-lookup"><span data-stu-id="a3c32-123">It may delete messages if necessary to restore consistency.</span></span> <span data-ttu-id="a3c32-124">Verificare i log degli errori di sistema per vedere se l'errore è stato causato da un altro malfunzionamento del sistema.</span><span class="sxs-lookup"><span data-stu-id="a3c32-124">Investigate system error logs to see if this error was caused by another failure in the system.</span></span>  
  
  
