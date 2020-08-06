---
title: Creare un attributo di data (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating date attributes [Master Data Services]
- attributes [Master Data Services], creating date attributes
ms.assetid: 22a8f1a3-b4f2-4cfa-8495-7daad5ce9d12
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 93797b90ff03c6a2b60ce8e015897a46a7448aad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623386"
---
# <a name="create-a-date-attribute-master-data-services"></a><span data-ttu-id="00941-102">Creare un attributo di data (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="00941-102">Create a Date Attribute (Master Data Services)</span></span>
  <span data-ttu-id="00941-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare un attributo date quando si desidera che gli utenti inseriscano una data come valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="00941-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a date attribute when you want users to enter a date as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00941-104">L'attributo viene chiamato DateTime, ma i valori ora non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="00941-104">The attribute is called DateTime, but time values are not supported.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="00941-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="00941-105">Prerequisites</span></span>  
 <span data-ttu-id="00941-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="00941-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="00941-107">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="00941-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="00941-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="00941-108">You must be a model administrator.</span></span> <span data-ttu-id="00941-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="00941-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="00941-110">È necessario avere un'entità per la quale creare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="00941-110">You must have an entity to create the attribute for.</span></span> <span data-ttu-id="00941-111">Per altre informazioni, vedere [Creare un'entità &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="00941-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-date-attribute"></a><span data-ttu-id="00941-112">Per creare un attributo di data</span><span class="sxs-lookup"><span data-stu-id="00941-112">To create a date attribute</span></span>  
  
1.  <span data-ttu-id="00941-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="00941-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="00941-114">Nella pagina **Vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **Entità**.</span><span class="sxs-lookup"><span data-stu-id="00941-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="00941-115">Nella pagina **Gestione entità** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="00941-115">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="00941-116">Selezionare la riga relativa all'entità per la quale si desidera creare un attributo.</span><span class="sxs-lookup"><span data-stu-id="00941-116">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="00941-117">Fare clic su **Modifica entità selezionata**.</span><span class="sxs-lookup"><span data-stu-id="00941-117">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="00941-118">Nella pagina **Modifica entità** :</span><span class="sxs-lookup"><span data-stu-id="00941-118">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="00941-119">Se l'attributo è per membri foglia, nel riquadro **Attributi membro foglia** fare clic su **Aggiungi attributo foglia**.</span><span class="sxs-lookup"><span data-stu-id="00941-119">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="00941-120">Se l'attributo è per membri consolidati, nel riquadro **Attributi membro consolidati** fare clic su **Aggiungi attributo consolidato**.</span><span class="sxs-lookup"><span data-stu-id="00941-120">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="00941-121">Se l'attributo è per raccolte, nel riquadro **Attributi raccolta** fare clic su **Aggiungi attributo raccolta**.</span><span class="sxs-lookup"><span data-stu-id="00941-121">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="00941-122">Nella pagina **Aggiungi attributo** selezionare l'opzione **Formato libero** .</span><span class="sxs-lookup"><span data-stu-id="00941-122">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="00941-123">Nella casella **Nome** digitare un nome per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="00941-123">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="00941-124">Per un elenco di parole che non devono essere usate come nomi di attributo, vedere [parole riservate &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="00941-124">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="00941-125">Nella casella **Larghezza in pixel visualizzazione** digitare la larghezza della colonna attributo da visualizzare nella griglia **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="00941-125">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="00941-126">Nell'elenco **Tipo di dati** selezionare **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="00941-126">From the **Data type** list, select **DateTime**.</span></span>  
  
11. <span data-ttu-id="00941-127">Nell'elenco **Maschera di input** selezionare un formato per le date.</span><span class="sxs-lookup"><span data-stu-id="00941-127">From the **Input mask** list, select a format for dates.</span></span>  
  
12. <span data-ttu-id="00941-128">Facoltativamente, selezionare **Abilita rilevamento modifiche** per tenere traccia delle modifiche a gruppi di attributi.</span><span class="sxs-lookup"><span data-stu-id="00941-128">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="00941-129">Per altre informazioni, vedere [Aggiungere attributi ad un gruppo rilevamento modifiche &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="00941-129">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="00941-130">Fare clic su **Salva attributo**.</span><span class="sxs-lookup"><span data-stu-id="00941-130">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="00941-131">Nella pagina **Gestione entità** , fare clic su **Salva entità**.</span><span class="sxs-lookup"><span data-stu-id="00941-131">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="to-display-the-time-portion-of-a-datetime-value"></a><span data-ttu-id="00941-132">Per visualizzare la porzione dell'ora di un valore datetime</span><span class="sxs-lookup"><span data-stu-id="00941-132">To display the time portion of a datetime value</span></span>  
 <span data-ttu-id="00941-133">Per fare in modo che nell'interfaccia utente venga visualizzata la porzione dell'ora di un valore datetime, è necessario selezionare una maschera di input appropriata per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="00941-133">To have the user interface display the time portion of a datetime value, you must select an appropriate input mask for the attribute.</span></span> <span data-ttu-id="00941-134">Questa operazione non viene effettuata da nessuna delle maschere predefinite per gli attributi Datetime, tuttavia è possibile aggiungerne una nuova tramite cui sarà possibile visualizzare l'ora.</span><span class="sxs-lookup"><span data-stu-id="00941-134">None of the built-in masks for Datetime attributes do this, but you can add a new mask that will allow you to display time.</span></span> <span data-ttu-id="00941-135">A tale scopo, aggiungere una riga nella tabella mdm.tblList del database MDS in cui sono archiviate le maschere predefinite.</span><span class="sxs-lookup"><span data-stu-id="00941-135">To do so, add a row in the mdm.tblList table of the MDS database, where the built-in masks are stored.</span></span> <span data-ttu-id="00941-136">Nella riga dovrebbero essere presenti i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="00941-136">The row should have the following values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00941-137">ListCode</span><span class="sxs-lookup"><span data-stu-id="00941-137">ListCode</span></span>|<span data-ttu-id="00941-138">lstInputMask</span><span class="sxs-lookup"><span data-stu-id="00941-138">lstInputMask</span></span>|  
|<span data-ttu-id="00941-139">ListName</span><span class="sxs-lookup"><span data-stu-id="00941-139">ListName</span></span>|<span data-ttu-id="00941-140">Maschera di input</span><span class="sxs-lookup"><span data-stu-id="00941-140">Input Mask</span></span>|  
|<span data-ttu-id="00941-141">Seq</span><span class="sxs-lookup"><span data-stu-id="00941-141">Seq</span></span>|<span data-ttu-id="00941-142">19</span><span class="sxs-lookup"><span data-stu-id="00941-142">19</span></span>|  
|<span data-ttu-id="00941-143">List Option</span><span class="sxs-lookup"><span data-stu-id="00941-143">List Option</span></span>|<span data-ttu-id="00941-144">dd/MM/yyyy hh:mm:ss tt</span><span class="sxs-lookup"><span data-stu-id="00941-144">dd/MM/yyyy hh:mm:ss tt</span></span>|  
|<span data-ttu-id="00941-145">Option ID</span><span class="sxs-lookup"><span data-stu-id="00941-145">Option ID</span></span>|<span data-ttu-id="00941-146">19</span><span class="sxs-lookup"><span data-stu-id="00941-146">19</span></span>|  
|<span data-ttu-id="00941-147">IsVisible</span><span class="sxs-lookup"><span data-stu-id="00941-147">IsVisible</span></span>|<span data-ttu-id="00941-148">1</span><span class="sxs-lookup"><span data-stu-id="00941-148">1</span></span>|  
|<span data-ttu-id="00941-149">Group_ID</span><span class="sxs-lookup"><span data-stu-id="00941-149">Group_ID</span></span>|<span data-ttu-id="00941-150">3</span><span class="sxs-lookup"><span data-stu-id="00941-150">3</span></span>|  
  
 <span data-ttu-id="00941-151">Dopo aver immesso una riga con i valori riportati in precedenza nella tabella mdm.tblList, la maschera "dd/MM/yyyy hh:mm:ss tt" sarà disponibile nella casella di riepilogo Maschera di input.</span><span class="sxs-lookup"><span data-stu-id="00941-151">After you enter a row with the above values in the mdm.tblList table, the "dd/MM/yyyy hh:mm:ss tt" mask will be available in the Input mask list box.</span></span> <span data-ttu-id="00941-152">È quindi possibile selezionare questa maschera per visualizzare la data e l'ora in una colonna di attributo datetime di un'entità in Esplora risorse di MDS.</span><span class="sxs-lookup"><span data-stu-id="00941-152">You can then select that mask to display the date and time in a datetime attribute column of an entity in the MDS Explorer.</span></span>  
  
 <span data-ttu-id="00941-153">La maschera di input è una stringa in formato DateTime .NET personalizzato.</span><span class="sxs-lookup"><span data-stu-id="00941-153">The Input Mask is a custom .NET DateTime format string.</span></span> <span data-ttu-id="00941-154">Per altre informazioni, vedere [Stringhe di formato di data e ora personalizzato](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="00941-154">For more information, see [Custom Date and Time Format Strings](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00941-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00941-155">See Also</span></span>  
 <span data-ttu-id="00941-156">[Attributi &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="00941-156">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="00941-157">[Modificare il nome di un attributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="00941-157">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="00941-158">[Creare un attributo basato su dominio &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="00941-158">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="00941-159">Creare un attributo di file &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="00941-159">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
