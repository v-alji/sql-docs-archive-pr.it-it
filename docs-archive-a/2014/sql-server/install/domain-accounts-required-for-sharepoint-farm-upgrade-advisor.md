---
title: Account di dominio necessari per la farm di SharePoint (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 90cd6d3e-a271-4cb8-81f2-fc555b2d3cab
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7d180fbc12a264256156c878916838f7caeec723
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637614"
---
# <a name="domain-accounts-required-for-sharepoint-farm-upgrade-advisor"></a><span data-ttu-id="3d04a-102">Account di dominio richiesti per la farm di SharePoint (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="3d04a-102">Domain accounts required for SharePoint farm (Upgrade Advisor)</span></span>
  <span data-ttu-id="3d04a-103">I prodotti SharePoint configurati per un ambiente della farm richiedono l'utilizzo di account di dominio.</span><span class="sxs-lookup"><span data-stu-id="3d04a-103">SharePoint products that are configured for a farm environment require that you use domain accounts.</span></span>  
  
||  
|-|  
|<span data-ttu-id="3d04a-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità SharePoint di.</span><span class="sxs-lookup"><span data-stu-id="3d04a-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="3d04a-105">Componente</span><span class="sxs-lookup"><span data-stu-id="3d04a-105">Component</span></span>  
 [!INCLUDE[ssRS](../../includes/ssrs.md)]  
  
### <a name="description"></a><span data-ttu-id="3d04a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d04a-106">Description</span></span>  
 <span data-ttu-id="3d04a-107">I prodotti SharePoint configurati per un ambiente della farm richiedono l'utilizzo di account di dominio per i servizi e le connessioni ai database.</span><span class="sxs-lookup"><span data-stu-id="3d04a-107">SharePoint products that are configured for a farm environment require that you use domain accounts for services and database connections.</span></span> <span data-ttu-id="3d04a-108">È incluso l'account specificato per l'account del servizio Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="3d04a-108">This includes the account you have specified for the Reporting Services service account.</span></span>  
  
 <span data-ttu-id="3d04a-109">Le pagine Amministrazione centrale SharePoint 2010, ad esempio, restituiscono problemi se non si utilizza un account utente di dominio per Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="3d04a-109">SharePoint 2010 Central Administration pages are one place you will see problems if you are not using a domain user account for Reporting Services.</span></span> <span data-ttu-id="3d04a-110">Quando si tenta di configurare l'integrazione di Reporting Services, verrà visualizzato un messaggio di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="3d04a-110">When you try to configure Reporting Services integration, you will see an error message similar to the following:</span></span>  
  
 <span data-ttu-id="3d04a-111">"Il server di report è in esecuzione con l'account NT AUTHORITY\NETWORK SERVICE predefinito, condizione non supportata dall'installazione di una farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3d04a-111">"The report server is running under the built-in NT AUTHORITY\NETWORK SERVICE account, which is not supported by a SharePoint farm installation.</span></span> <span data-ttu-id="3d04a-112">Riconfigurare il server di report affinché venga eseguito con un account di dominio".</span><span class="sxs-lookup"><span data-stu-id="3d04a-112">Please reconfigure the report server to run under a domain account."</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="3d04a-113">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="3d04a-113">Corrective Action</span></span>  
 <span data-ttu-id="3d04a-114">Per [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e versioni precedenti, utilizzare il Configuration Manager Reporting Services per modificare l'account assegnato come account del servizio del server di report.</span><span class="sxs-lookup"><span data-stu-id="3d04a-114">For [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and previous versions, use the Reporting Services Configuration Manager to change the account that is assigned as the report server service account.</span></span>  
  
#### <a name="to-change-the-service-account-from-configuration-manager"></a><span data-ttu-id="3d04a-115">Per modificare l'account del servizio da Gestione configurazione</span><span class="sxs-lookup"><span data-stu-id="3d04a-115">To change the service account from Configuration Manager</span></span>  
  
1.  <span data-ttu-id="3d04a-116">Dal menu **Start** selezionare **tutti i programmi**, quindi fare clic su **Microsoft SQL Server 2008 R2**.</span><span class="sxs-lookup"><span data-stu-id="3d04a-116">From the **Start** menu, select **All Programs**, and then click **Microsoft SQL Server 2008 R2**.</span></span>  
  
2.  <span data-ttu-id="3d04a-117">Selezionare **strumenti di configurazione**, quindi fare clic su **Reporting Services Configuration Manager**.</span><span class="sxs-lookup"><span data-stu-id="3d04a-117">Select **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="3d04a-118">In Configuration Manager selezionare la scheda **account del servizio** .</span><span class="sxs-lookup"><span data-stu-id="3d04a-118">In Configuration Manager, select the **Service Account** tab.</span></span>  
  
4.  <span data-ttu-id="3d04a-119">Selezionare **Usa un altro account** e immettere le credenziali per un account di dominio.</span><span class="sxs-lookup"><span data-stu-id="3d04a-119">Select **Use another account** and enter the credentials for a domain account.</span></span>  
  
5.  <span data-ttu-id="3d04a-120">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="3d04a-120">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d04a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d04a-121">See Also</span></span>  
 [<span data-ttu-id="3d04a-122">Configurare l'account del servizio del server di report &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3d04a-122">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
  
  
