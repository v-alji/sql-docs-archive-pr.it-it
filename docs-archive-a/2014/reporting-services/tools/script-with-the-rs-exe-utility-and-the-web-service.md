---
title: Eseguire lo script con l'utilità rs.exe e il servizio Web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Web service [Reporting Services], scripts
- rs utility
- XML Web service [Reporting Services], scripts
- Report Server Web service, scripts
- scripts [Reporting Services], Web service
ms.assetid: 0ec5ac6e-b3cf-49cd-96f6-6b4b7dc29982
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d84bb8722fd31a08ff7788ad31c601b377c23d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629723"
---
# <a name="script-with-the-rsexe-utility-and-the-web-service"></a><span data-ttu-id="a9e61-102">Eseguire lo script con l'utilità rs.exe e il servizio Web</span><span class="sxs-lookup"><span data-stu-id="a9e61-102">Script with the rs.exe Utility and the Web Service</span></span>
  <span data-ttu-id="a9e61-103">Gli sviluppatori e gli amministratori del server di report possono eseguire operazioni su un server di report con l'utilità **rs** (RS.exe).</span><span class="sxs-lookup"><span data-stu-id="a9e61-103">Developers and report server administrators can perform operations on a report server through the use of the **rs** utility (RS.exe).</span></span> <span data-ttu-id="a9e61-104">Tramite questa utilità, è possibile amministrare a livello di programmazione un server di report usando gli script scritti con [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9e61-104">Using this utility, you can programmatically administer a report server using scripts written with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="a9e61-105">- Gli script possono essere usati per eseguire qualsiasi operazione del servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="a9e61-105">scripts can be used to run any of the Report Server Web service operations.</span></span> <span data-ttu-id="a9e61-106">Gli script possono essere utilizzati per copiare la sicurezza su più report in un server, per aggiungere ed eliminare elementi, per copiare elementi del server di report da un server a un altro e per altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="a9e61-106">Scripting can be used to copy security to multiple reports on a server, to add and delete items, to copy report server items from one server to another and more.</span></span> <span data-ttu-id="a9e61-107">Per altre informazioni sull'ambiente di scripting, vedere [Eseguire un file script di Reporting Services](run-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="a9e61-107">For more information about the scripting environment, see [Run a Reporting Services Script File](run-a-reporting-services-script-file.md).</span></span> <span data-ttu-id="a9e61-108">I file script hanno un formato specifico e vengono scritti in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="a9e61-108">Script files take a certain format and are written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET.</span></span> <span data-ttu-id="a9e61-109">Per altre informazioni, vedere [Formattare un file script di Reporting Services](format-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="a9e61-109">For more information, see [Format a Reporting Services Script File](format-a-reporting-services-script-file.md).</span></span>  
  
 <span data-ttu-id="a9e61-110">Per esempi di script, vedere quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a9e61-110">For script samples, see the following:</span></span>  
  
 <span data-ttu-id="a9e61-111">[Esempio Reporting Services Script rs.exe per eseguire la migrazione del contenuto tra server di report](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="a9e61-111">[Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
 <span data-ttu-id="a9e61-112">[Esempi del prodotto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="a9e61-112">[SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e61-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9e61-113">See Also</span></span>  
 <span data-ttu-id="a9e61-114">[Utilizzare script per l'esecuzione di attività di distribuzione e di amministrazione](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="a9e61-114">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 <span data-ttu-id="a9e61-115">[Servizio Web ReportServer](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="a9e61-115">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="a9e61-116">[Riferimento tecnico &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a9e61-116">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="a9e61-117">Utilità RS.exe &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a9e61-117">RS.exe Utility &#40;SSRS&#41;</span></span>](rs-exe-utility-ssrs.md)  
  
  
