---
title: Opzione di configurazione del server allow updates | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- allow updates option
ms.assetid: 3967c3ed-280a-4de8-a2ce-393e82745a7b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d7e3ede317509a2044be90635db46e30a932af66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630052"
---
# <a name="allow-updates-server-configuration-option"></a><span data-ttu-id="1515c-102">Opzione di configurazione del server allow updates</span><span class="sxs-lookup"><span data-stu-id="1515c-102">allow updates Server Configuration Option</span></span>
  <span data-ttu-id="1515c-103">Questa opzione è ancora presente nella stored procedure **sp_configure** , sebbene la relativa funzionalità non sia disponibile in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1515c-103">This option is still present in the **sp_configure** stored procedure, although its functionality is unavailable in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1515c-104">L'impostazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="1515c-104">The setting has no effect.</span></span> <span data-ttu-id="1515c-105">Gli aggiornamenti diretti delle tabelle di sistema non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="1515c-105">Direct updates to the system tables are not supported.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="1515c-106">La modifica dell'opzione **allow updates** provocherà l'esito negativo dell'istruzione RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="1515c-106">Changing the **allow updates** option will cause the RECONFIGURE statement to fail.</span></span> <span data-ttu-id="1515c-107">È necessario eliminare le modifiche apportate all'opzione **allow updates** in tutti gli script.</span><span class="sxs-lookup"><span data-stu-id="1515c-107">Changes to the **allow updates** option should be removed from all scripts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1515c-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1515c-108">See Also</span></span>  
 [<span data-ttu-id="1515c-109">Opzioni di configurazione del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1515c-109">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
