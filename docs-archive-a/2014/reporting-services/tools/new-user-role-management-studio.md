---
title: Nuovo ruolo utente (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newrole.f1
ms.assetid: 9f76a235-0b58-479c-8e5b-50588091b71c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 78201c5ebedd0cdb7f8108b9e6effcaa7fbe87b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716015"
---
# <a name="new-user-role-management-studio"></a><span data-ttu-id="e0c03-102">Nuovo ruolo utente (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="e0c03-102">New User Role (Management Studio)</span></span>
  <span data-ttu-id="e0c03-103">Utilizzare questa pagina per creare una definizione di ruolo a livello di elemento.</span><span class="sxs-lookup"><span data-stu-id="e0c03-103">Use this page to create an item-level role definition.</span></span> <span data-ttu-id="e0c03-104">Una definizione di ruolo a livello di elemento è una raccolta denominata di attività che elenca quelle eseguibili dagli utenti in relazione a cartelle, report, modelli, risorse e origini dei dati condivise.</span><span class="sxs-lookup"><span data-stu-id="e0c03-104">An item-level role definition is a named collection of tasks that enumerate the tasks a user can perform in relation to folders, reports, models, resources, and shared data sources.</span></span> <span data-ttu-id="e0c03-105">Un esempio di definizione di ruolo a livello di elemento è il ruolo predefinito Visualizzazione che identifica il tipo di azioni che un utente finale di un report potrebbe avere la necessità di eseguire per l'esplorazione delle cartelle e la visualizzazione dei report.</span><span class="sxs-lookup"><span data-stu-id="e0c03-105">An example of an item-level role definition is the predefined Browser role that identifies the kinds of actions a report end user might require for navigating folders and viewing reports.</span></span>  
  
 <span data-ttu-id="e0c03-106">Le definizioni di ruolo sono progettate per essere in numero limitato.</span><span class="sxs-lookup"><span data-stu-id="e0c03-106">Role definitions are intended to be few in number.</span></span> <span data-ttu-id="e0c03-107">Per la maggior parte delle organizzazioni sono infatti necessarie solo poche definizioni di ruolo.</span><span class="sxs-lookup"><span data-stu-id="e0c03-107">Most organizations only require a few role definitions.</span></span> <span data-ttu-id="e0c03-108">Se le definizioni di ruolo predefinite fossero insufficienti, è comunque possibile modificarle o crearne di nuove.</span><span class="sxs-lookup"><span data-stu-id="e0c03-108">However, if the predefined role definitions are insufficient, you can vary them or create new ones.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e0c03-109">Le definizioni di ruolo vengono utilizzate solo in un server di report in esecuzione in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="e0c03-109">Role definitions are used only on a report server that runs in native mode.</span></span> <span data-ttu-id="e0c03-110">Se il server di report è configurato per l'integrazione con SharePoint, questa pagina non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="e0c03-110">If the report server is configured for SharePoint integration, this page is not available.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e0c03-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e0c03-111">Options</span></span>  
 <span data-ttu-id="e0c03-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e0c03-112">**Name**</span></span>  
 <span data-ttu-id="e0c03-113">Consente di digitare la definizione del ruolo.</span><span class="sxs-lookup"><span data-stu-id="e0c03-113">Type the name of the role definition.</span></span> <span data-ttu-id="e0c03-114">I nomi di definizione di ruolo devono essere univoci nell'ambito dello spazio dei nomi del server di report.</span><span class="sxs-lookup"><span data-stu-id="e0c03-114">A role definition name must be unique within the report server namespace.</span></span> <span data-ttu-id="e0c03-115">Il nome deve includere almeno un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="e0c03-115">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="e0c03-116">È inoltre possibile utilizzare spazi e alcuni simboli.</span><span class="sxs-lookup"><span data-stu-id="e0c03-116">It can also include spaces and some symbols.</span></span> <span data-ttu-id="e0c03-117">Il nome non può contenere i caratteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0c03-117">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="e0c03-118">; ?</span><span class="sxs-lookup"><span data-stu-id="e0c03-118">; ?</span></span> <span data-ttu-id="e0c03-119">: \@ & = +, $/\*\< ></span><span class="sxs-lookup"><span data-stu-id="e0c03-119">: \@ & = + , $ / \* \< ></span></span>  
  
 <span data-ttu-id="e0c03-120">" /</span><span class="sxs-lookup"><span data-stu-id="e0c03-120">" /</span></span>  
  
 <span data-ttu-id="e0c03-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e0c03-121">**Description**</span></span>  
 <span data-ttu-id="e0c03-122">Consente di digitare una descrizione per illustrare le modalità di utilizzo del ruolo ed elencare le azioni supportate.</span><span class="sxs-lookup"><span data-stu-id="e0c03-122">Type a description that explains how to use the role and enumerates what the role supports.</span></span>  
  
 <span data-ttu-id="e0c03-123">**Attività**</span><span class="sxs-lookup"><span data-stu-id="e0c03-123">**Task**</span></span>  
 <span data-ttu-id="e0c03-124">Consente di selezionare le attività che possono essere eseguite tramite questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="e0c03-124">Select the tasks that can be performed through this role.</span></span> <span data-ttu-id="e0c03-125">Non è possibile creare nuove attività o modificare attività esistenti supportate da [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0c03-125">You cannot create new tasks or modify the existing tasks that are supported by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="e0c03-126">In una definizione di ruolo a livello di elemento è possibile utilizzare solo attività a livello di elemento.</span><span class="sxs-lookup"><span data-stu-id="e0c03-126">Only item-level tasks can be used in an item-level role definition.</span></span>  
  
 <span data-ttu-id="e0c03-127">**Descrizione dell'attività**</span><span class="sxs-lookup"><span data-stu-id="e0c03-127">**Task Description**</span></span>  
 <span data-ttu-id="e0c03-128">Visualizza una descrizione dell'attività, che include le operazioni o autorizzazioni supportate.</span><span class="sxs-lookup"><span data-stu-id="e0c03-128">Shows a description of the task that enumerates the operations or permissions that the task supports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c03-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0c03-129">See Also</span></span>  
 <span data-ttu-id="e0c03-130">[Guida sensibile al contesto del server di report in Management Studio](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e0c03-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="e0c03-131">Definizioni di ruolo</span><span class="sxs-lookup"><span data-stu-id="e0c03-131">Role Definitions</span></span>](../security/role-definitions.md)  
  
  
