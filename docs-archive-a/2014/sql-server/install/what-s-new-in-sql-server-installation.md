---
title: Novità relative all'installazione di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- installing SQL Server, what's new
- SQL Server, what's new
- SQL Server, installing
ms.assetid: c8642a96-3a09-4ec7-a9c3-c539147e6330
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d34085e320cd8ca0b82d382d6d49eaa303086114
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628094"
---
# <a name="what39s-new-in-sql-server-installation"></a><span data-ttu-id="b7955-102">Novità relative all'installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="b7955-102">What&#39;s New in SQL Server Installation</span></span>
  <span data-ttu-id="b7955-103">Windows Vista non è un sistema operativo supportato per [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7955-103">Windows Vista is not a supported operating system for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span> <span data-ttu-id="b7955-104">Service Pack 1 è il requisito minimo per i sistemi operativi [!INCLUDE[win7](../../includes/win7-md.md)] e [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7955-104">Service Pack 1 remains as the minimum requirement for [!INCLUDE[win7](../../includes/win7-md.md)] and [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] operating systems.</span></span> <span data-ttu-id="b7955-105">Per ulteriori informazioni sui requisiti del sistema operativo, vedere [requisiti hardware e software per l'installazione di SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b7955-105">For more information on operating system requirements, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
 <span data-ttu-id="b7955-106">L'installazione di [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] richiede di specificare la directory in cui salvare il pacchetto estratto.</span><span class="sxs-lookup"><span data-stu-id="b7955-106">Installation of [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] will prompt you to specify the directory to save the extracted package.</span></span> <span data-ttu-id="b7955-107">Se non viene specificato alcun percorso, verrà utilizzato il valore predefinito di [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] che corrisponde all'unità di sistema del computer.</span><span class="sxs-lookup"><span data-stu-id="b7955-107">If no location is entered, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] will default to the computer's system drive.</span></span> <span data-ttu-id="b7955-108">I file estratti vengono conservati dopo il completamento dell'installazione di [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b7955-108">The extracted files will remain after [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] installation is complete.</span></span>  
  
 <span data-ttu-id="b7955-109">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], SysPrep è supportato per tutte le installazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7955-109">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], SysPrep is supported for all installations of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b7955-110">SysPrep ora supporta le installazioni del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="b7955-110">SysPrep now supports failover cluster installations.</span></span> <span data-ttu-id="b7955-111">Per ulteriori informazioni, vedere [considerazioni per l'installazione di SQL Server tramite Sysprep](../../database-engine/install-windows/considerations-for-installing-sql-server-using-sysprep.md) e [installare SQL Server 2014 mediante Sysprep](../../database-engine/install-windows/install-sql-server-using-sysprep.md).</span><span class="sxs-lookup"><span data-stu-id="b7955-111">For more information, see [Considerations for Installing SQL Server Using SysPrep](../../database-engine/install-windows/considerations-for-installing-sql-server-using-sysprep.md) and [Install SQL Server 2014 Using SysPrep](../../database-engine/install-windows/install-sql-server-using-sysprep.md).</span></span>  
  
 <span data-ttu-id="b7955-112">L'aggiornamento da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] è supportato, ma non è supportata l'installazione side-by-side.</span><span class="sxs-lookup"><span data-stu-id="b7955-112">Upgrade from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] is supported, but side-by-side is not supported.</span></span> <span data-ttu-id="b7955-113">Per altre informazioni sul supporto di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], vedere [Aggiornamenti di versione ed edizione supportati](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="b7955-113">For more information about [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] support in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], see [Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span></span>  
  
 <span data-ttu-id="b7955-114">A partire da [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], la capacità del motore di database nell'edizione Standard è di 128 GB.</span><span class="sxs-lookup"><span data-stu-id="b7955-114">Beginning in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], the database engine in the Standard edition has a memory capacity of 128 GB.</span></span> <span data-ttu-id="b7955-115">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] il motore di database nell'edizione standard ha una capacità di memoria di 64 GB.</span><span class="sxs-lookup"><span data-stu-id="b7955-115">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the database engine in the Standard edition had a memory capacity of 64 GB.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7955-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7955-116">See Also</span></span>  
 <span data-ttu-id="b7955-117">[Novità di SQL Server 2014](../what-s-new-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="b7955-117">[What's New in SQL Server 2014](../what-s-new-in-sql-server-2016.md) </span></span>  
 <span data-ttu-id="b7955-118">[Specifiche del prodotto per SQL Server 2014](../../../2014/getting-started/sql-server-2014-product-specifications.md) </span><span class="sxs-lookup"><span data-stu-id="b7955-118">[Product Specifications for SQL Server 2014](../../../2014/getting-started/sql-server-2014-product-specifications.md) </span></span>  
 <span data-ttu-id="b7955-119">[Pianificazione di un'installazione di SQL Server](../../../2014/sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="b7955-119">[Planning a SQL Server Installation](../../../2014/sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="b7955-120">Requisiti hardware e software per l'installazione di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b7955-120">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
  
