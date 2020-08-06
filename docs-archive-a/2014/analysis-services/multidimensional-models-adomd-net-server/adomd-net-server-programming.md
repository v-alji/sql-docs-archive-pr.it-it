---
title: Programmazione del server ADOMD.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- programming [ADOMD.NET]
- ADOMD.NET, programming
ms.assetid: 7f7ff5be-3826-43a5-b94d-ddeec5ddb2eb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 522478af0b19f1745d80f167e40345d4751136b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711119"
---
# <a name="adomdnet-server-programming"></a><span data-ttu-id="4170b-102">Programmazione di server ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="4170b-102">ADOMD.NET Server Programming</span></span>
  <span data-ttu-id="4170b-103">I componenti server ADOMD.NET di ADOMD.NET si trovano nello spazio dei nomi `Microsoft.AnalysisServices.AdomdServer` (in msmgdsrv.dll).</span><span class="sxs-lookup"><span data-stu-id="4170b-103">The ADOMD.NET server components of ADOMD.NET reside within the `Microsoft.AnalysisServices.AdomdServer` namespace (in msmgdsrv.dll).</span></span> <span data-ttu-id="4170b-104">Questi componenti server vengono utilizzati per creare funzioni MDX (Multidimensional Expression) personalizzate e stored procedure eseguite in un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4170b-104">You use these server components to create custom Multidimensional Expressions (MDX) functions and stored procedures that are run on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="4170b-105">Gli oggetti server forniscono le funzionalità per l'esecuzione di query su cubi e modelli di data mining e per la valutazione di espressioni in un contesto specifico.</span><span class="sxs-lookup"><span data-stu-id="4170b-105">The server objects provide the capabilities for querying cubes and mining models, and for evaluating expressions in a given context.</span></span> <span data-ttu-id="4170b-106">I vantaggi relativi alla creazione di funzioni e stored procedure personalizzate includono un'esecuzione rapida, una distribuzione centralizzata e una gestibilità migliorata.</span><span class="sxs-lookup"><span data-stu-id="4170b-106">The benefits for creating custom functions and stored procedures include fast execution, centralized deployment, and improved maintainability.</span></span>  
  
 <span data-ttu-id="4170b-107">Gli argomenti indicati nella tabella seguente consentiranno di sviluppare applicazioni server ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="4170b-107">The topics in the following table will help you develop ADOMD.NET server applications.</span></span>  
  
|<span data-ttu-id="4170b-108">Argomento</span><span class="sxs-lookup"><span data-stu-id="4170b-108">Topic</span></span>|<span data-ttu-id="4170b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4170b-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4170b-110">Funzionalità server di ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="4170b-110">ADOMD.NET Server Functionality</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-functionality)|<span data-ttu-id="4170b-111">Descrive gli utilizzi relativi agli oggetti del server ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="4170b-111">Describes the uses for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="4170b-112">Architettura degli oggetti server in ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="4170b-112">ADOMD.NET Server Object Architecture</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-object-architecture)|<span data-ttu-id="4170b-113">Descrive l'architettura relativa agli oggetti server ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="4170b-113">Describes the object architecture for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="4170b-114">Funzioni definite dall'utente e stored procedure</span><span class="sxs-lookup"><span data-stu-id="4170b-114">User Defined Functions and Stored Procedures</span></span>](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-server/user-defined-functions-and-stored-procedures)|<span data-ttu-id="4170b-115">Illustra il processo di creazione di una funzione definita dall'utente o di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="4170b-115">Walks you through the process of creating a user defined function or stored Procedure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4170b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4170b-116">See Also</span></span>  
 <span data-ttu-id="4170b-117">[Programmazione client ADOMD.NET](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span><span class="sxs-lookup"><span data-stu-id="4170b-117">[ADOMD.NET Client Programming](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span></span>  
 [<span data-ttu-id="4170b-118">Sviluppo con ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="4170b-118">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
  
  
