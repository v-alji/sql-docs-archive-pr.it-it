---
title: MSSQL_ENG018456 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG018456 error
ms.assetid: 3daa8144-d81f-445a-b6c3-4bb3e9fd1526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b05ca549781215e0c4f247110fee87f6def56f04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717969"
---
# <a name="mssql_eng018456"></a><span data-ttu-id="fa993-102">MSSQL_ENG018456</span><span class="sxs-lookup"><span data-stu-id="fa993-102">MSSQL_ENG018456</span></span>
    
## <a name="message-details"></a><span data-ttu-id="fa993-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="fa993-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa993-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="fa993-104">Product Name</span></span>|<span data-ttu-id="fa993-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fa993-105">SQL Server</span></span>|  
|<span data-ttu-id="fa993-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="fa993-106">Event ID</span></span>|<span data-ttu-id="fa993-107">18456</span><span class="sxs-lookup"><span data-stu-id="fa993-107">18456</span></span>|  
|<span data-ttu-id="fa993-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="fa993-108">Event Source</span></span>|<span data-ttu-id="fa993-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fa993-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fa993-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fa993-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="fa993-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="fa993-111">Symbolic Name</span></span>||  
|<span data-ttu-id="fa993-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="fa993-112">Message Text</span></span>|<span data-ttu-id="fa993-113">Accesso non riuscito per l'utente '%.\*ls'.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="fa993-113">Login failed for user '%.\*ls'.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fa993-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="fa993-114">Explanation</span></span>  
 <span data-ttu-id="fa993-115">L'errore MSSQL_ENG018456 viene generato quando un tentativo di accesso non riesce.</span><span class="sxs-lookup"><span data-stu-id="fa993-115">Error MSSQL_ENG018456 is raised whenever a login attempt fails.</span></span> <span data-ttu-id="fa993-116">Se il messaggio di errore include l'account **distributor_admin** (Accesso non riuscito per l'utente 'distributor_admin'.) il problema riguarda un account utilizzato dalla replica.</span><span class="sxs-lookup"><span data-stu-id="fa993-116">If the error message includes the account **distributor_admin** (Login failed for user 'distributor_admin'.), the issue is with an account used by replication.</span></span> <span data-ttu-id="fa993-117">La replica crea un server remoto, **repl_distributor**, che consente la comunicazione tra il server di distribuzione e quello di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="fa993-117">Replication creates a remote server, **repl_distributor**, which allows communication between the Distributor and Publisher.</span></span> <span data-ttu-id="fa993-118">L'account di accesso **distributor_admin** è associato a questo server remoto e deve avere una password valida.</span><span class="sxs-lookup"><span data-stu-id="fa993-118">The login **distributor_admin** is associated with this remote server and must have a valid password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa993-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="fa993-119">User Action</span></span>  
 <span data-ttu-id="fa993-120">Verificare di avere specificato la password per questo account.</span><span class="sxs-lookup"><span data-stu-id="fa993-120">Ensure that you have specified a password for this account.</span></span> <span data-ttu-id="fa993-121">Per altre informazioni, vedere [Sicurezza del database di distribuzione](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="fa993-121">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa993-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa993-122">See Also</span></span>  
 [<span data-ttu-id="fa993-123">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="fa993-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
