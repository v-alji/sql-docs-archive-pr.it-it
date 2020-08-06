---
title: MSSQL_ENG020596 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020596 error
ms.assetid: fa33627c-2e99-4be3-9424-52ab83446e07
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b1c61f3683442e0d474ff36a65c89446dbd7bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637792"
---
# <a name="mssql_eng020596"></a><span data-ttu-id="b11ad-102">MSSQL_ENG020596</span><span class="sxs-lookup"><span data-stu-id="b11ad-102">MSSQL_ENG020596</span></span>
    
## <a name="message-details"></a><span data-ttu-id="b11ad-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="b11ad-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b11ad-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b11ad-104">Product Name</span></span>|<span data-ttu-id="b11ad-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b11ad-105">SQL Server</span></span>|  
|<span data-ttu-id="b11ad-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b11ad-106">Event ID</span></span>|<span data-ttu-id="b11ad-107">20596</span><span class="sxs-lookup"><span data-stu-id="b11ad-107">20596</span></span>|  
|<span data-ttu-id="b11ad-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b11ad-108">Event Source</span></span>|<span data-ttu-id="b11ad-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b11ad-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b11ad-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b11ad-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="b11ad-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b11ad-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b11ad-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b11ad-112">Message Text</span></span>|<span data-ttu-id="b11ad-113">L'agente anonimo può essere eliminato solo da '%s' e dai membri del ruolo db_owner.</span><span class="sxs-lookup"><span data-stu-id="b11ad-113">Only '%s' or members of db_owner can drop the anonymous agent.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b11ad-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b11ad-114">Explanation</span></span>  
 <span data-ttu-id="b11ad-115">Non si dispone di autorizzazioni sufficienti per eliminare l'agente della sottoscrizione anonima.</span><span class="sxs-lookup"><span data-stu-id="b11ad-115">You do not have sufficient permissions to drop the agent for the anonymous subscription.</span></span> <span data-ttu-id="b11ad-116">L'account di accesso usato per chiamare [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql) deve essere un membro del ruolo predefinito del server **sysadmin** nel server di distribuzione o del ruolo predefinito del database **db_owner** nel database di distribuzione oppure l'utente deve essere lo stesso che ha avviato la prima esecuzione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="b11ad-116">The login used when calling [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql) must be a member of the **sysadmin** fixed server role at the Distributor or **db_owner** fixed database role in the distribution database, or the user must be the one that initiated the first run of the agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b11ad-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b11ad-117">User Action</span></span>  
 <span data-ttu-id="b11ad-118">Accedere con le credenziali appropriate ed eseguire **sp_dropanonymousagent**.</span><span class="sxs-lookup"><span data-stu-id="b11ad-118">Login with the appropriate credentials, and execute **sp_dropanonymousagent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b11ad-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b11ad-119">See Also</span></span>  
 [<span data-ttu-id="b11ad-120">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="b11ad-120">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
