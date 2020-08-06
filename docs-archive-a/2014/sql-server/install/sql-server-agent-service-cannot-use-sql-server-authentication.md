---
title: SQL Server Agent servizio non può utilizzare l'autenticazione SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- authentication [SQL Server Agent]
- SQL Server Authentication [SQL Server Agent]
ms.assetid: c39f3ec3-fc2c-4c12-940f-60d8d3d17660
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 32188b1c47168aefbca914fa15f71850df716153
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630260"
---
# <a name="sql-server-agent-service-cannot-use-sql-server-authentication"></a><span data-ttu-id="8a67a-102">Il servizio SQL Server Agent non può utilizzare l'autenticazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8a67a-102">SQL Server Agent Service cannot use SQL Server Authentication</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8a67a-103">Agent supporta solo l'autenticazione di Windows quando il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent si connette a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a67a-103">Agent only supports Windows Authentication when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service connects to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="8a67a-104">Componente</span><span class="sxs-lookup"><span data-stu-id="8a67a-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8a67a-105">Agent</span><span class="sxs-lookup"><span data-stu-id="8a67a-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="8a67a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a67a-106">Description</span></span>  
 <span data-ttu-id="8a67a-107">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent può accedere al database solo utilizzando l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="8a67a-107">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service can only log on to the database using Windows Authentication.</span></span> <span data-ttu-id="8a67a-108">Pertanto, l'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent deve essere un utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a67a-108">This means that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account must be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user.</span></span>  
  
 <span data-ttu-id="8a67a-109">Per ulteriori informazioni, vedere gli argomenti relativi alla sicurezza per l'amministrazione automatica e all'implementazione della sicurezza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a67a-109">For more information, see the topics "Security for Automatic Administration" and "Implementing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Security" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a67a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a67a-110">See Also</span></span>  
 [<span data-ttu-id="8a67a-111">Problemi di aggiornamento di SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="8a67a-111">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
