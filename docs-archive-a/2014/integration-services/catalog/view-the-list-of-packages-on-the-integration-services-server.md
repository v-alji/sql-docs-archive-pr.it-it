---
title: Visualizzare l'elenco di pacchetti nel server Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 67a992d1-7524-4f4b-b3d8-ebd9e5ea82a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 47b30f9ea0b2abae73f9260b873b7c8436c423eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710995"
---
# <a name="view-the-list-of-packages-on-the-integration-services-server"></a><span data-ttu-id="34858-102">Visualizzazione dell'elenco di pacchetti nel server Integration Services</span><span class="sxs-lookup"><span data-stu-id="34858-102">View the List of Packages on the Integration Services Server</span></span>
  <span data-ttu-id="34858-103">È possibile visualizzare l'elenco di pacchetti archiviati nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="34858-103">You can view the list of packages that are stored on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server in one of two ways.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="34858-104">accesso</span><span class="sxs-lookup"><span data-stu-id="34858-104">access</span></span>  
 <span data-ttu-id="34858-105">Per visualizzare l'elenco di pacchetti archiviati nel server, eseguire una query sulla vista [catalog.packages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-packages-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="34858-105">To view the list of packages that are stored on the server, query the view, [catalog.packages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-packages-ssisdb-database).</span></span>  
  
 <span data-ttu-id="34858-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34858-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>  
 <span data-ttu-id="34858-107">Per visualizzare i pacchetti archiviati nel server tramite Esplora oggetti in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], attenersi alla procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="34858-107">To view packages stored on the server by using Object Explorer in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], follow the procedure below.</span></span>  
  
### <a name="to-view-packages-using-ssmanstudiofull"></a><span data-ttu-id="34858-108">Per visualizzare i pacchetti utilizzando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34858-108">To view packages using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>  
  
1.  <span data-ttu-id="34858-109">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]connettersi al server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34858-109">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="34858-110">cioè connettersi all'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] in cui è ospitato il database di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34858-110">That is, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="34858-111">In Esplora oggetti espandere l'albero per visualizzare il nodo dei **cataloghi di Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="34858-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="34858-112">Espandere il nodo **Cataloghi di Integration Services** per visualizzare il nodo **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="34858-112">Expand the **Integration Services Catalogs** node to display the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="34858-113">Espandere il nodo **SSISDB** per visualizzare un elenco di una o più cartelle.</span><span class="sxs-lookup"><span data-stu-id="34858-113">Expand the **SSISDB** node to display a list of one or more folders.</span></span> <span data-ttu-id="34858-114">Nella cartella **Progetti** di ogni cartella sono contenuti uno o più progetti e nella cartella **Pacchetti** di ogni progetto sono contenuti uno o più pacchetti.</span><span class="sxs-lookup"><span data-stu-id="34858-114">Each folder contains one or more projects in the **Projects** folder, and each project contains one more packages in the **Packages** folder.</span></span>  
  
  
