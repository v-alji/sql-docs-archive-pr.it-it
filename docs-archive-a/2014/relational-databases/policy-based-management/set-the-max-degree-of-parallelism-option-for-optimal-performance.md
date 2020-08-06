---
title: Impostare l'opzione relativa al massimo grado di parallelismo per ottenere prestazioni ottimali | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: ec908006-67ae-4674-9a61-25ea741d6197
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3043a656cbe1ac1ec40f0d0a67b6eac057005af4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724528"
---
# <a name="set-the-max-degree-of-parallelism-option-for-optimal-performance"></a><span data-ttu-id="e96eb-102">Impostazione dell'opzione relativa al massimo grado di parallelismo per ottenere prestazioni ottimali</span><span class="sxs-lookup"><span data-stu-id="e96eb-102">Set the Max Degree of Parallelism Option for Optimal Performance</span></span>
  <span data-ttu-id="e96eb-103">Questa regola consente di determinare se l'opzione relativa al massimo grado di parallelismo (MAXDOP) sia un valore maggiore di 8.</span><span class="sxs-lookup"><span data-stu-id="e96eb-103">This rule determines whether the max degree of parallelism (MAXDOP) option for a value greater than 8.</span></span> <span data-ttu-id="e96eb-104">L'impostazione di questa opzione su un valore maggiore provoca in genere un utilizzo indesiderato delle risorse e una riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e96eb-104">Setting this option to a larger value often causes unwanted resource consumption and performance degradation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="e96eb-105">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="e96eb-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="e96eb-106">Impostare l'opzione relativa al massimo grado di parallelismo su 8 o su un valore inferiore utilizzando sp_configure.</span><span class="sxs-lookup"><span data-stu-id="e96eb-106">Set the max degree of parallelism option to 8 or less by using sp_configure.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="e96eb-107">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="e96eb-107">For More Information</span></span>  
 [<span data-ttu-id="e96eb-108">Articolo 329204 della Microsoft Knowledge Base</span><span class="sxs-lookup"><span data-stu-id="e96eb-108">Microsoft Knowledge Base article 329204</span></span>](https://go.microsoft.com/fwlink/?linkid=117786)  
  
 [<span data-ttu-id="e96eb-109">Configurare l'opzione di configurazione del server max degree of parallelism</span><span class="sxs-lookup"><span data-stu-id="e96eb-109">Configure the max degree of parallelism Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md)  
  
 [<span data-ttu-id="e96eb-110">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e96eb-110">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
