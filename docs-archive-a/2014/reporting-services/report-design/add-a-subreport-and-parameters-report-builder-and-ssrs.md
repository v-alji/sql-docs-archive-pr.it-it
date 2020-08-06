---
title: Aggiungere un sottoreport e i parametri (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10093"
- sql12.rtp.rptdesigner.subreportproperties.general.f1
ms.assetid: 94f960f8-a629-4f1e-8277-c3b8f0680d98
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3aeede343763ea5fc8fbdfde179208f98fa1a2ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623796"
---
# <a name="add-a-subreport-and-parameters-report-builder-and-ssrs"></a><span data-ttu-id="a77d9-102">Aggiungere un sottoreport e di parametri (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a77d9-102">Add a Subreport and Parameters (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a77d9-103">Aggiungere sottoreport a un report quando si desidera creare un report principale in cui è possibile includere più report correlati.</span><span class="sxs-lookup"><span data-stu-id="a77d9-103">Add subreports to a report when you want to create a main report that is a container for multiple related reports.</span></span> <span data-ttu-id="a77d9-104">Un sottoreport rappresenta un riferimento a un altro report.</span><span class="sxs-lookup"><span data-stu-id="a77d9-104">A subreport is a reference to another report.</span></span> <span data-ttu-id="a77d9-105">Per correlare i report tramite valori dei dati, ad esempio per fare in modo che in più report vengano visualizzati i dati relativi allo stesso cliente, è necessario progettare come sottoreport un report con parametri, ovvero un report in cui sono visualizzati i dettagli relativi a un cliente specifico.</span><span class="sxs-lookup"><span data-stu-id="a77d9-105">To relate the reports through data values (for example, to have multiple reports show data for the same customer), you must design a parameterized report (for example, a report that shows the details for a specific customer) as the subreport.</span></span> <span data-ttu-id="a77d9-106">Quando al report principale si aggiunge un sottoreport, è possibile specificare parametri da passare a quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="a77d9-106">When you add a subreport to the main report, you can specify parameters to pass to the subreport.</span></span>  
  
 <span data-ttu-id="a77d9-107">È inoltre possibile aggiungere sottoreport a righe o colonne dinamiche in una tabella oppure in una matrice.</span><span class="sxs-lookup"><span data-stu-id="a77d9-107">You can also add subreports to dynamic rows or columns in a table or matrix.</span></span> <span data-ttu-id="a77d9-108">Quando il report principale viene elaborato, il sottoreport viene elaborato per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="a77d9-108">When the main report is processed, the subreport is processed for each row.</span></span> <span data-ttu-id="a77d9-109">In questo caso, è necessario valutare se sia possibile ottenere l'effetto desiderato utilizzando aree dati o aree dati annidate.</span><span class="sxs-lookup"><span data-stu-id="a77d9-109">In this case, consider whether you can achieve the desired effect by using data regions or nested data regions.</span></span>  
  
 <span data-ttu-id="a77d9-110">Per aggiungere un sottoreport a un report, è necessario prima creare il report che sarà utilizzato come sottoreport.</span><span class="sxs-lookup"><span data-stu-id="a77d9-110">To add a subreport to a report, you must first create the report that will act as the subreport.</span></span> <span data-ttu-id="a77d9-111">Per altre informazioni sulla creazione del sottoreport, vedere [Sottoreport &#40;Generatore report e SSRS&#41;](subreports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a77d9-111">For more information on creating the subreport, see [Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-subreport"></a><span data-ttu-id="a77d9-112">Per aggiungere un sottoreport</span><span class="sxs-lookup"><span data-stu-id="a77d9-112">To add a subreport</span></span>  
  
1.  <span data-ttu-id="a77d9-113">Fare clic su **Sottoreport** nella scheda **Inserisci**.</span><span class="sxs-lookup"><span data-stu-id="a77d9-113">On the **Insert** tab, click **Subreport**.</span></span>  
  
2.  <span data-ttu-id="a77d9-114">Nell'area di progettazione fare clic in un punto del report, quindi trascinare una casella fino alle dimensioni desiderate per il sottoreport.</span><span class="sxs-lookup"><span data-stu-id="a77d9-114">On the design surface, click a location on the report and then drag a box to the desired size of the subreport.</span></span> <span data-ttu-id="a77d9-115">In alternativa, fare clic nell'area di progettazione per creare un sottoreport di dimensioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="a77d9-115">Alternatively, click the design surface to create a subreport of default size.</span></span>  
  
3.  <span data-ttu-id="a77d9-116">Fare clic con il pulsante destro del mouse sul sottoreport e quindi scegliere **Proprietà sottoreport**.</span><span class="sxs-lookup"><span data-stu-id="a77d9-116">Right-click the subreport, and then click **Subreport Properties**.</span></span>  
  
4.  <span data-ttu-id="a77d9-117">Nella finestra di dialogo **Proprietà sottoreport** digitare un nome nella casella di testo **Nome** o accettare il nome predefinito.</span><span class="sxs-lookup"><span data-stu-id="a77d9-117">In the **Subreport Properties** dialog box, type a name in the **Name** text box or accept the default.</span></span> <span data-ttu-id="a77d9-118">Il nome deve essere univoco nel report.</span><span class="sxs-lookup"><span data-stu-id="a77d9-118">The name must be unique within the report.</span></span> <span data-ttu-id="a77d9-119">Per impostazione predefinita, viene assegnato un nome generale, ad esempio Subreport1 o Subreport2.</span><span class="sxs-lookup"><span data-stu-id="a77d9-119">By default, a general name such as Subreport1 or Subreport2 is assigned.</span></span>  
  
5.  <span data-ttu-id="a77d9-120">Nella casella **Utilizzare il report come sottoreport** fare clic su **Sfoglia**oppure digitare il nome del report.</span><span class="sxs-lookup"><span data-stu-id="a77d9-120">In the **Use this report as a subreport** box, click **Browse**, or type the name of the report.</span></span> <span data-ttu-id="a77d9-121">È preferibile fare clic su **Sfoglia** perché il percorso del sottoreport verrà specificato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a77d9-121">Clicking **Browse** is preferred because the path to the subreport will be specified automatically.</span></span> <span data-ttu-id="a77d9-122">È possibile specificare il report in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="a77d9-122">You can specify the report in the several ways.</span></span> <span data-ttu-id="a77d9-123">Per altre informazioni, vedere [Specifica di percorsi di elementi esterni &#40;Generatore report e SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a77d9-123">For more information, see [Specifying Paths to External Items &#40;Report Builder and SSRS&#41;](specifying-paths-to-external-items-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="a77d9-124">(Facoltativo) Fare clic su **Sì** per **Ometti bordo sull'interruzione di pagina** per impedire che venga visualizzato un bordo a metà del sottoreport se si estende su più di una pagina.</span><span class="sxs-lookup"><span data-stu-id="a77d9-124">(Optional) Click **Yes** for **Omit border on page break** to prevent a border from being rendered in the middle of the subreport if the subreport spans more than one page.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-specify-parameters-to-pass-to-a-subreport"></a><span data-ttu-id="a77d9-125">Per specificare i parametri da passare a un sottoreport</span><span class="sxs-lookup"><span data-stu-id="a77d9-125">To specify parameters to pass to a subreport</span></span>  
  
1.  <span data-ttu-id="a77d9-126">Nella visualizzazione della struttura fare clic con il pulsante destro del mouse sul sottoreport e quindi scegliere **Proprietà sottoreport**.</span><span class="sxs-lookup"><span data-stu-id="a77d9-126">In Design view, right-click the subreport and then click **Subreport Properties**.</span></span>  
  
2.  <span data-ttu-id="a77d9-127">Nella finestra di dialogo **Proprietà sottoreport** fare clic su **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="a77d9-127">In the **Subreport Properties** dialog box, click **Parameters**.</span></span>  
  
3.  <span data-ttu-id="a77d9-128">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a77d9-128">Click **Add**.</span></span> <span data-ttu-id="a77d9-129">Alla griglia dei parametri verrà aggiunta una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="a77d9-129">A new row is added to the parameter grid.</span></span>  
  
4.  <span data-ttu-id="a77d9-130">Nella casella di testo **Nome** digitare il nome di un parametro nel sottoreport o sceglierlo dalla casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="a77d9-130">In the **Name** text box, type the name of a parameter in the subreport or choose it from the list box.</span></span> <span data-ttu-id="a77d9-131">Il nome deve corrispondere a un parametro del report e non al parametro di query nel sottoreport.</span><span class="sxs-lookup"><span data-stu-id="a77d9-131">This name must match a report parameter, not a query parameter, in the subreport.</span></span>  
  
5.  <span data-ttu-id="a77d9-132">Nella casella di riepilogo **Valore** digitare o selezionare un valore da passare al sottoreport.</span><span class="sxs-lookup"><span data-stu-id="a77d9-132">In the **Value** list box, type or select a value to pass to the subreport.</span></span> <span data-ttu-id="a77d9-133">È possibile specificare un testo statico o un'espressione che fa riferimento a un campo oppure a un altro oggetto nel report principale.</span><span class="sxs-lookup"><span data-stu-id="a77d9-133">This value can be static text or an expression that references a field or other object in the main report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a77d9-134">In Generatore report, se un parametro non è presente nell'elenco **Parametri** e il sottoreport dispone di un valore predefinito, il sottoreport sarà elaborato correttamente.</span><span class="sxs-lookup"><span data-stu-id="a77d9-134">In Report Builder, if a parameter is missing from the **Parameters** list and the subreport has a default value defined, the subreport will be processed correctly.</span></span>  
    >   
    >  <span data-ttu-id="a77d9-135">In Progettazione report, tutti i parametri necessari per il sottoreport devono essere inclusi nell'elenco **Parametri** .</span><span class="sxs-lookup"><span data-stu-id="a77d9-135">In Report Designer, all parameters that are required by the subreport must be included in the **Parameters** list.</span></span> <span data-ttu-id="a77d9-136">Se non viene specificato un parametro obbligatorio, il sottoreport non verrà visualizzato correttamente nel report principale.</span><span class="sxs-lookup"><span data-stu-id="a77d9-136">If a required parameter is missing, the subreport is not displayed correctly in the main report.</span></span>  
  
6.  <span data-ttu-id="a77d9-137">Ripetere i passaggi 3-5 per specificare un nome e un valore per ogni parametro del sottoreport.</span><span class="sxs-lookup"><span data-stu-id="a77d9-137">Repeat steps 3-5 to specify a name and value for each subreport parameter.</span></span>  
  
7.  <span data-ttu-id="a77d9-138">Per eliminare un parametro di sottoreport, fare clic sul parametro nella griglia dei parametri e quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="a77d9-138">To delete a subreport parameter, click the parameter in the parameter grid, and then click **Delete**.</span></span>  
  
8.  <span data-ttu-id="a77d9-139">Per modificare l'ordine di un parametro di sottoreport, fare clic sul parametro e quindi sul pulsante freccia in su o freccia in giù.</span><span class="sxs-lookup"><span data-stu-id="a77d9-139">To change the order of a subreport parameter, click the parameter, and then click the up button or the down button.</span></span>  
  
     <span data-ttu-id="a77d9-140">La modifica dell'ordine di un parametro di sottoreport non comporta effetti sull'elaborazione del sottoreport.</span><span class="sxs-lookup"><span data-stu-id="a77d9-140">Changing the order of a subreport parameter does not affect the processing of the subreport.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a77d9-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a77d9-141">See Also</span></span>  
 <span data-ttu-id="a77d9-142">[Sottoreport &#40;Generatore report e SSRS&#41;](subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a77d9-142">[Subreports &#40;Report Builder and SSRS&#41;](subreports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a77d9-143">Tipi di rendering &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a77d9-143">Rendering Behaviors &#40;Report Builder  and SSRS&#41;</span></span>](rendering-behaviors-report-builder-and-ssrs.md)  
  
  
