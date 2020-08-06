---
title: MSSQLSERVER_21889 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21889 (Database Engine error)
ms.assetid: ae199540-7986-4cc2-b782-cd22793236d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c152a542550d7b81af880545f526037baeb4644e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718180"
---
# <a name="mssqlserver_21889"></a><span data-ttu-id="25925-102">MSSQLSERVER_21889</span><span class="sxs-lookup"><span data-stu-id="25925-102">MSSQLSERVER_21889</span></span>
    
## <a name="details"></a><span data-ttu-id="25925-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="25925-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25925-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="25925-104">Product Name</span></span>|<span data-ttu-id="25925-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="25925-105">SQL Server</span></span>|  
|<span data-ttu-id="25925-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="25925-106">Event ID</span></span>|<span data-ttu-id="25925-107">21889</span><span class="sxs-lookup"><span data-stu-id="25925-107">21889</span></span>|  
|<span data-ttu-id="25925-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="25925-108">Event Source</span></span>|<span data-ttu-id="25925-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="25925-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="25925-110">Componente</span><span class="sxs-lookup"><span data-stu-id="25925-110">Component</span></span>|<span data-ttu-id="25925-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="25925-111">SQLEngine</span></span>|  
|<span data-ttu-id="25925-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="25925-112">Symbolic Name</span></span>|<span data-ttu-id="25925-113">SQLErrorNum21889</span><span class="sxs-lookup"><span data-stu-id="25925-113">SQLErrorNum21889</span></span>|  
|<span data-ttu-id="25925-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="25925-114">Message Text</span></span>|<span data-ttu-id="25925-115">L'istanza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] '%s' non è un server di pubblicazione della replica.</span><span class="sxs-lookup"><span data-stu-id="25925-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' is not a replication publisher.</span></span> <span data-ttu-id="25925-116">Eseguire `sp_adddistributor` sull'istanza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] '%s' con il database di distribuzione '%s' per consentire all'istanza di ospitare il database di pubblicazione '%s.'</span><span class="sxs-lookup"><span data-stu-id="25925-116">Run `sp_adddistributor` on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' with distributor '%s' in order to enable the instance to host the publishing database '%s'.</span></span> <span data-ttu-id="25925-117">Assicurarsi di specificare lo stesso account di accesso e password di quello utilizzato per il server di pubblicazione originale.</span><span class="sxs-lookup"><span data-stu-id="25925-117">Make certain to specify the same login and password as that used for the original publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25925-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="25925-118">Explanation</span></span>  
 <span data-ttu-id="25925-119">Per ospitare il database del server di pubblicazione, l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve essere un server di pubblicazione di replica.</span><span class="sxs-lookup"><span data-stu-id="25925-119">In order to host the publisher database, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be a replication publisher.</span></span> <span data-ttu-id="25925-120">`sp_validate_redirected_publisher` richiama `sp_helpdistributor` sul server remoto per determinare se il server è un server di pubblicazione di replica.</span><span class="sxs-lookup"><span data-stu-id="25925-120">`sp_validate_redirected_publisher` calls `sp_helpdistributor` at the remote server to determine whether the server is a replication publisher.</span></span> <span data-ttu-id="25925-121">Questo errore viene restituito quando l'esecuzione della stored procedure `sp_helpdistributor` indica che l'istanza di destinazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è un server di pubblicazione di replica.</span><span class="sxs-lookup"><span data-stu-id="25925-121">This error is returned when execution of the stored procedure `sp_helpdistributor` indicates that the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not a replication publisher.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25925-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="25925-122">User Action</span></span>  
 <span data-ttu-id="25925-123">Eseguire `sp_adddistributor` sull'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che ospita il database del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="25925-123">Execute `sp_adddistributor` at the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the publisher database.</span></span> <span data-ttu-id="25925-124">Quando si esegue `sp_adddistributor`, specificare il database di distribuzione corretto.</span><span class="sxs-lookup"><span data-stu-id="25925-124">When running `sp_adddistributor`, specify the correct distributor.</span></span> <span data-ttu-id="25925-125">Utilizzare lo stesso valore per il *@password* parametro utilizzato quando `sp_adddistributor` è stato eseguito inizialmente nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="25925-125">Use the same value for the *@password* parameter as that used when `sp_adddistributor` was initially run at the distributor.</span></span>  
  
  
