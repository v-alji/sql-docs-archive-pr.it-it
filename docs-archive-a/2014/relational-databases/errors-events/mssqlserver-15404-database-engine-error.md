---
title: MSSQLSERVER_15404 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15404 (Database Engine error)
ms.assetid: 69677f02-bc81-4e4a-99b8-5c1bd1de36df
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beb854c866256728574e06f8c9efb50fb354e15a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636158"
---
# <a name="mssqlserver_15404"></a><span data-ttu-id="0c92b-102">MSSQLSERVER_15404</span><span class="sxs-lookup"><span data-stu-id="0c92b-102">MSSQLSERVER_15404</span></span>
    
## <a name="details"></a><span data-ttu-id="0c92b-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0c92b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c92b-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0c92b-104">Product Name</span></span>|<span data-ttu-id="0c92b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0c92b-105">SQL Server</span></span>|  
|<span data-ttu-id="0c92b-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="0c92b-106">Event ID</span></span>|<span data-ttu-id="0c92b-107">15404</span><span class="sxs-lookup"><span data-stu-id="0c92b-107">15404</span></span>|  
|<span data-ttu-id="0c92b-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0c92b-108">Event Source</span></span>|<span data-ttu-id="0c92b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0c92b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0c92b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0c92b-110">Component</span></span>|<span data-ttu-id="0c92b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0c92b-111">SQLEngine</span></span>|  
|<span data-ttu-id="0c92b-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0c92b-112">Symbolic Name</span></span>|<span data-ttu-id="0c92b-113">SEC_NTGRP_ERROR</span><span class="sxs-lookup"><span data-stu-id="0c92b-113">SEC_NTGRP_ERROR</span></span>|  
|<span data-ttu-id="0c92b-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0c92b-114">Message Text</span></span>|<span data-ttu-id="0c92b-115">Non è stato possibile ottenere informazioni relative al gruppo/utente di Windows NT '*user*', codice di errore *code*.</span><span class="sxs-lookup"><span data-stu-id="0c92b-115">Could not obtain information about Windows NT group/user '*user*', error code *code*.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0c92b-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0c92b-116">Explanation</span></span>  
 <span data-ttu-id="0c92b-117">L'errore 15404 è utilizzato nell'autenticazione quando si specifica un'entità non valida.</span><span class="sxs-lookup"><span data-stu-id="0c92b-117">15404 is used in authentication when an invalid principal is specified.</span></span> <span data-ttu-id="0c92b-118">In alternativa, la rappresentazione di un account di Windows ha esito negativo poiché non esiste alcuna relazione di trust completo tra l'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il dominio dell'account di Windows.</span><span class="sxs-lookup"><span data-stu-id="0c92b-118">Or, impersonation of a Windows account fails because there is no full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0c92b-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0c92b-119">User Action</span></span>  
 <span data-ttu-id="0c92b-120">Verificare che l'entità di Windows esista e non siano stati commessi errori di digitazione.</span><span class="sxs-lookup"><span data-stu-id="0c92b-120">Check that the Windows principal exists and is not misspelled.</span></span>  
  
 <span data-ttu-id="0c92b-121">Se questo errore è dovuto all'assenza di una relazione di trust completo tra l'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e il dominio dell'account di Windows, è possibile risolvere il problema tramite una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c92b-121">If this error is the result of a lack of a full trust relationship between the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and the domain of the Windows account, one of the following actions can resolve the error:</span></span>  
  
-   <span data-ttu-id="0c92b-122">Utilizzare un account dello stesso dominio dell'utente di Windows per il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c92b-122">Use an account from the same domain as the Windows user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="0c92b-123">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizza un account computer, ad esempio Servizio di rete o Sistema locale, il computer deve essere considerato attendibile dal dominio che contiene l'utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="0c92b-123">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is using a machine account such as Network Service or Local System, the machine must be trusted by the domain containing the Windows User.</span></span>  
  
-   <span data-ttu-id="0c92b-124">Utilizzare un account di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c92b-124">Use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account.</span></span>  
  
  
