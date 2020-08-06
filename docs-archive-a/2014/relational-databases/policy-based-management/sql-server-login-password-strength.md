---
title: Livello di complessità delle password di accesso di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b0862c3a-926b-490c-a37f-382e50146a3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5534748fbbf810539f2dcfc22239e4b987cf0f77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713036"
---
# <a name="sql-server-login-password-strength"></a><span data-ttu-id="a902a-102">Livello di complessità delle password di accesso di SQL Server</span><span class="sxs-lookup"><span data-stu-id="a902a-102">SQL Server Login Password Strength</span></span>
  <span data-ttu-id="a902a-103">Questa regola consente di controllare se è abilitata la funzionalità "Applica criteri password" di ogni account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a902a-103">This rule checks whether "Enforce password policy" of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is enabled.</span></span> <span data-ttu-id="a902a-104">Se è abilitata l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e la versione del sistema operativo è precedente a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], un utente malintenzionato potrebbe sfruttare ripetutamente una password di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nota.</span><span class="sxs-lookup"><span data-stu-id="a902a-104">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is enabled and if the operating system version is earlier than [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], an attacker could repeatedly exploit a known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login password.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="a902a-105">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="a902a-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="a902a-106">È consigliabile aggiornare il sistema operativo a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a902a-106">We recommend that you upgrade the operating system to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span></span>  
  
 <span data-ttu-id="a902a-107">Se nell'ambiente non è necessaria l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a902a-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is not required in your environment, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="a902a-108">Abilitare "Applica criteri password" per tutti gli account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a902a-108">Enable "Enforce password policy" for all the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="a902a-109">Per configurare i criteri password per gli account di accesso di [, utilizzare](/sql/t-sql/statements/alter-login-transact-sql) ALTER LOGIN [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a902a-109">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="a902a-110">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="a902a-110">For More Information</span></span>  
 [<span data-ttu-id="a902a-111">Criteri password</span><span class="sxs-lookup"><span data-stu-id="a902a-111">Password Policy</span></span>](../security/password-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="a902a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a902a-112">See Also</span></span>  
 [<span data-ttu-id="a902a-113">Monitorare e applicare le procedure consigliate tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="a902a-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
