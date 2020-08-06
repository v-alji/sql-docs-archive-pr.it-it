---
title: Proprietà server (pagina sicurezza) - Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.security.f1
ms.assetid: f49aedc6-f145-4df1-8f69-d5d910f492c6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f709d42bf593b4933d9fc1fdc423c195967df382
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629717"
---
# <a name="server-properties-security-page---reporting-services"></a><span data-ttu-id="7cd61-102">Proprietà server (pagina sicurezza) - Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7cd61-102">Server Properties (Security Page) - Reporting Services</span></span>
  <span data-ttu-id="7cd61-103">Questa pagina consente di disattivare le caratteristiche che potrebbero compromettere un server di report.</span><span class="sxs-lookup"><span data-stu-id="7cd61-103">Use this page to turn off features that can potentially compromise a report server.</span></span> <span data-ttu-id="7cd61-104">La disattivazione di queste caratteristiche comporta l'impostazione di determinati limiti, ma consente di migliorare la sicurezza globale del server di report riducendo i rischi di minacce specifiche.</span><span class="sxs-lookup"><span data-stu-id="7cd61-104">Turning off these features will limit some functionality, but can improve the overall security of the report server by mitigating specific threats.</span></span>  
  
 <span data-ttu-id="7cd61-105">Per aprire questa pagina, avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connettersi a un'istanza del server di report, fare clic con il pulsante destro del mouse sul nome del server di report e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7cd61-105">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="7cd61-106">Fare clic su **sicurezza** per aprire la pagina.</span><span class="sxs-lookup"><span data-stu-id="7cd61-106">Click **Security** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7cd61-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7cd61-107">Options</span></span>  
 <span data-ttu-id="7cd61-108">**Attiva la sicurezza integrata di Windows per le origini dati dei report**</span><span class="sxs-lookup"><span data-stu-id="7cd61-108">**Enable Windows integrated security for report data sources**</span></span>  
 <span data-ttu-id="7cd61-109">Consente di specificare se è possibile stabilire una connessione all'origine dati di un report utilizzando il token di sicurezza di Windows dell'utente che ha richiesto il report.</span><span class="sxs-lookup"><span data-stu-id="7cd61-109">Specify whether a connection to a report data source can be made using the Windows security token of the user who requested the report.</span></span>  
  
 <span data-ttu-id="7cd61-110">Se si disattiva questa caratteristica, la sicurezza integrata di Windows non sarà disponibile nelle pagine delle proprietà dell'origine dati del report.</span><span class="sxs-lookup"><span data-stu-id="7cd61-110">If you turn off this feature, the Windows Integrated Security feature in the report data source property pages will be unavailable.</span></span> <span data-ttu-id="7cd61-111">Se le origini dati del report sono configurate per la sicurezza integrata di Windows e successivamente si disattiva questa caratteristica, nel server di report vengono immediatamente aggiornate tutte le proprietà di connessione all'origine dati in modo che vengano richieste le credenziali.</span><span class="sxs-lookup"><span data-stu-id="7cd61-111">If report data sources are configured for Windows integrated security and you subsequently turn off this feature, the report server will immediately update all data source connection properties to prompt for credentials.</span></span>  
  
 <span data-ttu-id="7cd61-112">**Consenti reporting ad hoc**</span><span class="sxs-lookup"><span data-stu-id="7cd61-112">**Enable Ad Hoc Reporting**</span></span>  
 <span data-ttu-id="7cd61-113">Consente di specificare se gli utenti possono eseguire query ad hoc da un report di Generatore report, nel caso in cui i nuovi report vengano generati automaticamente quando un utente fa clic su dati di interesse.</span><span class="sxs-lookup"><span data-stu-id="7cd61-113">Specify whether users can perform ad hoc queries from a Report Builder report, where new reports are automatically generated when a user clicks data of interest.</span></span>  
  
 <span data-ttu-id="7cd61-114">L'impostazione di questa opzione determina se il valore della proprietà `EnableLoadReportDefinition` nel server di report è impostato su `True` o su `False`.</span><span class="sxs-lookup"><span data-stu-id="7cd61-114">Setting this option determines whether the `EnableLoadReportDefinition` property on the report server is set to `True` or `False`.</span></span> <span data-ttu-id="7cd61-115">Se si deseleziona questa opzione, la proprietà viene impostata su `False` e nel server di report non verranno generati report click-through creati durante l'esplorazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="7cd61-115">If you clear this option, the property will be set to `False` and report server will not generate clickthrough reports that are created during data exploration.</span></span> <span data-ttu-id="7cd61-116">Tutte le chiamate al metodo `LoadReportDefinition` verranno bloccate.</span><span class="sxs-lookup"><span data-stu-id="7cd61-116">All calls to the `LoadReportDefinition` method will be blocked.</span></span>  
  
 <span data-ttu-id="7cd61-117">La disattivazione di questa opzione consente di attenuare i rischi di attacchi Denial of Service condotti da utenti malintenzionati tramite overload del server di report con richieste `LoadReportDefinition`.</span><span class="sxs-lookup"><span data-stu-id="7cd61-117">Turning off this option mitigates a threat whereby a malicious user launches a denial of service attack by overloading the report server with `LoadReportDefinition` requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cd61-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cd61-118">See Also</span></span>  
 <span data-ttu-id="7cd61-119">[Impostazione delle proprietà del server di report &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7cd61-119">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="7cd61-120">[Connettersi a un server di report in Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7cd61-120">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="7cd61-121">[Specificare le credenziali e le informazioni di connessione per le origini dati del report] (.. /report-data/Specify-Credential-and-Connection-Information-for-report-data-sources.MD [del server di report nella Guida sensibile al contesto Management Studio](report-server-in-management-studio-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="7cd61-121">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md [Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md)</span></span>  
  
  
