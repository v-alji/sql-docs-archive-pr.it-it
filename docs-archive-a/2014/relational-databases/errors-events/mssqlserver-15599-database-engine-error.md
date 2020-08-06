---
title: MSSQLSERVER_15599 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15599 (Database Engine error)
ms.assetid: 97e427a9-8587-46ea-954b-974b5df9c223
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 15f1b3eb6d97837f1c1c4a9944535cade5b31300
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636155"
---
# <a name="mssqlserver_15599"></a><span data-ttu-id="9458f-102">MSSQLSERVER_15599</span><span class="sxs-lookup"><span data-stu-id="9458f-102">MSSQLSERVER_15599</span></span>
    
## <a name="details"></a><span data-ttu-id="9458f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9458f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9458f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="9458f-104">Product Name</span></span>|<span data-ttu-id="9458f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9458f-105">SQL Server</span></span>|  
|<span data-ttu-id="9458f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="9458f-106">Event ID</span></span>|<span data-ttu-id="9458f-107">15599</span><span class="sxs-lookup"><span data-stu-id="9458f-107">15599</span></span>|  
|<span data-ttu-id="9458f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="9458f-108">Event Source</span></span>|<span data-ttu-id="9458f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9458f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9458f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9458f-110">Component</span></span>|<span data-ttu-id="9458f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9458f-111">SQLEngine</span></span>|  
|<span data-ttu-id="9458f-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="9458f-112">Symbolic Name</span></span>|<span data-ttu-id="9458f-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span><span class="sxs-lookup"><span data-stu-id="9458f-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span></span>|  
|<span data-ttu-id="9458f-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="9458f-114">Message Text</span></span>|<span data-ttu-id="9458f-115">Impossibile impostare controllo e autorizzazioni in oggetti temporanei locali.</span><span class="sxs-lookup"><span data-stu-id="9458f-115">Auditing and permissions can't be set on local temporary objects.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9458f-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="9458f-116">Explanation</span></span>  
 <span data-ttu-id="9458f-117">Il controllo e le autorizzazioni non hanno alcuno effetto quando si impostano oggetti temporanei locali o globali.</span><span class="sxs-lookup"><span data-stu-id="9458f-117">Auditing and permissions do not have any effect when set for local or global temp objects.</span></span> <span data-ttu-id="9458f-118">Le istruzioni non restituiscono un errore e verranno eseguite correttamente, ma non hanno effetto.</span><span class="sxs-lookup"><span data-stu-id="9458f-118">The statements do not result in an error (the operations will return success), but have no effect.</span></span>  
  
 <span data-ttu-id="9458f-119">Questo comportamento non viene modificato. Tuttavia, a partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], il messaggio ha lo scopo informativo di avvisare l'utente.</span><span class="sxs-lookup"><span data-stu-id="9458f-119">This behavior has not changed, however beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this informational message alerts the user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9458f-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="9458f-120">User Action</span></span>  
 <span data-ttu-id="9458f-121">Non è necessaria alcuna azione, ma è opportuno prendere in considerazione la rimozione delle istruzioni che tentano di impostare controllo o autorizzazioni sugli oggetti temporanei locali o globali.</span><span class="sxs-lookup"><span data-stu-id="9458f-121">No action is necessary, but consider removing statements that attempt to set auditing or permissions on local or global temp objects.</span></span>  
  
  
