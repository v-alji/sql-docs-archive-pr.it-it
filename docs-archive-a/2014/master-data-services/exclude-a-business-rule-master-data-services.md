---
title: Escludere una regola di business (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], excluding
ms.assetid: bdbc9df0-23f7-40b9-8aba-4445c1482580
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 317964dcbc7b2cbe212c415b3aa4f9f1a0743301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715519"
---
# <a name="exclude-a-business-rule-master-data-services"></a><span data-ttu-id="631ce-102">Escludere una regola business (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="631ce-102">Exclude a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="631ce-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]escludere una regola di business quando non si vuole eliminarla in modo permanente, ma non si vuole convalidare i dati rispetto a essa.</span><span class="sxs-lookup"><span data-stu-id="631ce-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclude a business rule when you do not want to delete the rule permanently, but you do not want to validate data against it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="631ce-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="631ce-104">Prerequisites</span></span>  
 <span data-ttu-id="631ce-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="631ce-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="631ce-106">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="631ce-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="631ce-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="631ce-107">You must be a model administrator.</span></span> <span data-ttu-id="631ce-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="631ce-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-exclude-a-business-rule"></a><span data-ttu-id="631ce-109">Per escludere una regola business</span><span class="sxs-lookup"><span data-stu-id="631ce-109">To exclude a business rule</span></span>  
  
1.  <span data-ttu-id="631ce-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="631ce-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="631ce-111">Dalla barra dei menu scegliere **Gestisci** e fare clic su **Regole business**.</span><span class="sxs-lookup"><span data-stu-id="631ce-111">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="631ce-112">Nella pagina **Manutenzione regola business** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="631ce-112">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="631ce-113">Dall'elenco **Entità** selezionare un'entità.</span><span class="sxs-lookup"><span data-stu-id="631ce-113">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="631ce-114">Dall'elenco **tipo di membro** selezionare un tipo di membro.</span><span class="sxs-lookup"><span data-stu-id="631ce-114">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="631ce-115">Dall'elenco **Attributo** selezionare un attributo o lasciare inalterata l'impostazione predefinita **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="631ce-115">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="631ce-116">Nella griglia, nella riga relativa alla regola business, selezionare la casella di controllo nella colonna **Escludi** .</span><span class="sxs-lookup"><span data-stu-id="631ce-116">In the grid, in the row for the business rule, select the check box in the **Exclude** column.</span></span> <span data-ttu-id="631ce-117">Il valore nella colonna **stato** è **esclusione in sospeso**.</span><span class="sxs-lookup"><span data-stu-id="631ce-117">The value in the **Status** column is **Exclusion pending**.</span></span>  
  
8.  <span data-ttu-id="631ce-118">Fare clic su **Pubblica regole business**.</span><span class="sxs-lookup"><span data-stu-id="631ce-118">Click **Publish business rules**.</span></span>  
  
9. <span data-ttu-id="631ce-119">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="631ce-119">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="631ce-120">Il valore nella colonna **stato** è **escluso**.</span><span class="sxs-lookup"><span data-stu-id="631ce-120">The value in the **Status** column is **Excluded**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="631ce-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="631ce-121">See Also</span></span>  
 <span data-ttu-id="631ce-122">[Eliminare una regola business &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="631ce-122">[Delete a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="631ce-123">[Creare e pubblicare una regola business &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="631ce-123">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="631ce-124">Regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="631ce-124">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
