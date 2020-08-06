---
title: Rimuovere UDT&#39;s denominato dopo il tipo di dati ORDPATH riservato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 474e910a-6abb-4e28-acc2-055338c011d4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0528d19de17781d863e3a42fdef7db558fe5d190
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726483"
---
# <a name="remove-udt39s-named-after-the-reserved-ordpath-data-type"></a><span data-ttu-id="10989-102">Rimuovi UDT&#39;s denominato dopo il tipo di dati ORDPATH riservato</span><span class="sxs-lookup"><span data-stu-id="10989-102">Remove UDT&#39;s named after the reserved ORDPATH data type</span></span>
  <span data-ttu-id="10989-103">Tramite Preparazione aggiornamento è stato rilevato un tipo definito dall'utente denominato in base a un termine riservato per i tipi di dati `ORDPATH`.</span><span class="sxs-lookup"><span data-stu-id="10989-103">Upgrade Advisor detected a user-defined type (UDT) that is named after a term reserved for the `ORDPATH` data type.</span></span>  
  
## <a name="component"></a><span data-ttu-id="10989-104">Componente</span><span class="sxs-lookup"><span data-stu-id="10989-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="10989-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10989-105">Description</span></span>  
 <span data-ttu-id="10989-106">I termini utilizzati per i tipi di dati predefiniti non devono essere utilizzati come nomi per Common Language Runtime (CLR) o per tipi di dati definiti dall'utente alias.</span><span class="sxs-lookup"><span data-stu-id="10989-106">The terms used for built-in data types should not be used as names for either common language runtime (CLR) or alias UDTs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="10989-107">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="10989-107">Corrective Action</span></span>  
 <span data-ttu-id="10989-108">Rimuovere il tipo definito dall'utente denominato in base al tipo di dati e ricreare il tipo con un nome non riservato.</span><span class="sxs-lookup"><span data-stu-id="10989-108">Remove the UDT that is named after the data type and recreate the UDT with an unreserved name.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="10989-109">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="10989-109">External Resources</span></span>  
 [<span data-ttu-id="10989-110">Creazione di un tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="10989-110">Creating a User-Defined Type</span></span>](../../relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types.md)  
  
  
