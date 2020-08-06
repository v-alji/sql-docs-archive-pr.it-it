---
title: Sviluppo sicuro (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- development security [Reporting Services]
- security [Reporting Services], development
- security [Reporting Services], strategies
ms.assetid: 12161a6c-b93b-4312-9d27-0c922561eb9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ba284b9013c5da6b03cce06ec72deccb045cfad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638277"
---
# <a name="secure-development-reporting-services"></a><span data-ttu-id="acd49-102">Sviluppo sicuro (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="acd49-102">Secure Development (Reporting Services)</span></span>
  <span data-ttu-id="acd49-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] è un potente sistema di sicurezza che consente l'esecuzione di codice in contesti di sicurezza soggetti a vincoli definiti dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="acd49-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides a robust security system that can run code in tightly constrained, administrator-defined security contexts.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="acd49-104">usano il sistema di sicurezza di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], noto come sicurezza dall'accesso di codice (o sicurezza basata sull'evidenza).</span><span class="sxs-lookup"><span data-stu-id="acd49-104">uses the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] security system, known as code access security (or evidence-based security).</span></span> <span data-ttu-id="acd49-105">In un sistema con sicurezza dall'accesso di codice un utente può essere considerato attendibile per accedere a una risorsa, ma se il codice eseguito non è attendibile, l'accesso alla risorsa verrà negato.</span><span class="sxs-lookup"><span data-stu-id="acd49-105">Under code access security, a user may be trusted to access a resource, but if the code the user executes is not trusted, access to the resource will be denied.</span></span>  
  
 <span data-ttu-id="acd49-106">A differenza della sicurezza basata su utenti specifici, la sicurezza basata su codice può essere espressa per assembly o dati personalizzati, per il recapito, il rendering e le estensioni di sicurezza sviluppati per [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acd49-106">Security based on code, as opposed to specific users, permits security to be expressed for custom assemblies or data, delivery, rendering, and security extensions that you develop for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="acd49-107">Il codice dell'estensione può essere eseguito da un numero qualsiasi di utenti di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], ciascuno dei quali non è noto in fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="acd49-107">Your extension code may be executed by any number of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] users, all of whom are unknown at development time.</span></span> <span data-ttu-id="acd49-108">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] le estensioni o gli assembly personalizzati richiedono criteri di sicurezza specifici,</span><span class="sxs-lookup"><span data-stu-id="acd49-108">The custom assemblies or extensions that you develop require specific security policies in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="acd49-109">rappresentati come tipi in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acd49-109">These security policies are represented as types in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="acd49-110">Per altre informazioni sulla sicurezza dall'accesso di codice, vedere "Sicurezza dall'accesso di codice" nella documentazione di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acd49-110">For a more information about code access security, see "Code Access Security" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="acd49-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="acd49-111">In This Section</span></span>  
 [<span data-ttu-id="acd49-112">Sicurezza dall'accesso di codice in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="acd49-112">Code Access Security in Reporting Services</span></span>](code-access-security-in-reporting-services.md)  
 <span data-ttu-id="acd49-113">Descrive la sicurezza dall'accesso di codice e la configurazione dei criteri per le estensioni e gli assembly personalizzati in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="acd49-113">Introduces code access security and policy configuration for custom assemblies and extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="acd49-114">Informazioni sui criteri di sicurezza</span><span class="sxs-lookup"><span data-stu-id="acd49-114">Understanding Security Policies</span></span>](understanding-security-policies.md)  
 <span data-ttu-id="acd49-115">Descrive i diversi tipi di assembly in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] e il modo in cui la sicurezza dall'accesso di codice influisce sulle autorizzazioni per il codice.</span><span class="sxs-lookup"><span data-stu-id="acd49-115">Describes the various assembly types in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] and how code access security affects code permissions.</span></span>  
  
 [<span data-ttu-id="acd49-116">Uso di file di criteri di sicurezza di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="acd49-116">Using Reporting Services Security Policy Files</span></span>](using-reporting-services-security-policy-files.md)  
 <span data-ttu-id="acd49-117">Descrive i diversi componenti di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] e i corrispondenti file di configurazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="acd49-117">Describes the different [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] components and the corresponding policy configuration files.</span></span>  
  
  
