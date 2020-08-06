---
title: Generare automaticamente valori per l'attributo Code (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 19b354ee-2906-4cc7-ba2f-32b4543bddcf
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 6c442f37ffe322985ba55b29b2c4cd539b8a3e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636258"
---
# <a name="automatically-generate-code-attribute-values-master-data-services"></a><span data-ttu-id="c9e55-102">Generare automaticamente valori per l'attributo Code (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c9e55-102">Automatically Generate Code Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="c9e55-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] vengono automaticamente generati valori per l'attributo Code di un'entità quando si vuole che un valore intero venga assegnato automaticamente al valore Code ogni volta che si crea un nuovo membro.</span><span class="sxs-lookup"><span data-stu-id="c9e55-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's Code attribute when you want an integer to be automatically assigned to the Code value each time a new member is created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c9e55-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c9e55-104">Prerequisites</span></span>  
 <span data-ttu-id="c9e55-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c9e55-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="c9e55-106">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="c9e55-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="c9e55-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="c9e55-107">You must be a model administrator.</span></span> <span data-ttu-id="c9e55-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c9e55-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="c9e55-109">Deve essere presente l'entità.</span><span class="sxs-lookup"><span data-stu-id="c9e55-109">The entity must exist.</span></span> <span data-ttu-id="c9e55-110">Per altre informazioni, vedere [Creare un'entità &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c9e55-110">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-code-values"></a><span data-ttu-id="c9e55-111">Per generare automaticamente valori Code</span><span class="sxs-lookup"><span data-stu-id="c9e55-111">To automatically generate Code values</span></span>  
  
1.  <span data-ttu-id="c9e55-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="c9e55-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="c9e55-113">Nella pagina **Esplora modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **entità**.</span><span class="sxs-lookup"><span data-stu-id="c9e55-113">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="c9e55-114">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="c9e55-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="c9e55-115">Selezionare la riga per l'entità per cui si desidera generare codici.</span><span class="sxs-lookup"><span data-stu-id="c9e55-115">Select the row for the entity that you want to generate codes for.</span></span>  
  
5.  <span data-ttu-id="c9e55-116">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="c9e55-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="c9e55-117">Selezionare la casella di controllo **Crea valori Code automaticamente** .</span><span class="sxs-lookup"><span data-stu-id="c9e55-117">Select the **Create Code values automatically** check box.</span></span>  
  
7.  <span data-ttu-id="c9e55-118">Nella casella **Inizia con** digitare un numero da cui iniziare l'incremento.</span><span class="sxs-lookup"><span data-stu-id="c9e55-118">In the **Start with** box, type a number to begin incrementing.</span></span> <span data-ttu-id="c9e55-119">Se i membri esistono già, il valore Code verrà impostato in base al valore esistente più elevato.</span><span class="sxs-lookup"><span data-stu-id="c9e55-119">If members already exist, the Code will be set based on the highest existing value.</span></span> <span data-ttu-id="c9e55-120">Ad esempio, se il valore Code esistente più elevato è 299, il valore Code del membro successivo sarà impostato su 300.</span><span class="sxs-lookup"><span data-stu-id="c9e55-120">For example, if the highest existing Code value is 299, the next member's Code value will be set to 300.</span></span>  
  
8.  <span data-ttu-id="c9e55-121">Fare clic su **Salva entità**.</span><span class="sxs-lookup"><span data-stu-id="c9e55-121">Click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e55-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9e55-122">See Also</span></span>  
 <span data-ttu-id="c9e55-123">[Creazione automatica del codice &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="c9e55-123">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 [<span data-ttu-id="c9e55-124">Generare automaticamente valori di attributi diversi da Code &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9e55-124">Automatically Generate Attribute Values Other Than Code &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/automatically-generate-attribute-values-other-than-code-master-data-services.md)  
  
  
