---
title: Configurare il data warehouse del punto di controllo dell'utilità (Utilità SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c2c6f050-8cdb-4b8e-ad38-4aae0a949847
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60b9623b468f2763cf619c325412373e3603f3a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625396"
---
# <a name="configure-your-utility-control-point-data-warehouse-sql-server-utility"></a><span data-ttu-id="e9521-102">Configurazione del data warehouse del punto di controllo dell'utilità (Utilità SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e9521-102">Configure Your Utility Control Point Data Warehouse (SQL Server Utility)</span></span>
  <span data-ttu-id="e9521-103">I dati raccolti dalle istanze gestite di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono archiviati nel data warehouse di gestione dell'utilità. Il nome del file del data warehouse di gestione dell'utilità è sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="e9521-103">Data collected by managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are stored in the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="e9521-104">È possibile configurare il periodo di memorizzazione dei dati in tale data warehouse.</span><span class="sxs-lookup"><span data-stu-id="e9521-104">You can configure the UMDW data retention period.</span></span> <span data-ttu-id="e9521-105">Per altre informazioni, vedere [Amministrazione utilità &#40;Utilità SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="e9521-105">For more information, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="e9521-106">Le impostazioni di configurazione seguenti non sono configurabili in questa versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e9521-106">The following configuration settings are not configurable in this release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="e9521-107">Nome del data warehouse di gestione dell'utilità (UMDW): Sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="e9521-107">UMDW name: Sysutility_mdw.</span></span>  
  
-   <span data-ttu-id="e9521-108">Frequenza di caricamento del set di raccolta: ogni 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="e9521-108">Collection set upload frequency: Every 15 minutes.</span></span>  
  
 <span data-ttu-id="e9521-109">La directory del data warehouse di gestione dell'utilità è configurabile: \<System drive>:\Programmi\Microsoft SQL Server\MSSQL10_50.<Nome_UCP>\MSSQL\Data\\, dove \<System drive> è in genere l'unità C:\.</span><span class="sxs-lookup"><span data-stu-id="e9521-109">The UMDW directory is configurable: \<System drive>:\Program Files\Microsoft SQL Server\MSSQL10_50.<UCP_Name>\MSSQL\Data\\, where \<System drive> is normally the C:\ drive.</span></span> <span data-ttu-id="e9521-110">Il file di log, Sysutility_mdw_\<GUID>_LOG, si trova nella stessa directory.</span><span class="sxs-lookup"><span data-stu-id="e9521-110">The log file, Sysutility_mdw_\<GUID>_LOG, is located in the same directory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9521-111">È possibile modificare la posizione del file data warehouse di gestione dell'utilità (UMDW) sysutility_mdw utilizzando i comandi collega/scollega o l'istruzione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="e9521-111">The UMDW (sysutility_mdw) file location can be changed using detach/attach or ALTER DATABASE.</span></span> <span data-ttu-id="e9521-112">È consigliabile utilizzare l'istruzione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="e9521-112">We recommend the use of ALTER DATABASE.</span></span> <span data-ttu-id="e9521-113">Per altre informazioni, vedere [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e9521-113">For more information see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9521-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9521-114">See Also</span></span>  
 [<span data-ttu-id="e9521-115">Attività e funzionalità di Utilità SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9521-115">SQL Server Utility Features and Tasks</span></span>](sql-server-utility-features-and-tasks.md)  
  
  
