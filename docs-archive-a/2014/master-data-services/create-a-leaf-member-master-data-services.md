---
title: Creare un membro foglia (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services], creating
- creating leaf members [Master Data Services]
- members [Master Data Services], creating leaf members
ms.assetid: 0499d3b3-d508-4d43-a740-19cf53ade9f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe0245dd30019e1cb9112754bd8b8eeafed93aa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623384"
---
# <a name="create-a-leaf-member-master-data-services"></a><span data-ttu-id="c8607-102">Creare un membro foglia (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c8607-102">Create a Leaf Member (Master Data Services)</span></span>
  <span data-ttu-id="c8607-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] creare un membro foglia quando si desidera aggiungere dati master al sistema e non si utilizzano tabelle di staging o [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] per importare dati.</span><span class="sxs-lookup"><span data-stu-id="c8607-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a leaf member when you want to add master data to your system and are not using staging tables or the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] to import data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c8607-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c8607-104">Prerequisites</span></span>  
 <span data-ttu-id="c8607-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c8607-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c8607-106">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="c8607-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="c8607-107">È necessario disporre almeno dell'autorizzazione **aggiornamento** per l'oggetto modello foglia per l'entità a cui si desidera aggiungere un membro.</span><span class="sxs-lookup"><span data-stu-id="c8607-107">You must have a minimum of **Update** permission to the leaf model object for the entity you are adding a member to.</span></span>  
  
### <a name="to-create-a-leaf-member"></a><span data-ttu-id="c8607-108">Per creare un membro foglia</span><span class="sxs-lookup"><span data-stu-id="c8607-108">To create a leaf member</span></span>  
  
1.  <span data-ttu-id="c8607-109">Nella home page di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] selezionare un modello nell'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="c8607-109">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="c8607-110">Se si è un utente, selezionare una versione aperta nell'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="c8607-110">If you are a user, select an open version from the **Version** list.</span></span> <span data-ttu-id="c8607-111">Se si è un amministratore, selezionare una versione con stato aperto o bloccato nell'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="c8607-111">If you are an administrator, select a version with open or locked status from the **Version** list.</span></span>  
  
3.  <span data-ttu-id="c8607-112">Fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="c8607-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="c8607-113">Dalla barra dei menu scegliere **Entità** , quindi fare clic sul nome dell'entità alla quale si desidera aggiungere un membro.</span><span class="sxs-lookup"><span data-stu-id="c8607-113">From the menu bar, point to **Entities** and click the name of the entity you want to add a member to.</span></span>  
  
5.  <span data-ttu-id="c8607-114">Fare clic su **Aggiungi membro**.</span><span class="sxs-lookup"><span data-stu-id="c8607-114">Click **Add member**.</span></span>  
  
6.  <span data-ttu-id="c8607-115">Nel riquadro **Dettagli** completare i campi.</span><span class="sxs-lookup"><span data-stu-id="c8607-115">In the **Details** pane, complete the fields.</span></span>  
  
7.  <span data-ttu-id="c8607-116">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c8607-116">Optional.</span></span> <span data-ttu-id="c8607-117">Nella casella **Annotazioni** , digitare un commento indicando il perché è stato aggiunto il membro.</span><span class="sxs-lookup"><span data-stu-id="c8607-117">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="c8607-118">Tutti gli utenti che dispongono di accesso al membro possono visualizzare l'annotazione.</span><span class="sxs-lookup"><span data-stu-id="c8607-118">All users who have access to the member can view the annotation.</span></span>  
  
8.  <span data-ttu-id="c8607-119">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8607-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8607-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8607-120">See Also</span></span>  
 <span data-ttu-id="c8607-121">[Caricare o aggiornare membri in Master Data Services tramite il processo di gestione temporanea](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c8607-121">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="c8607-122">[Creazione di un membro consolidato &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c8607-122">[Create a Consolidated Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span></span>  
 [<span data-ttu-id="c8607-123">Membri &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c8607-123">Members &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/members-master-data-services.md)  
  
  
