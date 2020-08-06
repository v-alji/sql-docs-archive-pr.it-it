---
title: MSSQLSERVER_33081 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33081 (Database Engine error)
ms.assetid: 839705e7-fa37-4c0d-9f3f-95a9eab98bcf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0752220cc20641d9b51a3a66fecc86f9efd63433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627765"
---
# <a name="mssqlserver_33081"></a><span data-ttu-id="65d17-102">MSSQLSERVER_33081</span><span class="sxs-lookup"><span data-stu-id="65d17-102">MSSQLSERVER_33081</span></span>
    
## <a name="details"></a><span data-ttu-id="65d17-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="65d17-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="65d17-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="65d17-104">Product Name</span></span>|<span data-ttu-id="65d17-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="65d17-105">SQL Server</span></span>|  
|<span data-ttu-id="65d17-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="65d17-106">Event ID</span></span>|<span data-ttu-id="65d17-107">33081</span><span class="sxs-lookup"><span data-stu-id="65d17-107">33081</span></span>|  
|<span data-ttu-id="65d17-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="65d17-108">Event Source</span></span>|<span data-ttu-id="65d17-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="65d17-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="65d17-110">Componente</span><span class="sxs-lookup"><span data-stu-id="65d17-110">Component</span></span>|<span data-ttu-id="65d17-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="65d17-111">SQLEngine</span></span>|  
|<span data-ttu-id="65d17-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="65d17-112">Symbolic Name</span></span>|<span data-ttu-id="65d17-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span><span class="sxs-lookup"><span data-stu-id="65d17-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span></span>|  
|<span data-ttu-id="65d17-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="65d17-114">Message Text</span></span>|<span data-ttu-id="65d17-115">Impossibile caricare il provider del servizio di crittografia '%.\*ls' a causa di una firma Authenticode o un percorso file non valido.</span><span class="sxs-lookup"><span data-stu-id="65d17-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span>  <span data-ttu-id="65d17-116">Controllare i messaggi precedenti per altri errori.</span><span class="sxs-lookup"><span data-stu-id="65d17-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="65d17-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="65d17-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="65d17-118">non è stato in grado di caricare il provider del servizio di crittografia elencato nel messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="65d17-118">was unable to load the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="65d17-119">Questo errore può essere provocato da numerose API Windows non corrette.</span><span class="sxs-lookup"><span data-stu-id="65d17-119">There are several Win API failures which might cause this error.</span></span> <span data-ttu-id="65d17-120">Il buffer circolare contiene il nome dell'API non corretta e il codice di errore Windows restituito dall'API.</span><span class="sxs-lookup"><span data-stu-id="65d17-120">The ring buffer contains the name of the failed API and the Windows error code returned by the API.</span></span> <span data-ttu-id="65d17-121">Per ottenere altre informazioni, eseguire una query sulla vista sys.dm_os_ring_buffers nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="65d17-121">To get more information, query the sys.dm_os_ring_buffers view using the following query.</span></span>  
  
```  
SELECT * FROM sys.dm_os_ring_buffers   
WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
```  
  
## <a name="user-action"></a><span data-ttu-id="65d17-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="65d17-122">User Action</span></span>  
 <span data-ttu-id="65d17-123">Per ricercare la causa del problema, individuare il codice di errore Windows in MSDN (https://msdn.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="65d17-123">To investigate the problem, search for the Windows error code in MSDN (https://msdn.microsoft.com/).</span></span> <span data-ttu-id="65d17-124">Risolvere l'errore o contattare il Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)] per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="65d17-124">Resolve the error, or contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] CSS for more information.</span></span> <span data-ttu-id="65d17-125">Se è necessario contattare il Servizio Supporto Tecnico Clienti Microsoft, raccogliere le informazioni seguenti che dovranno essere comunicate al personale di supporto:</span><span class="sxs-lookup"><span data-stu-id="65d17-125">If you need to contact CSS, collect the following information for our support staff.</span></span>  
  
-   <span data-ttu-id="65d17-126">Log degli errori che mostra l'errore relativo all'impossibilità di caricare il provider di crittografia.</span><span class="sxs-lookup"><span data-stu-id="65d17-126">The error log showing the failed to load cryptographic provider error.</span></span>  
  
-   <span data-ttu-id="65d17-127">Output dell'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="65d17-127">The output from the following statement:</span></span>  
  
    ```  
    SELECT * FROM sys.dm_os_ring_buffers   
    WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="65d17-128">Tentare di raccogliere subito le informazioni sul buffer circolare poiché possono essere perse durante un riavvio.</span><span class="sxs-lookup"><span data-stu-id="65d17-128">Try to collect the ring buffer information promptly as ring buffer information can be lost during a restart.</span></span>  
  
  
