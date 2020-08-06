---
title: Rinominare gli account di accesso corrispondenti ai nomi di ruoli predefinito del server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- user-defined login names [SQL Server]
- fixed server roles [SQL Server]
- renamed logins [SQL Server]
- logins [SQL Server], names
ms.assetid: 10a1d77c-3153-474f-a6a0-969556794467
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 296ae4d4051e79e3c5d3bc158ef3e87c9164ecd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720838"
---
# <a name="rename-logins-matching-fixed-server-role-names"></a><span data-ttu-id="986d6-102">Rinominare gli account di accesso con nomi uguali a quelli dei ruoli predefiniti del server</span><span class="sxs-lookup"><span data-stu-id="986d6-102">Rename logins matching fixed server role names</span></span>
  <span data-ttu-id="986d6-103">Uno o più nomi di account di accesso definiti dall'utente sono uguali a nomi di ruoli predefiniti del server.</span><span class="sxs-lookup"><span data-stu-id="986d6-103">Upgrade Advisor detected one or more user-defined login names that match the names of fixed server roles.</span></span> <span data-ttu-id="986d6-104">I nomi dei ruoli predefiniti del server sono riservati.</span><span class="sxs-lookup"><span data-stu-id="986d6-104">Fixed server role names are reserved.</span></span> <span data-ttu-id="986d6-105">Prima di eseguire l'aggiornamento, rinominare gli account di accesso.</span><span class="sxs-lookup"><span data-stu-id="986d6-105">Rename the login before you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="986d6-106">Componente</span><span class="sxs-lookup"><span data-stu-id="986d6-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="986d6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="986d6-107">Description</span></span>  
 <span data-ttu-id="986d6-108">I nomi dei ruoli predefiniti del server riportati di seguito sono riservati e non possono essere utilizzati come nomi di account di accesso definiti dall'utente:</span><span class="sxs-lookup"><span data-stu-id="986d6-108">The following fixed server role names are reserved and cannot be used as user-defined login names.</span></span>  
  
-   <span data-ttu-id="986d6-109">**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="986d6-109">**sysadmin**</span></span>  
  
-   <span data-ttu-id="986d6-110">**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="986d6-110">**serveradmin**</span></span>  
  
-   <span data-ttu-id="986d6-111">**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="986d6-111">**setupadmin**</span></span>  
  
-   <span data-ttu-id="986d6-112">**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="986d6-112">**securityadmin**</span></span>  
  
-   <span data-ttu-id="986d6-113">**processadmin**</span><span class="sxs-lookup"><span data-stu-id="986d6-113">**processadmin**</span></span>  
  
-   <span data-ttu-id="986d6-114">**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="986d6-114">**dbcreator**</span></span>  
  
-   <span data-ttu-id="986d6-115">**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="986d6-115">**diskadmin**</span></span>  
  
-   <span data-ttu-id="986d6-116">**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="986d6-116">**bulkadmin**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="986d6-117">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="986d6-117">Corrective Action</span></span>  
 <span data-ttu-id="986d6-118">Prima di eseguire l'aggiornamento, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="986d6-118">Before upgrading, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="986d6-119">Registrare gli ID di sicurezza (SID) degli account di accesso eseguendo l'istruzione seguente.</span><span class="sxs-lookup"><span data-stu-id="986d6-119">Record the security identifiers (SIDs) of the logins by executing the following statement.</span></span>  
  
    ```  
    SELECT name, sid   
    FROM master.dbo.syslogins   
    WHERE name IN('sysadmin', 'serveradmin','setupadmin', 'securityadmin','processadmin', 'dbcreator','diskadmin','bulkadmin')  
    ```  
  
2.  <span data-ttu-id="986d6-120">Eliminare gli account di accesso.</span><span class="sxs-lookup"><span data-stu-id="986d6-120">Drop the logins.</span></span>  
  
3.  <span data-ttu-id="986d6-121">Utilizzare la procedura di sistema **sp_addlogin** per creare nuovi account di accesso.</span><span class="sxs-lookup"><span data-stu-id="986d6-121">Use the **sp_addlogin** system procedure to create new logins.</span></span> <span data-ttu-id="986d6-122">Specificare il SID restituito nel passaggio 1 nel parametro \*\* \@ SID\*\* per ogni account di accesso corrispondente.</span><span class="sxs-lookup"><span data-stu-id="986d6-122">Specify the SID returned in step 1 in the **\@sid** parameter for each corresponding login.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="986d6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="986d6-123">See Also</span></span>  
 <span data-ttu-id="986d6-124">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="986d6-124">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="986d6-125">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="986d6-125">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
