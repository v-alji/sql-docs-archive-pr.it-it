---
title: MSSQLSERVER_33027 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33027 (Database Engine error)
ms.assetid: bfdc626e-7958-4511-987d-3b687824e8af
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f6bb461b42b66368224fffd2c14f9b4da61abf5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627767"
---
# <a name="mssqlserver_33027"></a><span data-ttu-id="5fff1-102">MSSQLSERVER_33027</span><span class="sxs-lookup"><span data-stu-id="5fff1-102">MSSQLSERVER_33027</span></span>
    
## <a name="details"></a><span data-ttu-id="5fff1-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5fff1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fff1-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="5fff1-104">Product Name</span></span>|<span data-ttu-id="5fff1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5fff1-105">SQL Server</span></span>|  
|<span data-ttu-id="5fff1-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="5fff1-106">Event ID</span></span>|<span data-ttu-id="5fff1-107">33027</span><span class="sxs-lookup"><span data-stu-id="5fff1-107">33027</span></span>|  
|<span data-ttu-id="5fff1-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="5fff1-108">Event Source</span></span>|<span data-ttu-id="5fff1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5fff1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5fff1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5fff1-110">Component</span></span>|<span data-ttu-id="5fff1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5fff1-111">SQLEngine</span></span>|  
|<span data-ttu-id="5fff1-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="5fff1-112">Symbolic Name</span></span>|<span data-ttu-id="5fff1-113">SEC_CRYPTOPROV_CANTLOADDLL</span><span class="sxs-lookup"><span data-stu-id="5fff1-113">SEC_CRYPTOPROV_CANTLOADDLL</span></span>|  
|<span data-ttu-id="5fff1-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5fff1-114">Message Text</span></span>|<span data-ttu-id="5fff1-115">Impossibile caricare il provider del servizio di crittografia '%.\*ls' a causa di una firma Authenticode o un percorso file non valido.</span><span class="sxs-lookup"><span data-stu-id="5fff1-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span> <span data-ttu-id="5fff1-116">Controllare i messaggi precedenti per altri errori.</span><span class="sxs-lookup"><span data-stu-id="5fff1-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5fff1-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5fff1-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5fff1-118">non è stato in grado di usare il provider del servizio di crittografia elencato nel messaggio di errore perché [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è in grado di caricare la DLL.</span><span class="sxs-lookup"><span data-stu-id="5fff1-118">was unable to use the cryptographic provider listed in the error message, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not load the DLL.</span></span> <span data-ttu-id="5fff1-119">Il nome non è valido o la firma Authenticode è non valida.</span><span class="sxs-lookup"><span data-stu-id="5fff1-119">Either the name is invalid or the Authenticode signature is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5fff1-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="5fff1-120">User Action</span></span>  
 <span data-ttu-id="5fff1-121">Verificare che il file sia presente e che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponga dell'autorizzazione ad accedere a tale percorso.</span><span class="sxs-lookup"><span data-stu-id="5fff1-121">Check that the file is present and that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has permission to access that location.</span></span> <span data-ttu-id="5fff1-122">Per visualizzare altri messaggi correlati, controllare il log degli errori.</span><span class="sxs-lookup"><span data-stu-id="5fff1-122">Check the error log for additional related messages.</span></span> <span data-ttu-id="5fff1-123">In caso contrario, contattare il provider del servizio di crittografia per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="5fff1-123">Otherwise, contact the cryptographic provider for more information.</span></span>  
  
  
