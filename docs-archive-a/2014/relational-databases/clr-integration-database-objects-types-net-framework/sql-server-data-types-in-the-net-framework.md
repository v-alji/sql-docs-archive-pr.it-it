---
title: SQL Server tipi di dati nel .NET Framework | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- System.Data library
- System.Data.SqlTypes namespace
- data types [CLR integration]
- SqlTypes library
- database objects [CLR integration], data types
- common language runtime [SQL Server], data types
- building database objects [CLR integration], data types
- mapping data types [CLR integration]
ms.assetid: c70d3ffe-2c32-45a5-849b-ef113dda09b9
author: rothja
ms.author: jroth
ms.openlocfilehash: fe0ed680e7050c58738301256575e4138f21276f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725951"
---
# <a name="sql-server-data-types-in-the-net-framework"></a><span data-ttu-id="c2f4e-102">Tipi di dati di SQL Server in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c2f4e-102">SQL Server Data Types in the .NET Framework</span></span>
  <span data-ttu-id="c2f4e-103">La libreria `SqlTypes` fa parte della libreria di classi di base di [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c2f4e-103">The `SqlTypes` library is part of the base class library of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="c2f4e-104">ed è progettata per fornire tipi di dati con la stessa semantica e la stessa precisione di quelle disponibili nel database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2f4e-104">It is designed to provide data types with the same semantics and precision as those found in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="c2f4e-105">In questo argomento viene descritta la nuova semantica per i programmatori di .NET Framework e vengono introdotti i tipi implementati nello spazio dei nomi `System.Data.SqlTypes` incluso nella libreria `System.Data`.</span><span class="sxs-lookup"><span data-stu-id="c2f4e-105">This topic describes the new semantics to .NET Framework programmers, and introduces the types implemented in the `System.Data.SqlTypes` namespace that is included in the `System.Data` library.</span></span>  
  
 <span data-ttu-id="c2f4e-106">Nella tabella seguente sono elencati gli argomenti inclusi in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="c2f4e-106">This following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="c2f4e-107">Supporto dei valori Null e confronti di logica a tre valori</span><span class="sxs-lookup"><span data-stu-id="c2f4e-107">Nullability and Three-Value Logic Comparisons</span></span>](nullability-and-three-value-logic-comparisons.md)  
 <span data-ttu-id="c2f4e-108">Viene descritta la gestione dei valori NULL con i tipi di dati di integrazione con CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="c2f4e-108">Discusses how NULL values are handled with common language runtime (CLR) integration data types.</span></span>  
  
 [<span data-ttu-id="c2f4e-109">Regole di confronto e tipi di dati di integrazione CLR</span><span class="sxs-lookup"><span data-stu-id="c2f4e-109">Collation and CLR Integration Data Types</span></span>](collation-and-clr-integration-data-types.md)  
 <span data-ttu-id="c2f4e-110">Viene descritta la gestione delle regole di confronto con l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="c2f4e-110">Describes how collations are handled with CLR integration.</span></span>  
  
 [<span data-ttu-id="c2f4e-111">Gestione di Large Object &#40;i parametri LOB&#41; in CLR</span><span class="sxs-lookup"><span data-stu-id="c2f4e-111">Handling Large Object &#40;LOB&#41; Parameters in the CLR</span></span>](handling-large-object-lob-parameters-in-the-clr.md)  
 <span data-ttu-id="c2f4e-112">Viene descritto come passare tipi LOB tra [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e CLR.</span><span class="sxs-lookup"><span data-stu-id="c2f4e-112">Describes how to pass LOB types between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the CLR.</span></span>  
  
 [<span data-ttu-id="c2f4e-113">Mapping dei dati dei parametri CLR</span><span class="sxs-lookup"><span data-stu-id="c2f4e-113">Mapping CLR Parameter Data</span></span>](mapping-clr-parameter-data.md)  
 <span data-ttu-id="c2f4e-114">Vengono illustrati i mapping dei tipi di dati tra [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], l'integrazione CLR e .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c2f4e-114">Shows data type mappings between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], CLR integration, and the .NET Framework.</span></span>  
  
  
