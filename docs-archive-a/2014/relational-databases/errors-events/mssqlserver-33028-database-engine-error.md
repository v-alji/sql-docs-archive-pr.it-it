---
title: MSSQLSERVER_33028 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33028 (Database Engine error)
ms.assetid: c5cec0e4-0bcd-4907-826f-e7d835cfcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 555dcf0220793abc0e8af81b3f56867f9960c5f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627766"
---
# <a name="mssqlserver_33028"></a><span data-ttu-id="72439-102">MSSQLSERVER_33028</span><span class="sxs-lookup"><span data-stu-id="72439-102">MSSQLSERVER_33028</span></span>
    
## <a name="details"></a><span data-ttu-id="72439-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="72439-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="72439-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="72439-104">Product Name</span></span>|<span data-ttu-id="72439-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="72439-105">SQL Server</span></span>|  
|<span data-ttu-id="72439-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="72439-106">Event ID</span></span>|<span data-ttu-id="72439-107">33028</span><span class="sxs-lookup"><span data-stu-id="72439-107">33028</span></span>|  
|<span data-ttu-id="72439-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="72439-108">Event Source</span></span>|<span data-ttu-id="72439-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="72439-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="72439-110">Componente</span><span class="sxs-lookup"><span data-stu-id="72439-110">Component</span></span>|<span data-ttu-id="72439-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="72439-111">SQLEngine</span></span>|  
|<span data-ttu-id="72439-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="72439-112">Symbolic Name</span></span>|<span data-ttu-id="72439-113">SEC_CRYPTOPROV_CANTOPENSESSION</span><span class="sxs-lookup"><span data-stu-id="72439-113">SEC_CRYPTOPROV_CANTOPENSESSION</span></span>|  
|<span data-ttu-id="72439-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="72439-114">Message Text</span></span>|<span data-ttu-id="72439-115">Impossibile aprire la sessione per % S_MSG '%.\* ls.'</span><span class="sxs-lookup"><span data-stu-id="72439-115">Cannot open session for %S_MSG '%.\*ls'.</span></span> <span data-ttu-id="72439-116">Codice di errore del provider: %d.</span><span class="sxs-lookup"><span data-stu-id="72439-116">Provider error code: %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="72439-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="72439-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="72439-118">non è stato in grado di aprire il provider del servizio di crittografia elencato nel messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="72439-118">was unable to open the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="72439-119">Il codice di errore è stato indicato dal provider del servizio di crittografia.</span><span class="sxs-lookup"><span data-stu-id="72439-119">The cryptographic provider supplied the error code listed.</span></span> <span data-ttu-id="72439-120">Per ulteriori informazioni sull'errore, potrebbe essere necessario contattare il provider.</span><span class="sxs-lookup"><span data-stu-id="72439-120">You may need to contact your cryptographic provider for more information about the error.</span></span>  
  
|<span data-ttu-id="72439-121">Codice di errore</span><span class="sxs-lookup"><span data-stu-id="72439-121">Error code</span></span>|<span data-ttu-id="72439-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72439-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="72439-123">0</span><span class="sxs-lookup"><span data-stu-id="72439-123">0</span></span>|<span data-ttu-id="72439-124">Esito positivo.</span><span class="sxs-lookup"><span data-stu-id="72439-124">Success.</span></span> <span data-ttu-id="72439-125">Nessun errore.</span><span class="sxs-lookup"><span data-stu-id="72439-125">No error.</span></span>|  
|<span data-ttu-id="72439-126">1</span><span class="sxs-lookup"><span data-stu-id="72439-126">1</span></span>|<span data-ttu-id="72439-127">Esito negativo.</span><span class="sxs-lookup"><span data-stu-id="72439-127">Failure.</span></span> <span data-ttu-id="72439-128">Si verificato un errore non specificato o imprevisto.</span><span class="sxs-lookup"><span data-stu-id="72439-128">An unspecified or unexpected error occurred.</span></span> <span data-ttu-id="72439-129">Non sono disponibili informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="72439-129">Additional information is not available.</span></span>|  
|<span data-ttu-id="72439-130">2</span><span class="sxs-lookup"><span data-stu-id="72439-130">2</span></span>|<span data-ttu-id="72439-131">Buffer insufficiente.</span><span class="sxs-lookup"><span data-stu-id="72439-131">Insufficient Buffer.</span></span> <span data-ttu-id="72439-132">Impossibile allocare lo spazio per il provider del servizio di crittografia.</span><span class="sxs-lookup"><span data-stu-id="72439-132">Space could not be allocated for the cryptographic provider.</span></span>|  
|<span data-ttu-id="72439-133">3</span><span class="sxs-lookup"><span data-stu-id="72439-133">3</span></span>|<span data-ttu-id="72439-134">Non supportato.</span><span class="sxs-lookup"><span data-stu-id="72439-134">Not Supported.</span></span> <span data-ttu-id="72439-135">Il provider di crittografia non è supportato da questa versione.</span><span class="sxs-lookup"><span data-stu-id="72439-135">The cryptographic provider is not supported by this release.</span></span> <span data-ttu-id="72439-136">Selezionare un altro provider del servizio di crittografia.</span><span class="sxs-lookup"><span data-stu-id="72439-136">Select another cryptographic provider.</span></span>|  
|<span data-ttu-id="72439-137">4</span><span class="sxs-lookup"><span data-stu-id="72439-137">4</span></span>|<span data-ttu-id="72439-138">Non trovato.</span><span class="sxs-lookup"><span data-stu-id="72439-138">Not Found.</span></span> <span data-ttu-id="72439-139">Il provider del servizio di crittografia specificato non è presente o non si dispone dell'autorizzazione per accedere ai file.</span><span class="sxs-lookup"><span data-stu-id="72439-139">The specified cryptographic provider is not present or you do not have authorization to access the files.</span></span>|  
|<span data-ttu-id="72439-140">5</span><span class="sxs-lookup"><span data-stu-id="72439-140">5</span></span>|<span data-ttu-id="72439-141">Errore di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="72439-141">Authorization Failure.</span></span> <span data-ttu-id="72439-142">Viene visualizzato se si specifica una password o un nome utente errati durante la creazione della credenziale</span><span class="sxs-lookup"><span data-stu-id="72439-142">Can result from providing an incorrect password or username when creating the credential.</span></span> <span data-ttu-id="72439-143">o quando la credenziale non esiste.</span><span class="sxs-lookup"><span data-stu-id="72439-143">Can result if the credential does not exist.</span></span>|  
|<span data-ttu-id="72439-144">6</span><span class="sxs-lookup"><span data-stu-id="72439-144">6</span></span>|<span data-ttu-id="72439-145">Argomento non valido.</span><span class="sxs-lookup"><span data-stu-id="72439-145">Invalid Argument.</span></span> <span data-ttu-id="72439-146">Un argomento non valido è stato passato al provider del servizio di crittografia.</span><span class="sxs-lookup"><span data-stu-id="72439-146">An invalid argument was passed to the cryptographic provider.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="72439-147">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="72439-147">User Action</span></span>  
 <span data-ttu-id="72439-148">Risolvere l'errore o contattare il provider del servizio di crittografia per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="72439-148">Resolve the error, or contact the cryptographic provider for more information.</span></span>  
  
  
