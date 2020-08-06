---
title: MSSQLSERVER_1807 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1807 (Database Engine error)
ms.assetid: 13c1b240-098b-4d9e-89aa-21599548e074
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 261d352084e490fb7f9216e1a7e352542e85a6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627785"
---
# <a name="mssqlserver_1807"></a><span data-ttu-id="e6fad-102">MSSQLSERVER_1807</span><span class="sxs-lookup"><span data-stu-id="e6fad-102">MSSQLSERVER_1807</span></span>
    
## <a name="details"></a><span data-ttu-id="e6fad-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e6fad-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6fad-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="e6fad-104">Product Name</span></span>|<span data-ttu-id="e6fad-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6fad-105">SQL Server</span></span>|  
|<span data-ttu-id="e6fad-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="e6fad-106">Event ID</span></span>|<span data-ttu-id="e6fad-107">1807</span><span class="sxs-lookup"><span data-stu-id="e6fad-107">1807</span></span>|  
|<span data-ttu-id="e6fad-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="e6fad-108">Event Source</span></span>|<span data-ttu-id="e6fad-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e6fad-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e6fad-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e6fad-110">Component</span></span>|<span data-ttu-id="e6fad-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e6fad-111">SQLEngine</span></span>|  
|<span data-ttu-id="e6fad-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="e6fad-112">Symbolic Name</span></span>|<span data-ttu-id="e6fad-113">CANNOT_EX_LOCK</span><span class="sxs-lookup"><span data-stu-id="e6fad-113">CANNOT_EX_LOCK</span></span>|  
|<span data-ttu-id="e6fad-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="e6fad-114">Message Text</span></span>|<span data-ttu-id="e6fad-115">Impossibile ottenere il blocco esclusivo sul database '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="e6fad-115">Could not obtain exclusive lock on database '%.\*ls'.</span></span> <span data-ttu-id="e6fad-116">Ripetere l'operazione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="e6fad-116">Retry the operation later.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e6fad-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="e6fad-117">Explanation</span></span>  
 <span data-ttu-id="e6fad-118">Non è possibile ottenere l'accesso esclusivo al database necessario per l'esecuzione di un'operazione.</span><span class="sxs-lookup"><span data-stu-id="e6fad-118">An operation that required exclusive access to the database was unable to obtain it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e6fad-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="e6fad-119">User Action</span></span>  
 <span data-ttu-id="e6fad-120">Disconnettere tutte le connessioni al database oppure eseguire nuovamente la query in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="e6fad-120">Disconnect all the connections to that database or try the query again later.</span></span>  
  
  
