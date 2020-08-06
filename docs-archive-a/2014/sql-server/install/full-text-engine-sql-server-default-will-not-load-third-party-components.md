---
title: Il motore di ricerca full-text Microsoft per SQL Server non caricherà i componenti di terze parti non firmati per impostazione predefinita | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Full-Text Engine for SQL service
- MSFTESQL service
ms.assetid: 029f9895-7232-4149-9362-3ab1a4133d21
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 12ff188fb6aa6ac286817a7cc1c3ad726483c886
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638256"
---
# <a name="the-microsoft-full-text-engine-for-sql-server-will-not-load-unsigned-third-party-components-by-default"></a><span data-ttu-id="452f3-102">Per impostazione predefinita, il motore di ricerca full-text Microsoft per SQL Server non carica componenti di terze parti non firmato</span><span class="sxs-lookup"><span data-stu-id="452f3-102">The Microsoft Full-Text Engine for SQL Server will not load unsigned third-party components by default</span></span>
  <span data-ttu-id="452f3-103">Per impostazione predefinita, il motore di ricerca full-text [!INCLUDE[msCoName](../../includes/msconame-md.md)] per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non carica componenti non firmati da [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="452f3-103">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Full-Text Engine for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not load components that are not signed by [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="452f3-104">Componente</span><span class="sxs-lookup"><span data-stu-id="452f3-104">Component</span></span>  
 <span data-ttu-id="452f3-105">Ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="452f3-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="452f3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="452f3-106">Description</span></span>  
 <span data-ttu-id="452f3-107">Per impostazione predefinita, dopo l'aggiornamento, un filtro di terze parti, ad esempio un filtro PDF, attualmente installato nel server non viene caricato nel motore di ricerca full-text [!INCLUDE[msCoName](../../includes/msconame-md.md)] per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="452f3-107">A third-party filter, such as a PDF filter, that is currently installed on the server will not be loaded by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Full-Text Engine for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by default after upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="452f3-108">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="452f3-108">Corrective Action</span></span>  
 <span data-ttu-id="452f3-109">Per caricare un filtro di terze parti, è necessario impostare *load_os_resource* e disattivare *verify_signature* su tale istanza.</span><span class="sxs-lookup"><span data-stu-id="452f3-109">To load a third party filter, you must set *load_os_resource* and turn off *verify_signature* on that instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="452f3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="452f3-110">See Also</span></span>  
 [<span data-ttu-id="452f3-111">Uso di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="452f3-111">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
