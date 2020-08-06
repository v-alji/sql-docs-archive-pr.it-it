---
title: Eliminare i criteri della gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policies
ms.assetid: 488f0305-190c-4223-aa5c-e9bd43b520eb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c43bc3cdf4a7a5b5d9268bbd7e68506616d1f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711891"
---
# <a name="delete-a-policy-based-management-policy"></a><span data-ttu-id="498e6-102">Eliminare i criteri della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="498e6-102">Delete a Policy-Based Management Policy</span></span>
  <span data-ttu-id="498e6-103">In questo argomento verrà descritto come eliminare i criteri della gestione basata su criteri in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="498e6-103">This topic describes how to delete a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="498e6-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="498e6-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="498e6-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="498e6-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="498e6-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="498e6-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="498e6-107">**Per eliminare i criteri tramite:**</span><span class="sxs-lookup"><span data-stu-id="498e6-107">**To delete a policy, using:**</span></span>  
  
     [<span data-ttu-id="498e6-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="498e6-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="498e6-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="498e6-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="498e6-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="498e6-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="498e6-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="498e6-111">Permissions</span></span>  
 <span data-ttu-id="498e6-112">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="498e6-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="498e6-113">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="498e6-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-policy"></a><span data-ttu-id="498e6-114">Per eliminare i criteri</span><span class="sxs-lookup"><span data-stu-id="498e6-114">To delete a policy</span></span>  
  
1.  <span data-ttu-id="498e6-115">In Esplora oggetti fare clic sul segno più per espandere il server contenente i criteri della gestione basata su criteri da eliminare.</span><span class="sxs-lookup"><span data-stu-id="498e6-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to delete.</span></span>  
  
2.  <span data-ttu-id="498e6-116">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="498e6-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="498e6-117">Fare clic sul segno più per espandere la cartella **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="498e6-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="498e6-118">Fare clic sul segno più per espandere la cartella **Criteri** .</span><span class="sxs-lookup"><span data-stu-id="498e6-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="498e6-119">Fare clic con il pulsante destro del mouse sui criteri da eliminare, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="498e6-119">Right-click the policy that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="498e6-120">Nella finestra di dialogo **Elimina oggetto** verificare che sia selezionata la condizione corretta, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="498e6-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
