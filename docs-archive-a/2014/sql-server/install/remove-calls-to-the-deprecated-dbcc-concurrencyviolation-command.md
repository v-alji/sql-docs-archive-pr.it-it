---
title: Rimuovere le chiamate al comando DBCC CONCURRENCYVIOLATION deprecato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2cc9f6ff-de36-4e94-bd04-59f5c45c4911
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cde04ebfc2ea9996d1c9ed233123e5b66f6e81fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722259"
---
# <a name="remove-calls-to-the-deprecated-dbcc-concurrencyviolation-command"></a><span data-ttu-id="926f9-102">Rimuovere le chiamate al comando DBCC CONCURRENCYVIOLATION deprecato</span><span class="sxs-lookup"><span data-stu-id="926f9-102">Remove calls to the deprecated DBCC CONCURRENCYVIOLATION command</span></span>
  <span data-ttu-id="926f9-103">È stato rilevato il comando DBCC CONCURRENCYVIOLATION.</span><span class="sxs-lookup"><span data-stu-id="926f9-103">Upgrade Advisor detected the use of the DBCC CONCURRENCYVIOLATION command.</span></span> <span data-ttu-id="926f9-104">Questo comando non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="926f9-104">This command is no longer available.</span></span> <span data-ttu-id="926f9-105">L'esecuzione di questo comando restituisce l'errore 2526.</span><span class="sxs-lookup"><span data-stu-id="926f9-105">Executing this command returns error 2526.</span></span>  
  
## <a name="component"></a><span data-ttu-id="926f9-106">Componente</span><span class="sxs-lookup"><span data-stu-id="926f9-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="926f9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="926f9-107">Description</span></span>  
 <span data-ttu-id="926f9-108">Nessuna versione recente dell'edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] include un'utilità di Governor del carico di lavoro; pertanto il comando è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="926f9-108">No recent version of edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] includes a workload governor; therefore the command has been removed.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="926f9-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="926f9-109">Corrective Action</span></span>  
 <span data-ttu-id="926f9-110">Aggiornare le applicazioni e gli script per rimuovere i riferimenti a questo comando deprecato.</span><span class="sxs-lookup"><span data-stu-id="926f9-110">Update applications and scripts to remove references to this deprecated command.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="926f9-111">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="926f9-111">External Resources</span></span>  
  
