---
title: Visualizzare le proprietà di un facet della gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facet properties
ms.assetid: 022a244c-c2e7-4467-b9a2-c7a27859be22
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea24ff2768ecaeec426a8689455912d848b54813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626683"
---
# <a name="view-the-properties-of-a-policy-based-management-facet"></a><span data-ttu-id="3c44c-102">Visualizzare le proprietà di un facet della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="3c44c-102">View the Properties of a Policy-Based Management Facet</span></span>
  <span data-ttu-id="3c44c-103">In questo argomento verrà descritto come visualizzare le proprietà di un facet della gestione basata su criteri in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c44c-103">This topic describes how to view the properties of a Policy-Based Management facet in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3c44c-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="3c44c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3c44c-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="3c44c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3c44c-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3c44c-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3c44c-107">**Per visualizzare le proprietà di un facet tramite:**</span><span class="sxs-lookup"><span data-stu-id="3c44c-107">**To view the properties of a facet, using:**</span></span>  
  
     [<span data-ttu-id="3c44c-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3c44c-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3c44c-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3c44c-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3c44c-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3c44c-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3c44c-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3c44c-111">Permissions</span></span>  
 <span data-ttu-id="3c44c-112">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="3c44c-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3c44c-113">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3c44c-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-facet"></a><span data-ttu-id="3c44c-114">Per visualizzare le proprietà di un facet</span><span class="sxs-lookup"><span data-stu-id="3c44c-114">To view the properties of a facet</span></span>  
  
1.  <span data-ttu-id="3c44c-115">In **Esplora oggetti**fare clic sul segno più per espandere il server contenente il facet di cui si desidera visualizzare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="3c44c-115">In **Object Explorer**, click the plus sign to expand the server that contains the facet whose properties you want to view.</span></span>  
  
2.  <span data-ttu-id="3c44c-116">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="3c44c-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="3c44c-117">Fare clic sul segno più per espandere la cartella **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="3c44c-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="3c44c-118">Fare clic sul segno più per espandere la cartella **Facet** .</span><span class="sxs-lookup"><span data-stu-id="3c44c-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="3c44c-119">Fare clic con il pulsante destro del mouse sul facet di cui si vogliono visualizzare le proprietà e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3c44c-119">Right-click the facet whose properties you want to view and select **Properties**.</span></span> <span data-ttu-id="3c44c-120">Per altre informazioni sulle opzioni disponibili nella finestra di dialogo **Proprietà facet -**_nome_facet_, vedere [Finestra di dialogo Proprietà facet, pagina Generale](../../integration-services/general-page-of-integration-services-designers-options.md), [Finestra di dialogo Proprietà facet, pagina Criteri dipendenti](facet-properties-dialog-box-dependent-policies-page.md) e [Finestra di dialogo Proprietà facet, pagina Condizioni dipendenti](facet-properties-dialog-box-dependent-conditions-page.md).</span><span class="sxs-lookup"><span data-stu-id="3c44c-120">For more information on the available options in the **Facet Properties -**_facet_name_ dialog box, see [Facet Properties Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Facet Properties Dialog Box, Dependent Policies Page](facet-properties-dialog-box-dependent-policies-page.md), and [Facet Properties Dialog Box, Dependent Conditions Page](facet-properties-dialog-box-dependent-conditions-page.md).</span></span>  
  
6.  <span data-ttu-id="3c44c-121">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="3c44c-121">When finished, click **Close**.</span></span>  
  
  
