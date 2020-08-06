---
title: MSSQLSERVER_33129 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33129 (Database Engine error)
ms.assetid: 83b5f368-f1a1-4a40-9bb6-c77e2dec690f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da7735889dce8bfc33e624115e8245f8a02f46b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627762"
---
# <a name="mssqlserver_33129"></a><span data-ttu-id="c2630-102">MSSQLSERVER_33129</span><span class="sxs-lookup"><span data-stu-id="c2630-102">MSSQLSERVER_33129</span></span>
    
## <a name="details"></a><span data-ttu-id="c2630-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c2630-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c2630-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="c2630-104">Product Name</span></span>|<span data-ttu-id="c2630-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c2630-105">SQL Server</span></span>|  
|<span data-ttu-id="c2630-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="c2630-106">Event ID</span></span>|<span data-ttu-id="c2630-107">33129</span><span class="sxs-lookup"><span data-stu-id="c2630-107">33129</span></span>|  
|<span data-ttu-id="c2630-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="c2630-108">Event Source</span></span>|<span data-ttu-id="c2630-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c2630-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c2630-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c2630-110">Component</span></span>|<span data-ttu-id="c2630-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c2630-111">SQLEngine</span></span>|  
|<span data-ttu-id="c2630-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="c2630-112">Symbolic Name</span></span>|<span data-ttu-id="c2630-113">SEC_CANNOT_DISABLE_WIN_GROUP</span><span class="sxs-lookup"><span data-stu-id="c2630-113">SEC_CANNOT_DISABLE_WIN_GROUP</span></span>|  
|<span data-ttu-id="c2630-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="c2630-114">Message Text</span></span>|<span data-ttu-id="c2630-115">Non è possibile utilizzare ALTER_LOGIN con l'argomento DISABLE per negare l'accesso a un gruppo di Windows.</span><span class="sxs-lookup"><span data-stu-id="c2630-115">Cannot use ALTER_LOGIN with the DISABLE argument to deny access to a Windows group.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c2630-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="c2630-116">Explanation</span></span>  
 <span data-ttu-id="c2630-117">Questo messaggio viene visualizzato se si tenta di disabilitare l'accesso di un Gruppo di Windows.</span><span class="sxs-lookup"><span data-stu-id="c2630-117">This message occurs when attempting to disable the login of a Windows Group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c2630-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="c2630-118">User Action</span></span>  
 <span data-ttu-id="c2630-119">Impossibile disabilitare l'accesso di un Gruppo di Windows.</span><span class="sxs-lookup"><span data-stu-id="c2630-119">The login of a Windows Group cannot be disabled.</span></span> <span data-ttu-id="c2630-120">Per rimuovere temporaneamente l'autorizzazione di accesso concessa a un Gruppo di Windows, revocare l'autorizzazione CONNECT dell'accesso per il Gruppo di Windows.</span><span class="sxs-lookup"><span data-stu-id="c2630-120">To temporarily remove access permission granted to a Windows Group, REVOKE the CONNECT permission of the login for the Windows Group.</span></span> <span data-ttu-id="c2630-121">Gli utenti di Windows potrebbero continuare a disporre dell'accesso tramite il proprio accesso individuale o un altro Gruppo di Windows.</span><span class="sxs-lookup"><span data-stu-id="c2630-121">Windows users might still have access through their individual login or through another Windows Group.</span></span> <span data-ttu-id="c2630-122">L'esempio seguente revoca l'autorizzazione di connessione al gruppo Contabilità del dominio WESTCOAST.</span><span class="sxs-lookup"><span data-stu-id="c2630-122">The following example revokes the connect permission to the Accounting Group of the WESTCOAST domain.</span></span>  
  
```sql  
REVOKE CONNECT TO [WESTCOAST\Accounting];  
```  
  
  
