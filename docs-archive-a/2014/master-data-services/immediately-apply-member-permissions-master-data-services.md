---
title: Applicare immediatamente le autorizzazioni ai membri (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- members [Master Data Services], applying permissions immediately
- permissions [Master Data Services], applying member permissions immediately
ms.assetid: 5b16de66-5c39-49f5-992f-402a9eb319aa
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e960ad06213b7c5057a6249b72ce225a6abe35e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629880"
---
# <a name="immediately-apply-member-permissions-master-data-services"></a><span data-ttu-id="c9be7-102">Applicare immediatamente autorizzazioni membri (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c9be7-102">Immediately Apply Member Permissions (Master Data Services)</span></span>
  <span data-ttu-id="c9be7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], anziché attendere che venga applicata la sicurezza membri a intervalli regolari, è possibile applicare immediatamente autorizzazioni per membri.</span><span class="sxs-lookup"><span data-stu-id="c9be7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], instead of waiting for member security to be applied at regular intervals, you can apply member permissions immediately.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c9be7-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c9be7-104">Prerequisites</span></span>  
 <span data-ttu-id="c9be7-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c9be7-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c9be7-106">È necessario disporre dell'autorizzazione per eseguire la stored procedure mdm.udpSecurityMemberProcessRebuildModel nel database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9be7-106">You must have permission to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="c9be7-107">Per altre informazioni, vedere [Sicurezza di oggetti di database &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c9be7-107">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-immediately-apply-hierarchy-member-permissions"></a><span data-ttu-id="c9be7-108">Per applicare immediatamente autorizzazioni per membri della gerarchia</span><span class="sxs-lookup"><span data-stu-id="c9be7-108">To immediately apply hierarchy member permissions</span></span>  
  
1.  <span data-ttu-id="c9be7-109">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e connettersi all'istanza [!INCLUDE[ssDE](../includes/ssde-md.md)] per il database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9be7-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="c9be7-110">Creare una nuova query.</span><span class="sxs-lookup"><span data-stu-id="c9be7-110">Create a new query.</span></span>  
  
3.  <span data-ttu-id="c9be7-111">Digitare il testo seguente, sostituendo *database* con il nome del database e *Model_Name* con il nome del modello.</span><span class="sxs-lookup"><span data-stu-id="c9be7-111">Type the following text, replacing *database* with the name of your database and *Model_Name* with the name of the model.</span></span>  
  
    ```  
    USE [database];  
    GO  
  
    DECLARE @Model_ID INT;  
    SELECT @Model_ID = ID FROM mdm.tblModel WHERE [Name] = N'Model_Name';  
    EXEC [mdm].[udpSecurityMemberProcessRebuildModel] @Model_ID=@Model_ID, @ProcessNow=1;  
    GO  
    ```  
  
4.  <span data-ttu-id="c9be7-112">Consente di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="c9be7-112">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9be7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9be7-113">See Also</span></span>  
 <span data-ttu-id="c9be7-114">[Assegnare autorizzazioni membri gerarchia &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c9be7-114">[Assign Hierarchy Member Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/assign-hierarchy-member-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="c9be7-115">Autorizzazioni membri gerarchie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9be7-115">Hierarchy Member Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  
