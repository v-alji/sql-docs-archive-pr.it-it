---
title: Esportare i criteri della gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, export policy
ms.assetid: f0001b33-9078-4432-8460-496736fb325a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 15f554aeeebfd47c3fa1ea13b100fbe6bcfcc055
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629373"
---
# <a name="export-a-policy-based-management-policy"></a><span data-ttu-id="03334-102">Esportare i criteri della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="03334-102">Export a Policy-Based Management Policy</span></span>
  <span data-ttu-id="03334-103">In questo argomento verrà descritto come esportare i criteri della gestione basata su criteri in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="03334-103">This topic describes how to export a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="03334-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="03334-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="03334-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="03334-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="03334-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="03334-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="03334-107">**Per esportare i criteri tramite:**</span><span class="sxs-lookup"><span data-stu-id="03334-107">**To export a policy, using:**</span></span>  
  
     [<span data-ttu-id="03334-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03334-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="03334-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="03334-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="03334-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="03334-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="03334-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="03334-111">Permissions</span></span>  
 <span data-ttu-id="03334-112">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="03334-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="03334-113">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="03334-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-export-a-policy"></a><span data-ttu-id="03334-114">Per esportare i criteri</span><span class="sxs-lookup"><span data-stu-id="03334-114">To export a policy</span></span>  
  
1.  <span data-ttu-id="03334-115">In Esplora oggetti fare clic sul segno più per espandere il server contenente i criteri della gestione basata su criteri da esportare.</span><span class="sxs-lookup"><span data-stu-id="03334-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to export.</span></span>  
  
2.  <span data-ttu-id="03334-116">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="03334-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="03334-117">Fare clic sul segno più per espandere la cartella **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="03334-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="03334-118">Fare clic sul segno più per espandere la cartella **Criteri** .</span><span class="sxs-lookup"><span data-stu-id="03334-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="03334-119">Fare clic con il pulsante destro del mouse sui criteri che si vuole esportare e scegliere **Esporta criteri**.</span><span class="sxs-lookup"><span data-stu-id="03334-119">Right-click the policy that you want to export and select **Export Policy**.</span></span>  
  
6.  <span data-ttu-id="03334-120">Nella finestra di dialogo **Esporta criteri** digitare il percorso e il nome del file nella barra degli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="03334-120">In the **Export Policy** dialog box, type the path and name of the file in the address bar.</span></span> <span data-ttu-id="03334-121">In alternativa, individuare un percorso appropriato per il file nel pannello di navigazione della finestra di dialogo, quindi digitare il nome del file XML nella casella **Nome file** .</span><span class="sxs-lookup"><span data-stu-id="03334-121">Alternately, find a suitable location for the file in the dialog box's navigation pane, and then type the name of the XML file in the **File Name** box.</span></span>  
  
7.  <span data-ttu-id="03334-122">Al termine fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="03334-122">When finished, click **Save**.</span></span>  
  
  
