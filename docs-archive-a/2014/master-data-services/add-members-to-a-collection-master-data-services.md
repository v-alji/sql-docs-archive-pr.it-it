---
title: Aggiungere membri a una raccolta (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], adding members
ms.assetid: 1a7155e6-2d4a-4ed1-a72c-edb37fa1a46b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce2038f3bc90a2f17506b0aadaaf9707fa911896
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637405"
---
# <a name="add-members-to-a-collection-master-data-services"></a><span data-ttu-id="20c94-102">Aggiungere membri a una raccolta (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="20c94-102">Add Members to a Collection (Master Data Services)</span></span>
  <span data-ttu-id="20c94-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]è possibile aggiungere membri foglia e membri consolidati a una raccolta.</span><span class="sxs-lookup"><span data-stu-id="20c94-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can add leaf and consolidated members to a collection.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="20c94-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="20c94-104">Prerequisites</span></span>  
 <span data-ttu-id="20c94-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="20c94-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="20c94-106">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="20c94-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="20c94-107">È necessario disporre almeno dell'autorizzazione **Update** per l'oggetto modello raccolta al quale si vuole aggiungere membri.</span><span class="sxs-lookup"><span data-stu-id="20c94-107">You must have a minimum of **Update** permission to the collection model object that you are adding members to.</span></span>  
  
-   <span data-ttu-id="20c94-108">È necessario che sia presente una raccolta.</span><span class="sxs-lookup"><span data-stu-id="20c94-108">A collection must exist.</span></span> <span data-ttu-id="20c94-109">Per altre informazioni, vedere [Creare una raccolta &#40;Master Data Services&#41;](create-a-collection-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="20c94-109">For more information, see [Create a Collection &#40;Master Data Services&#41;](create-a-collection-master-data-services.md).</span></span>  
  
### <a name="to-add-members-to-a-collection"></a><span data-ttu-id="20c94-110">Per aggiungere membri a una raccolta</span><span class="sxs-lookup"><span data-stu-id="20c94-110">To add members to a collection</span></span>  
  
1.  <span data-ttu-id="20c94-111">Nella home page di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] selezionare un modello nell'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="20c94-111">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="20c94-112">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="20c94-112">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="20c94-113">Fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="20c94-113">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="20c94-114">Dalla barra dei menu scegliere **Raccolte** e fare clic su *nome_entità*.</span><span class="sxs-lookup"><span data-stu-id="20c94-114">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="20c94-115">Nella griglia fare clic sulla riga per la raccolta a cui si desidera aggiungere membri.</span><span class="sxs-lookup"><span data-stu-id="20c94-115">In the grid, click the row for the collection you want to add members to.</span></span>  
  
6.  <span data-ttu-id="20c94-116">Fare clic sulla scheda **Membri raccolta** .</span><span class="sxs-lookup"><span data-stu-id="20c94-116">Click the **Collection Members** tab.</span></span>  
  
7.  <span data-ttu-id="20c94-117">Fare clic su **Modifica membri**.</span><span class="sxs-lookup"><span data-stu-id="20c94-117">Click **Edit Members**.</span></span>  
  
8.  <span data-ttu-id="20c94-118">Per filtrare l'elenco di membri disponibili, effettuare una selezione nell'elenco sulla sinistra.</span><span class="sxs-lookup"><span data-stu-id="20c94-118">To filter the list of available members, select from the list on the left.</span></span>  
  
9. <span data-ttu-id="20c94-119">Fare clic sulla riga contenente il membro che si vuole aggiungere e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="20c94-119">Click the row with the member you want to add and click **Add**.</span></span>  
  
10. <span data-ttu-id="20c94-120">Facoltativamente, ridisporre i membri della raccolta facendo clic su **Su** o **Giù**.</span><span class="sxs-lookup"><span data-stu-id="20c94-120">Optionally, rearrange collection members by clicking **Up** or **Down**.</span></span>  
  
11. <span data-ttu-id="20c94-121">Facoltativamente, impostare i valori di peso facendo clic sul valore nella colonna **Peso** .</span><span class="sxs-lookup"><span data-stu-id="20c94-121">Optionally, set weight values by clicking the value in the **Weight** column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20c94-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20c94-122">See Also</span></span>  
 [<span data-ttu-id="20c94-123">Raccolte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="20c94-123">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
