---
title: Creare e pubblicare una regola business (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], creating
- creating business rules [Master Data Services]
ms.assetid: 6961d636-4d69-468e-81f7-8d0be6a4a039
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 4dfca5613a1f328e02b3fd2c7337885a23889207
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636251"
---
# <a name="create-and-publish-a-business-rule-master-data-services"></a><span data-ttu-id="8daa4-102">Creare e pubblicare una regola business (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8daa4-102">Create and Publish a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="8daa4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare una regola business per garantire l'accuratezza dei dati master.</span><span class="sxs-lookup"><span data-stu-id="8daa4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a business rule to ensure the accuracy of your master data.</span></span> <span data-ttu-id="8daa4-104">Dopo avere creato una regola, è necessario pubblicarla prima di poterla applicare ai dati.</span><span class="sxs-lookup"><span data-stu-id="8daa4-104">After you create a rule, you must publish it before you can apply it to data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8daa4-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8daa4-105">Prerequisites</span></span>  
 <span data-ttu-id="8daa4-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="8daa4-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8daa4-107">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="8daa4-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="8daa4-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="8daa4-108">You must be a model administrator.</span></span> <span data-ttu-id="8daa4-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8daa4-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-and-publish-a-business-rule"></a><span data-ttu-id="8daa4-110">Per creare e pubblicare una regola business</span><span class="sxs-lookup"><span data-stu-id="8daa4-110">To create and publish a business rule</span></span>  
  
1.  <span data-ttu-id="8daa4-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="8daa4-112">Dalla barra dei menu scegliere **Gestisci** e fare clic su **Regole business**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="8daa4-113">Nella pagina **Manutenzione regola business** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="8daa4-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="8daa4-114">Dall'elenco **Entità** selezionare un'entità.</span><span class="sxs-lookup"><span data-stu-id="8daa4-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="8daa4-115">Dall'elenco **Tipo di membro** selezionare un tipo di membro a cui applicare la regola di business.</span><span class="sxs-lookup"><span data-stu-id="8daa4-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="8daa4-116">Dall'elenco **Attributo** selezionare un attributo o lasciare inalterata l'impostazione predefinita **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="8daa4-117">Fare clic su **Aggiungi regola di business**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="8daa4-118">Fare clic su **Modifica regola business selezionata**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="8daa4-119">Nel riquadro **Componenti** espandere il nodo **Condizioni** .</span><span class="sxs-lookup"><span data-stu-id="8daa4-119">In the **Components** pane, expand the **Conditions** node.</span></span>  
  
10. <span data-ttu-id="8daa4-120">Fare clic su una condizione e trascinarla nell'etichetta **condizioni** del riquadro **if** .</span><span class="sxs-lookup"><span data-stu-id="8daa4-120">Click a condition and drag it to the **IF** pane's **Conditions** label.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="8daa4-121">È possibile eliminare elementi dalla regola business facendo clic con il pulsante destro del mouse e scegliendo **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-121">You can delete items from your business rule by right-clicking and choosing **Delete**.</span></span>  
  
11. <span data-ttu-id="8daa4-122">Nel riquadro **attributi** fare clic su un attributo e trascinarlo sull'etichetta **Seleziona attributo** del riquadro **Modifica condizione** .</span><span class="sxs-lookup"><span data-stu-id="8daa4-122">In the **Attributes** pane, click an attribute and drag it to the **Edit Condition** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="8daa4-123">Nel riquadro **Modifica condizione** completare tutti i campi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8daa4-123">In the **Edit Condition** pane, complete any required fields.</span></span>  
  
13. <span data-ttu-id="8daa4-124">Nel riquadro **Modifica condizione** fare clic su **Salva elemento**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-124">In the **Edit Condition** pane, click **Save item**.</span></span>  
  
14. <span data-ttu-id="8daa4-125">Nel riquadro **Componenti** espandere il nodo **Azioni** .</span><span class="sxs-lookup"><span data-stu-id="8daa4-125">In the **Components** pane, expand the **Actions** node.</span></span>  
  
15. <span data-ttu-id="8daa4-126">Fare clic su un'azione e trascinarla nell'etichetta **Azione** del riquadro **THEN** .</span><span class="sxs-lookup"><span data-stu-id="8daa4-126">Click an action and drag it to the **THEN** pane's **Action** label.</span></span>  
  
16. <span data-ttu-id="8daa4-127">Nel riquadro **Attributi** fare clic su un attributo e trascinarlo nell'etichetta **Seleziona attributo** del riquadro **Modifica azione** .</span><span class="sxs-lookup"><span data-stu-id="8daa4-127">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
17. <span data-ttu-id="8daa4-128">Nel riquadro **Modifica azione** completare tutti i campi obbligatori.</span><span class="sxs-lookup"><span data-stu-id="8daa4-128">In the **Edit Action** pane, complete any required fields.</span></span>  
  
18. <span data-ttu-id="8daa4-129">Nel riquadro **Modifica azione** fare clic su **Salva elemento**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-129">In the **Edit Action** pane, click **Save item**.</span></span>  
  
19. <span data-ttu-id="8daa4-130">Aggiungere facoltativamente più condizioni alla regola.</span><span class="sxs-lookup"><span data-stu-id="8daa4-130">Optionally, add multiple conditions to the rule.</span></span> <span data-ttu-id="8daa4-131">Per altre informazioni, vedere [Aggiungere più condizioni a una regola business &#40;Master Data Services&#41;](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8daa4-131">For more information, see [Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md).</span></span>  
  
20. <span data-ttu-id="8daa4-132">Fare clic su **Indietro**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-132">Click **Back**.</span></span>  
  
21. <span data-ttu-id="8daa4-133">Facoltativamente, nella pagina **Manutenzione regola business** per la riga che contiene la regola business fare doppio clic su una cella nella colonna **Nome**, **Descrizione**o **Notifica** per aggiornare il valore.</span><span class="sxs-lookup"><span data-stu-id="8daa4-133">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8daa4-134">Le notifiche vengono inviate soltanto per le regole che prevedono un'azione di convalida.</span><span class="sxs-lookup"><span data-stu-id="8daa4-134">Notifications are sent only for rules that include a validation action.</span></span>  
  
22. <span data-ttu-id="8daa4-135">Fare clic su **Pubblica regole business**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-135">Click **Publish business rules**.</span></span>  
  
23. <span data-ttu-id="8daa4-136">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-136">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="8daa4-137">Lo stato della regola viene modificato in **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="8daa4-137">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8daa4-138">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8daa4-138">Next Steps</span></span>  
  
-   <span data-ttu-id="8daa4-139">Applicare regole business ai dati eseguendo una delle procedure riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="8daa4-139">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="8daa4-140">Convalidare membri specifici rispetto a regole business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8daa4-140">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="8daa4-141">Convalidare una versione usando le regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8daa4-141">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="8daa4-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8daa4-142">See Also</span></span>  
 <span data-ttu-id="8daa4-143">[Configurare regole business per l'invio di notifiche &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8daa4-143">[Configure Business Rules to Send Notifications &#40;Master Data Services&#41;](../../2014/master-data-services/configure-business-rules-to-send-notifications-master-data-services.md) </span></span>  
 <span data-ttu-id="8daa4-144">[Modificare il nome di una regola business &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8daa4-144">[Change a Business Rule Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-a-business-rule-name-master-data-services.md) </span></span>  
 [<span data-ttu-id="8daa4-145">Aggiungere più condizioni a una regola business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8daa4-145">Add Multiple Conditions to a Business Rule &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-multiple-conditions-to-a-business-rule-master-data-services.md)  
  
  
