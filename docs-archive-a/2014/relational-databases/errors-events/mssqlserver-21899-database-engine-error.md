---
title: MSSQLSERVER_21899 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21899 (Database Engine error)
ms.assetid: 32b87a7c-5380-4638-b147-dd78618f6625
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cb1af04b56685d0e1b5a703b812d08d88909b693
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715320"
---
# <a name="mssqlserver_21899"></a><span data-ttu-id="48275-102">MSSQLSERVER_21899</span><span class="sxs-lookup"><span data-stu-id="48275-102">MSSQLSERVER_21899</span></span>
    
## <a name="details"></a><span data-ttu-id="48275-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="48275-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48275-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="48275-104">Product Name</span></span>|<span data-ttu-id="48275-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="48275-105">SQL Server</span></span>|  
|<span data-ttu-id="48275-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="48275-106">Event ID</span></span>|<span data-ttu-id="48275-107">21899</span><span class="sxs-lookup"><span data-stu-id="48275-107">21899</span></span>|  
|<span data-ttu-id="48275-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="48275-108">Event Source</span></span>|<span data-ttu-id="48275-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="48275-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="48275-110">Componente</span><span class="sxs-lookup"><span data-stu-id="48275-110">Component</span></span>|<span data-ttu-id="48275-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="48275-111">SQLEngine</span></span>|  
|<span data-ttu-id="48275-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="48275-112">Symbolic Name</span></span>|<span data-ttu-id="48275-113">SQLErrorNum21899</span><span class="sxs-lookup"><span data-stu-id="48275-113">SQLErrorNum21899</span></span>|  
|<span data-ttu-id="48275-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="48275-114">Message Text</span></span>|<span data-ttu-id="48275-115">Impossibile eseguire la query sul server di pubblicazione reindirizzato '%s' per determinare la presenza di voci sysserver per i Sottoscrittori del server di pubblicazione originale '%s'. Errore '%d', messaggio di errore '%s'.</span><span class="sxs-lookup"><span data-stu-id="48275-115">The query at the redirected publisher '%s' to determine whether there were sysserver entries for the subscribers of the original publisher '%s' failed with error '%d', error message '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="48275-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="48275-116">Explanation</span></span>  
 <span data-ttu-id="48275-117">In `sp_validate_redirected_publisher` vengono eseguite le query sulle tabelle di metadati delle sottoscrizioni del database del server di pubblicazione sul server remoto per determinare i sottoscrittori associati.</span><span class="sxs-lookup"><span data-stu-id="48275-117">`sp_validate_redirected_publisher` queries the subscription metadata tables of the publisher database at the remote server to determine its associated subscribers.</span></span> <span data-ttu-id="48275-118">L'errore 21899 viene restituito in caso di errore di questa query.</span><span class="sxs-lookup"><span data-stu-id="48275-118">Error 21899 is returned if this query fails.</span></span> <span data-ttu-id="48275-119">La query della convalida richiede l'accesso al database pubblicato sul server di pubblicazione reindirizzato.</span><span class="sxs-lookup"><span data-stu-id="48275-119">The validation query requires access to the published database at the redirected publisher.</span></span> <span data-ttu-id="48275-120">Se l'accesso, specificato quando `sp_adddistpublisher` viene chiamato per il server di pubblicazione originale, non è autorizzato ad accedere al database pubblicato sul server di pubblicazione reindirizzato, viene restituito l'errore 21899.</span><span class="sxs-lookup"><span data-stu-id="48275-120">If the login specified when `sp_adddistpublisher` is called for the original publisher is not authorized to access the published database at the redirected publisher, error 21899 is returned.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="48275-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="48275-121">User Action</span></span>  
 <span data-ttu-id="48275-122">Controllare il messaggio di errore citato per determinare la causa dell'errore ed eseguire azioni correttive appropriate</span><span class="sxs-lookup"><span data-stu-id="48275-122">Review the cited error message to determine the cause of the failure and take appropriate corrective action</span></span>  
  
  
