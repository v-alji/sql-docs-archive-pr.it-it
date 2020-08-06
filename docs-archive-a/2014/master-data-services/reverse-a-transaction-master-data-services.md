---
title: Invertire una transazione (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Master Data Services], reversing
ms.assetid: 6f7c3f07-0f64-4283-8c9c-93facd00a046
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fb5b1b0932b65b1d6f8fe7b1bc842836e21aaca6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714451"
---
# <a name="reverse-a-transaction-master-data-services"></a><span data-ttu-id="489a7-102">Invertire una transazione (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="489a7-102">Reverse a Transaction (Master Data Services)</span></span>
  <span data-ttu-id="489a7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]gli amministratori possono invertire una transazione quando è necessario annullare un'azione.</span><span class="sxs-lookup"><span data-stu-id="489a7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], administrators can reverse a transaction when an action needs to be undone.</span></span> <span data-ttu-id="489a7-104">Esempi di transazioni sono modifiche al valore dell'attributo, spostamenti di gerarchie o eliminazioni di membri.</span><span class="sxs-lookup"><span data-stu-id="489a7-104">Examples of transactions are attribute value changes, hierarchy moves, or member deletions.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="489a7-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="489a7-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="489a7-106">È necessario avere l'autorizzazione per accedere all'area funzionale **Gestione versioni** .</span><span class="sxs-lookup"><span data-stu-id="489a7-106">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="489a7-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="489a7-107">You must be a model administrator.</span></span> <span data-ttu-id="489a7-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="489a7-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-reverse-a-transaction"></a><span data-ttu-id="489a7-109">Per invertire una transazione</span><span class="sxs-lookup"><span data-stu-id="489a7-109">To reverse a transaction</span></span>  
  
1.  <span data-ttu-id="489a7-110">Scegliere [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Gestione versioni **dalla home page di**.</span><span class="sxs-lookup"><span data-stu-id="489a7-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="489a7-111">Sulla barra dei menu fare clic su **Transazioni**.</span><span class="sxs-lookup"><span data-stu-id="489a7-111">On the menu bar, click **Transactions**.</span></span>  
  
3.  <span data-ttu-id="489a7-112">Nella pagina **Transazioni** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="489a7-112">On the **Transactions** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="489a7-113">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="489a7-113">From the **Version** list, select a version.</span></span>  
  
5.  <span data-ttu-id="489a7-114">Fare clic sulla riga nella griglia per la transazione che si desidera invertire.</span><span class="sxs-lookup"><span data-stu-id="489a7-114">Click the row in the grid for the transaction you want to reverse.</span></span>  
  
6.  <span data-ttu-id="489a7-115">Fare clic su **Inverti transazione selezionata**.</span><span class="sxs-lookup"><span data-stu-id="489a7-115">Click **Reverse Transaction**.</span></span>  
  
7.  <span data-ttu-id="489a7-116">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="489a7-116">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="489a7-117">Un'altra transazione viene aggiunta alla griglia per registrare la transazione invertita.</span><span class="sxs-lookup"><span data-stu-id="489a7-117">Another transaction is added to the grid to record the reversed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="489a7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="489a7-118">See Also</span></span>  
 <span data-ttu-id="489a7-119">[Transazioni &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="489a7-119">[Transactions &#40;Master Data Services&#41;](../../2014/master-data-services/transactions-master-data-services.md) </span></span>  
 [<span data-ttu-id="489a7-120">Riattivare un membro o una raccolta &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="489a7-120">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)  
  
  
