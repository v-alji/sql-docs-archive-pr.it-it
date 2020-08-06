---
title: Eliminare un attributo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], deleting
- deleting attributes [Master Data Services]
ms.assetid: ec3e66f7-0e35-43d7-a80d-64899948ebfe
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 96db56dac9356b1131e722fc7f6b779c93305bb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712099"
---
# <a name="delete-an-attribute-master-data-services"></a><span data-ttu-id="9db79-102">Eliminare un attributo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9db79-102">Delete an Attribute (Master Data Services)</span></span>
  <span data-ttu-id="9db79-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]è possibile eliminare un attributo quando si vuole eliminarlo in modo permanente insieme a tutti i valori associati.</span><span class="sxs-lookup"><span data-stu-id="9db79-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute when you want to permanently delete the attribute and all associated attribute values.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9db79-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9db79-104">Prerequisites</span></span>  
 <span data-ttu-id="9db79-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="9db79-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9db79-106">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="9db79-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="9db79-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="9db79-107">You must be a model administrator.</span></span> <span data-ttu-id="9db79-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="9db79-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute"></a><span data-ttu-id="9db79-109">Per eliminare un attributo</span><span class="sxs-lookup"><span data-stu-id="9db79-109">To delete an attribute</span></span>  
  
1.  <span data-ttu-id="9db79-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="9db79-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="9db79-111">Nella pagina **Vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **Entità**.</span><span class="sxs-lookup"><span data-stu-id="9db79-111">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="9db79-112">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="9db79-112">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="9db79-113">Selezionare la riga relativa all'entità che contiene l'attributo da eliminare.</span><span class="sxs-lookup"><span data-stu-id="9db79-113">Select the row for the entity that contains the attribute you want to delete.</span></span>  
  
5.  <span data-ttu-id="9db79-114">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="9db79-114">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="9db79-115">Nella pagina **Modifica entità** fare clic sull'attributo che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="9db79-115">On the **Edit Entity** page, click the attribute you want to delete.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9db79-116">Gli attributi Nome e Codice non possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="9db79-116">You cannot delete the Name or Code attributes.</span></span>  
  
7.  <span data-ttu-id="9db79-117">Fare clic su **Elimina attributo selezionato**.</span><span class="sxs-lookup"><span data-stu-id="9db79-117">Click **Delete selected attribute**.</span></span>  
  
8.  <span data-ttu-id="9db79-118">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9db79-118">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="9db79-119">Nell'ulteriore finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9db79-119">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9db79-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9db79-120">See Also</span></span>  
 <span data-ttu-id="9db79-121">[Attributi &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9db79-121">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="9db79-122">[Attributi basati su dominio &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9db79-122">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="9db79-123">[Creare un attributo di testo &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="9db79-123">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="9db79-124">Creare un attributo basato su dominio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9db79-124">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
