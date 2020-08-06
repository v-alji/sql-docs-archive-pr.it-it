---
title: Proteggere le origini dei dati condivise | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
- security [Reporting Services], data sources
ms.assetid: 7299e498-0a1a-4821-a22a-5199bb773ce0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c4177834a90e2852f4079e3b2bf5a1dd85b9cd51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629178"
---
# <a name="secure-shared-data-source-items"></a><span data-ttu-id="646b6-102">Proteggere le origini dei dati condivise</span><span class="sxs-lookup"><span data-stu-id="646b6-102">Secure Shared Data Source Items</span></span>
  <span data-ttu-id="646b6-103">È possibile impostare la sicurezza per un'origine dei dati condivisa in modo da abilitarne o disabilitarne l'accesso.</span><span class="sxs-lookup"><span data-stu-id="646b6-103">You can set security on a shared data source item to enable or disable access to it.</span></span>  
  
 <span data-ttu-id="646b6-104">Un utente con autorizzazioni di accesso minime a un'origine dei dati condivisa, ad esempio quelle concesse tramite il ruolo **Visualizzazione** , è in grado di visualizzare l'elenco dei report che usano tale elemento, a condizione che sia anche autorizzato a visualizzare tali report.</span><span class="sxs-lookup"><span data-stu-id="646b6-104">A user who has minimal access to a shared data source (for example, the access granted through the **Browser** role) can view the list of reports that use the item, provided the user is also authorized to view the reports themselves.</span></span>  
  
 <span data-ttu-id="646b6-105">Un utente con autorizzazioni di accesso più estese, ad esempio quelle concesse tramite il ruolo **Gestione contenuto** , è in grado di visualizzare e impostare proprietà per l'origine dei dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="646b6-105">A user who has additional access (such as that granted through the **Content Manager** role) can view and set properties for the shared data source.</span></span>  
  
 <span data-ttu-id="646b6-106">Per impostare la sicurezza, è necessario creare un'assegnazione di ruolo che specifichi quale account utente o di gruppo è autorizzato ad accedere all'origine dei dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="646b6-106">To set security, you create a role assignment that specifies which user or group account has access to the shared data source.</span></span> <span data-ttu-id="646b6-107">Gli utenti autorizzati ad accedere a un'origine dei dati condivisa possono modificarne il nome, la descrizione, la stringa di connessione o le informazioni sulle credenziali.</span><span class="sxs-lookup"><span data-stu-id="646b6-107">Users who have access to a shared data source item can change its name, description, connection string, or credential information.</span></span>  
  
## <a name="tasks-and-access-to-items"></a><span data-ttu-id="646b6-108">Attività e accesso agli elementi</span><span class="sxs-lookup"><span data-stu-id="646b6-108">Tasks and Access to Items</span></span>  
 <span data-ttu-id="646b6-109">Quando si creano assegnazioni di ruolo, per assegnare autorizzazioni appropriate a utenti e gruppi utilizzare un ruolo che contenga le attività seguenti.</span><span class="sxs-lookup"><span data-stu-id="646b6-109">When creating role assignments, use a role that has these tasks to assign appropriate permissions to users and groups.</span></span>  
  
|<span data-ttu-id="646b6-110">Selezionare questa attività</span><span class="sxs-lookup"><span data-stu-id="646b6-110">Select this task</span></span>|<span data-ttu-id="646b6-111">Per concedere agli utenti l'autorizzazione per</span><span class="sxs-lookup"><span data-stu-id="646b6-111">To give users permission to</span></span>|  
|----------------------|---------------------------------|  
|<span data-ttu-id="646b6-112">Visualizzazione di origini dei dati</span><span class="sxs-lookup"><span data-stu-id="646b6-112">View data sources</span></span>|<span data-ttu-id="646b6-113">Visualizzare l'origine dei dati condivisa nella gerarchia di cartelle.</span><span class="sxs-lookup"><span data-stu-id="646b6-113">View the shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="646b6-114">Se questa attività non è selezionata, l'elemento non è visibile agli utenti che potrebbero non essere consapevoli che l'origine dei dati è disponibile.</span><span class="sxs-lookup"><span data-stu-id="646b6-114">Without this task, the item is not visible to users and they may not be aware that the data source is available.</span></span>|  
|<span data-ttu-id="646b6-115">Gestire le origini dati</span><span class="sxs-lookup"><span data-stu-id="646b6-115">Manage data sources</span></span>|<span data-ttu-id="646b6-116">Visualizzare le proprietà che specificano il nome, la descrizione e le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="646b6-116">View properties that specify the name, description, and connection information.</span></span> <span data-ttu-id="646b6-117">Questa attività viene inoltre utilizzata per visualizzare un'origine dei dati condivisa nella gerarchia di cartelle.</span><span class="sxs-lookup"><span data-stu-id="646b6-117">This task is also used to display a shared data source item in the folder hierarchy.</span></span> <span data-ttu-id="646b6-118">Se si seleziona questa attività, è possibile evitare di selezionare l'attività Visualizzazione di origini dei dati.</span><span class="sxs-lookup"><span data-stu-id="646b6-118">If you choose this task, you can omit the "View data sources" task.</span></span>|  
|<span data-ttu-id="646b6-119">Impostazione della sicurezza per singoli elementi</span><span class="sxs-lookup"><span data-stu-id="646b6-119">Set security on items</span></span>|<span data-ttu-id="646b6-120">Creare e modificare assegnazioni di ruolo che controllano l'accesso all'origine dei dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="646b6-120">Create and modify role assignments that control access to the shared data source.</span></span> <span data-ttu-id="646b6-121">Questa attività deve essere utilizzata con l'attività Visualizzazione di origini dei dati o Gestione di origini dei dati.</span><span class="sxs-lookup"><span data-stu-id="646b6-121">This task must be used with either "View data source" or "Manage data sources" tasks.</span></span> <span data-ttu-id="646b6-122">In caso contrario non avrà alcun effetto, poiché l'utente non potrà selezionare l'elemento.</span><span class="sxs-lookup"><span data-stu-id="646b6-122">If it is not, it has no effect because the user cannot select the item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="646b6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="646b6-123">See Also</span></span>  
 <span data-ttu-id="646b6-124">[Gestire origini dati dei report](../report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="646b6-124">[Manage Report Data Sources](../report-data/manage-report-data-sources.md) </span></span>  
 <span data-ttu-id="646b6-125">[Proteggere le cartelle](secure-folders.md) </span><span class="sxs-lookup"><span data-stu-id="646b6-125">[Secure Folders](secure-folders.md) </span></span>  
 <span data-ttu-id="646b6-126">[Garantire la sicurezza di report e risorse](secure-reports-and-resources.md) </span><span class="sxs-lookup"><span data-stu-id="646b6-126">[Secure Reports and Resources](secure-reports-and-resources.md) </span></span>  
 <span data-ttu-id="646b6-127">[Concessione di autorizzazioni in un server di report in modalità nativa](granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="646b6-127">[Granting Permissions on a Native Mode Report Server](granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 [<span data-ttu-id="646b6-128">Archiviare le credenziali in un'origine dati di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="646b6-128">Store Credentials in a Reporting Services Data Source</span></span>](../report-data/store-credentials-in-a-reporting-services-data-source.md)  
  
  
