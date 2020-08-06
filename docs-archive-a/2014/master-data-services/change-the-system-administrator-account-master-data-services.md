---
title: Modificare l'account amministratore di sistema (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- administrators [Master Data Services], changing
ms.assetid: cf30312e-4338-49a7-90f0-6e4f7b431ff8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d13cdc19c70c9e16c92dfd290393739d7e4f5e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718371"
---
# <a name="change-the-system-administrator-account-master-data-services"></a><span data-ttu-id="30441-102">Modificare l'account amministratore di sistema (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="30441-102">Change the System Administrator Account (Master Data Services)</span></span>
  <span data-ttu-id="30441-103">È possibile modificare l'account utente designato come amministratore di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] sistema.</span><span class="sxs-lookup"><span data-stu-id="30441-103">You can change the user account that is designated as the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] system administrator.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="30441-104">Al termine di questa procedura, l'account utente dell'amministratore di sistema precedente viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="30441-104">When you complete this procedure, the former system administrator user account is deleted.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="30441-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="30441-105">Prerequisites</span></span>  
 <span data-ttu-id="30441-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="30441-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="30441-107">È necessario aggiungere il nome utente del nuovo amministratore all'elenco degli utenti di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30441-107">You must add the new administrator's user name to the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Users list.</span></span> <span data-ttu-id="30441-108">Per altre informazioni, vedere [aggiungere un utente &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="30441-108">For more information, see [Add a User &#40;Master Data Services&#41;](add-a-user-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="30441-109">È necessario disporre dell'autorizzazione per visualizzare mdm.tblUser ed eseguire la stored procedure mdm.udpSecurityMemberProcessRebuildModel nel database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30441-109">You must have permission to view mdm.tblUser and to execute the mdm.udpSecurityMemberProcessRebuildModel stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="30441-110">Per altre informazioni, vedere [Sicurezza di oggetti di database &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="30441-110">For more information, see [Database Object Security &#40;Master Data Services&#41;](../../2014/master-data-services/database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-change-the-administrator-account"></a><span data-ttu-id="30441-111">Per modificare l'account amministratore</span><span class="sxs-lookup"><span data-stu-id="30441-111">To change the administrator account</span></span>  
  
1.  <span data-ttu-id="30441-112">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e connettersi all'istanza [!INCLUDE[ssDE](../includes/ssde-md.md)] per il database [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="30441-112">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="30441-113">In MDM. tblUser trovare l'utente che sarà il nuovo amministratore e copiare il valore nella `SID` colonna.</span><span class="sxs-lookup"><span data-stu-id="30441-113">In mdm.tblUser, find the user that will be the new administrator and copy the value in the `SID` column.</span></span>  
  
3.  <span data-ttu-id="30441-114">Creare una nuova query.</span><span class="sxs-lookup"><span data-stu-id="30441-114">Create a new query.</span></span>  
  
4.  <span data-ttu-id="30441-115">Digitare il testo seguente, sostituendo *Domain \ user_name* con il nome utente e il *SID* del nuovo amministratore con il valore copiato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="30441-115">Type the following text, replacing *DOMAIN\user_name* with the new administrator's user name and *SID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpSecuritySetAdministrator] @UserName='DOMAIN\user_name', @SID = 'SID', @PromoteNonAdmin = 1  
    ```  
  
5.  <span data-ttu-id="30441-116">Consente di eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="30441-116">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30441-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30441-117">See Also</span></span>  
 [<span data-ttu-id="30441-118">Amministratori &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="30441-118">Administrators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/administrators-master-data-services.md)  
  
  
