---
title: Classi gestite SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- .NET Framework [SQLXML], Managed Classes
- SQL Server .NET Data Provider
- Managed Classes [SQLXML], about managed classes
- providers [SQLXML], SQL Server .NET Data Provider
- data providers [SQLXML], SQL Server .NET Data Provider
- Managed Classes [SQLXML]
- XML [SQLXML]
- SQLXML Managed Classes
- providers [SQLXML], SQLXML Managed Classes
- data providers [SQLXML], SQLXML Managed Classes
- SQLXML, Managed Classes
ms.assetid: 73a5faeb-dabf-4895-acb5-a9651b646065
author: rothja
ms.author: jroth
ms.openlocfilehash: bb8d2d4f2d2fc512901e4ad37f0e46cf696b9475
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623113"
---
# <a name="sqlxml-managed-classes"></a><span data-ttu-id="1ac71-102">classi gestite SQLXML</span><span class="sxs-lookup"><span data-stu-id="1ac71-102">SQLXML Managed Classes</span></span>
  <span data-ttu-id="1ac71-103">Le classi gestite [!INCLUDE[msCoName](../../../includes/msconame-md.md)] espongono la funzionalità di SQLXML 4.0 in [!INCLUDE[msCoName](../../../includes/msconame-md.md)].NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ac71-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML Managed Classes exposes the functionality of SQLXML 4.0 inside the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="1ac71-104">Le classi gestite SQLXML consentono di scrivere un'applicazione C# per accedere ai dati XML da un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], portare i dati nell'ambiente .NET Framework, elaborare i dati e inviare nuovamente gli aggiornamenti a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] come DiffGram per applicarli.</span><span class="sxs-lookup"><span data-stu-id="1ac71-104">With SQLXML Managed Classes, you can write a C# application to access XML data from an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], bring the data into the .NET Framework environment, process the data, and send the updates back to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as a DiffGram to apply the updates.</span></span> <span data-ttu-id="1ac71-105">Quando si applicano aggiornamenti a un database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizzando le classi gestite SQLXML, è necessario utilizzare uno schema di mapping.</span><span class="sxs-lookup"><span data-stu-id="1ac71-105">You must use a mapping schema when applying updates to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database using SQLXML Managed Classes.</span></span> <span data-ttu-id="1ac71-106">Per un esempio funzionante, vedere [accesso alla funzionalità SQLXML nell'ambiente .NET](accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1ac71-106">For a working sample, see [Accessing SQLXML Functionality in the .NET Environment](accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
 <span data-ttu-id="1ac71-107">Per utilizzare le classi gestite SQLXML con SQLXML 4.0, è necessario installare Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ac71-107">To use the SQLXML Managed Classes with SQLXML 4.0, you must install Microsoft Visual Studio.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ac71-108">.NET Framework include il provider di dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="1ac71-108">The .NET Framework includes the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .NET Data Provider.</span></span> <span data-ttu-id="1ac71-109">Tale provider può essere utilizzato per accedere a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dall'ambiente .NET. È tuttavia in grado di gestire solo query SQL tradizionali (ovvero query del database relazionale ad eccezione delle query FOR XML).</span><span class="sxs-lookup"><span data-stu-id="1ac71-109">This provider can be used to access [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from the .NET environment; however, it can handle only traditional SQL queries (that is, relational database queries with the exception of FOR XML queries).</span></span> <span data-ttu-id="1ac71-110">Non è possibile eseguire modelli XML o query XPath sul lato server in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ac71-110">You cannot execute XML templates or the server-side XPath queries in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ac71-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1ac71-111">In This Section</span></span>  
 [<span data-ttu-id="1ac71-112">Modello a oggetti di classi gestite SQLXML</span><span class="sxs-lookup"><span data-stu-id="1ac71-112">SQLXML Managed Classes Object Model</span></span>](../../../database-engine/dev-guide/sqlxml-managed-classes-object-model.md)  
 <span data-ttu-id="1ac71-113">Vengono documentate le classi gestite SQLXML e le proprietà e i metodi rispettivi.</span><span class="sxs-lookup"><span data-stu-id="1ac71-113">Documents SQLXML Managed Classes and their properties and methods.</span></span>  
  
 [<span data-ttu-id="1ac71-114">Utilizzo di classi gestite SQLXML</span><span class="sxs-lookup"><span data-stu-id="1ac71-114">Using the SQLXML Managed Classes</span></span>](sqlxml-4-0-net-framework-support-managed-classes.md)  
 <span data-ttu-id="1ac71-115">Vengono forniti esempi di utilizzo delle classi gestite SQLXML.</span><span class="sxs-lookup"><span data-stu-id="1ac71-115">Provides examples of using SQLXML Managed Classes.</span></span>  
  
  
