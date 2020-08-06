---
title: Rimuovere UDT&#39;s denominato dopo i tipi di dati di data e ora riservati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- time data type [SQL Server], UDTs
- date data type [SQL Server], UDTs
ms.assetid: 48f109af-b1d1-4f03-a7e3-8a0b05ed94e8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 827f060b309a7a620fd448554b074f45d78d3cb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635355"
---
# <a name="remove-udt39s-named-after-the-reserved-date-and-time-data-types"></a><span data-ttu-id="4083d-102">Rimuovi UDT&#39;s denominato dopo i tipi di dati riservati di data e ora</span><span class="sxs-lookup"><span data-stu-id="4083d-102">Remove UDT&#39;s named after the reserved DATE and TIME data types</span></span>
  <span data-ttu-id="4083d-103">È stato rilevato un tipo definito dall'utente denominato in base a un termine riservato per i tipi di dati `date` o `time`.</span><span class="sxs-lookup"><span data-stu-id="4083d-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for either the `date` or the `time` data types.</span></span>  
  
## <a name="component"></a><span data-ttu-id="4083d-104">Componente</span><span class="sxs-lookup"><span data-stu-id="4083d-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="4083d-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4083d-105">Description</span></span>  
 <span data-ttu-id="4083d-106">Non è consigliabile utilizzare i termini utilizzati per i tipi di dati come nomi per Common Language Runtime (CLR) o per tipi di dati definiti dall'utente alias.</span><span class="sxs-lookup"><span data-stu-id="4083d-106">The terms used for data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="4083d-107">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="4083d-107">Corrective Action</span></span>  
 <span data-ttu-id="4083d-108">Rimuovere il tipo definito dall'utente denominato in base al tipo di dati e ricreare il tipo con un nome non riservato.</span><span class="sxs-lookup"><span data-stu-id="4083d-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
  
