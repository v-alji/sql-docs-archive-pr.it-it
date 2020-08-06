---
title: Metodi del modello | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
ms.assetid: d3e658c9-bb22-480b-a3d5-bcde8f537ab2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d0b93b43383a4b0e5bf19d7c6be9c415d7c91e57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721084"
---
# <a name="model-methods"></a><span data-ttu-id="cb1d0-102">Metodi per i modelli</span><span class="sxs-lookup"><span data-stu-id="cb1d0-102">Model Methods</span></span>
  <span data-ttu-id="cb1d0-103">Per gestire modelli, è possibile utilizzare i metodi seguenti.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-103">You can use these methods to manage models.</span></span>  
  
|<span data-ttu-id="cb1d0-104">Metodo</span><span class="sxs-lookup"><span data-stu-id="cb1d0-104">Method</span></span>|<span data-ttu-id="cb1d0-105">Azione</span><span class="sxs-lookup"><span data-stu-id="cb1d0-105">Action</span></span>|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.GenerateModel%2A>|<span data-ttu-id="cb1d0-106">Viene generato un modello predefinito basato su un'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-106">Generates a default model on top of a shared data source.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetModelItemPermissions%2A>|<span data-ttu-id="cb1d0-107">Recupera le autorizzazioni dell'utente associate all'elemento del modello.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-107">Retrieves the user permissions that are associated with the model item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetModelItemPolicies%2A>|<span data-ttu-id="cb1d0-108">Recupera i criteri associati a un elemento del modello.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-108">Retrieves the policies that are associated with a model item.</span></span>|  
|<xref:ReportService2010.ReportingService2010.GetUserModel%2A>|<span data-ttu-id="cb1d0-109">Restituisce il pezzo semantico di un modello per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-109">Returns the semantic piece of a model for the current user.</span></span>|  
|<xref:ReportService2010.ReportingService2010.InheritModelItemParentSecurity%2A>|<span data-ttu-id="cb1d0-110">Elimina i criteri associati a un elemento del modello e determina l'ereditarietà dei criteri del padre da parte dell'elemento del modello.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-110">Deletes the policies that are associated with a model item and causes the model item to inherit the policies from its parent.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListModelDrillthroughReports%2A>|<span data-ttu-id="cb1d0-111">Elenca report drill-through associati a un'entità in un modello.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-111">Lists drillthrough reports that are associated with an entity in a model.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListModelItemChildren%2A>|<span data-ttu-id="cb1d0-112">Restituisce un array di elementi figlio dell'elemento del modello.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-112">Returns an array of model item child elements.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListModelItemTypes%2A>|<span data-ttu-id="cb1d0-113">Restituisce un elenco di tipi di elementi del modello.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-113">Returns a list of supported model item types.</span></span>|  
|<xref:ReportService2010.ReportingService2010.ListModelPerspectives%2A>|<span data-ttu-id="cb1d0-114">Elenca modelli e prospettive disponibili all'utente.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-114">Lists models and perspectives that are available to the user.</span></span>|  
|<xref:ReportService2010.ReportingService2010.RegenerateModel%2A>|<span data-ttu-id="cb1d0-115">Aggiorna un modello esistente basato sulle modifiche allo schema dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-115">Updates an existing model based on changes to the data source schema.</span></span>|  
|<xref:ReportService2010.ReportingService2010.RemoveAllModelItemPolicies%2A>|<span data-ttu-id="cb1d0-116">Elimina tutti i criteri associati agli elementi del modello nel modello specificato.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-116">Deletes all policies that are associated with model items in the specified model.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetModelDrillthroughReports%2A>|<span data-ttu-id="cb1d0-117">Associa un set di report drill-through a un modello.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-117">Associates a set of drillthrough reports together with a model.</span></span>|  
|<xref:ReportService2010.ReportingService2010.SetModelItemPolicies%2A>|<span data-ttu-id="cb1d0-118">Imposta i criteri di sicurezza su un elemento del modello.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-118">Sets security policies on a model item.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb1d0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb1d0-119">See Also</span></span>  
 <span data-ttu-id="cb1d0-120">[Compilazione di applicazioni tramite servizio Web e .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="cb1d0-120">[Building Applications Using the Web Service and the .NET Framework](../net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="cb1d0-121">[Servizio Web ReportServer](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="cb1d0-121">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="cb1d0-122">[Metodi del servizio Web ReportServer](report-server-web-service-methods.md) </span><span class="sxs-lookup"><span data-stu-id="cb1d0-122">[Report Server Web Service Methods](report-server-web-service-methods.md) </span></span>  
 [<span data-ttu-id="cb1d0-123">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="cb1d0-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
