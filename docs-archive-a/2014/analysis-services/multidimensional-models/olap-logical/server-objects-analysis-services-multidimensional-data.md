---
title: Oggetti server (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services objects, server objects
ms.assetid: 365bfd63-c55a-433d-9e1a-a788bc149a25
author: minewiskan
ms.author: owend
ms.openlocfilehash: f41a930bd5054583918180d7c50eca46c3ea5e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721883"
---
# <a name="server-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="940fa-102">Oggetti server (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="940fa-102">Server Objects (Analysis Services - Multidimensional Data)</span></span>
    
## <a name="introducing-server-objects"></a><span data-ttu-id="940fa-103">Introduzione agli oggetti server</span><span class="sxs-lookup"><span data-stu-id="940fa-103">Introducing Server Objects</span></span>  
 <span data-ttu-id="940fa-104">L' <xref:Microsoft.AnalysisServices.Server> oggetto rappresenta il server e l'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="940fa-104">The <xref:Microsoft.AnalysisServices.Server> object represents the server and the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] that you want to work with.</span></span>  
  
 <span data-ttu-id="940fa-105">Una volta stabilita la connessione per un'istanza di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], sarà possibile visualizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="940fa-105">As soon as you have a connected instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], you will be able to see:</span></span>  
  
-   <span data-ttu-id="940fa-106">Tutti i database a cui è possibile accedere, sotto forma di raccolta.</span><span class="sxs-lookup"><span data-stu-id="940fa-106">All databases that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="940fa-107">Tutte le proprietà del server definite, sotto forma di raccolta.</span><span class="sxs-lookup"><span data-stu-id="940fa-107">All defined server properties, as a collection.</span></span>  
  
-   <span data-ttu-id="940fa-108">La stringa di connessione, le informazioni di connessione e l'ID di sessione.</span><span class="sxs-lookup"><span data-stu-id="940fa-108">The connection string, the connection information, and the session ID.</span></span>  
  
-   <span data-ttu-id="940fa-109">Il nome, l'edizione e la versione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="940fa-109">The product name, edition, and version.</span></span>  
  
-   <span data-ttu-id="940fa-110">Le raccolte dei ruoli.</span><span class="sxs-lookup"><span data-stu-id="940fa-110">The roles collections.</span></span>  
  
-   <span data-ttu-id="940fa-111">La raccolta delle tracce.</span><span class="sxs-lookup"><span data-stu-id="940fa-111">The traces collection.</span></span>  
  
-   <span data-ttu-id="940fa-112">La raccolta degli assembly.</span><span class="sxs-lookup"><span data-stu-id="940fa-112">The assemblies collection.</span></span>  
  
  
