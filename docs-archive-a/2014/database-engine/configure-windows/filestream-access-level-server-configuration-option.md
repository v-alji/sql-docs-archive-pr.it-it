---
title: Opzione di configurazione del server filestream access level | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], access level
- filestream access level
ms.assetid: b88f6ff2-795e-4730-bfb8-dbc6a958f2ad
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dfa43b8e6e1762e87dd9c2abbdf7a583963e196e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637457"
---
# <a name="filestream-access-level-server-configuration-option"></a><span data-ttu-id="d04fe-102">Opzione di configurazione del server filestream access level</span><span class="sxs-lookup"><span data-stu-id="d04fe-102">filestream access level Server Configuration Option</span></span>
  <span data-ttu-id="d04fe-103">Utilizzare l'opzione filestream_access_level per modificare il livello di accesso di FILESTREAM per l'istanza corrente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d04fe-103">Use the filestream_access_level option to change the FILESTREAM access level for this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d04fe-104">Prima che questa opzione abbia effetto, è necessario abilitare le impostazioni dell'amministrazione di Windows per FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d04fe-104">Before this option has any effect, the Windows administration settings for FILESTREAM must be enabled.</span></span> <span data-ttu-id="d04fe-105">È possibile abilitare queste impostazioni durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oppure tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d04fe-105">You can enable these settings when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
|<span data-ttu-id="d04fe-106">valore</span><span class="sxs-lookup"><span data-stu-id="d04fe-106">Value</span></span>|<span data-ttu-id="d04fe-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="d04fe-107">Definition</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="d04fe-108">0</span><span class="sxs-lookup"><span data-stu-id="d04fe-108">0</span></span>|<span data-ttu-id="d04fe-109">Disabilita il supporto di FILESTREAM per l'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="d04fe-109">Disables FILESTREAM support for this instance.</span></span>|  
|<span data-ttu-id="d04fe-110">1</span><span class="sxs-lookup"><span data-stu-id="d04fe-110">1</span></span>|<span data-ttu-id="d04fe-111">Abilita FILESTREAM per l'accesso [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d04fe-111">Enables FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span>|  
|<span data-ttu-id="d04fe-112">2</span><span class="sxs-lookup"><span data-stu-id="d04fe-112">2</span></span>|<span data-ttu-id="d04fe-113">Abilita l'accesso tramite flusso [!INCLUDE[tsql](../../includes/tsql-md.md)] e Win32 per FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="d04fe-113">Enables FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] and Win32 streaming access.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d04fe-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d04fe-114">See Also</span></span>  
 <span data-ttu-id="d04fe-115">[Configurazione del Motore di database - Filestream](../../sql-server/install/database-engine-configuration-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="d04fe-115">[Database Engine Configuration - Filestream](../../sql-server/install/database-engine-configuration-filestream.md) </span></span>  
 [<span data-ttu-id="d04fe-116">Abilitare e configurare FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="d04fe-116">Enable and Configure FILESTREAM</span></span>](../../relational-databases/blob/enable-and-configure-filestream.md)  
  
  
