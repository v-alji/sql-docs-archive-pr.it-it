---
title: Abilitare l'integrazione di Data Quality Services con Master Data Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: ab32938d-a80e-4106-80d4-94b2de3d67dc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8d2fa25254cae2a129b6e08ff657d92af4ff9455
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626823"
---
# <a name="enable-data-quality-services-integration-with-master-data-services"></a><span data-ttu-id="e3377-102">Abilitare l'integrazione di Data Quality Services con Master Data Services</span><span class="sxs-lookup"><span data-stu-id="e3377-102">Enable Data Quality Services Integration with Master Data Services</span></span>
  <span data-ttu-id="e3377-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]la funzionalità di corrispondenza viene fornita da Data Quality Services (DQS).</span><span class="sxs-lookup"><span data-stu-id="e3377-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], matching functionality is provided by Data Quality Services (DQS).</span></span> <span data-ttu-id="e3377-104">Questa funzionalità deve essere abilitata per essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="e3377-104">This functionality must be enabled to be used.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e3377-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e3377-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="e3377-106">È necessario che siano disponibili un database e un'applicazione Web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3377-106">A [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web application and database must exist.</span></span>  
  
-   <span data-ttu-id="e3377-107">La funzionalità Data Quality Services e il client Data Quality devono essere installati nella stessa istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che ospita il database MDS.</span><span class="sxs-lookup"><span data-stu-id="e3377-107">The Data Quality Services feature and the Data Quality Client must be installed on the same [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the MDS database.</span></span> <span data-ttu-id="e3377-108">Per altre informazioni, vedere [Installare Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span><span class="sxs-lookup"><span data-stu-id="e3377-108">For more information, see [Install Data Quality Services](../../data-quality-services/install-windows/install-data-quality-services.md).</span></span>  
  
### <a name="to-enable-data-quality-services-integration"></a><span data-ttu-id="e3377-109">Per abilitare l'integrazione con Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="e3377-109">To enable Data Quality Services integration</span></span>  
  
1.  <span data-ttu-id="e3377-110">Aprire [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3377-110">Open [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span>  
  
2.  <span data-ttu-id="e3377-111">Nel riquadro sinistro fare clic su **Configurazione Web**.</span><span class="sxs-lookup"><span data-stu-id="e3377-111">In the left pane, click **Web Configuration**.</span></span>  
  
3.  <span data-ttu-id="e3377-112">Nella pagina **Configurazione Web** selezionare il sito Web e l'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="e3377-112">On the **Web Configuration** page, select the website and web application.</span></span>  
  
4.  <span data-ttu-id="e3377-113">Nella sezione **Abilita integrazione DQS** fare clic su **Abilitare l'integrazione con Data Quality Services**.</span><span class="sxs-lookup"><span data-stu-id="e3377-113">In the **Enable DQS Integration** section, click **Enable integration with Data Quality Services**.</span></span>  
  
5.  <span data-ttu-id="e3377-114">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3377-114">On the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3377-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3377-115">See Also</span></span>  
 <span data-ttu-id="e3377-116">[Corrispondenza Data Quality nel Componente aggiuntivo MDS per Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="e3377-116">[Data Quality Matching in the MDS Add-in for Excel](../microsoft-excel-add-in/data-quality-matching-in-the-mds-add-in-for-excel.md) </span></span>  
 <span data-ttu-id="e3377-117">[Componente aggiuntivo Master Data Services per Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span><span class="sxs-lookup"><span data-stu-id="e3377-117">[Master Data Services Add-in for Microsoft Excel](../microsoft-excel-add-in/master-data-services-add-in-for-microsoft-excel.md) </span></span>  
 [<span data-ttu-id="e3377-118">Installazione di Master Data Services</span><span class="sxs-lookup"><span data-stu-id="e3377-118">Install Master Data Services</span></span>](install-master-data-services.md)  
  
  
