---
title: Convalidare membri specifici rispetto a regole business (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- applying business rules [Master Data Services]
- business rules [Master Data Services], applying to select members
ms.assetid: 2288ef43-5392-47ea-b651-ec25e5692a14
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 18af83146679eb77638dfbc98b31f198dc8e07b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627863"
---
# <a name="validate-specific-members-against-business-rules-master-data-services"></a><span data-ttu-id="41f33-102">Convalidare membri specifici rispetto a regole business (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="41f33-102">Validate Specific Members against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="41f33-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]è opportuno applicare selettivamente regole business quando si desidera aggiornare o convalidare subset di membri rispetto a regole business.</span><span class="sxs-lookup"><span data-stu-id="41f33-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], apply business rules selectively when you want to update or validate subsets of members against business rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41f33-104">Per applicare le regole di business a tutti i membri in una versione di un modello, vedere [Convalidare una versione usando le regole di business &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="41f33-104">If you want to apply business rules to all members in a version of a model, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="41f33-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="41f33-105">Prerequisites</span></span>  
 <span data-ttu-id="41f33-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="41f33-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="41f33-107">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="41f33-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="41f33-108">È necessario disporre almeno dell'autorizzazione **Update** per l'oggetto modello al quale vengono applicate le regole di business.</span><span class="sxs-lookup"><span data-stu-id="41f33-108">You must have a minimum of **Update** permission to the model object you are applying business rules to.</span></span>  
  
### <a name="to-apply-business-rules-selectively"></a><span data-ttu-id="41f33-109">Per applicare regole business selettivamente</span><span class="sxs-lookup"><span data-stu-id="41f33-109">To apply business rules selectively</span></span>  
  
1.  <span data-ttu-id="41f33-110">Nella home page di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] selezionare un modello nell'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="41f33-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="41f33-111">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="41f33-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="41f33-112">Fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="41f33-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="41f33-113">Scegliere **Entità** dalla barra dei menu, quindi fare clic sul nome dell'entità contenente i membri a cui applicare le regole.</span><span class="sxs-lookup"><span data-stu-id="41f33-113">From the menu bar, point to **Entities** and click the name of the entity that contains members you want to apply rules to.</span></span>  
  
5.  <span data-ttu-id="41f33-114">Fare clic su **Applica regole business**.</span><span class="sxs-lookup"><span data-stu-id="41f33-114">Click **Apply business rules**.</span></span> <span data-ttu-id="41f33-115">Le regole business sono applicate solo ai membri visualizzati nella griglia.</span><span class="sxs-lookup"><span data-stu-id="41f33-115">Business rules are applied only to the members displayed in the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41f33-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41f33-116">See Also</span></span>  
 <span data-ttu-id="41f33-117">[Convalidare una versione rispetto alle regole business &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="41f33-117">[Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="41f33-118">Regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="41f33-118">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
