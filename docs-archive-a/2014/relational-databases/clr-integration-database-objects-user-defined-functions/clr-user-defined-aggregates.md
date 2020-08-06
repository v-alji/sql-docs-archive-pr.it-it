---
title: Funzioni di aggregazione CLR definite dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- aggregate functions [CLR integration]
- custom aggregates [CLR integration]
- calculations [CLR integration]
- user-defined functions [CLR integration]
ms.assetid: bad9b7e8-5967-4afa-8dc8-6d840faf9372
author: rothja
ms.author: jroth
ms.openlocfilehash: d1ef5d07fe082d0eeb2c3484d6e99572d8fc80e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629438"
---
# <a name="clr-user-defined-aggregates"></a><span data-ttu-id="98c4b-102">Aggregazioni CLR definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="98c4b-102">CLR User-Defined Aggregates</span></span>
  <span data-ttu-id="98c4b-103">Le funzioni di aggregazione eseguono un calcolo su un set di valori e restituiscono un singolo valore.</span><span class="sxs-lookup"><span data-stu-id="98c4b-103">Aggregate functions perform a calculation on a set of values and return a single value.</span></span> <span data-ttu-id="98c4b-104">Tradizionalmente, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha supportato solo funzioni di aggregazione predefinite, ad esempio `SUM` o `MAX` , che operano su un set di valori scalari di input e generano un singolo valore di aggregazione da tale set.</span><span class="sxs-lookup"><span data-stu-id="98c4b-104">Traditionally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has supported only built-in aggregate functions, such as `SUM` or `MAX`, that operate on a set of input scalar values and generate a single aggregate value from that set.</span></span> <span data-ttu-id="98c4b-105">L'integrazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con il CLR [!INCLUDE[msCoName](../../includes/msconame-md.md)] di .NET Framework consente ora agli sviluppatori di creare funzioni di aggregazione personalizzate in codice gestito e di rendere accessibili queste funzioni a [!INCLUDE[tsql](../../includes/tsql-md.md)] o all'altro codice gestito.</span><span class="sxs-lookup"><span data-stu-id="98c4b-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) now allows developers to create custom aggregate functions in managed code, and to make these functions accessible to [!INCLUDE[tsql](../../includes/tsql-md.md)] or other managed code.</span></span>  
  
 <span data-ttu-id="98c4b-106">Nella tabella seguente vengono elencati gli argomenti disponibili in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="98c4b-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="98c4b-107">Requisiti per le aggregazioni CLR definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="98c4b-107">Requirements for CLR User-Defined Aggregates</span></span>](clr-user-defined-aggregates-requirements.md)  
 <span data-ttu-id="98c4b-108">Viene fornita una panoramica dei requisiti per l'implementazione di funzioni di aggregazione CLR definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="98c4b-108">Provides an overview of the requirements for implementing CLR user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="98c4b-109">Chiamata di funzioni di aggregazione CLR definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="98c4b-109">Invoking CLR User-Defined Aggregate Functions</span></span>](clr-user-defined-aggregate-invoking-functions.md)  
 <span data-ttu-id="98c4b-110">Viene illustrato come richiamare aggregazioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="98c4b-110">Explains how to invoke user-defined aggregates.</span></span>  
  
  
