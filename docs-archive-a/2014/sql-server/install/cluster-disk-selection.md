---
title: Selezione disco cluster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster disk selection
ms.assetid: 0d6b863d-5972-4a20-9990-64ee8016fea6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0f53d6d3f623254d2b17996be7fd5b8235dca223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628211"
---
# <a name="cluster-disk-selection"></a><span data-ttu-id="a3939-102">Selezione dischi cluster</span><span class="sxs-lookup"><span data-stu-id="a3939-102">Cluster Disk Selection</span></span>
  <span data-ttu-id="a3939-103">Usare la pagina **Selezione dischi cluster** dell'Installazione guidata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per selezionare la risorsa disco del cluster condiviso per il cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3939-103">Use the **Cluster Disk Selection** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to select the shared cluster disk resource for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span> <span data-ttu-id="a3939-104">Il disco del cluster è l'unità in cui verranno memorizzati i dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3939-104">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="a3939-105">Un disco del cluster condiviso non è un requisito per le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] installazioni di cluster.</span><span class="sxs-lookup"><span data-stu-id="a3939-105">A shared cluster disk is not a requirement for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] cluster installations.</span></span> <span data-ttu-id="a3939-106">Un file server SMB è una risorsa di archiviazione supportata per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] le installazioni del cluster di failover di e può essere specificato tramite la pagina **motore di database-Directory dati** prima di completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a3939-106">An SMB file server is a supported storage for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] failover cluster installations, and can be specified by using the **Database Engine - Data Directories** page before completing the installation.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="a3939-107">Se si è scelto di installare Analysis Services, è necessario specificare un disco del cluster condiviso.</span><span class="sxs-lookup"><span data-stu-id="a3939-107">If you have selected Analysis Services to be installed, you must specify a shared cluster disk.</span></span>  
>   
>  <span data-ttu-id="a3939-108">Se si intende abilitare FILESTREAM in questa istanza del cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è necessario specificare un disco del cluster condiviso.</span><span class="sxs-lookup"><span data-stu-id="a3939-108">If you plan to enable FILESTREAM on this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster instance, you must specify a shared cluster disk.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a3939-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a3939-109">Options</span></span>  
 <span data-ttu-id="a3939-110">**Dischi condivisi**</span><span class="sxs-lookup"><span data-stu-id="a3939-110">**Shared Disks**</span></span>  
 <span data-ttu-id="a3939-111">Selezionare un singolo disco dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="a3939-111">Select a single disk from the list.</span></span> <span data-ttu-id="a3939-112">Il disco del cluster è l'unità in cui verranno memorizzati i dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a3939-112">The cluster disk is where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data will be placed.</span></span>  
  
 <span data-ttu-id="a3939-113">È possibile specificare un solo disco.</span><span class="sxs-lookup"><span data-stu-id="a3939-113">Only one disk can be specified.</span></span> <span data-ttu-id="a3939-114">Se si seleziona il gruppo contenente la risorsa quorum del cluster, verrà visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="a3939-114">If you select the group containing the cluster quorum resource, a warning will be displayed.</span></span> <span data-ttu-id="a3939-115">È consigliabile non installare la risorsa quorum del cluster.</span><span class="sxs-lookup"><span data-stu-id="a3939-115">We recommend that you do not install to the cluster quorum resource.</span></span>  
  
 <span data-ttu-id="a3939-116">**Dischi condivisi disponibili**</span><span class="sxs-lookup"><span data-stu-id="a3939-116">**Available Shared Disks**</span></span>  
 <span data-ttu-id="a3939-117">Visualizza un elenco dei dischi disponibili, una descrizione di ogni risorsa disco e l'indicazione se ciascun disco è qualificato come disco fisso.</span><span class="sxs-lookup"><span data-stu-id="a3939-117">Displays a list of available disks, whether each is qualified as a shared disk, and a description of each disk resource.</span></span>  
  
  
