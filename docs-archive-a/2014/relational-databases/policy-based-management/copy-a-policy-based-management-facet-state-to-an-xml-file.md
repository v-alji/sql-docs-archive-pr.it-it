---
title: Copiare lo stato di un facet della gestione basata su criteri in un file XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, copy facet state to XML file
ms.assetid: 7d604ab1-6dd6-4f8e-a79c-eba99ab106fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7be2332d9a2507a079d85a3424bda3a387609ca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715199"
---
# <a name="copy-a-policy-based-management-facet-state-to-an-xml-file"></a><span data-ttu-id="c7790-102">Copiare lo stato di un facet della gestione basata su criteri in un file XML</span><span class="sxs-lookup"><span data-stu-id="c7790-102">Copy a Policy-Based Management Facet State to an XML File</span></span>
  <span data-ttu-id="c7790-103">In questo argomento verrà descritto come copiare lo stato di un facet della gestione basata su criteri in un file XML in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7790-103">This topic describes how to how to copy the state of a Policy-Based Management facet to an XML file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c7790-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c7790-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c7790-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c7790-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c7790-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c7790-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c7790-107">**Per copiare lo stato di un facet in un file XML tramite:**</span><span class="sxs-lookup"><span data-stu-id="c7790-107">**To copy a facet state to an XML file, using:**</span></span>  
  
     [<span data-ttu-id="c7790-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7790-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c7790-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c7790-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c7790-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c7790-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c7790-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c7790-111">Permissions</span></span>  
 <span data-ttu-id="c7790-112">Le procedure descritte in questo argomento richiedono l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="c7790-112">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c7790-113">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7790-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-a-facet-state-to-an-xml-file"></a><span data-ttu-id="c7790-114">Per copiare lo stato di un facet in un file XML</span><span class="sxs-lookup"><span data-stu-id="c7790-114">To copy a facet state to an XML file</span></span>  
  
1.  <span data-ttu-id="c7790-115">In Esplora oggetti fare clic con il pulsante destro del mouse su un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], su un oggetto istanza, su un database o su un oggetto di database, quindi scegliere **Facet**.</span><span class="sxs-lookup"><span data-stu-id="c7790-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="c7790-116">Nella finestra di dialogo **Visualizza facet -**_nome_oggetto_ fare clic su **Esporta stato corrente come criteri**.</span><span class="sxs-lookup"><span data-stu-id="c7790-116">In the **View Facets -**_object_name_ dialog box, click **Export Current State as Policy**.</span></span>  
  
3.  <span data-ttu-id="c7790-117">Nella finestra di dialogo **Esporta come criterio** digitare il percorso e il nome del file oppure usare il pulsante Sfoglia (**...**) per trovare il file, quindi digitare il nome del file XML.</span><span class="sxs-lookup"><span data-stu-id="c7790-117">In the **Export as Policy** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the file, and then type the name of the XML file.</span></span> <span data-ttu-id="c7790-118">Per ulteriori informazioni sulle opzioni disponibili in questa finestra di dialogo, vedere [Export As Policy Dialog Box](export-as-policy-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="c7790-118">For more information on the available options in this dialog box, see [Export As Policy Dialog Box](export-as-policy-dialog-box.md)</span></span>  
  
4.  <span data-ttu-id="c7790-119">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7790-119">When finished, click **OK**.</span></span>  
  
  
