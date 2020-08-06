---
title: Generare automaticamente valori di attributi diversi da Code (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: b82f6f81-6e9c-4918-9ea9-4ab5f5d11b15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8db6c89bdce2a11a5a54ed3a763a7bc41bd7f1be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636259"
---
# <a name="automatically-generate-attribute-values-other-than-code-master-data-services"></a><span data-ttu-id="defb4-102">Generare automaticamente valori per attributi diversi da Code (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="defb4-102">Automatically Generate Attribute Values Other Than Code (Master Data Services)</span></span>
  <span data-ttu-id="defb4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] vengono automaticamente generati valori per l'attributo di un'entità quando si vuole che un valore intero venga assegnato automaticamente come valore ogni volta che viene applicata una regola di business.</span><span class="sxs-lookup"><span data-stu-id="defb4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], automatically generate values for an entity's attribute values when you want an integer to be automatically assigned as the value each time business rules are applied.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="defb4-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="defb4-104">Prerequisites</span></span>  
 <span data-ttu-id="defb4-105">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="defb4-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="defb4-106">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="defb4-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="defb4-107">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="defb4-107">You must be a model administrator.</span></span> <span data-ttu-id="defb4-108">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="defb4-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="defb4-109">Un attributo numerico deve esistere.</span><span class="sxs-lookup"><span data-stu-id="defb4-109">A numeric attribute must exist.</span></span> <span data-ttu-id="defb4-110">Per altre informazioni, vedere [Creare un attributo numerico &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="defb4-110">For more information, see [Create a Numeric Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md).</span></span>  
  
### <a name="to-automatically-generate-an-attribute-value"></a><span data-ttu-id="defb4-111">Per generare automaticamente un valore di attributo</span><span class="sxs-lookup"><span data-stu-id="defb4-111">To automatically generate an attribute value</span></span>  
  
1.  <span data-ttu-id="defb4-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="defb4-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="defb4-113">Dalla barra dei menu scegliere **Gestisci** e fare clic su **Regole business**.</span><span class="sxs-lookup"><span data-stu-id="defb4-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="defb4-114">Nella pagina **Manutenzione regola business** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="defb4-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="defb4-115">Dall'elenco **Entità** selezionare un'entità.</span><span class="sxs-lookup"><span data-stu-id="defb4-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="defb4-116">Dall'elenco **Tipo di membro** selezionare un tipo di membro a cui applicare la regola di business.</span><span class="sxs-lookup"><span data-stu-id="defb4-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="defb4-117">Dall'elenco **Attributo** lasciare inalterata l'impostazione predefinita **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="defb4-117">From the **Attribute** list, leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="defb4-118">Fare clic su **Aggiungi regola di business**.</span><span class="sxs-lookup"><span data-stu-id="defb4-118">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="defb4-119">Fare clic su **Modifica regola business selezionata**.</span><span class="sxs-lookup"><span data-stu-id="defb4-119">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="defb4-120">Nel riquadro **Componenti** espandere il nodo **Azioni** .</span><span class="sxs-lookup"><span data-stu-id="defb4-120">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="defb4-121">Nel nodo Valore predefinito fare clic su **assume un valore generato** e trascinarlo sull'etichetta **Azioni** del riquadro **THEN**.</span><span class="sxs-lookup"><span data-stu-id="defb4-121">In the Default Value node, click **defaults to a generated value** and drag it to the **THEN** pane's **Actions** label.</span></span>  
  
11. <span data-ttu-id="defb4-122">Nel riquadro **Attributi** fare clic sull'attributo con il valore che si vuole generare e trascinarlo sull'etichetta **Seleziona attributo** del riquadro **Modifica azione** .</span><span class="sxs-lookup"><span data-stu-id="defb4-122">In the **Attributes** pane, click the attribute with the value you want to generated and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="defb4-123">Digitare un valore nelle caselle **Inizia da** e **Incremento di** .</span><span class="sxs-lookup"><span data-stu-id="defb4-123">Type a value in the **Start with** and **Increment by** boxes.</span></span> <span data-ttu-id="defb4-124">Se i membri esistono già, il valore verrà impostato in base al valore esistente più elevato.</span><span class="sxs-lookup"><span data-stu-id="defb4-124">If members already exist, the value will be set based on the highest existing value.</span></span> <span data-ttu-id="defb4-125">Ad esempio, se il valore esistente più elevato è 299 e si imposta **Incremento di** su **1**, il valore del membro successivo sarà impostato su 300.</span><span class="sxs-lookup"><span data-stu-id="defb4-125">For example, if the highest existing value is 299 and you set **Increment by** to **1**, the next member's value will be set to 300.</span></span>  
  
13. <span data-ttu-id="defb4-126">Nel riquadro **Modifica azione** fare clic su **Salva elemento**.</span><span class="sxs-lookup"><span data-stu-id="defb4-126">In the **Edit Action** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="defb4-127">Fare clic su **Indietro**.</span><span class="sxs-lookup"><span data-stu-id="defb4-127">Click **Back**.</span></span>  
  
15. <span data-ttu-id="defb4-128">Facoltativamente, nella pagina **Manutenzione regola business** per la riga che contiene la regola business fare doppio clic su una cella nella colonna **Nome**, **Descrizione**o **Notifica** per aggiornare il valore.</span><span class="sxs-lookup"><span data-stu-id="defb4-128">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
16. <span data-ttu-id="defb4-129">Fare clic su **Pubblica regole business**.</span><span class="sxs-lookup"><span data-stu-id="defb4-129">Click **Publish business rules**.</span></span>  
  
17. <span data-ttu-id="defb4-130">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="defb4-130">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="defb4-131">Lo stato della regola viene modificato in **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="defb4-131">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="defb4-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="defb4-132">Next Steps</span></span>  
  
-   [<span data-ttu-id="defb4-133">Convalidare membri specifici rispetto a regole business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="defb4-133">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="defb4-134">Convalidare una versione usando le regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="defb4-134">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="defb4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="defb4-135">See Also</span></span>  
 <span data-ttu-id="defb4-136">[Creazione automatica del codice &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="defb4-136">[Automatic Code Creation &#40;Master Data Services&#41;](../../2014/master-data-services/automatic-code-creation-master-data-services.md) </span></span>  
 <span data-ttu-id="defb4-137">[Regole business &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="defb4-137">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="defb4-138">Convalida &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="defb4-138">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
  
