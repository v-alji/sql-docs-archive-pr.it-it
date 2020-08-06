---
title: Inizializzare azioni basate su modifiche dei valori di attributo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], tracking attribute changes
- change tracking groups [Master Data Services], initiating actions
ms.assetid: 5e4402ce-31db-4774-a2a1-552335f87693
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 50931b9f9c4bd5d08596d485ba695143b9c6594e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713232"
---
# <a name="initiate-actions-based-on-attribute-value-changes-master-data-services"></a><span data-ttu-id="516d3-102">Inizializzare azioni basate su modifiche dei valori di attributo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="516d3-102">Initiate Actions Based on Attribute Value Changes (Master Data Services)</span></span>
  <span data-ttu-id="516d3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare una regola di business per inizializzare azioni in base alle modifiche dei valori di attributo.</span><span class="sxs-lookup"><span data-stu-id="516d3-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a business rule to initiate actions based on changes to attribute values.</span></span> <span data-ttu-id="516d3-104">Ad esempio, quando un valore di attributo specifico viene modificato, è necessario modificare un valore, inviare una notifica o avviare un flusso di lavoro esterno.</span><span class="sxs-lookup"><span data-stu-id="516d3-104">For example, when a specific attribute value changes, you may want to change a value, send a notification, or start an external workflow.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="516d3-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="516d3-105">Prerequisites</span></span>  
 <span data-ttu-id="516d3-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="516d3-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="516d3-107">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="516d3-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="516d3-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="516d3-108">You must be a model administrator.</span></span> <span data-ttu-id="516d3-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="516d3-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="516d3-110">Gli attributi devono essere in un gruppo rilevamento modifiche.</span><span class="sxs-lookup"><span data-stu-id="516d3-110">Your attributes must be in a change tracking group.</span></span> <span data-ttu-id="516d3-111">Per altre informazioni, vedere [Aggiungere attributi ad un gruppo rilevamento modifiche &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) .</span><span class="sxs-lookup"><span data-stu-id="516d3-111">See [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) for more information.</span></span>  
  
### <a name="to-create-a-business-rule-to-initiate-actions-based-on-attribute-value-changes"></a><span data-ttu-id="516d3-112">Per creare una regola business per inizializzare azioni basate su modifiche dei valori di attributo</span><span class="sxs-lookup"><span data-stu-id="516d3-112">To create a business rule to initiate actions based on attribute value changes</span></span>  
  
1.  <span data-ttu-id="516d3-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="516d3-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="516d3-114">Dalla barra dei menu scegliere **Gestisci** e fare clic su **Regole business**.</span><span class="sxs-lookup"><span data-stu-id="516d3-114">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="516d3-115">Nella pagina **Manutenzione regola business** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="516d3-115">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="516d3-116">Dall'elenco **Entità** selezionare un'entità.</span><span class="sxs-lookup"><span data-stu-id="516d3-116">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="516d3-117">Dall'elenco **Tipo di membro** selezionare un tipo di membro a cui applicare la regola di business.</span><span class="sxs-lookup"><span data-stu-id="516d3-117">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="516d3-118">Dall'elenco **Attributo** selezionare un attributo o lasciare inalterata l'impostazione predefinita **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="516d3-118">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="516d3-119">Fare clic su **Aggiungi regola di business**.</span><span class="sxs-lookup"><span data-stu-id="516d3-119">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="516d3-120">Fare clic su **Modifica regola business selezionata**.</span><span class="sxs-lookup"><span data-stu-id="516d3-120">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="516d3-121">Nel riquadro **Componenti** espandere il nodo **Condizioni** .</span><span class="sxs-lookup"><span data-stu-id="516d3-121">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
10. <span data-ttu-id="516d3-122">Nel nodo **Confronto valori** trascinare **è stato modificato** nell'etichetta **Condizioni** del riquadro **IF** .</span><span class="sxs-lookup"><span data-stu-id="516d3-122">Under the **Value comparison** node, drag **has changed** to the **IF** pane's **Conditions** label.</span></span>  
  
