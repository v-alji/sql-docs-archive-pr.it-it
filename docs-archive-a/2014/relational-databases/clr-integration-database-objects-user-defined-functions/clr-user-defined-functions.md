---
title: Funzioni CLR definite dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- building database objects [CLR integration], user-defined functions
- functions [CLR integration]
- common language runtime [SQL Server], user-defined functions
- database objects [CLR integration], user-defined functions
- user-defined functions [CLR integration]
ms.assetid: 6f7491f1-9a46-4146-ae09-056248634de2
author: rothja
ms.author: jroth
ms.openlocfilehash: ba7a4a983ec0cb36ef0fd79df44491f7f23f7648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635660"
---
# <a name="clr-user-defined-functions"></a><span data-ttu-id="086cd-102">Funzioni definite dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="086cd-102">CLR User-Defined Functions</span></span>
  <span data-ttu-id="086cd-103">Le funzioni definite dall'utente sono routine che possono accettare parametri, eseguire calcoli o altre azioni e restituire un risultato.</span><span class="sxs-lookup"><span data-stu-id="086cd-103">User-defined functions are routines that can take parameters, perform calculations or other actions, and return a result.</span></span> <span data-ttu-id="086cd-104">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], è possibile scrivere le funzioni definite dall'utente in qualsiasi linguaggio di programmazione [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework, ad esempio [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="086cd-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can write user-defined functions in any [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework programming language, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic .NET or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="086cd-105">Esistono due tipi di funzioni: scalari, che restituiscono un solo valore, e con valori di tabella, che restituiscono un set di righe.</span><span class="sxs-lookup"><span data-stu-id="086cd-105">There are two types of functions: scalar, which returns a single value, and table-valued, which returns a set of rows.</span></span>  
  
 <span data-ttu-id="086cd-106">Nella tabella seguente vengono elencati gli argomenti disponibili in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="086cd-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="086cd-107">Funzioni a valori scalari CLR</span><span class="sxs-lookup"><span data-stu-id="086cd-107">CLR Scalar-Valued Functions</span></span>](clr-scalar-valued-functions.md)  
 <span data-ttu-id="086cd-108">Vengono descritti i requisiti di implementazione e vengono forniti esempi delle funzioni scalari e con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="086cd-108">Covers implementation requirements and examples of scalar-valued functions.</span></span>  
  
 [<span data-ttu-id="086cd-109">Funzioni CLR con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="086cd-109">CLR Table-Valued Functions</span></span>](clr-table-valued-functions.md)  
 <span data-ttu-id="086cd-110">Viene illustrato come implementare e utilizzare funzioni valutate a livello di tabella (TVF) e vengono discusse le differenze tra le funzioni TVF CLR (Common Language Runtime) e [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="086cd-110">Discusses how to implement and use table-valued functions (TVFs), as well as differences between [!INCLUDE[tsql](../../includes/tsql-md.md)] and common language runtime (CLR) TVFs.</span></span>  
  
 [<span data-ttu-id="086cd-111">Aggregazioni CLR definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="086cd-111">CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates.md)  
 <span data-ttu-id="086cd-112">Viene descritto come implementare e utilizzare le aggregazioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="086cd-112">Describes how to implement and use user-defined aggregates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="086cd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="086cd-113">See Also</span></span>  
 [<span data-ttu-id="086cd-114">Funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="086cd-114">User-Defined Functions</span></span>](../user-defined-functions/user-defined-functions.md)  
  
  
