---
title: Ruoli e autorizzazioni (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- access controls [Reporting Services]
- permissions [Reporting Services], about permissions
- security [Reporting Services], identity and access control
- authentication [Reporting Services]
- permissions [Reporting Services]
- security [Reporting Services], role-based
- identity [Reporting Services]
ms.assetid: eea655fe-43ed-418d-8233-b288a8f4daa4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0e6098a51afde04164e3ef0dfa5e5297457b4440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629184"
---
# <a name="roles-and-permissions-reporting-services"></a><span data-ttu-id="154bf-102">Ruoli e autorizzazioni (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="154bf-102">Roles and Permissions (Reporting Services)</span></span>
  <span data-ttu-id="154bf-103">In Reporting Services sono disponibili un sottosistema di autenticazione e un modello di autorizzazione basata sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="154bf-103">Reporting Services provides an authentication subsystem and role-based authorization model.</span></span> <span data-ttu-id="154bf-104">I modelli di autenticazione e autorizzazione variano a seconda che il server di report sia in esecuzione in modalità nativa o in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="154bf-104">Authentication and authorization models vary depending on whether the report server runs in native mode or SharePoint mode.</span></span> <span data-ttu-id="154bf-105">Se il server di report fa parte di una distribuzione di SharePoint, con le autorizzazioni di SharePoint è possibile determinare gli utenti che possono accedere al server di report.</span><span class="sxs-lookup"><span data-stu-id="154bf-105">If the report server is part of a SharePoint deployment, SharePoint permissions determine who has access to the report server.</span></span>  
  
## <a name="identity-and-access-control-for-native-mode"></a><span data-ttu-id="154bf-106">Controllo di identità e accesso per la modalità nativa</span><span class="sxs-lookup"><span data-stu-id="154bf-106">Identity and Access Control for Native Mode</span></span>  
 <span data-ttu-id="154bf-107">L'autenticazione predefinita è basata sull'autenticazione di Windows e sulla sicurezza integrata.</span><span class="sxs-lookup"><span data-stu-id="154bf-107">Default authentication is based on Windows Authentication and integrated security.</span></span> <span data-ttu-id="154bf-108">È possibile modificare le impostazioni di autenticazione per consentire al server di report di rispondere a richieste di autenticazione diverse o anche sostituire le funzionalità di sicurezza predefinite con un'estensione di autenticazione personalizzata fornita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="154bf-108">You can change the authentication settings to allow the report server to respond to different authentication requests, or even replace the default security features with a custom authentication extension that you provide.</span></span>  
  
 <span data-ttu-id="154bf-109">L'autorizzazione è basata su ruoli che vengono assegnati a un'entità.</span><span class="sxs-lookup"><span data-stu-id="154bf-109">Authorization is based on roles that you assign to a principle.</span></span> <span data-ttu-id="154bf-110">Ogni ruolo è costituito da un set di attività correlate, a loro volta composte da operazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="154bf-110">Each role consists of a set of related tasks, which are in turn composed of related operations.</span></span> <span data-ttu-id="154bf-111">Ad esempio, l'attività **Gestione di report** concede l'accesso alle operazioni seguenti sul server di report: visualizzazione, aggiunta, aggiornamento, eliminazione e pianificazione di report, nonché aggiornamento delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="154bf-111">For example, the **Manage reports** task grants access to the following report server operations: view reports, add report, update report, delete report, schedule report, and update report properties.</span></span>  
  
## <a name="identity-and-access-control-for-sharepoint-mode"></a><span data-ttu-id="154bf-112">Controllo di identità e accesso per la modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="154bf-112">Identity and Access Control for SharePoint Mode</span></span>  
 <span data-ttu-id="154bf-113">In modalità integrata SharePoint l'autenticazione e l'autorizzazione vengono gestite sul sito di SharePoint, prima che le richieste raggiungano il server di report.</span><span class="sxs-lookup"><span data-stu-id="154bf-113">In SharePoint integrated mode, authentication and authorization are handled on the SharePoint site, before requests reach the report server.</span></span> <span data-ttu-id="154bf-114">A seconda della modalità di configurazione dell'autenticazione, le richieste provenienti da un sito di SharePoint includono un token di sicurezza o un nome utente attendibile.</span><span class="sxs-lookup"><span data-stu-id="154bf-114">Depending on how you configure authentication, requests from a SharePoint site include a security token or a trusted user name.</span></span> <span data-ttu-id="154bf-115">Le autorizzazione impostate per gli utenti e i gruppi di SharePoint autorizzano l'accesso agli elementi del server di report inseriti nelle raccolte di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="154bf-115">Permissions that you set for SharePoint users and groups authorize access to report server items that are placed in SharePoint libraries.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="154bf-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="154bf-116">In This Section</span></span>  
 [<span data-ttu-id="154bf-117">Concessione di autorizzazioni in un server di report in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="154bf-117">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
 <span data-ttu-id="154bf-118">Viene descritto il modello di autorizzazione basata sui ruoli che fornisce l'accesso al contenuto e alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="154bf-118">Describes the role-based authorization model that provides access to content and operations.</span></span>  
  
 [<span data-ttu-id="154bf-119">Concessione di autorizzazioni per elementi del server di report in un sito di SharePoint</span><span class="sxs-lookup"><span data-stu-id="154bf-119">Granting Permissions on Report Server Items on a SharePoint Site</span></span>](granting-permissions-on-report-server-items-on-a-sharepoint-site.md)  
 <span data-ttu-id="154bf-120">Viene illustrato l'utilizzo di gruppi, livelli di autorizzazione e autorizzazioni di SharePoint per il controllo dell'accesso a un server di report.</span><span class="sxs-lookup"><span data-stu-id="154bf-120">Explains how SharePoint groups, permission levels, and permissions are used to control access to a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="154bf-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="154bf-121">See Also</span></span>  
 <span data-ttu-id="154bf-122">[Autenticazione con il server di report](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="154bf-122">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 [<span data-ttu-id="154bf-123">Concessione di autorizzazioni in un server di report in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="154bf-123">Granting Permissions on a Native Mode Report Server</span></span>](granting-permissions-on-a-native-mode-report-server.md)  
  
  