11. <span data-ttu-id="516d3-123">Nel riquadro **attributi** fare clic su un attributo e trascinarlo sull'etichetta **Seleziona attributo** del riquadro **Modifica condizione** .</span><span class="sxs-lookup"><span data-stu-id="516d3-123">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span> <span data-ttu-id="516d3-124">Tale attributo non ha alcun effetto sulla regola, selezionare quindi qualsiasi attributo disponibile.</span><span class="sxs-lookup"><span data-stu-id="516d3-124">This attribute has no effect on the rule, so select any available attribute.</span></span>  
  
12. <span data-ttu-id="516d3-125">Nel riquadro **Modifica condizione** nella casella **Gruppo rilevamento modifiche** digitare il numero del gruppo di rilevamento delle modifiche assegnato come parte dei prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="516d3-125">In the **Edit Condition** pane, in the **Change tracking group** box, type the number of the change tracking group that you assigned as part of the prerequisites.</span></span>  
  
13. <span data-ttu-id="516d3-126">Nel riquadro **Modifica condizione** fare clic su **Salva elemento**.</span><span class="sxs-lookup"><span data-stu-id="516d3-126">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="516d3-127">Nel riquadro **Componenti** espandere il nodo **Azioni** .</span><span class="sxs-lookup"><span data-stu-id="516d3-127">In the **Components** pane, expand the **Actions** node.</span></span>  
  
15. <span data-ttu-id="516d3-128">Fare clic su un'azione e trascinarla nell'etichetta **Azione** del riquadro **THEN** .</span><span class="sxs-lookup"><span data-stu-id="516d3-128">Click an action and drag it to the **THEN** pane's **Action** label.</span></span>  
  
16. <span data-ttu-id="516d3-129">Nel riquadro **Attributi** fare clic su un attributo e trascinarlo nell'etichetta **Seleziona attributo** del riquadro **Modifica azione** .</span><span class="sxs-lookup"><span data-stu-id="516d3-129">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
17. <span data-ttu-id="516d3-130">Nel riquadro **Modifica azione** completare tutti i campi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="516d3-130">In the **Edit Action** pane, complete any required fields.</span></span>  
  
18. <span data-ttu-id="516d3-131">Nel riquadro **Modifica azione** fare clic su **Salva elemento**.</span><span class="sxs-lookup"><span data-stu-id="516d3-131">In the **Edit Action** pane, click **Save item**.</span></span>  
  
19. <span data-ttu-id="516d3-132">Fare clic su **Indietro**.</span><span class="sxs-lookup"><span data-stu-id="516d3-132">Click **Back**.</span></span>  
  
20. <span data-ttu-id="516d3-133">Facoltativamente, nella pagina **Manutenzione regola business** per la riga che contiene la regola business fare doppio clic su una cella nella colonna **Nome**, **Descrizione**o **Notifica** per aggiornare il valore.</span><span class="sxs-lookup"><span data-stu-id="516d3-133">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="516d3-134">Le notifiche vengono inviate soltanto per le regole che prevedono un'azione di convalida.</span><span class="sxs-lookup"><span data-stu-id="516d3-134">Notifications are sent only for rules that include a validation action.</span></span>  
  
21. <span data-ttu-id="516d3-135">Fare clic su **Pubblica regole business**.</span><span class="sxs-lookup"><span data-stu-id="516d3-135">Click **Publish business rules**.</span></span>  
  
22. <span data-ttu-id="516d3-136">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="516d3-136">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="516d3-137">Lo stato della regola viene modificato in **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="516d3-137">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="516d3-138">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="516d3-138">Next Steps</span></span>  
  
-   <span data-ttu-id="516d3-139">Applicare regole business ai dati eseguendo una delle procedure riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="516d3-139">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="516d3-140">Convalidare membri specifici rispetto a regole business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="516d3-140">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="516d3-141">Convalidare una versione usando le regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="516d3-141">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="516d3-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="516d3-142">See Also</span></span>  
 <span data-ttu-id="516d3-143">[Aggiungere attributi a un gruppo di Rilevamento modifiche &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="516d3-143">[Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md) </span></span>  
 [<span data-ttu-id="516d3-144">Regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="516d3-144">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
