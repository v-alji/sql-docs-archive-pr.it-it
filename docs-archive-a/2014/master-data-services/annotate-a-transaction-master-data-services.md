---
title: Annotare una transazione (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- annotations [Master Data Services], for transactions
ms.assetid: f5a6b2ca-56de-4e42-9da8-fba0ac3e8d92
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c384f4241d0ddcd78fd8942fe28da8c0b5b1e77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718389"
---
# <a name="annotate-a-transaction-master-data-services"></a><span data-ttu-id="a0bd0-102">Annotare una transazione (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="a0bd0-102">Annotate a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="a0bd0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]annotare una transazione quando si desidera fornire dettagli di supporto sulla transazione per scopi cronologici.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], annotate a transaction when you want to provide supporting details about the transaction for historical purposes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a0bd0-104">Non è possibile eliminare le annotazioni.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-104">You cannot delete annotations.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a0bd0-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a0bd0-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="a0bd0-106">Per annotare le transazioni create, è necessario disporre dell'autorizzazione per accedere all'area funzionale **Visualizzatore** e almeno dell'autorizzazione **Update** per l'oggetto modello che si vuole annotare.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-106">To annotate transactions that you created, you must have permission to access the **Explorer** functional area, and have a minimum of **Update** permission to the model object you want to annotate.</span></span>  
  
-   <span data-ttu-id="a0bd0-107">Per annotare le transazioni per tutti gli utenti, è necessario disporre dell'autorizzazione per l'accesso all'area funzionale **Gestione versioni** ed essere un amministratore di modelli.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-107">To annotate transactions for all users, you must have permission to access the **Version Management** functional area and be a model administrator.</span></span> <span data-ttu-id="a0bd0-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a0bd0-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-annotate-a-transaction-in-explorer"></a><span data-ttu-id="a0bd0-109">Per annotare una transazione in Esplora</span><span class="sxs-lookup"><span data-stu-id="a0bd0-109">To annotate a transaction in Explorer</span></span>  
  
1.  <span data-ttu-id="a0bd0-110">Nella home page di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] selezionare un modello nell'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="a0bd0-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="a0bd0-111">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="a0bd0-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="a0bd0-112">Fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="a0bd0-113">Scegliere **Entità** dalla barra dei menu e quindi fare clic sull'entità contenente il membro con una transazione che si vuole annotare.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-113">From the menu bar, point to **Entities** and click the entity that contains the member with a transaction you want to annotate.</span></span>  
  
5.  <span data-ttu-id="a0bd0-114">Fare clic sulla riga del membro nella griglia.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-114">In the grid, click the row of the member.</span></span>  
  
6.  <span data-ttu-id="a0bd0-115">Fare clic su **Visualizza transazioni**.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-115">Click **View Transactions**.</span></span>  
  
7.  <span data-ttu-id="a0bd0-116">Nella finestra di dialogo **Visualizza transazioni** fare clic sulla transazione che si vuole annotare.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-116">In the **View Transactions** dialog box, click the transaction you want to annotate.</span></span>  
  
8.  <span data-ttu-id="a0bd0-117">Nella casella in corrispondenza della parte inferiore della finestra di dialogo digitare l'annotazione.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-117">In the box at the bottom of the dialog box, type your annotation.</span></span>  
  
9. <span data-ttu-id="a0bd0-118">Fare clic su **Aggiungi annotazione**.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-118">Click **Add Annotation**.</span></span> <span data-ttu-id="a0bd0-119">L'annotazione verrà visualizzata nel riquadro **Annotazioni** .</span><span class="sxs-lookup"><span data-stu-id="a0bd0-119">The annotation is displayed in the **Annotations** pane.</span></span>  
  
### <a name="to-annotate-a-transaction-in-version-management-administrators-only"></a><span data-ttu-id="a0bd0-120">Per annotare una transazione in Gestione versioni (solo amministratori)</span><span class="sxs-lookup"><span data-stu-id="a0bd0-120">To annotate a transaction in Version Management (administrators only)</span></span>  
  
1.  <span data-ttu-id="a0bd0-121">Scegliere [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Gestione versioni **dalla home page di**.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-121">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="a0bd0-122">Sulla barra dei menu fare clic su **Transazioni**.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-122">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="a0bd0-123">Nel riquadro **Transazioni** fare clic sulla riga nella griglia per la transazione che si vuole annotare.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-123">In the **Transactions** pane, click the row in the grid for the transaction you want to annotate.</span></span>  
  
4.  <span data-ttu-id="a0bd0-124">Nella casella **Annotazione** del riquadro **Annotazioni transazioni** digitare l'annotazione.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-124">In the **Transaction Annotations** pane, in the **Annotation** box, type your annotation.</span></span>  
  
5.  <span data-ttu-id="a0bd0-125">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0bd0-125">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0bd0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0bd0-126">See Also</span></span>  
 <span data-ttu-id="a0bd0-127">[Annotazioni &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="a0bd0-127">[Annotations &#40;Master Data Services&#41;](../../2014/master-data-services/annotations-master-data-services.md) </span></span>  
 [<span data-ttu-id="a0bd0-128">Transazioni &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a0bd0-128">Transactions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/transactions-master-data-services.md)  
  
  
