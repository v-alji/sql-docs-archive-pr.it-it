---
title: Risolvere i problemi relativi all'integrità delle risorse di SQL Server (Utilità SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 614f07b5-f221-4013-9f8d-22964cf42270
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 182225dd618dd1e9e058c549bdc07818813ba764
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625390"
---
# <a name="troubleshoot-sql-server-resource-health-sql-server-utility"></a><span data-ttu-id="34fd9-102">Risoluzione dei problemi relativi all'integrità delle risorse di SQL Server (Utilità SQL Server)</span><span class="sxs-lookup"><span data-stu-id="34fd9-102">Troubleshoot SQL Server Resource Health (SQL Server Utility)</span></span>
  <span data-ttu-id="34fd9-103">La risoluzione dei problemi di integrità delle risorse identificati da un punto di controllo dell'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] potrebbe includere la riduzione di una CPU sovrautilizzata su un computer o su un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]oppure la riduzione di una CPU sovrautilizzata per un'applicazione del livello dati.</span><span class="sxs-lookup"><span data-stu-id="34fd9-103">Troubleshooting resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP might include mitigating overutilized CPU on a computer or on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or mitigating overutilized CPU for a data-tier application.</span></span> <span data-ttu-id="34fd9-104">Altri problemi potrebbero includere la risoluzione dello spazio file sovrautilizzato per i file di database o la risoluzione del sovrautilizzo dello spazio su disco allocato su un volume di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="34fd9-104">Other issues might include resolving overutilized file space for database files or resolving overutilization of allocated disk space on a storage volume.</span></span>  
  
 <span data-ttu-id="34fd9-105">Si noti che se il database si trova in stato di "emergenza", lo stato di integrità visualizzerà lo spazio sovrautilizzato del file di log.</span><span class="sxs-lookup"><span data-stu-id="34fd9-105">Note that if a database is in "emergency" state, the health state will display overutilized log file space.</span></span>  
  
 <span data-ttu-id="34fd9-106">Per altre informazioni sulla raccolta dati con errori che comporta icone di stato grigie nella visualizzazione elenco dell'istanza gestita su un punto di controllo dell'utilità, vedere [Risoluzione dei problemi relativi a Utilità SQL Server](../../database-engine/troubleshoot-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="34fd9-106">For more information about failed data collection resulting in gray status icons in the managed instance list view on a UCP, see [Troubleshoot the SQL Server Utility](../../database-engine/troubleshoot-the-sql-server-utility.md).</span></span> <span data-ttu-id="34fd9-107">Per altre informazioni sulle attività iniziali con Utilità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [Attività e funzionalità di Utilità SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="34fd9-107">For more information about getting started with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="34fd9-108">Per ulteriori informazioni sulla riduzione dei problemi di integrità specifici delle risorse identificati da un punto di controllo dell'utilità di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="34fd9-108">For more information about mitigating specific resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP, see the following topics:</span></span>  
  
-   [<span data-ttu-id="34fd9-109">Identificazione della versione e dell'edizione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="34fd9-109">How to identify your SQL Server version and edition</span></span>](https://go.microsoft.com/fwlink/?LinkID=178504)  
  
-   [<span data-ttu-id="34fd9-110">Risoluzione dei problemi relativi alle prestazioni in SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="34fd9-110">Troubleshooting Performance Problems in SQL Server 2008</span></span>](https://go.microsoft.com/fwlink/?LinkId=151354)  
  
  
