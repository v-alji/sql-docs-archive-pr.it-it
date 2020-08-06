---
title: Gli hint di tabella nelle definizioni delle viste indicizzate vengono ignorati nella modalità di compatibilità 80 e non sono consentiti in modalità 90 o versioni successive | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- query hints [SQL Server]
- indexed views [SQL Server], query hints
ms.assetid: 405dfcff-a3a6-4e6d-a53a-ed77bbacdd13
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cf3cb2b06dc477d93c8fd42312b4835ded42afb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720801"
---
# <a name="table-hints-in-indexed-view-definitions-are-ignored-in-80-compatibility-mode-and-are-not-allowed-in-90-mode-or-later"></a><span data-ttu-id="71768-102">Gli hint di tabella contenuti nelle definizioni delle viste indicizzate vengono ignorati in modalità di compatibilità 80 e non sono consentiti in modalità di compatibilità 90 o successiva</span><span class="sxs-lookup"><span data-stu-id="71768-102">Table hints in indexed view definitions are ignored in 80 compatibility mode and are not allowed in 90 mode or later</span></span>
  <span data-ttu-id="71768-103">In modalità di compatibilità 90 o successiva, gli hint di tabella non sono consentiti nelle definizioni delle viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="71768-103">Table hints in the definitions of indexed views are not permitted in the compatibility mode of 90 or later.</span></span> <span data-ttu-id="71768-104">Per ulteriori informazioni, vedere gli argomenti seguenti nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: "Progettazione di viste indicizzate", "Creazione di viste indicizzate" e "Hint per la query ([!INCLUDE[tsql](../../includes/tsql-md.md)])".</span><span class="sxs-lookup"><span data-stu-id="71768-104">For more information, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online: "Designing Indexed Views," "Creating Indexed Views," and "Query Hint ([!INCLUDE[tsql](../../includes/tsql-md.md)])."</span></span>  
  
## <a name="component"></a><span data-ttu-id="71768-105">Componente</span><span class="sxs-lookup"><span data-stu-id="71768-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="71768-106">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="71768-106">Corrective Action</span></span>  
 <span data-ttu-id="71768-107">Gli hint di tabella devono essere rimossi dalle definizioni delle viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="71768-107">Table hints must be removed from the definitions of indexed views.</span></span> <span data-ttu-id="71768-108">Indipendentemente dalla modalità di compatibilità utilizzata, si consiglia di testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="71768-108">Regardless of which compatibility mode is used, we recommend that you test the application.</span></span> <span data-ttu-id="71768-109">per verificare la corretta esecuzione delle operazioni di creazione, aggiornamento e accesso alle viste indicizzate, inclusa l'associazione di query a viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="71768-109">By testing the application, you can make sure it performs as expected when indexed views are created, updated, and accessed, including when indexed views are matched to queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71768-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71768-110">See Also</span></span>  
 <span data-ttu-id="71768-111">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="71768-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="71768-112">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="71768-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
