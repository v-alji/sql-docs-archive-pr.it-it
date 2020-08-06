---
title: MSSQLSERVER_26014 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 26014 (Database Engine error)
ms.assetid: e2b0dfc7-0681-4e5d-8875-1d5f63534086
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8114183b212767d01013eee9387d8b2efa2e0d7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628743"
---
# <a name="mssqlserver_26014"></a><span data-ttu-id="14a71-102">MSSQLSERVER_26014</span><span class="sxs-lookup"><span data-stu-id="14a71-102">MSSQLSERVER_26014</span></span>
    
## <a name="details"></a><span data-ttu-id="14a71-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="14a71-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14a71-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="14a71-104">Product Name</span></span>|<span data-ttu-id="14a71-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="14a71-105">SQL Server</span></span>|  
|<span data-ttu-id="14a71-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="14a71-106">Event ID</span></span>|<span data-ttu-id="14a71-107">26014</span><span class="sxs-lookup"><span data-stu-id="14a71-107">26014</span></span>|  
|<span data-ttu-id="14a71-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="14a71-108">Event Source</span></span>|<span data-ttu-id="14a71-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="14a71-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="14a71-110">Componente</span><span class="sxs-lookup"><span data-stu-id="14a71-110">Component</span></span>|<span data-ttu-id="14a71-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="14a71-111">SQLEngine</span></span>|  
|<span data-ttu-id="14a71-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="14a71-112">Symbolic Name</span></span>|<span data-ttu-id="14a71-113">SNI_SSL_USER_CERT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="14a71-113">SNI_SSL_USER_CERT_FAILURE</span></span>|  
|<span data-ttu-id="14a71-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="14a71-114">Message Text</span></span>|<span data-ttu-id="14a71-115">Impossibile caricare il certificato specificato dall'utente [Cert Hash(sha1) "%hs"].</span><span class="sxs-lookup"><span data-stu-id="14a71-115">Unable to load user-specified certificate [Cert Hash(sha1) "%hs"].</span></span> <span data-ttu-id="14a71-116">Il server non accetterà la connessione.</span><span class="sxs-lookup"><span data-stu-id="14a71-116">The server will not accept a connection.</span></span> <span data-ttu-id="14a71-117">Verificare che il certificato sia installato in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="14a71-117">You should verify that the certificate is correctly installed.</span></span> <span data-ttu-id="14a71-118">Vedere la sezione relativa alla configurazione dei certificati per l'utilizzo con SSL nella documentazione online.</span><span class="sxs-lookup"><span data-stu-id="14a71-118">See "Configuring Certificate for Use by SSL" in Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="14a71-119">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="14a71-119">Explanation</span></span>  
 <span data-ttu-id="14a71-120">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stato eseguito un tentativo di caricare il certificato indicato nel messaggio, ma l'operazione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="14a71-120">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attempted to load the certificate named in the message but the operation failed.</span></span> <span data-ttu-id="14a71-121">Prima che in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sia possibile utilizzare questo certificato, è necessario risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="14a71-121">This problem must be resolved before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use this certificate.</span></span>  
  
 <span data-ttu-id="14a71-122">Alcune cause possibili dell'errore sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="14a71-122">Possible causes of the error include:</span></span>  
  
-   <span data-ttu-id="14a71-123">È possibile che il certificato sia stato spostato o eliminato.</span><span class="sxs-lookup"><span data-stu-id="14a71-123">The certificate could have been moved or deleted.</span></span>  
  
-   <span data-ttu-id="14a71-124">Se l'account di accesso utilizzato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stato modificato, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] potrebbero non essere disponibili le autorizzazioni per accedere al certificato.</span><span class="sxs-lookup"><span data-stu-id="14a71-124">If the login used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has changed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] may not have permission to access the certificate.</span></span>  
  
-   <span data-ttu-id="14a71-125">Il certificato potrebbe essere scaduto.</span><span class="sxs-lookup"><span data-stu-id="14a71-125">The certificate may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14a71-126">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="14a71-126">User Action</span></span>  
 <span data-ttu-id="14a71-127">Verificare che certificato indicato nel messaggio esista nel sistema, che sia accessibile e che sia valido per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="14a71-127">Make sure the certificate named in the message exists on the system, is accessible, and it is valid for use.</span></span>  
  
  
