---
title: Concetti relativi alla programmazione dell'integrazione con CLR (Common Language Runtime) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- CLR [SQL Server] See common language runtime [SQL Server]
- Database Engine [SQL Server], .NET Framework
- .NET Framework [SQL Server], Database Engine programming
- common language runtime [SQL Server]
- .NET Framework [SQL Server]
ms.assetid: 951bf851-3e6e-4361-ae6a-2bcd5b837ebd
author: rothja
ms.author: jroth
ms.openlocfilehash: 38323b0145132ad60d59c001d5147a7d19942462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627292"
---
# <a name="common-language-runtime-clr-integration-programming-concepts"></a><span data-ttu-id="a41b5-102">Concetti relativi alla programmazione dell'integrazione con CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="a41b5-102">Common Language Runtime (CLR) Integration Programming Concepts</span></span>
  <span data-ttu-id="a41b5-103">A partire da [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è inclusa l'integrazione del componente CRL (Common Language Runtime) di .NET Framework per [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="a41b5-103">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="a41b5-104">È pertanto possibile scrivere stored procedure, trigger, tipi definiti dall'utente, funzioni definite dall'utente, funzioni di aggregazione definite dall'utente e funzioni di flusso con valori di tabella usando qualsiasi linguaggio di .NET Framework, inclusi [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET e [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="a41b5-104">This means that you can now write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="a41b5-105">Lo spazio dei nomi Microsoft.SqlServer.Server include la funzionalità principali per la programmazione CLR in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a41b5-105">The Microsoft.SqlServer.Server namespace includes core functionality for CLR programming in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a41b5-106">Lo spazio dei nomi Microsoft.SqlServer.Server, tuttavia, viene trattato nella documentazione di .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="a41b5-106">However, the Microsoft.SqlServer.Server namespace is documented in the .NET Framework SDK.</span></span> <span data-ttu-id="a41b5-107">Questa documentazione non è inclusa nella documentazione online di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a41b5-107">This documentation is not included in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a41b5-108">Per impostazione predefinita, durante l'installazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] viene installato .NET Framework, ma non .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="a41b5-108">By default, the .NET Framework is installed with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but the .NET Framework SDK is not.</span></span> <span data-ttu-id="a41b5-109">Se SDK non è installato nel computer né incluso nella raccolta della documentazione online, i collegamenti al contenuto SDK presenti in questa sezione non funzionano.</span><span class="sxs-lookup"><span data-stu-id="a41b5-109">Without the SDK installed on your computer and included in the Books Online collection, links to SDK content in this section do not work.</span></span> <span data-ttu-id="a41b5-110">Installare .NET Framework SDK,</span><span class="sxs-lookup"><span data-stu-id="a41b5-110">Install the .NET Framework SDK.</span></span> <span data-ttu-id="a41b5-111">Al termine dell'installazione, aggiungere l'SDK alla raccolta della documentazione online e al sommario seguendo le istruzioni riportate in [installazione di .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx).</span><span class="sxs-lookup"><span data-stu-id="a41b5-111">Once installed, add the SDK to the Books Online collection and table of contents by following the instructions in [Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx).</span></span>  
  
 <span data-ttu-id="a41b5-112">Nella tabella seguente vengono elencati gli argomenti disponibili in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="a41b5-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="a41b5-113">Panoramica dell'integrazione di Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="a41b5-113">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](common-language-runtime-integration-overview.md)  
 <span data-ttu-id="a41b5-114">Viene fornita una breve panoramica di CLR e vengono descritti i motivi e le modalità dell'utilizzo di questa tecnologia in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a41b5-114">Provides a brief overview of the CLR, and describes how and why this technology has been used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a41b5-115">Vengono inoltre descritti i vantaggi dell'utilizzo di CLR per creare oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="a41b5-115">Describes the benefits of using the CLR to create database objects.</span></span>  
  
 [<span data-ttu-id="a41b5-116">Assembly &#40;Motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="a41b5-116">Assemblies &#40;Database Engine&#41;</span></span>](assemblies-database-engine.md)  
 <span data-ttu-id="a41b5-117">Viene descritto come usare gli assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per distribuire funzioni, stored procedure, trigger, aggregazioni definite dall'utente e tipi definiti dall'utente scritti usando uno dei linguaggi di codice gestito di Common Language Runtime (CLR) di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework e non [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a41b5-117">Describes how assemblies are used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework common language runtime (CLR), and not written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 [<span data-ttu-id="a41b5-118">Compilazione di oggetti di database con Common Language Runtime &#40;integrazione&#41; CLR</span><span class="sxs-lookup"><span data-stu-id="a41b5-118">Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration</span></span>](database-objects/building-database-objects-with-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="a41b5-119">Vengono descritti i tipi di oggetti che è possibile compilare usando CLR e vengono esaminati i requisiti per la compilazione di oggetti di database CLR.</span><span class="sxs-lookup"><span data-stu-id="a41b5-119">Describes the kinds of objects that can be built using the CLR, and reviews the requirements for building CLR database objects.</span></span>  
  
 [<span data-ttu-id="a41b5-120">Accesso ai dati da oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="a41b5-120">Data Access from CLR Database Objects</span></span>](data-access/data-access-from-clr-database-objects.md)  
 <span data-ttu-id="a41b5-121">Viene descritto il modo in cui una routine CLR può accedere a dati archiviati in un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a41b5-121">Describes how a CLR routine can access data stored in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="a41b5-122">Sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="a41b5-122">CLR Integration Security</span></span>](security/clr-integration-security.md)  
 <span data-ttu-id="a41b5-123">Viene descritto il modello di sicurezza dell'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="a41b5-123">Describes the CLR integration security model.</span></span>  
  
 [<span data-ttu-id="a41b5-124">Debug di oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="a41b5-124">Debugging CLR Database Objects</span></span>](debugging-clr-database-objects.md)  
 <span data-ttu-id="a41b5-125">Vengono descritte le limitazioni e i requisiti per il debug di oggetti di database CLR.</span><span class="sxs-lookup"><span data-stu-id="a41b5-125">Describes limitations of and requirements for debugging CLR database objects.</span></span>  
  
 [<span data-ttu-id="a41b5-126">Distribuzione di oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="a41b5-126">Deploying CLR Database Objects</span></span>](deploying-clr-database-objects.md)  
 <span data-ttu-id="a41b5-127">Viene descritta la distribuzione di assembly in server di produzione.</span><span class="sxs-lookup"><span data-stu-id="a41b5-127">Describes deploying assemblies to production servers.</span></span>  
  
 [<span data-ttu-id="a41b5-128">Gestione degli assembly dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="a41b5-128">Managing CLR Integration Assemblies</span></span>](assemblies/managing-clr-integration-assemblies.md)  
 <span data-ttu-id="a41b5-129">Viene descritto come creare ed eliminare assembly di integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="a41b5-129">Describes how to create and drop CLR integration assemblies.</span></span>  
  
 [<span data-ttu-id="a41b5-130">Monitoraggio e risoluzione dei problemi relativi agli oggetti di database gestiti</span><span class="sxs-lookup"><span data-stu-id="a41b5-130">Monitoring and Troubleshooting Managed Database Objects</span></span>](monitoring-and-troubleshooting-managed-database-objects.md)  
 <span data-ttu-id="a41b5-131">Vengono fornite informazioni sugli strumenti che è possibile usare per monitorare e risolvere i problemi relativi agli oggetti di database e agli assembly gestiti in esecuzione in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a41b5-131">Provides information about the tools that can be used to monitor and troubleshoot managed database objects and assemblies running in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="a41b5-132">Scenari di utilizzo ed esempi per l'integrazione con CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="a41b5-132">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="a41b5-133">Vengono descritti gli scenari di utilizzo e gli esempi di codice che usano oggetti CLR.</span><span class="sxs-lookup"><span data-stu-id="a41b5-133">Describes usage scenarios and code samples using CLR objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a41b5-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a41b5-134">See Also</span></span>  
 <span data-ttu-id="a41b5-135">[Assembly &#40;motore di database&#41;](assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="a41b5-135">[Assemblies &#40;Database Engine&#41;](assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="a41b5-136">[Installazione di .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="a41b5-136">[Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span></span>  
  
  
