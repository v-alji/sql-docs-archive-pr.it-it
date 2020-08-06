---
title: Sicurezza dell'integrazione con CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- authorization [CLR integration]
- common language runtime [SQL Server], security
- database objects [CLR integration], security
ms.assetid: 05d7a471-c5d5-4730-b903-e4edc8157bb4
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d99d32a061d8fe78a8ac3642a503cceb45f3809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627289"
---
# <a name="clr-integration-security"></a><span data-ttu-id="53b06-102">Sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="53b06-102">CLR Integration Security</span></span>
  <span data-ttu-id="53b06-103">Il modello di sicurezza del [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR) gestisce e protegge l'accesso tra diversi tipi di oggetti CLR e non CLR in esecuzione all'interno di [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] un'istruzione o un altro oggetto CLR in esecuzione nel server.</span><span class="sxs-lookup"><span data-stu-id="53b06-103">The security model of the [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] statement or another CLR object running in the server.</span></span> <span data-ttu-id="53b06-104">Le chiamate tra gli oggetti vengono definite collegamenti.</span><span class="sxs-lookup"><span data-stu-id="53b06-104">The calls between objects are referred to as links.</span></span> <span data-ttu-id="53b06-105">I tipi di controllo della sicurezza eseguiti su questi oggetti dipendono dai tipi di collegamento utilizzati.</span><span class="sxs-lookup"><span data-stu-id="53b06-105">The types of security checks performed on these objects depend on the types of links involved.</span></span>  
  
 <span data-ttu-id="53b06-106">Il modello di sicurezza dell'integrazione con CLR presenta gli obiettivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="53b06-106">The CLR integration security model has the following goals:</span></span>  
  
-   <span data-ttu-id="53b06-107">Per impostazione predefinita, il codice utente gestito viene eseguito in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53b06-107">By default, running managed user code on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="53b06-108">L'esecuzione di operazioni che potenzialmente compromettono l'affidabilità di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] deve essere protetta grazie alle autorizzazioni di livello elevato appropriate.</span><span class="sxs-lookup"><span data-stu-id="53b06-108">Performing operations that potentially compromise the robustness of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] should be protected by appropriate high-level permissions.</span></span>  
  
-   <span data-ttu-id="53b06-109">Non è consigliabile concedere al codice utente gestito l'accesso non autorizzato ai dati dell'utente o ad altro codice dell'utente nel database.</span><span class="sxs-lookup"><span data-stu-id="53b06-109">Managed user code should not gain unauthorized access to user data or other user code in the database.</span></span> <span data-ttu-id="53b06-110">Il codice definito dall'utente deve essere eseguito nel contesto di sicurezza della sessione utente che lo ha richiamato e con i privilegi corretti per il contesto di sicurezza in questione.</span><span class="sxs-lookup"><span data-stu-id="53b06-110">User-defined code should run under the security context of the user-session that invoked it, and with the correct privileges for that security context.</span></span>  
  
-   <span data-ttu-id="53b06-111">È necessario effettuare controlli per limitare al codice utente l'accesso alle risorse esterne al server consentendone l'utilizzo esclusivamente per il calcolo e l'accesso ai dati locali.</span><span class="sxs-lookup"><span data-stu-id="53b06-111">There should be controls for restricting user code from accessing any resources outside the server, using it strictly for local data access and computation.</span></span>  
  
-   <span data-ttu-id="53b06-112">Non è consigliabile concedere al codice definito dall'utente l'accesso non autorizzato alle risorse di sistema solo perché è in esecuzione nel processo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53b06-112">User-defined code should not be able to gain unauthorized access to system resources by virtue of running in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="53b06-113">con il modello di sicurezza basato sull'accesso al codice di CLR.</span><span class="sxs-lookup"><span data-stu-id="53b06-113">with the code access-based security model of the CLR.</span></span> <span data-ttu-id="53b06-114">Alcuni dei vantaggi di questo approccio combinato alla sicurezza vengono esaminati nella presente sezione.</span><span class="sxs-lookup"><span data-stu-id="53b06-114">Some of the advantages of this combined approach to security are discussed in this section.</span></span>  
  
 <span data-ttu-id="53b06-115">Nella tabella seguente vengono elencati gli argomenti disponibili in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="53b06-115">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="53b06-116">Sicurezza da accesso di codice dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="53b06-116">CLR Integration Code Access Security</span></span>](clr-integration-code-access-security.md)  
 <span data-ttu-id="53b06-117">Viene illustrato il modello di sicurezza da accesso di codice (CAS, Code Access Security) per il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="53b06-117">Discusses the code access security (CAS) model for managed code.</span></span>  
  
 [<span data-ttu-id="53b06-118">Attributi di protezione host e programmazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="53b06-118">Host Protection Attributes and CLR Integration Programming</span></span>](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md)  
 <span data-ttu-id="53b06-119">Vengono fornite informazioni sui valori di attributi di protezione host che non sono consentiti negli assembly SAFE e EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="53b06-119">Provides information about the host protection attribute (HPA) values that are disallowed in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
 [<span data-ttu-id="53b06-120">Collegamenti nella sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="53b06-120">Links in CLR Integration Security</span></span>](../../../database-engine/dev-guide/links-in-clr-integration-security.md)  
 <span data-ttu-id="53b06-121">Viene illustrato come parti del codice utente possano chiamarsi reciprocamente in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53b06-121">Describes how pieces of user-code can call each other in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="53b06-122">Rappresentazione e sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="53b06-122">Impersonation and CLR Integration Security</span></span>](../../../database-engine/dev-guide/impersonation-and-clr-integration-security.md)  
 <span data-ttu-id="53b06-123">Viene illustrato con il codice gestito acceda a risorse esterne utilizzando la rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="53b06-123">Discusses how managed code accesses external resources using impersonation.</span></span>  
  
 [<span data-ttu-id="53b06-124">Accettazione di chiamanti parzialmente attendibili</span><span class="sxs-lookup"><span data-stu-id="53b06-124">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
 <span data-ttu-id="53b06-125">Vengono illustrati i problemi che si verificano quando un metodo gestito richiama un metodo di una classe contenuta in un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="53b06-125">Discusses issues that arise when a managed method invokes a method in a class contained in another assembly.</span></span>  
  
 [<span data-ttu-id="53b06-126">Domini applicazione e sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="53b06-126">Application Domains and CLR Integration Security</span></span>](../../../database-engine/dev-guide/application-domains-and-clr-integration-security.md)  
 <span data-ttu-id="53b06-127">Viene descritto come caricare gli assembly nei domini applicazione.</span><span class="sxs-lookup"><span data-stu-id="53b06-127">Describes how assemblies are loaded into application domains.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53b06-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53b06-128">See Also</span></span>  
 [<span data-ttu-id="53b06-129">Gestione degli assembly dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="53b06-129">Managing CLR Integration Assemblies</span></span>](../assemblies/managing-clr-integration-assemblies.md)  
  
  
