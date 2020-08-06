---
title: Visualizzare i facet della gestione basata su criteri in un oggetto di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facets
ms.assetid: 5f423b9f-a6c4-41a7-9d8d-8f4926ce1fb4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9137971a79e9e5a18e0ef5d901184133a4c3eff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626684"
---
# <a name="view-the-policy-based-management-facets-on-a-sql-server-object"></a><span data-ttu-id="ae552-102">Visualizzare i facet della gestione basata su criteri in un oggetto di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae552-102">View the Policy-Based Management Facets on a SQL Server Object</span></span>
  <span data-ttu-id="ae552-103">In questo argomento verrà descritto come visualizzare tutti i facet della gestione basata su criteri applicati a un oggetto specifico di SQL Server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae552-103">This topic describes how to view all of the Policy-Based Management facets applied to a specific SQL Server object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ae552-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ae552-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ae552-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ae552-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ae552-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ae552-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ae552-107">**Per visualizzare tutti i facet in un oggetto tramite:**</span><span class="sxs-lookup"><span data-stu-id="ae552-107">**To view all of the facets in an object, using:**</span></span>  
  
     [<span data-ttu-id="ae552-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ae552-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ae552-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ae552-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ae552-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ae552-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ae552-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ae552-111">Permissions</span></span>  
 <span data-ttu-id="ae552-112">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="ae552-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ae552-113">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ae552-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-all-of-the-facets-in-an-object"></a><span data-ttu-id="ae552-114">Per visualizzare tutti i facet in un oggetto</span><span class="sxs-lookup"><span data-stu-id="ae552-114">To view all of the facets in an object</span></span>  
  
1.  <span data-ttu-id="ae552-115">In Esplora oggetti fare clic con il pulsante destro del mouse su un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], su un oggetto istanza, su un database o su un oggetto di database, quindi scegliere **Facet**.</span><span class="sxs-lookup"><span data-stu-id="ae552-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="ae552-116">Nella finestra di dialogo **Visualizza facet -**_nome_oggetto_ selezionare un facet nell'elenco **Facet** per visualizzarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="ae552-116">In the **View Facets -**_object_name_ dialog box, in the **Facet** list, select a facet to view its properties.</span></span> <span data-ttu-id="ae552-117">Per ulteriori informazioni sulle opzioni disponibili in questa finestra di dialogo, vedere [View Facets Dialog Box](view-facets-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="ae552-117">For more information on the available options in this dialog box, see [View Facets Dialog Box](view-facets-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="ae552-118">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae552-118">When finished, click **OK**.</span></span>  
  
  
