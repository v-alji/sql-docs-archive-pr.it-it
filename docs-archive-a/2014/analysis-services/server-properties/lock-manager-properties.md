---
title: Proprietà di gestione blocchi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- lock manager properties [Analysis Services]
- LockWaitGranularityMS property
- DefaultLockTimeoutMS property
- DeadlockDetectionGranularityMS property
ms.assetid: 15fe9ead-825b-4ac3-9191-7a07caa2861b
author: minewiskan
ms.author: owend
ms.openlocfilehash: d10927f1c549f00625b8affb801ec7b0831827c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727171"
---
# <a name="lock-manager-properties"></a><span data-ttu-id="701a6-102">Proprietà di Gestione blocchi</span><span class="sxs-lookup"><span data-stu-id="701a6-102">Lock Manager Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="701a6-103">supporta le proprietà del server di Gestione blocchi elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="701a6-103">supports the lock manager server properties listed in the following table.</span></span> <span data-ttu-id="701a6-104">Per altre informazioni sulle proprietà aggiuntive del server e sulla relativa impostazione, vedere [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="701a6-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="701a6-105">**Si applica a:** modalità server multidimensionale e tabulare</span><span class="sxs-lookup"><span data-stu-id="701a6-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="701a6-106">Proprietà</span><span class="sxs-lookup"><span data-stu-id="701a6-106">Properties</span></span>  
 `DefaultLockTimeoutMS`  
 <span data-ttu-id="701a6-107">Proprietà a valore integer a 32 bit con segno che definisce il timeout predefinito dei blocchi per le richieste di blocco interne.</span><span class="sxs-lookup"><span data-stu-id="701a6-107">A signed 32-bit integer property that defines default lock timeout in milliseconds for internal lock requests.</span></span>  
  
 <span data-ttu-id="701a6-108">Il valore predefinito di questa proprietà è -1, che indica l'assenza di timeout per le richieste di blocco interne.</span><span class="sxs-lookup"><span data-stu-id="701a6-108">The default value for this property is -1, which indicates there is no timeout for internal lock requests.</span></span>  
  
 `LockWaitGranularityMS`  
 <span data-ttu-id="701a6-109">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="701a6-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DeadlockDetectionGranularityMS`  
 <span data-ttu-id="701a6-110">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="701a6-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="701a6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="701a6-111">See Also</span></span>  
 <span data-ttu-id="701a6-112">[Configurare le proprietà del server in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="701a6-112">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="701a6-113">Determinare la modalità server di un'istanza di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="701a6-113">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
