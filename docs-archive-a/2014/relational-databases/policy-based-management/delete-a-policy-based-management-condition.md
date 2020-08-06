---
title: Eliminare una condizione della gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, delete policy conditions
ms.assetid: e04148b8-f6dd-4c50-a5ef-c650b71dbf4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02a5294ecb53db4d8baa4f3dae0a232d9551a13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624098"
---
# <a name="delete-a-policy-based-management-condition"></a><span data-ttu-id="e452b-102">Eliminare una condizione della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="e452b-102">Delete a Policy-Based Management Condition</span></span>
  <span data-ttu-id="e452b-103">In questo argomento verrà descritto come eliminare una condizione della gestione basata su criteri in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e452b-103">This topic describes how to delete a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="e452b-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="e452b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e452b-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e452b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e452b-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e452b-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e452b-107">**Per eliminare una condizione tramite:**</span><span class="sxs-lookup"><span data-stu-id="e452b-107">**To delete a condition, using:**</span></span>  
  
     [<span data-ttu-id="e452b-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e452b-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e452b-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e452b-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e452b-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e452b-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e452b-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e452b-111">Permissions</span></span>  
 <span data-ttu-id="e452b-112">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="e452b-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e452b-113">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e452b-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-condition"></a><span data-ttu-id="e452b-114">Per eliminare una condizione</span><span class="sxs-lookup"><span data-stu-id="e452b-114">To delete a condition</span></span>  
  
1.  <span data-ttu-id="e452b-115">In **Esplora oggetti**fare clic sul segno più per espandere il server contenente la condizione da eliminare.</span><span class="sxs-lookup"><span data-stu-id="e452b-115">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to delete.</span></span>  
  
2.  <span data-ttu-id="e452b-116">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="e452b-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="e452b-117">Fare clic sul segno più per espandere la cartella **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="e452b-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="e452b-118">Fare clic sul segno più per espandere la cartella **Condizioni** .</span><span class="sxs-lookup"><span data-stu-id="e452b-118">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="e452b-119">Fare clic con il pulsante destro del mouse sulla condizione da eliminare, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e452b-119">Right-click the condition that you want to delete and select **Delete**.</span></span>  
  
6.  <span data-ttu-id="e452b-120">Nella finestra di dialogo **Elimina oggetto** verificare che sia selezionata la condizione corretta, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e452b-120">In the **Delete Object** dialog box, ensure that the correct condition is selected and then click **OK**.</span></span>  
  
  
