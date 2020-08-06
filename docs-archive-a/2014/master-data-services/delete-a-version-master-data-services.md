---
title: Eliminare una versione (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], deleting
- deleting versions [Master Data Services]
ms.assetid: 2a4eeffe-8379-4744-ad44-c27d8c8ac9a8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f83a3bc396b2a13ac7ac03ef653b16a0d556189a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637398"
---
# <a name="delete-a-version-master-data-services"></a><span data-ttu-id="9cb86-102">Eliminare una versione (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9cb86-102">Delete a Version (Master Data Services)</span></span>
  <span data-ttu-id="9cb86-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eliminare una versione quando si è certi che non sono più necessari i dati master a essa associati.</span><span class="sxs-lookup"><span data-stu-id="9cb86-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a version when you are sure you no longer need the master data associated with the version.</span></span> <span data-ttu-id="9cb86-104">Dopo avere eliminato una versione, non è possibile recuperare i dati master associati.</span><span class="sxs-lookup"><span data-stu-id="9cb86-104">After you delete a version, you cannot retrieve the associated master data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="9cb86-105">Se un modello presenta una sola versione e la si elimina, il modello diventa inutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="9cb86-105">If a model has only one version and you delete it, the model becomes unusable.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9cb86-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9cb86-106">Prerequisites</span></span>  
 <span data-ttu-id="9cb86-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="9cb86-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9cb86-108">È necessario disporre delle autorizzazioni per visualizzare la vista mdm.viw_SYSTEM_SCHEMA_VERSION ed eseguire la stored procedure mds.udpVersionDelete nel database di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9cb86-108">You must have permission to view the mdm.viw_SYSTEM_SCHEMA_VERSION view and to execute the mds.udpVersionDelete stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="9cb86-109">Per altre informazioni, vedere [Sicurezza di oggetti di database &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9cb86-109">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-version"></a><span data-ttu-id="9cb86-110">Per eliminare una versione</span><span class="sxs-lookup"><span data-stu-id="9cb86-110">To delete a version</span></span>  
  
1.  <span data-ttu-id="9cb86-111">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e connettersi all'istanza [!INCLUDE[ssDE](../includes/ssde-md.md)] per il database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9cb86-111">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="9cb86-112">Aprire la vista mdm.viw_SYSTEM_SCHEMA_VERSION.</span><span class="sxs-lookup"><span data-stu-id="9cb86-112">Open the mdm.viw_SYSTEM_SCHEMA_VERSION view.</span></span>  
  
3.  <span data-ttu-id="9cb86-113">Trovare la versione del modello che si vuole eliminare e copiare il valore nel campo **ID** .</span><span class="sxs-lookup"><span data-stu-id="9cb86-113">Find the version of the model you want to delete and copy the value in the **ID** field.</span></span>  
  
4.  <span data-ttu-id="9cb86-114">Creare una nuova query.</span><span class="sxs-lookup"><span data-stu-id="9cb86-114">Create a new query.</span></span>  
  
5.  <span data-ttu-id="9cb86-115">Digitare il testo seguente, sostituendo *version_ID* con il valore copiato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="9cb86-115">Type the following text, replacing *version_ID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpVersionDelete] @Version_ID='version_ID'  
    ```  
  
6.  <span data-ttu-id="9cb86-116">Consente di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="9cb86-116">Run the query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9cb86-117">Può essere necessario attendere alcuni minuti prima che l'applicazione Web rifletta la modifica.</span><span class="sxs-lookup"><span data-stu-id="9cb86-117">You may have to wait a few minutes before the Web application reflects the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb86-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cb86-118">See Also</span></span>  
 <span data-ttu-id="9cb86-119">[Versioni &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9cb86-119">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="9cb86-120">Copiare una versione &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9cb86-120">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
  
