---
title: ISSCommandWithParameters (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSCommandWithParameters interface
ms.assetid: 3419b7f3-36a3-4863-816e-e641e4e90496
author: rothja
ms.author: jroth
ms.openlocfilehash: 295026497a97b4ce13d1a1a68de48079809390ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626744"
---
# <a name="isscommandwithparameters-ole-db"></a><span data-ttu-id="bd6dd-102">ISSCommandWithParameters (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="bd6dd-102">ISSCommandWithParameters (OLE DB)</span></span>
  <span data-ttu-id="bd6dd-103">**ISSCommandWithParameters** espone il supporto per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML e i tipi definiti dall'utente (UDT).</span><span class="sxs-lookup"><span data-stu-id="bd6dd-103">**ISSCommandWithParameters** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML and user-defined types (UDT).</span></span> <span data-ttu-id="bd6dd-104">Si tratta di un'interfaccia facoltativa che eredita dall'interfaccia di base OLE DB **ICommandWithParameters**.</span><span class="sxs-lookup"><span data-stu-id="bd6dd-104">This is an optional interface that inherits from the core OLE DB interface **ICommandWithParameters**.</span></span> <span data-ttu-id="bd6dd-105">Oltre ai tre metodi ereditati da **ICommandWithParameters**; **GetParameterInfo**, **MapParameterNames**e **separameterinfo**; In **ISSCommandWithParameters** sono disponibili due nuovi metodi utilizzati per gestire i tipi di dati specifici del server.</span><span class="sxs-lookup"><span data-stu-id="bd6dd-105">In addition to the three methods inherited from **ICommandWithParameters**; **GetParameterInfo**, **MapParameterNames**, and **SetParameterInfo**; **ISSCommandWithParameters** provides two new methods that are used to handle server specific data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd6dd-106">L'interfaccia **ISSCommandWithParameters** può essere utilizzata quando si utilizzano i componenti del servizio, ma i componenti del servizio non utilizzeranno questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="bd6dd-106">The **ISSCommandWithParameters** interface can be used when Service Components are used, but the Service Components themselves will not use this interface.</span></span>  
  
|<span data-ttu-id="bd6dd-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="bd6dd-107">Method</span></span>|<span data-ttu-id="bd6dd-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd6dd-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bd6dd-109">ISSCommandWithParameters::GetParameterProperties &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="bd6dd-109">ISSCommandWithParameters::GetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-getparameterproperties-ole-db.md)|<span data-ttu-id="bd6dd-110">Restituisce una struttura del set di proprietà **SSPARAMPROPS** della matrice per ogni parametro XML o tipo definito dall'utente passato al comando. Per gli altri tipi di parametro non ne restituisce nessuna.</span><span class="sxs-lookup"><span data-stu-id="bd6dd-110">Returns one **SSPARAMPROPS** property set structure in the array for each UDT or XML parameter passed to the command, but none is returned for other types of parameters.</span></span>|  
|[<span data-ttu-id="bd6dd-111">ISSCommandWithParameters::SetParameterProperties &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="bd6dd-111">ISSCommandWithParameters::SetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-setparameterproperties-ole-db.md)|<span data-ttu-id="bd6dd-112">Imposta le proprietà per i singoli parametri in base al numero ordinale oppure imposta proprietà dei parametri bulk specificando una matrice di strutture **SSPARAMPROPS**.</span><span class="sxs-lookup"><span data-stu-id="bd6dd-112">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of **SSPARAMPROPS** structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd6dd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd6dd-113">See Also</span></span>  
 <span data-ttu-id="bd6dd-114">[Interfacce &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="bd6dd-114">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 <span data-ttu-id="bd6dd-115">[Utilizzo di tipi di dati XML](../native-client/features/using-xml-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="bd6dd-115">[Using XML Data Types](../native-client/features/using-xml-data-types.md) </span></span>  
 [<span data-ttu-id="bd6dd-116">Utilizzo dei tipi definiti dall'utente (UDT)</span><span class="sxs-lookup"><span data-stu-id="bd6dd-116">Using User-Defined Types</span></span>](../native-client/features/using-user-defined-types.md)  
  
  
