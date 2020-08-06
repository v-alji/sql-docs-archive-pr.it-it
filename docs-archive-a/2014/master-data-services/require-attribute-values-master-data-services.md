---
title: Richiedere valori di attributo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], requiring attribute values
- attributes [Master Data Services], requiring values
ms.assetid: a360ef13-0c34-43b8-a87e-2f5d8732d30e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42b412fc42138c5e186c6c7ad42373f20e35f3cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626126"
---
# <a name="require-attribute-values-master-data-services"></a><span data-ttu-id="6357a-102">Richiedere valori di attributo (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="6357a-102">Require Attribute Values (Master Data Services)</span></span>
  <span data-ttu-id="6357a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]richiedere valori di attributo quando si desidera essere sicuri che i dati master siano completi.</span><span class="sxs-lookup"><span data-stu-id="6357a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], require attribute values when you want to ensure your master data is complete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6357a-104">I membri a cui mancano valori di attributo basati su dominio non sono visualizzati nelle gerarchie derivate basate su tali relazioni.</span><span class="sxs-lookup"><span data-stu-id="6357a-104">Members that are missing domain-based attribute values are not displayed in derived hierarchies that are based on those relationships.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6357a-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6357a-105">Prerequisites</span></span>  
 <span data-ttu-id="6357a-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="6357a-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="6357a-107">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="6357a-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="6357a-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="6357a-108">You must be a model administrator.</span></span> <span data-ttu-id="6357a-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="6357a-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-require-attribute-values"></a><span data-ttu-id="6357a-110">Per richiedere valori di attributo</span><span class="sxs-lookup"><span data-stu-id="6357a-110">To require attribute values</span></span>  
  
1.  <span data-ttu-id="6357a-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="6357a-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="6357a-112">Dalla barra dei menu scegliere **Gestisci** e fare clic su **Regole business**.</span><span class="sxs-lookup"><span data-stu-id="6357a-112">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="6357a-113">Nella pagina **Manutenzione regola business** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="6357a-113">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="6357a-114">Dall'elenco **Entità** selezionare un'entità.</span><span class="sxs-lookup"><span data-stu-id="6357a-114">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="6357a-115">Dall'elenco **Tipo di membro** selezionare un tipo di membro a cui applicare la regola di business.</span><span class="sxs-lookup"><span data-stu-id="6357a-115">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="6357a-116">Dall'elenco **Attributo** selezionare un attributo o lasciare inalterata l'impostazione predefinita **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="6357a-116">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="6357a-117">Fare clic su **Aggiungi regola di business**.</span><span class="sxs-lookup"><span data-stu-id="6357a-117">Click **Add business rule**.</span></span>  
  
8.  <span data-ttu-id="6357a-118">Fare clic su **Modifica regola business selezionata**.</span><span class="sxs-lookup"><span data-stu-id="6357a-118">Click **Edit selected business rule**.</span></span>  
  
9. <span data-ttu-id="6357a-119">Nel riquadro **Componenti** espandere il nodo **Azioni** .</span><span class="sxs-lookup"><span data-stu-id="6357a-119">In the **Components** pane, expand the **Actions** node.</span></span>  
  
10. <span data-ttu-id="6357a-120">Fare clic su **obbligatorio** e trascinarlo sull'etichetta **azione** del riquadro **then** .</span><span class="sxs-lookup"><span data-stu-id="6357a-120">Click **is required** and drag it to the **THEN** pane's **Action** label.</span></span>  
  
11. <span data-ttu-id="6357a-121">Nel riquadro **Attributi** fare clic su un attributo e trascinarlo nell'etichetta **Seleziona attributo** del riquadro **Modifica azione** .</span><span class="sxs-lookup"><span data-stu-id="6357a-121">In the **Attributes** pane, click an attribute and drag it to the **Edit Action** pane's **Select attribute** label.</span></span>  
  
12. <span data-ttu-id="6357a-122">Nel riquadro **Modifica azione** fare clic su **Salva elemento**.</span><span class="sxs-lookup"><span data-stu-id="6357a-122">In the **Edit Action** pane, click **Save item**.</span></span>  
  
13. <span data-ttu-id="6357a-123">Fare clic su **Indietro**.</span><span class="sxs-lookup"><span data-stu-id="6357a-123">Click **Back**.</span></span>  
  
14. <span data-ttu-id="6357a-124">Facoltativamente, nella pagina **Manutenzione regola business** per la riga che contiene la regola business fare doppio clic su una cella nella colonna **Nome**, **Descrizione**o **Notifica** per aggiornare il valore.</span><span class="sxs-lookup"><span data-stu-id="6357a-124">Optionally, on the **Business Rules Maintenance** page, for the row that contains your business rule, double-click a cell in the **Name**, **Description**, or **Notification** column to update the value.</span></span>  
  
15. <span data-ttu-id="6357a-125">Fare clic su **Pubblica regole business**.</span><span class="sxs-lookup"><span data-stu-id="6357a-125">Click **Publish business rules**.</span></span>  
  
16. <span data-ttu-id="6357a-126">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6357a-126">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="6357a-127">Lo stato della regola viene modificato in **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="6357a-127">The rule's status changes to **Active**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6357a-128">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6357a-128">Next Steps</span></span>  
  
-   <span data-ttu-id="6357a-129">Applicare regole business ai dati eseguendo una delle procedure riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="6357a-129">Apply business rules to data by following one of these procedures:</span></span>  
  
    -   [<span data-ttu-id="6357a-130">Convalidare membri specifici rispetto a regole business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6357a-130">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
    -   [<span data-ttu-id="6357a-131">Convalidare una versione usando le regole di business &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6357a-131">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="6357a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6357a-132">See Also</span></span>  
 <span data-ttu-id="6357a-133">[Regole business &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="6357a-133">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="6357a-134">Gerarchie derivate &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="6357a-134">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
