---
title: Nuovo ruolo a livello di sistema (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newsystemrole.f1
ms.assetid: 7b4a0b98-975b-478a-8359-7db39ccbb347
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a744fc78bdd5ae6ef3a37f96ff5ae8cd10f71a80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716016"
---
# <a name="new-system-role-management-studio"></a><span data-ttu-id="dcbf7-102">Nuovo ruolo a livello di sistema (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="dcbf7-102">New System Role (Management Studio)</span></span>
  <span data-ttu-id="dcbf7-103">Utilizzare questa pagina per creare una definizione di ruolo a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-103">Use this page to create a system-level role definition.</span></span> <span data-ttu-id="dcbf7-104">Tramite una definizione di ruolo a livello di sistema è possibile specificare un set di attività a livello di sistema consentite per un server di report nel suo complesso.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-104">A system role definition specifies a set of system-level tasks that apply to a report server as whole.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dcbf7-105">Le definizioni di ruolo vengono utilizzate solo in un server di report in esecuzione in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-105">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="dcbf7-106">Se il server di report è configurato per l'integrazione con SharePoint, questa pagina non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-106">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="dcbf7-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="dcbf7-107">Options</span></span>  
 <span data-ttu-id="dcbf7-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="dcbf7-108">**Name**</span></span>  
 <span data-ttu-id="dcbf7-109">Consente di digitare la definizione del ruolo.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-109">Type the name of the role definition.</span></span> <span data-ttu-id="dcbf7-110">I nomi di definizione di ruolo devono essere univoci nell'ambito dello spazio dei nomi del server di report.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-110">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="dcbf7-111">Il nome deve includere almeno un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-111">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="dcbf7-112">È inoltre possibile utilizzare spazi e alcuni simboli.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-112">It can also include spaces and some symbols.</span></span> <span data-ttu-id="dcbf7-113">Il nome non può contenere i caratteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="dcbf7-113">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="dcbf7-114">; ?</span><span class="sxs-lookup"><span data-stu-id="dcbf7-114">; ?</span></span> <span data-ttu-id="dcbf7-115">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="dcbf7-115">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="dcbf7-116">" /</span><span class="sxs-lookup"><span data-stu-id="dcbf7-116">" /</span></span>  
  
 <span data-ttu-id="dcbf7-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dcbf7-117">**Description**</span></span>  
 <span data-ttu-id="dcbf7-118">Consente di digitare una descrizione per illustrare le modalità di utilizzo del ruolo ed elencare le azioni supportate.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-118">Provide a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="dcbf7-119">**Attività**</span><span class="sxs-lookup"><span data-stu-id="dcbf7-119">**Task**</span></span>  
 <span data-ttu-id="dcbf7-120">Consente di selezionare le attività a livello di sistema che possono essere eseguite tramite questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-120">Select the system-level tasks that can be performed through this role.</span></span> <span data-ttu-id="dcbf7-121">Non è possibile creare nuove attività o modificare attività esistenti supportate da [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcbf7-121">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="dcbf7-122">Non è possibile selezionare attività a livello di elemento per una definizione di ruolo a livello di sistema.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-122">You cannot choose item-level tasks for a system role definition.</span></span>  
  
 <span data-ttu-id="dcbf7-123">**Descrizione dell'attività**</span><span class="sxs-lookup"><span data-stu-id="dcbf7-123">**Task Description**</span></span>  
 <span data-ttu-id="dcbf7-124">Visualizza una descrizione dell'attività, che include le operazioni o autorizzazioni supportate.</span><span class="sxs-lookup"><span data-stu-id="dcbf7-124">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcbf7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcbf7-125">See Also</span></span>  
 <span data-ttu-id="dcbf7-126">[Guida sensibile al contesto del server di report in Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="dcbf7-126">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="dcbf7-127">Definizioni di ruolo</span><span class="sxs-lookup"><span data-stu-id="dcbf7-127">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
