---
title: Modificare il tipo di attributo (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 9d3001d9-8d0f-4e4a-8e04-4f666bf0df69
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a55ca53fcf6923957e2196840aea2fb5914e1746
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714480"
---
# <a name="change-the-attribute-type-mds-add-in-for-excel"></a><span data-ttu-id="970e7-102">Modificare il tipo di attributo (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="970e7-102">Change the Attribute Type (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="970e7-103">Nel [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]gli amministratori possono modificare il tipo di attributo quando il tipo di dati o il numero di caratteri consentiti non è corretto.</span><span class="sxs-lookup"><span data-stu-id="970e7-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can change the attribute type when the data type or number of allowed characters is incorrect.</span></span>  
  
 <span data-ttu-id="970e7-104">Per modificare il tipo di attributo per creare un elenco vincolato (attributo basato su dominio), vedere [Creare un attributo basato su dominio &#40;componente aggiuntivo MDS per Excel&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="970e7-104">If you want to change the attribute type to create a constrained list (domain-based attribute), see [Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;](create-a-domain-based-attribute-mds-add-in-for-excel.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="970e7-105">Non è possibile aggiornare il tipo o la lunghezza delle colonne **Nome** o **Codice**.</span><span class="sxs-lookup"><span data-stu-id="970e7-105">You cannot update the type or length of the **Name** or **Code** columns.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="970e7-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="970e7-106">Prerequisites</span></span>  
 <span data-ttu-id="970e7-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="970e7-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="970e7-108">È necessario disporre dell'autorizzazione di accesso alle aree funzionali **Amministrazione sistema** e **Visualizzatore** .</span><span class="sxs-lookup"><span data-stu-id="970e7-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="970e7-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="970e7-109">You must be a model administrator.</span></span> <span data-ttu-id="970e7-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="970e7-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="970e7-111">Devono essere disponibili un modello esistente, un'entità e un attributo.</span><span class="sxs-lookup"><span data-stu-id="970e7-111">There must be an existing model, entity, and attribute.</span></span>  
  
### <a name="to-change-the-attribute-type"></a><span data-ttu-id="970e7-112">Per modificare il tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="970e7-112">To change the attribute type</span></span>  
  
1.  <span data-ttu-id="970e7-113">In Excel caricare l'entità contenente la colonna (attributo) che si desiderare modificare.</span><span class="sxs-lookup"><span data-stu-id="970e7-113">In Excel, load the entity that contains the column (attribute) you want to change.</span></span> <span data-ttu-id="970e7-114">Per altre informazioni, vedere [caricare i dati da MDS in Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="970e7-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="970e7-115">Fare clic su una cella nella colonna che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="970e7-115">Click any cell in the column you want to change.</span></span>  
  
3.  <span data-ttu-id="970e7-116">Nel gruppo **Compila modello** fare clic su **Proprietà attributi**.</span><span class="sxs-lookup"><span data-stu-id="970e7-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="970e7-117">Nella finestra di dialogo **Proprietà attributi** aggiornare le impostazioni in base alle necessità.</span><span class="sxs-lookup"><span data-stu-id="970e7-117">In the **Attribute Properties** dialog box, update settings as needed.</span></span>  
  
5.  <span data-ttu-id="970e7-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="970e7-118">Click **OK**.</span></span>  
  
## <a name="what-happens-when-you-change-the-attribute-type"></a><span data-ttu-id="970e7-119">Cosa accade quando si modifica il tipo di attributo</span><span class="sxs-lookup"><span data-stu-id="970e7-119">What happens when you change the attribute type?</span></span>  
 <span data-ttu-id="970e7-120">Se è presente una dipendenza dall'attributo, ad esempio all'attributo viene fatto riferimento da qualsiasi regola business MDS o l'attributo è incluso in una vista sottoscrizioni e si modifica il tipo di dati di un attributo, in MDS dovranno essere effettuate le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="970e7-120">If there is any dependency on the attribute, such as the attribute is referenced by any MDS business rule or the attribute is included in a subscription view, and you change the data type of an attribute, MDS will:</span></span>  
  
-   <span data-ttu-id="970e7-121">Modificare il tipo di dati dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="970e7-121">Change the data type of the attribute.</span></span>  
  
-   <span data-ttu-id="970e7-122">Genera una copia dell'attributo con il suffisso "_old" che non contiene alcun valore.</span><span class="sxs-lookup"><span data-stu-id="970e7-122">Generate a copy of the attribute with the suffix "_old" that does not contain any value.</span></span> <span data-ttu-id="970e7-123">Questa operazione è denominata attributo **deprecato** .</span><span class="sxs-lookup"><span data-stu-id="970e7-123">This is called a **deprecated** attribute.</span></span>  
  
 <span data-ttu-id="970e7-124">Tutte le dipendenze esistenti dall'attributo originale faranno tuttavia riferimento all'attributo deprecato e non a quello modificato.</span><span class="sxs-lookup"><span data-stu-id="970e7-124">However, all the existing dependencies on the original attribute will point to the deprecated attribute, and not to the changed one.</span></span>  
  
 <span data-ttu-id="970e7-125">Ciò implica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="970e7-125">This implies that:</span></span>  
  
-   <span data-ttu-id="970e7-126">È necessario aggiornare le regole business in modo che facciano riferimento all'attributo modificato, in quanto la logica potrebbe non essere la stessa applicata al nuovo tipo di dati dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="970e7-126">You must refresh the business rules to point to the changed attribute because the logic may not be the same given the new data type of the attribute.</span></span> <span data-ttu-id="970e7-127">Sarà necessario modificare ogni regola interessata, quindi rielaborare le espressioni in modo che vengano rimossi i riferimenti dall'attributo deprecato (_old) e venga fatto riferimento all'attributo aggiornato.</span><span class="sxs-lookup"><span data-stu-id="970e7-127">You will have to edit each affected rule, and then rework the expressions to point to remove references from the deprecated attribute (_old) to point to the updated attribute.</span></span>  
  
-   <span data-ttu-id="970e7-128">È necessario aprire tutte le viste sottoscrizioni sotto la selezione gestione integrazione, selezionare la riga Visualizza, aprirla per la modifica facendo clic sull'icona della matita, quindi fare clic sull'icona **Salva disco** per aggiornare la definizione della vista.</span><span class="sxs-lookup"><span data-stu-id="970e7-128">You must open any subscription views under the Integration Management selection, select the view row, open it for editing by clicking the pencil icon, and then click the **Save disk** icon to refresh the view definition.</span></span> <span data-ttu-id="970e7-129">Non sono necessarie altre modifiche per rigenerare la sintassi della vista.</span><span class="sxs-lookup"><span data-stu-id="970e7-129">No other change is needed to regenerate the view syntax.</span></span>  
  
-   <span data-ttu-id="970e7-130">Alle tabelle di gestione temporanea che includono l'attributo verrà una colonna per l'attributo deprecato e ciò influirà sul codice di gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="970e7-130">Staging tables that include the attribute will have a deprecated attribute column added to them, which means that your staging code will be affected.</span></span> <span data-ttu-id="970e7-131">Per eliminare l'attributo deprecato, è possibile eliminarlo dopo avere aggiornato regole business e le viste sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="970e7-131">To get rid of the deprecated attribute, you can delete it after you have updated the business rules and subscription views.</span></span>  
  
 <span data-ttu-id="970e7-132">**Eliminazione dell'attributo deprecato**</span><span class="sxs-lookup"><span data-stu-id="970e7-132">**Deleting the deprecated attribute**</span></span>  
  
 <span data-ttu-id="970e7-133">Prima di eliminare qualsiasi attributo deprecato, è necessario rimuovere tutti i riferimenti all'attributo, ad esempio correggere le regole business e rigenerare le viste sottoscrizioni come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="970e7-133">Before you delete any deprecated attribute, you must remove any references to the attribute such as fixing the business rules and regenerating subscription views as described earlier.</span></span> <span data-ttu-id="970e7-134">In caso contrario, quando si tenta di eliminare l'attributo deprecato, verrà generato un errore nella pagina Web di amministrazione del sistema nel quale è indicato che l'attributo non può essere eliminato perché un oggetto fa riferimento a tale attributo.</span><span class="sxs-lookup"><span data-stu-id="970e7-134">Otherwise, you will get an error in the System Administration web page when you attempt to delete the deprecated attribute stating that the attribute cannot be deleted because it is referenced by an object.</span></span>  
  
 <span data-ttu-id="970e7-135">Per eliminare un attributo, vedere [eliminare un attributo &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="970e7-135">To delete an attribute, see [Delete an Attribute &#40;Master Data Services&#41;](../delete-an-attribute-master-data-services.md)</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="970e7-136">Modificare i tipi di dati per gli attributi MDS con dati esistenti ed entità correlate è un'operazione complessa, soprattutto se è presente una regola business o una vista sottoscrizioni dichiarata che dipende dall'entità.</span><span class="sxs-lookup"><span data-stu-id="970e7-136">It is cumbersome to change data types for MDS attributes that have existing data and related entities, especially if there is a business rule or subscription view declared which depends on the entity.</span></span> <span data-ttu-id="970e7-137">La procedura consigliata consiste nell'iniziare con un tipo di dati sufficientemente flessibile per contenere i valori necessari.</span><span class="sxs-lookup"><span data-stu-id="970e7-137">The best practice is to start with a data type that is flexible enough to hold the necessary values.</span></span> <span data-ttu-id="970e7-138">Ad esempio, le stringhe potrebbero essere brevi inizialmente, ma con il tempo potrebbe essere necessario allungarle, quindi è consigliabile considerare il peggiore dei casi.</span><span class="sxs-lookup"><span data-stu-id="970e7-138">For example, strings may start small, but may need to be lengthened over time, so consider the worst case scenarios.</span></span> <span data-ttu-id="970e7-139">Una lunghezza aggiuntiva della stringa di testo può essere gravosa, ad esempio le caselle di testo di grandi dimensioni della GUI sono difficili da adattare alla schermata, quindi è opportuno evitare stringhe troppo lunghe.</span><span class="sxs-lookup"><span data-stu-id="970e7-139">Extra text string length can be burdensome (for example, wide GUI text boxes are hard to fit on the screen), so avoid too long string length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="970e7-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="970e7-140">See Also</span></span>  
 <span data-ttu-id="970e7-141">[Attributi &#40;Master Data Services&#41;](../attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="970e7-141">[Attributes &#40;Master Data Services&#41;](../attributes-master-data-services.md) </span></span>  
 [<span data-ttu-id="970e7-142">Compilazione di un modello &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="970e7-142">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
