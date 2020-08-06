---
title: Importare i criteri della gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, import policy
ms.assetid: 850b7ef9-d2b7-4754-bf04-7cb419ffb776
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d83ed589e147c61b1692447aacb17535f18a5c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624686"
---
# <a name="import-a-policy-based-management-policy"></a><span data-ttu-id="4fc89-102">Importare i criteri della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="4fc89-102">Import a Policy-Based Management Policy</span></span>
  <span data-ttu-id="4fc89-103">In questo argomento verrà descritto come importare un'istanza dei criteri della gestione basata su criteri in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fc89-103">This topic describes how to import a Policy-Based Management policy instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="4fc89-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="4fc89-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4fc89-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="4fc89-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4fc89-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4fc89-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4fc89-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4fc89-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4fc89-108">**Per importare un'istanza dei criteri tramite:**</span><span class="sxs-lookup"><span data-stu-id="4fc89-108">**To import a policy instance, using:**</span></span>  
  
     [<span data-ttu-id="4fc89-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4fc89-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4fc89-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4fc89-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4fc89-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="4fc89-111">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4fc89-112">sono inclusi criteri che possono essere utilizzati per monitorare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4fc89-112">ships with policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4fc89-113">Per impostazione predefinita, questi criteri non vengono installati nel [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], ma possono essere importati dal percorso predefinito C:\Programmi\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span><span class="sxs-lookup"><span data-stu-id="4fc89-113">By default, these policies are not installed on the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], but they can be imported from the default location of C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4fc89-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4fc89-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4fc89-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4fc89-115">Permissions</span></span>  
 <span data-ttu-id="4fc89-116">È necessaria l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="4fc89-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4fc89-117">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4fc89-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-import-a-policy-instance"></a><span data-ttu-id="4fc89-118">Per importare un'istanza dei criteri</span><span class="sxs-lookup"><span data-stu-id="4fc89-118">To import a policy instance</span></span>  
  
1.  <span data-ttu-id="4fc89-119">In **Esplora oggetti**fare clic sul segno più per espandere il server in cui si troverà l'istanza dei criteri appena importata.</span><span class="sxs-lookup"><span data-stu-id="4fc89-119">In **Object Explorer**, click the plus sign to expand the server where the newly-imported policy instance will reside.</span></span>  
  
2.  <span data-ttu-id="4fc89-120">Fare clic sul segno più per espandere la cartella **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="4fc89-120">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="4fc89-121">Fare clic sul segno più per espandere la cartella **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="4fc89-121">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="4fc89-122">Fare clic con il pulsante destro del mouse sulla cartella **Criteri** e selezionare **Importa criteri**.</span><span class="sxs-lookup"><span data-stu-id="4fc89-122">Right-click the **Policies** folder and select **Import Policy**.</span></span>  
  
5.  <span data-ttu-id="4fc89-123">Nella finestra di dialogo **Importa** digitare il percorso e il nome del file oppure usare il pulsante Sfoglia ( **...** ) per trovare il file XML che contiene i criteri, quindi selezionare il file.</span><span class="sxs-lookup"><span data-stu-id="4fc89-123">In the **Import** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the XML file that contains the policy, and then select the file.</span></span> <span data-ttu-id="4fc89-124">Per ulteriori informazioni sulle opzioni disponibili nella finestra di dialogo **Importa** , vedere [Import Policies Dialog Box](import-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="4fc89-124">For more information on the available options in the **Import** dialog box, see [Import Policies Dialog Box](import-policies-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="4fc89-125">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fc89-125">When finished, click **OK**.</span></span>  
  
  
