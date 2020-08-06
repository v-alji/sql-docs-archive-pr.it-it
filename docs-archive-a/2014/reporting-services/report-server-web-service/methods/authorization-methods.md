---
title: Metodi di autorizzazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], reports
- authorization [Reporting Services]
- reports [Reporting Services], security
- tasks [Reporting Services]
- roles [Reporting Services], methods
ms.assetid: 45e9cf2c-facf-4801-9482-c855403f42a8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b04a21b5075e939a4732e2f8ec219e169f4ba440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721101"
---
# <a name="authorization-methods"></a><span data-ttu-id="7e710-102">Metodi di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7e710-102">Authorization Methods</span></span>
  <span data-ttu-id="7e710-103">È possibile utilizzare questi metodi per gestire attività, ruoli e criteri nel server di report.</span><span class="sxs-lookup"><span data-stu-id="7e710-103">You can use these methods to manage tasks, roles, and policies on the report server.</span></span>  
  
|<span data-ttu-id="7e710-104">Metodo</span><span class="sxs-lookup"><span data-stu-id="7e710-104">Method</span></span>|<span data-ttu-id="7e710-105">Azione</span><span class="sxs-lookup"><span data-stu-id="7e710-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateRole%2A>|<span data-ttu-id="7e710-106">Aggiunge un nuovo ruolo al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="7e710-106">Adds a new role to the report server database.</span></span> <span data-ttu-id="7e710-107">Questo metodo può essere applicato solo in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="7e710-107">This method =applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.DeleteRole%2A>|<span data-ttu-id="7e710-108">Elimina un ruolo dal database del server di report.</span><span class="sxs-lookup"><span data-stu-id="7e710-108">Deletes a role from the report server database.</span></span> <span data-ttu-id="7e710-109">Questo metodo può essere applicato solo in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="7e710-109">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPermissions%2A>|<span data-ttu-id="7e710-110">Restituisce le autorizzazioni utente associate a un particolare elemento nel database del server di report o in una raccolta di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e710-110">Returns the user permissions that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetPolicies%2A>|<span data-ttu-id="7e710-111">Restituisce i criteri associati a un particolare elemento nel database del server di report o in una raccolta di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7e710-111">Returns the policies that are associated with a particular item in the report server database or SharePoint library.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetRoleProperties%2A>|<span data-ttu-id="7e710-112">Restituisce le proprietà dei metadati dei ruoli e una raccolta di attività associate.</span><span class="sxs-lookup"><span data-stu-id="7e710-112">Returns role metadata properties and a collection of associated tasks.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPermissions%2A>|<span data-ttu-id="7e710-113">Restituisce le autorizzazioni di sistema dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7e710-113">Returns the user's system permissions.</span></span> <span data-ttu-id="7e710-114">Questo metodo può essere applicato solo in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="7e710-114">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetSystemPolicies%2A>|<span data-ttu-id="7e710-115">Restituisce i criteri di sistema, inclusi i gruppi e i ruoli ai quali sono associati.</span><span class="sxs-lookup"><span data-stu-id="7e710-115">Returns the system policies, including groups and roles with which they are associated.</span></span> <span data-ttu-id="7e710-116">Questo metodo può essere applicato solo in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="7e710-116">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.InheritParentSecurity%2A>|<span data-ttu-id="7e710-117">Elimina i criteri associati a un particolare elemento nel database del server di report e imposta i criteri di sicurezza per l'elemento in modo che corrispondano a quelli dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="7e710-117">Deletes the policies that are associated with a particular item in the report server database and sets the security policies for the item to those of its parent.</span></span>|  
|<xref:ReportService2010.ReportingService2010.IsSSLRequired%2A>|<span data-ttu-id="7e710-118">Restituisce un valore booleano che indica se il protocollo Secure Socket Layer (SSL) è obbligatorio per l'utilizzo dell'endpoint <xref:ReportService2010>.</span><span class="sxs-lookup"><span data-stu-id="7e710-118">Returns a Boolean value that indicates whether the Secure Socket Layer (SSL) protocol is required to use the <xref:ReportService2010> end point.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListRoles%2A>|<span data-ttu-id="7e710-119">Restituisce i nomi e le descrizioni dei ruoli gestiti dal server di report.</span><span class="sxs-lookup"><span data-stu-id="7e710-119">Returns the names and descriptions of roles that are managed by the report server.</span></span>|  
|<xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A>|<span data-ttu-id="7e710-120">Restituisce un elenco di metodi SOAP (Simple Object Access Protocol) nell'endpoint <xref:ReportExecution2005> che richiedono una connessione protetta quando vengono richiamati.</span><span class="sxs-lookup"><span data-stu-id="7e710-120">Returns a list of Simple Object Access Protocol (SOAP) methods in the <xref:ReportExecution2005> endpoint that require a secure connection when invoked.</span></span> <span data-ttu-id="7e710-121">L'impostazione `SecureConnectionLevel` del server di report viene utilizzata per determinare quali metodi vengono restituiti.</span><span class="sxs-lookup"><span data-stu-id="7e710-121">The `SecureConnectionLevel` setting of the report server is used to determine which methods are returned.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListTasks%2A>|<span data-ttu-id="7e710-122">Restituisce le attività gestite dal server di report.</span><span class="sxs-lookup"><span data-stu-id="7e710-122">Returns the tasks that are managed by the report server.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetPolicies%2A>|<span data-ttu-id="7e710-123">Imposta i criteri associati a un elemento specificato.</span><span class="sxs-lookup"><span data-stu-id="7e710-123">Sets the policies that are associated with a specified item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetRoleProperties%2A>|<span data-ttu-id="7e710-124">Imposta le proprietà dei metadati dei ruoli e associa un set di attività a un ruolo.</span><span class="sxs-lookup"><span data-stu-id="7e710-124">Sets role metadata properties and associates a set of tasks with a role.</span></span> <span data-ttu-id="7e710-125">Questo metodo può essere applicato solo in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="7e710-125">This method applies to native mode only.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A>|<span data-ttu-id="7e710-126">Imposta i criteri di sistema che definiscono i gruppi e i ruoli associati.</span><span class="sxs-lookup"><span data-stu-id="7e710-126">Sets the system policy that defines groups and their associated roles.</span></span> <span data-ttu-id="7e710-127">Questo metodo può essere applicato solo in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="7e710-127">This method applies to native mode only.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e710-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e710-128">See Also</span></span>  
 <span data-ttu-id="7e710-129">[Compilazione di applicazioni tramite servizio Web e .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="7e710-129">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="7e710-130">[Servizio Web ReportServer](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="7e710-130">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="7e710-131">[Metodi del servizio Web ReportServer](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="7e710-131">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="7e710-132">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7e710-132">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
