---
title: Il trigger AFTER annidato viene attivato anche quando l'annidamento del trigger è disattivato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, nested
- nested triggers option
- triggers [SQL Server], nested
ms.assetid: 94d72960-676e-40d9-81bc-08bffe778110
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f91c04e8d69880b451c1479e2907cd1910e8f9c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726496"
---
# <a name="nested-after-trigger-fires-even-when-trigger-nesting-is-off"></a><span data-ttu-id="babb0-102">I trigger AFTER nidificati vengono attivati anche quando l'opzione relativa alla nidificazione dei trigger è disattivata</span><span class="sxs-lookup"><span data-stu-id="babb0-102">Nested AFTER trigger fires even when trigger nesting is OFF</span></span>
  <span data-ttu-id="babb0-103">È presente un trigger AFTER nidificato in un trigger INSTEAD OF definito su una o più tabelle.</span><span class="sxs-lookup"><span data-stu-id="babb0-103">Upgrade Advisor detected an AFTER trigger nested inside an INSTEAD OF trigger that is defined on one or more tables.</span></span> <span data-ttu-id="babb0-104">I trigger AFTER annidati possono essere attivati anche se l'opzione di configurazione del server `nested triggers` è impostata su 0.</span><span class="sxs-lookup"><span data-stu-id="babb0-104">Nested AFTER triggers may fire even when the `nested triggers` server configuration option is set to 0.</span></span>  
  
## <a name="component"></a><span data-ttu-id="babb0-105">Componente</span><span class="sxs-lookup"><span data-stu-id="babb0-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="babb0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="babb0-106">Description</span></span>  
 <span data-ttu-id="babb0-107">Il primo trigger AFTER nidificato in un trigger INSTEAD OF viene attivato anche se l'opzione di configurazione del server `nested triggers` è impostata su 0.</span><span class="sxs-lookup"><span data-stu-id="babb0-107">The first AFTER trigger nested inside an INSTEAD OF trigger fires even if the `nested triggers` server configuration option is set to 0.</span></span> <span data-ttu-id="babb0-108">Tuttavia, con questa impostazione, i successivi trigger AFTER non vengono attivati.</span><span class="sxs-lookup"><span data-stu-id="babb0-108">However, under this setting, subsequent AFTER triggers do not fire.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="babb0-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="babb0-109">Corrective Action</span></span>  
 <span data-ttu-id="babb0-110">Verificare se nelle proprie applicazioni sono presenti trigger nidificati per determinare se tali applicazioni sono comunque conformi alle regole business in uso, in relazione a questo nuovo comportamento quando l'opzione di configurazione del server `nested triggers` è impostata su 0, quindi apportare le modifiche eventualmente necessarie.</span><span class="sxs-lookup"><span data-stu-id="babb0-110">Review your applications for nested triggers to determine whether the applications still comply with your business rules with regard to this new behavior when the `nested triggers` server configuration option is set to 0, and then make appropriate modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="babb0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="babb0-111">See Also</span></span>  
 <span data-ttu-id="babb0-112">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="babb0-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="babb0-113">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="babb0-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
