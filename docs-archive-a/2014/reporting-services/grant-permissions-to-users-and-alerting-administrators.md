---
title: Concedere autorizzazioni a utenti e amministratori di avvisi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166808e1-ada7-48d2-bda8-8f7c017fb3aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5bf7f030871287379ce9fb32a1789b95cff0fc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637092"
---
# <a name="grant-permissions-to-users-and-alerting-administrators"></a><span data-ttu-id="2c34e-102">Concedere autorizzazione a utenti e amministratori di avvisi</span><span class="sxs-lookup"><span data-stu-id="2c34e-102">Grant Permissions to Users and Alerting Administrators</span></span>
  <span data-ttu-id="2c34e-103">Per poter creare, modificare, eliminare e visualizzare avvisi dati, è necessario che agli utenti e agli amministratori di avvisi vengano concesse le autorizzazioni di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2c34e-103">Before users and alerting administrators can create, edit, delete, and view data alerts they must be granted SharePoint permissions.</span></span> <span data-ttu-id="2c34e-104">Non esistono autorizzazioni speciali da usare con la funzionalità relativa agli avvisi dati di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] . È possibile usare le autorizzazioni predefinite di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2c34e-104">There are no special permissions to use with the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] data alerting feature, you use the built-in SharePoint permissions.</span></span>  
  
 <span data-ttu-id="2c34e-105">**Information worker**: le autorizzazioni devono includere le autorizzazioni di SharePoint per la creazione di avvisi e la visualizzazione di elementi.</span><span class="sxs-lookup"><span data-stu-id="2c34e-105">**Information workers**-Permissions must include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="2c34e-106">I livelli di autorizzazione predefiniti di SharePoint denominati Progettazione, Collaborazione, Lettura e Solo visualizzazione includono le autorizzazioni di SharePoint relative alla creazione di avvisi e alla visualizzazione di elementi.</span><span class="sxs-lookup"><span data-stu-id="2c34e-106">The built-in SharePoint permission levels named Design, Contribute, Read, and View Only include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="2c34e-107">È inoltre possibile creare un livello di autorizzazione personalizzato con le autorizzazioni necessarie per gli utenti che creano, modificano, eseguono e visualizzano avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="2c34e-107">You can also create a custom permission level with the permissions required to support users that create, edit, run, and view data alerts.</span></span>  
  
 <span data-ttu-id="2c34e-108">**Amministratori di avvisi**: le autorizzazioni devono includere l'autorizzazione Gestisci avvisi di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2c34e-108">**Alerting administrators**-Permissions must include the Manage Alert SharePoint permission.</span></span> <span data-ttu-id="2c34e-109">Per impostazione predefinita solamente il livello di autorizzazione Controllo completo include questa autorizzazione per i siti creati con il modello di sito del team.</span><span class="sxs-lookup"><span data-stu-id="2c34e-109">By default only the Full Control permission level includes this permission for sites created with the Team Site site template.</span></span> <span data-ttu-id="2c34e-110">Se si utilizzano altri modelli di sito, vengono visualizzati elenchi diversi di gruppi di SharePoint predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2c34e-110">If you use other site templates, you will see different lists of default SharePoint groups.</span></span> <span data-ttu-id="2c34e-111">È possibile aggiungere l'autorizzazione Gestione avvisi a uno dei livelli di autorizzazione predefiniti oppure creare un livello di autorizzazione personalizzato con l'autorizzazione necessaria per supportare gli amministratori di avvisi che visualizzano ed eliminano gli avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="2c34e-111">You can add the Manage Alert permission to one of the built-in permission levels or create a custom permission level with the permission required to support alerting administrators that view and delete data alerts.</span></span>  
  
 <span data-ttu-id="2c34e-112">Per altre informazioni sulle autorizzazioni di SharePoint, vedere la pagina relativa alle [autorizzazioni utente e ai livelli di autorizzazione (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span><span class="sxs-lookup"><span data-stu-id="2c34e-112">To learn more about SharePoint permissions, see [User permissions and permission levels (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span></span>  
  
### <a name="to-grant-permissions"></a><span data-ttu-id="2c34e-113">Per concedere autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2c34e-113">To grant permissions</span></span>  
  
1.  <span data-ttu-id="2c34e-114">Accedere al sito di SharePoint in cui si desidera concedere autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2c34e-114">Go to the SharePoint site to which you want to grant permissions.</span></span>  
  
2.  <span data-ttu-id="2c34e-115">Nella barra degli strumenti, fare clic su **Azioni sito** , quindi su **Autorizzazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="2c34e-115">On the toolbar, click **Site Actions** and then click **Site Permissions**.</span></span>  
  
     <span data-ttu-id="2c34e-116">Se questa opzione non viene visualizzata, non si dispone del livello di autorizzazione sufficiente per concedere autorizzazioni ad altri.</span><span class="sxs-lookup"><span data-stu-id="2c34e-116">If you do not see this option, you do not sufficient permission to grant permissions to others.</span></span>  
  
3.  <span data-ttu-id="2c34e-117">Fare clic su **Concedere le autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="2c34e-117">Click **Grant Permissions**.</span></span>  
  
4.  <span data-ttu-id="2c34e-118">In **Utenti/Gruppi**digitare i nomi degli utenti, i nomi dei gruppi e gli indirizzi di posta elettronica a cui si vuole concedere autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2c34e-118">In **Users/Groups**, type the user names, group names, or e-mail addresses you want grant permission to.</span></span>  
  
5.  <span data-ttu-id="2c34e-119">Selezionare l'opzione **Aggiungi utenti a un gruppo di SharePoint** o **Concedi direttamente le autorizzazioni agli utenti** .</span><span class="sxs-lookup"><span data-stu-id="2c34e-119">Select the **Add users to a SharePoint group** or **Grant users permission directly** option.</span></span> <span data-ttu-id="2c34e-120">A seconda del fatto che sia stata selezionata l'opzione **Aggiungi utenti a un gruppo di SharePoint** o **Concedi direttamente le autorizzazioni agli utenti** , effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c34e-120">Depending on whether you selected **Add users to a SharePoint group** or **Grant users permissions directly** do one of the following:</span></span>  
  
    -   <span data-ttu-id="2c34e-121">Se è stata selezionata l'opzione **Aggiungi utenti a un gruppo di SharePoint**, selezionare un livello di autorizzazione nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="2c34e-121">If you selected **Add users to a SharePoint group**, select a permission level in the drop-down list.</span></span>  
  
    -   <span data-ttu-id="2c34e-122">Se è stato selezionato **Concedi direttamente le autorizzazioni agli utenti**, selezionare un livello di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="2c34e-122">If you selected **Grant users permissions directly**, select a permission level.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2c34e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c34e-123">See Also</span></span>  
 <span data-ttu-id="2c34e-124">[Impostare le autorizzazioni per gli elementi del server di report in un sito di SharePoint &#40;Reporting Services in modalità integrata SharePoint&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="2c34e-124">[Set Permissions for Report Server Items on a SharePoint Site &#40;Reporting Services in SharePoint Integrated Mode&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="2c34e-125">Reporting Services Data Alerts</span><span class="sxs-lookup"><span data-stu-id="2c34e-125">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
