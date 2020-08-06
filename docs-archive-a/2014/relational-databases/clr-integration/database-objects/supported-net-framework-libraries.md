---
title: Librerie di .NET Framework supportate | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], .NET Framework libraries
- .NET Framework [CLR Integration]
ms.assetid: 417544ff-c25c-496e-add4-2f278f8a4911
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f92e3eadccc869452cf35534f786724c8e259a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623335"
---
# <a name="supported-net-framework-libraries"></a><span data-ttu-id="71d17-102">Librerie .NET Framework supportate</span><span class="sxs-lookup"><span data-stu-id="71d17-102">Supported .NET Framework Libraries</span></span>
  <span data-ttu-id="71d17-103">Grazie all'integrazione di CLR in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], è possibile creare stored procedure, trigger, funzioni definite dall'utente, tipi definiti dall'utente e aggregazioni definite dall'utente nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="71d17-103">With the common language runtime (CLR) hosted in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="71d17-104">Con le librerie di classi .NET Framework è possibile accedere alle classi preesistenti che offrono funzionalità per manipolazione delle stringhe, operazioni matematiche avanzate, accesso ai file, crittografia e così via.</span><span class="sxs-lookup"><span data-stu-id="71d17-104">With the functionality found in the .NET Framework class libraries, you have access to pre-built classes that provide functionality for string manipulation, advanced math operations, file access, cryptography, and more.</span></span> <span data-ttu-id="71d17-105">A queste classi è possibile accedere da stored procedure gestite, tipi definiti dall'utente, trigger, funzioni definite dall'utente o funzioni di aggregazione definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="71d17-105">These classes can be accessed from any managed stored procedure, user-defined type, trigger, user-defined function, or user-defined aggregate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71d17-106">Se si esegue il servizio o si aggiornano assembly non supportati nella Global Assembly Cache (GAC), il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71d17-106">If you service or upgrade unsupported assemblies in the global assembly cache (GAC), your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="71d17-107">Se esiste un assembly in un' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="71d17-107">If an assembly exists both in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span> <span data-ttu-id="71d17-108">Se si gestiscono o aggiornano assembly della GAC registrati anche nel database, inclusi gli assembly .NET Framework non supportati, assicurarsi di gestirne o aggiornarne anche la copia che si trova nei database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con l'istruzione `ALTER ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="71d17-108">If you service or upgrade any assemblies in the GAC that are also registered in the database, including unsupported .NET Framework assemblies, make sure to also service or upgrade the copy of the assembly inside your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases with the `ALTER ASSEMBLY` statement.</span></span> <span data-ttu-id="71d17-109">Per ulteriori informazioni, vedere l' [articolo della Knowledge Base 949080](https://support.microsoft.com/kb/949080).</span><span class="sxs-lookup"><span data-stu-id="71d17-109">For more information, see [Knowledge Base article 949080](https://support.microsoft.com/kb/949080).</span></span>  
  
## <a name="supported-libraries"></a><span data-ttu-id="71d17-110">Librerie supportate</span><span class="sxs-lookup"><span data-stu-id="71d17-110">Supported Libraries</span></span>  
 <span data-ttu-id="71d17-111">A partire da [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] è disponibile un elenco di librerie di .NET Framework supportate, che sono state testate per garantire che soddisfino gli standard di affidabilità e sicurezza per l'interazione con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] li carica direttamente dalla Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="71d17-111">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] has a list of supported .NET Framework libraries, which have been tested to ensure that they meet reliability and security standards for interaction with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] loads them directly from the Global Assembly Cache (GAC).</span></span>  
  
 <span data-ttu-id="71d17-112">Le librerie e gli spazi dei nomi supportati dall'integrazione con CLR in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sono:</span><span class="sxs-lookup"><span data-stu-id="71d17-112">The libraries/namespaces supported by CLR integration in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are:</span></span>  
  
-   <span data-ttu-id="71d17-113">CustomMarshalers</span><span class="sxs-lookup"><span data-stu-id="71d17-113">CustomMarshalers</span></span>  
  
-   <span data-ttu-id="71d17-114">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="71d17-114">Microsoft.VisualBasic</span></span>  
  
-   <span data-ttu-id="71d17-115">Microsoft.VisualC</span><span class="sxs-lookup"><span data-stu-id="71d17-115">Microsoft.VisualC</span></span>  
  
-   <span data-ttu-id="71d17-116">mscorlib</span><span class="sxs-lookup"><span data-stu-id="71d17-116">mscorlib</span></span>  
  
-   <span data-ttu-id="71d17-117">System</span><span class="sxs-lookup"><span data-stu-id="71d17-117">System</span></span>  
  
-   <span data-ttu-id="71d17-118">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="71d17-118">System.Configuration</span></span>  
  
-   <span data-ttu-id="71d17-119">System.Data</span><span class="sxs-lookup"><span data-stu-id="71d17-119">System.Data</span></span>  
  
-   <span data-ttu-id="71d17-120">System.Data.OracleClient</span><span class="sxs-lookup"><span data-stu-id="71d17-120">System.Data.OracleClient</span></span>  
  
-   <span data-ttu-id="71d17-121">System.Data.SqlXml</span><span class="sxs-lookup"><span data-stu-id="71d17-121">System.Data.SqlXml</span></span>  
  
-   <span data-ttu-id="71d17-122">System.Deployment</span><span class="sxs-lookup"><span data-stu-id="71d17-122">System.Deployment</span></span>  
  
-   <span data-ttu-id="71d17-123">System.Security</span><span class="sxs-lookup"><span data-stu-id="71d17-123">System.Security</span></span>  
  
-   <span data-ttu-id="71d17-124">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="71d17-124">System.Transactions</span></span>  
  
-   <span data-ttu-id="71d17-125">System.Web.Services</span><span class="sxs-lookup"><span data-stu-id="71d17-125">System.Web.Services</span></span>  
  
-   <span data-ttu-id="71d17-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="71d17-126">System.Xml</span></span>  
  
-   <span data-ttu-id="71d17-127">System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="71d17-127">System.Core.dll</span></span>  
  
-   <span data-ttu-id="71d17-128">System.Xml.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="71d17-128">System.Xml.Linq.dll</span></span>  
  
## <a name="unsupported-libraries"></a><span data-ttu-id="71d17-129">Librerie non supportate</span><span class="sxs-lookup"><span data-stu-id="71d17-129">Unsupported Libraries</span></span>  
 <span data-ttu-id="71d17-130">Le librerie non supportate possono essere comunque chiamate da stored procedure gestite, trigger, funzioni definite dall'utente, tipi definiti dall'utente e funzioni di aggregazione definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="71d17-130">Unsupported libraries can still be called from your managed stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates.</span></span> <span data-ttu-id="71d17-131">La libreria non supportata deve essere prima registrata nel database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizzando l'istruzione `CREATE ASSEMBLY` prima che possa essere utilizzata nel codice.</span><span class="sxs-lookup"><span data-stu-id="71d17-131">The unsupported library must first be registered in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, using the `CREATE ASSEMBLY` statement, before it can be used in your code.</span></span> <span data-ttu-id="71d17-132">È necessario verificare e testare la sicurezza e l'affidabilità delle librerie non supportate registrate ed eseguite nel server.</span><span class="sxs-lookup"><span data-stu-id="71d17-132">Any unsupported library that is registered and run on the server should be reviewed and tested for security and reliability.</span></span>  
  
 <span data-ttu-id="71d17-133">Lo spazio dei nomi `System.DirectoryServices` non è ad esempio supportato.</span><span class="sxs-lookup"><span data-stu-id="71d17-133">For example, the `System.DirectoryServices` namespace is not supported.</span></span> <span data-ttu-id="71d17-134">È necessario registrare l'assembly System.DirectoryServices.dll con le autorizzazioni `UNSAFE` prima che sia possibile chiamarlo dal codice.</span><span class="sxs-lookup"><span data-stu-id="71d17-134">You must register the System.DirectoryServices.dll assembly with `UNSAFE` permissions before you can call it from your code.</span></span> <span data-ttu-id="71d17-135">L'autorizzazione `UNSAFE` è necessaria perché le classi nello spazio dei nomi `System.DirectoryServices` non soddisfano i requisiti per `SAFE` o `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="71d17-135">The `UNSAFE` permission is necessary because classes in the `System.DirectoryServices` namespace do not meet the requirements for `SAFE` or `EXTERNAL_ACCESS`.</span></span> <span data-ttu-id="71d17-136">Per altre informazioni, vedere [restrizioni del modello di programmazione dell'integrazione CLR](clr-integration-programming-model-restrictions.md) e [sicurezza dall'accesso di codice per l'integrazione con CLR](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="71d17-136">For more information, see [CLR Integration Programming Model Restrictions](clr-integration-programming-model-restrictions.md) and [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d17-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71d17-137">See Also</span></span>  
 <span data-ttu-id="71d17-138">[Creazione di un assembly](../assemblies/creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="71d17-138">[Creating an Assembly](../assemblies/creating-an-assembly.md) </span></span>  
 <span data-ttu-id="71d17-139">[Sicurezza dall'accesso di codice per l'integrazione con CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="71d17-139">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 [<span data-ttu-id="71d17-140">Restrizioni relative al modello di programmazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="71d17-140">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
  
  
