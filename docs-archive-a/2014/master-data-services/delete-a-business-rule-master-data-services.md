---
title: Eliminare una regola di business (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting business rules [Master Data Services]
- business rules [Master Data Services], deleting
ms.assetid: b97aa4f9-569f-451d-ad62-65b81f980299
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8e6db486f71634cf025c57eabbedeeb9efdbc437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712095"
---
# <a name="delete-a-business-rule-master-data-services"></a><span data-ttu-id="25877-102">Eliminare una regola business (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="25877-102">Delete a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="25877-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eliminare una regola di business quando non è più necessaria.</span><span class="sxs-lookup"><span data-stu-id="25877-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a business rule when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25877-104">È possibile impedire la convalida dei dati rispetto a una regola business escludendoli, anziché eliminandoli.</span><span class="sxs-lookup"><span data-stu-id="25877-104">You can prevent data from being validated against a business rule by excluding it, rather than deleting it.</span></span> <span data-ttu-id="25877-105">Per altre informazioni, vedere [Escludere una regola business &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="25877-105">For more information, see [Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="25877-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="25877-106">Prerequisites</span></span>  
 <span data-ttu-id="25877-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="25877-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="25877-108">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="25877-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="25877-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="25877-109">You must be a model administrator.</span></span> <span data-ttu-id="25877-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="25877-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-business-rule"></a><span data-ttu-id="25877-111">Per eliminare una regola business</span><span class="sxs-lookup"><span data-stu-id="25877-111">To delete a business rule</span></span>  
  
1.  <span data-ttu-id="25877-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="25877-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="25877-113">Dalla barra dei menu scegliere **Gestisci** e fare clic su **Regole business**.</span><span class="sxs-lookup"><span data-stu-id="25877-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="25877-114">Nella pagina **Manutenzione regola business** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="25877-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="25877-115">Dall'elenco **Entità** selezionare un'entità.</span><span class="sxs-lookup"><span data-stu-id="25877-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="25877-116">Dall'elenco **Tipo di membro** selezionare un tipo di membro a cui applicare la regola di business.</span><span class="sxs-lookup"><span data-stu-id="25877-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="25877-117">Dall'elenco **Attributo** selezionare un attributo o lasciare inalterata l'impostazione predefinita **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="25877-117">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="25877-118">Nella griglia fare clic sulla riga relativa alla regola business da eliminare.</span><span class="sxs-lookup"><span data-stu-id="25877-118">In the grid, click the row for the business rule you want to delete.</span></span>  
  
8.  <span data-ttu-id="25877-119">Fare clic su **Elimina regola business selezionata**.</span><span class="sxs-lookup"><span data-stu-id="25877-119">Click **Delete selected business rule**.</span></span>  
  
9. <span data-ttu-id="25877-120">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="25877-120">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="25877-121">Il valore nella colonna **stato** è **eliminazione in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="25877-121">The value in the **Status** column is **Deletion pending**.</span></span>  
  
10. <span data-ttu-id="25877-122">Fare clic su **Pubblica regole business**.</span><span class="sxs-lookup"><span data-stu-id="25877-122">Click **Publish business rules**.</span></span>  
  
11. <span data-ttu-id="25877-123">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="25877-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25877-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25877-124">See Also</span></span>  
 <span data-ttu-id="25877-125">[Escludere una regola business &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="25877-125">[Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="25877-126">[Creare e pubblicare una regola business &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="25877-126">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="25877-127">Regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="25877-127">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
