---
title: Installare ADOMD.NET nei server front-end Web che eseguono Amministrazione centrale | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2372180-e847-4cdb-b267-4befac3faf7e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 0d9f52bf612c4878a8dacd4f5acfdcc135ae115e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624538"
---
# <a name="install-adomdnet-on-web-front-end-servers-running-central-administration"></a><span data-ttu-id="388ec-102">Installare ADOMD.NET in server front-end Web in cui viene eseguita Amministrazione centrale</span><span class="sxs-lookup"><span data-stu-id="388ec-102">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>
  <span data-ttu-id="388ec-103">Se si installa PowerPivot per SharePoint in una farm che dispone della topologia di Amministrazione centrale, senza Excel Services o PowerPivot per SharePoint, scaricare e installare la libreria client Microsoft ADOMD.NET se si desidera l'accesso completo ai report incorporati nel dashboard di gestione PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="388ec-103">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="388ec-104">Alcuni report nel dashboard utilizzano ADOMD.NET per accedere a dati interni relativi all'integrità del server e all'elaborazione query di PowerPivot nella farm.</span><span class="sxs-lookup"><span data-stu-id="388ec-104">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span>  
  
 <span data-ttu-id="388ec-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="388ec-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010</span></span>  
  
 <span data-ttu-id="388ec-106">Per SharePoint 2013, il provider è incluso nel Feature Pack di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="388ec-106">For SharePoint 2013, the provider is included in the SQL Server feature pack.</span></span> <span data-ttu-id="388ec-107">Per informazioni su come scaricare spPowerPivot.msi, vedere [Microsoft SQL Server Feature Pack di 2014](https://www.microsoft.com/download/details.aspx?id=35577)</span><span class="sxs-lookup"><span data-stu-id="388ec-107">For information on how to download spPowerPivot.msi, see [Microsoft SQL Server 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=35577)</span></span>  
  
### <a name="download-and-install-the-client-library"></a><span data-ttu-id="388ec-108">Scaricare e installare la libreria client</span><span class="sxs-lookup"><span data-stu-id="388ec-108">Download and install the client library</span></span>  
  
1.  <span data-ttu-id="388ec-109">Nella [pagina SQL Server 2014 Feature Pack](https://go.microsoft.com/fwlink/?LinkID=296473)trovare Microsoft ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="388ec-109">On the [SQL Server 2014 Feature Pack page](https://go.microsoft.com/fwlink/?LinkID=296473), find Microsoft ADOMD.NET.</span></span>  
  
2.  <span data-ttu-id="388ec-110">Scaricare il pacchetto per x64 del programma di installazione `SQL_AS_ADOMD.msi`.</span><span class="sxs-lookup"><span data-stu-id="388ec-110">Download the x64 Package of the `SQL_AS_ADOMD.msi` installation program.</span></span>  
  
3.  <span data-ttu-id="388ec-111">Eseguire il file con estensione msi per installare la libreria.</span><span class="sxs-lookup"><span data-stu-id="388ec-111">Run the .msi to install the library.</span></span>  
  
4.  <span data-ttu-id="388ec-112">Reimpostare IIS dopo aver completato l'installazione.</span><span class="sxs-lookup"><span data-stu-id="388ec-112">Reset IIS after installation is finished.</span></span> <span data-ttu-id="388ec-113">Aprire un prompt dei comandi amministrativo e digitare **iisreset**.</span><span class="sxs-lookup"><span data-stu-id="388ec-113">Open an administrative command prompt and type **IISRESET**.</span></span>  
  
### <a name="verify-installation"></a><span data-ttu-id="388ec-114">Verificare l'installazione</span><span class="sxs-lookup"><span data-stu-id="388ec-114">Verify installation</span></span>  
  
1.  <span data-ttu-id="388ec-115">Spostarsi su Windows\Assembly.</span><span class="sxs-lookup"><span data-stu-id="388ec-115">Go to Windows\Assembly.</span></span>  
  
2.  <span data-ttu-id="388ec-116">Fare clic con il pulsante destro del mouse su Microsoft. AnalysisServices. AdomdClient e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="388ec-116">Right-click Microsoft.AnalysisServices.AdomdClient and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="388ec-117">Fare clic su **Versione**.</span><span class="sxs-lookup"><span data-stu-id="388ec-117">Click **Version**.</span></span>  
  
4.  <span data-ttu-id="388ec-118">Verificare che la versione includa 12,00.\<build number></span><span class="sxs-lookup"><span data-stu-id="388ec-118">Verify that the version includes 12.00.\<build number></span></span> <span data-ttu-id="388ec-119">e che la descrizione sia Microsoft. AnalysisService. AdomdClient.</span><span class="sxs-lookup"><span data-stu-id="388ec-119">and that the description is Microsoft.AnalysisService.AdomdClient.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388ec-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="388ec-120">See Also</span></span>  
 [<span data-ttu-id="388ec-121">Dati di utilizzo e dashboard di gestione PowerPivot</span><span class="sxs-lookup"><span data-stu-id="388ec-121">PowerPivot Management Dashboard and Usage Data</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data)  
  
  
