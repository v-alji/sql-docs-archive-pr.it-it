---
title: Errori di sistema imprevisti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 1679bf9e-a2ef-4f90-8907-a002f7341a7d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b791ba0e3f709288a4e2c5b6add4e74e15d56dee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626694"
---
# <a name="unexpected-system-failures"></a><span data-ttu-id="d5c4c-102">Errori di sistema imprevisti</span><span class="sxs-lookup"><span data-stu-id="d5c4c-102">Unexpected System Failures</span></span>
  <span data-ttu-id="d5c4c-103">Questa regola consente di controllare l'evento SYSTEM 6008 nel registro eventi del computer.</span><span class="sxs-lookup"><span data-stu-id="d5c4c-103">This rule checks for SYSTEM Event 6008 in the computer event log.</span></span> <span data-ttu-id="d5c4c-104">Questo evento indica un arresto del sistema imprevisto.</span><span class="sxs-lookup"><span data-stu-id="d5c4c-104">This event indicates an unexpected system shutdown.</span></span> <span data-ttu-id="d5c4c-105">Il sistema potrebbe essere instabile e non fornire la stabilità e l'integrità necessarie per ospitare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5c4c-105">The system might be unstable and might not provide the stability and integrity that is required to host an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="d5c4c-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="d5c4c-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="d5c4c-107">Determinare immediatamente la causa dei riavvii imprevisti del server oppure spostare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un altro computer.</span><span class="sxs-lookup"><span data-stu-id="d5c4c-107">Immediately address the cause of the unexpected server restarts, or move the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to another computer.</span></span>  
  
  
