---
title: Programmazione di stored procedure estese del motore di database | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], programming
- stored procedures [SQL Server], extended
- Database Engine [SQL Server], stored procedures
- macros [SQL Server]
- Extended Stored Procedure API [SQL Server]
ms.assetid: 158a6765-0542-4e84-b5ab-f173d946ef5e
author: rothja
ms.author: jroth
ms.openlocfilehash: fecb8f996ddfcaede83cdb330e9c82bffdce5819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637373"
---
# <a name="database-engine-extended-stored-procedure-programming"></a><span data-ttu-id="6d5a9-102">Programmazione di stored procedure estese del Motore di database</span><span class="sxs-lookup"><span data-stu-id="6d5a9-102">Database Engine Extended Stored Procedure Programming</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="6d5a9-103">Utilizzare invece la funzionalità di integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="6d5a9-103">Use CLR Integration instead.</span></span> <span data-ttu-id="6d5a9-104">Per altre informazioni, vedere [Concetti relativi alla programmazione dell'integrazione con CLR &#40;Common Language Runtime&#41;](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="6d5a9-104">For more information, see [Common Language Runtime &#40;CLR&#41; Integration Programming Concepts](clr-integration/common-language-runtime-clr-integration-programming-concepts.md).</span></span>  
  
 <span data-ttu-id="6d5a9-105">L' [!INCLUDE[msCoName](../includes/msconame-md.md)] API stored procedure estesa fornisce un'API (Application Programming Interface) basata su server per l'estensione della [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6d5a9-105">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Extended Stored Procedure API provides a server-based application programming interface (API) for extending [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="6d5a9-106">L'API è costituita da macro e funzioni C e C++ utilizzate per compilare applicazioni nelle categorie seguenti: stored procedure estese e applicazioni gateway.</span><span class="sxs-lookup"><span data-stu-id="6d5a9-106">The API consists of C and C++ functions and macros used to build applications in the following categories: extended stored procedures and gateway applications.</span></span>  
  
 <span data-ttu-id="6d5a9-107">Le stored procedure estese consentono di creare routine esterne personalizzate in un linguaggio di programmazione quale C. Le stored procedure estese appaiono come stored procedure normali e vengono eseguite in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="6d5a9-107">Extended stored procedures allow you to create your own external routines in a programming language such as C. The extended stored procedures appear to users as typical stored procedures and are executed in the same way.</span></span> <span data-ttu-id="6d5a9-108">È possibile passare parametri alle stored procedure estese che possono restituire risultati e informazioni sullo stato.</span><span class="sxs-lookup"><span data-stu-id="6d5a9-108">Parameters can be passed to extended stored procedures, and they can return results and return status.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d5a9-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6d5a9-109">In This Section</span></span>  
 [<span data-ttu-id="6d5a9-110">Programmazione di stored procedure estese</span><span class="sxs-lookup"><span data-stu-id="6d5a9-110">Programming Extended Stored Procedures</span></span>](extended-stored-procedures-programming/database-engine-extended-stored-procedures-programming.md)  
 <span data-ttu-id="6d5a9-111">Viene illustrato come creare, gestire e utilizzare stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="6d5a9-111">Explains how to create, manage, and use extended stored procedures.</span></span>  
  
 [<span data-ttu-id="6d5a9-112">Guida di riferimento per i programmatori delle stored procedure estese</span><span class="sxs-lookup"><span data-stu-id="6d5a9-112">Extended Stored Procedures Programmer's Reference</span></span>](extended-stored-procedures-reference/database-engine-extended-stored-procedures-reference.md)  
 <span data-ttu-id="6d5a9-113">Contiene argomenti di riferimento per l'API Stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="6d5a9-113">Contains reference topics for the Extended Stored Procedure API.</span></span>  
  
  
