---
title: Importare i valori di un progetto di pulizia in un dominio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.importprojectvalues.f1
ms.assetid: f23e38e2-39e0-42d7-abd5-34d8fcca5d2a
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 38616da5a0a8fb9c8f149d9f55a08b63dee5ff6a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715723"
---
# <a name="import-cleansing-project-values-into-a-domain"></a><span data-ttu-id="ff386-102">Importazione dei valori di un progetto di pulizia in un dominio</span><span class="sxs-lookup"><span data-stu-id="ff386-102">Import Cleansing Project Values into a Domain</span></span>
  <span data-ttu-id="ff386-103">In [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), è possibile importare informazioni sulla qualità dei dati raccolta durante il processo di pulizia in un processo di pulizia Data Quality o in un pacchetto di Integration Services contenente il componente di pulizia di DQS in un dominio.</span><span class="sxs-lookup"><span data-stu-id="ff386-103">In [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS), you can import data quality knowledge gathered during the cleansing process in a data quality cleansing project or an Integration Services package containing the DQS Cleansing component into a domain.</span></span> <span data-ttu-id="ff386-104">Ciò garantisce che le informazioni attendibili non vadano perse e che la Knowledge Base venga continuamente migliorata.</span><span class="sxs-lookup"><span data-stu-id="ff386-104">This ensures that trusted knowledge is not lost, and that the knowledge base is continually improved.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ff386-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ff386-105">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ff386-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ff386-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="ff386-107">Per importare valori di un progetto di pulizia in un dominio, il dominio deve essere stato utilizzato nel progetto di pulizia in Client Data Quality o nel pacchetto di Integration Services contenente un componente di pulizia di DQS.</span><span class="sxs-lookup"><span data-stu-id="ff386-107">To import cleansing project values into a domain, the domain must have been used in the cleansing project in Data Quality Client or in the Integration Services package containing a DQS Cleansing component.</span></span>  
  
-   <span data-ttu-id="ff386-108">Il progetto di pulizia in Client Data Quality o nel pacchetto di Integration Services contenente il componente di pulizia di DQS deve essere stato completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ff386-108">The cleansing project in Data Quality Client or the Integration Services package containing the DQS Cleansing component must have successfully completed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ff386-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ff386-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ff386-110">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ff386-110">Permissions</span></span>  
 <span data-ttu-id="ff386-111">Per importare in un dominio informazioni sulla qualità dei dati raccolta durante il processo di pulizia, è necessario disporre del ruolo dqs_kb_editor o dqs_administrator nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="ff386-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to import data quality knowledge gathered during the cleansing process into a domain.</span></span>  
  
##  <a name="import-cleansing-project-values"></a><a name="Import"></a> <span data-ttu-id="ff386-112">Importazione dei valori di un progetto di pulizia</span><span class="sxs-lookup"><span data-stu-id="ff386-112">Import Cleansing Project Values</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="ff386-113">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="ff386-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="ff386-114">Nella schermata iniziale del [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] aprire una Knowledge Base nell'attività Gestione dominio.</span><span class="sxs-lookup"><span data-stu-id="ff386-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open a knowledge base in the Domain Management activity.</span></span>  
  
3.  <span data-ttu-id="ff386-115">In caso di aggiunta di valori a un dominio esistente, selezionare il dominio nell'elenco di domini.</span><span class="sxs-lookup"><span data-stu-id="ff386-115">If adding values to an existing domain, select the domain in the domain list.</span></span>  
  
4.  <span data-ttu-id="ff386-116">Fare clic sulla scheda **Valori di dominio** , fare clic sull'icona **Importa valori** nella barra delle icone, quindi fare clic su **Importa valori progetto**.</span><span class="sxs-lookup"><span data-stu-id="ff386-116">Click the **Domain Values** tab, click the **Import Values** icon in the icon bar, and then click **Import project values**.</span></span> <span data-ttu-id="ff386-117">Viene visualizzata la finestra di dialogo **Importa valori progetto** con un elenco di progetti Data Quality e pacchetti di Integration Services che sono stati puliti utilizzando il dominio.</span><span class="sxs-lookup"><span data-stu-id="ff386-117">The **Import Project Values** dialog box appears with a list of data quality projects and Integration Services packages that were cleansed using the domain.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff386-118"> Se non è stato creato alcun progetto utilizzando il dominio o uno dei domini collegati, oppure se il progetto non è stato completato, l'opzione **Importa valori progetto** non sarà disponibile.</span><span class="sxs-lookup"><span data-stu-id="ff386-118">If no project has been created using the domain or any of its linked domains, or the project was not finished, the **Import project values** option will not be available.</span></span>  
  
5.  <span data-ttu-id="ff386-119">Nella finestra di dialogo **Importa valori progetto** :</span><span class="sxs-lookup"><span data-stu-id="ff386-119">In the **Import Project Values** dialog box:</span></span>  
  
    -   <span data-ttu-id="ff386-120">Selezionare **Tutto** nell'elenco a discesa **Importato** per visualizzare tutti i progetti o **No** per mostrare solo progetti i cui valori non sono stati importati.</span><span class="sxs-lookup"><span data-stu-id="ff386-120">Select **All** in the **Imported** drop-down list to display all projects, or **No** to display only projects whose values have not been imported yet.</span></span>  
  
    -   <span data-ttu-id="ff386-121">Selezionare il progetto da cui si desidera importare i valori.</span><span class="sxs-lookup"><span data-stu-id="ff386-121">Select the project that you want to import values from.</span></span>  
  
    -   <span data-ttu-id="ff386-122">Selezionare **Aggiungere i valori dalla scheda Nuova** per importare valori nella nuova scheda, oltre a valori nelle schede **Corretti** e **Con correzione** .</span><span class="sxs-lookup"><span data-stu-id="ff386-122">Select **Add values from New tab** to import values in the new tab, in addition to values in the **Correct** and **Corrected** tabs.</span></span>  
  
    -   <span data-ttu-id="ff386-123">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff386-123">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="ff386-124">Si torna nella scheda **Valori di dominio** e viene visualizzato un messaggio sulla corretta importazione dei valori.</span><span class="sxs-lookup"><span data-stu-id="ff386-124">You return to the **Domain Values** tab, and a message is displayed on successful import of the values.</span></span> <span data-ttu-id="ff386-125">I valori importati, e quindi nuovi per il dominio, verranno visualizzati nella tabella **Valori** .</span><span class="sxs-lookup"><span data-stu-id="ff386-125">Values that have been imported, and so are new to the domain, will be displayed in the **Values** table.</span></span>  
  
7.  <span data-ttu-id="ff386-126">Deselezionare **Mostra solo nuovi** per visualizzare tutti i valori presenti nel dominio.</span><span class="sxs-lookup"><span data-stu-id="ff386-126">Deselect **Show Only New** to display all values that are in the domain.</span></span>  
  
8.  <span data-ttu-id="ff386-127">Selezionare **Corretti**, **Errori**o **Non validi** per visualizzare solo i valori del tipo selezionato.</span><span class="sxs-lookup"><span data-stu-id="ff386-127">Select **Correct**, **Error**, or **Invalid** to display only those values of the selected type.</span></span>  
  
9. <span data-ttu-id="ff386-128">Per cercare una stringa specifica, immettere la stringa nella casella di testo **Trova** .</span><span class="sxs-lookup"><span data-stu-id="ff386-128">To search for a specific string, enter the string in the **Find** text box.</span></span> <span data-ttu-id="ff386-129">Fare clic sulla freccia Su o Giù per spostarsi tra i valori che soddisfano il criterio di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff386-129">Click the up or down arrow to step through the values that meet the search criteria.</span></span> <span data-ttu-id="ff386-130">Questi verranno evidenziati in giallo.</span><span class="sxs-lookup"><span data-stu-id="ff386-130">They will be highlighted in yellow.</span></span>  
  
10. <span data-ttu-id="ff386-131">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="ff386-131">Click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ff386-132"> Per ulteriori informazioni sull'utilizzo di valori nella scheda **Valori di dominio** , vedere [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span><span class="sxs-lookup"><span data-stu-id="ff386-132">For more information on working with values in the **Domain Values** tab, see [Change Domain Values](../../2014/data-quality-services/change-domain-values.md).</span></span>  
  
##  <a name="follow-up-after-importing-project-values-into-a-domain"></a><a name="FollowUp"></a> <span data-ttu-id="ff386-133">Completamento: Dopo avere importato i valori di progetto in un dominio</span><span class="sxs-lookup"><span data-stu-id="ff386-133">Follow Up: After Importing Project Values into a Domain</span></span>  
 <span data-ttu-id="ff386-134">Dopo avere importato le informazioni sulla qualità dei dati raccolta durante il processo di pulizia in un dominio, è possibile eseguire attività di gestione relative ai domini sul dominio e sui relativi valori.</span><span class="sxs-lookup"><span data-stu-id="ff386-134">After you import data quality knowledge gathered during the cleansing process into a domain, you can perform other domain management tasks on the domain and the values.</span></span> <span data-ttu-id="ff386-135">Per altre informazioni, vedere [Gestione di un dominio](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="ff386-135">For more information, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
##  <a name="values-that-will-be-imported"></a><a name="Values"></a> <span data-ttu-id="ff386-136">Valori che verranno importati</span><span class="sxs-lookup"><span data-stu-id="ff386-136">Values that Will Be Imported</span></span>  
 <span data-ttu-id="ff386-137">I valori seguenti verranno importati da un progetto in un dominio:</span><span class="sxs-lookup"><span data-stu-id="ff386-137">The following values will be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="ff386-138">Solo i valori stringa vengono importati nel dominio.</span><span class="sxs-lookup"><span data-stu-id="ff386-138">Only string values are imported to the domain.</span></span>  
  
-   <span data-ttu-id="ff386-139">Verranno importato solo i valori delle schede **Corretti**, **Con correzione**e **Nuovi** nella pagina **Gestisci e visualizza risultati** dell'attività **Pulizia** .</span><span class="sxs-lookup"><span data-stu-id="ff386-139">Only values from the **Correct**, **Corrected**, and **New** tabs on the **Manage and View results** page of the **Cleansing** activity will be imported.</span></span> <span data-ttu-id="ff386-140">I valori della scheda **Nuovi** verranno importati solo se è stata selezionata la casella di controllo **Aggiungere i valori dalla scheda Nuova** nella finestra di dialogo **Importa valori progetto** .</span><span class="sxs-lookup"><span data-stu-id="ff386-140">Values from the **New** tab will be imported only if the **Add values from New tab** check box in the **Import Project Values** dialog box has been selected.</span></span>  
  
-   <span data-ttu-id="ff386-141">I valori verranno importati come corretti o come errore con relativa correzione.</span><span class="sxs-lookup"><span data-stu-id="ff386-141">Values will be imported as correct or as an error with its correction.</span></span> <span data-ttu-id="ff386-142">Verranno importati solo valori di errore con relativo valore di correzione.</span><span class="sxs-lookup"><span data-stu-id="ff386-142">Only an error value with a correction value will be imported.</span></span>  
  
-   <span data-ttu-id="ff386-143">Il valore della correzione sarà un nuovo valore che non esiste nella Knowledge Base o un valore corretto esistente.</span><span class="sxs-lookup"><span data-stu-id="ff386-143">The correction value will be either a new value that does not exist in the knowledge base or an existing correct value.</span></span>  
  
-   <span data-ttu-id="ff386-144">Solo correzioni eseguite a livello di valore, e non a livello di record, verranno importate nella Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="ff386-144">Only corrections performed on the value level, not the record level, will be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="ff386-145">Se il valore importato è in contrasto con una regola di dominio, verranno creati valori non validi.</span><span class="sxs-lookup"><span data-stu-id="ff386-145">Invalid values will be created if the imported value contradicts a domain rule.</span></span>  
  
-   <span data-ttu-id="ff386-146">Se si importano valori da diversi progetti in una sola operazione, i valori vengono importati secondo un ordine sequenziale.</span><span class="sxs-lookup"><span data-stu-id="ff386-146">If you import values from several projects at once, the values are imported in a sequential order.</span></span>  
  
-   <span data-ttu-id="ff386-147">Una correzione effettuata come risultato di una relazione basata su termine in un dominio, viene importata come valore corretto (non come errore).</span><span class="sxs-lookup"><span data-stu-id="ff386-147">A correction made as a result of a term-based relation in a domain is imported as a correct value (not as an error).</span></span>  
  
##  <a name="values-that-will-not-be-imported"></a><a name="ValuesNot"></a> <span data-ttu-id="ff386-148">Valori che non verranno importati</span><span class="sxs-lookup"><span data-stu-id="ff386-148">Values that Will Not Be Imported</span></span>  
 <span data-ttu-id="ff386-149">I valori seguenti non verranno importati da un progetto in un dominio:</span><span class="sxs-lookup"><span data-stu-id="ff386-149">The following values will not be imported from a project into a domain:</span></span>  
  
-   <span data-ttu-id="ff386-150">I valori dalle schede **Suggeriti** e **Non validi** nella pagina **Gestisci e visualizza risultati** dell'attività **Pulizia** non vengono importati.</span><span class="sxs-lookup"><span data-stu-id="ff386-150">Values from the **Suggested** and **Invalid** tabs on the **Manage and View results** page of the **Cleansing** activity will not be imported.</span></span>  
  
-   <span data-ttu-id="ff386-151">Se un valore trovato nel progetto di pulizia è in contrasto con un valore esistente nel dominio, il valore trovato nel progetto verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="ff386-151">If a value found in the cleansing project contradicts an existing value in the domain, the value found in the project is skipped.</span></span> <span data-ttu-id="ff386-152">Questo include conflitti tra valori di pulizia e valori della Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="ff386-152">This will include conflicts between cleansing and knowledge base values.</span></span>  
  
-   <span data-ttu-id="ff386-153">Le correzioni eseguite a livello di record non verranno importate nella Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="ff386-153">Corrections performed on the record level will not be imported into the knowledge base.</span></span>  
  
-   <span data-ttu-id="ff386-154">Non verrà importato alcun valore in un dominio se il valore che sostituirebbe è corretto o è stato approvato come corretto da un servizio dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="ff386-154">No value will be imported to a domain if the value that it would replace was corrected or approved as correct by a reference data service.</span></span>  
  
-   <span data-ttu-id="ff386-155">Se un valore di correzione compare nella Knowledge Base come valore erroneo o non valido, non verranno importati né l'errore né il valore di correzione.</span><span class="sxs-lookup"><span data-stu-id="ff386-155">If a correction value appears in the knowledge base as an invalid or error value, neither the error nor the correction value will be imported.</span></span>  
  
-   <span data-ttu-id="ff386-156">Se il dominio fa parte di un dominio composito, e la pulizia è stata eseguita sul dominio composito, non verrà importato alcun valore.</span><span class="sxs-lookup"><span data-stu-id="ff386-156">If the domain is part of a composite domain, and the cleansing was performed on the composite domain, no values will be imported.</span></span>  
  
-   <span data-ttu-id="ff386-157">È possibile importare valori da un progetto solo quando la Knowledge Base presenta uno stato operativo ed è bloccata dall'utente che sta effettuando l'importazione.</span><span class="sxs-lookup"><span data-stu-id="ff386-157">You can import values from a project only when the knowledge base has a state of in-work and the knowledge base is locked by the user who is importing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff386-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff386-158">See Also</span></span>  
 <span data-ttu-id="ff386-159">[Pulizia dei dati](../../2014/data-quality-services/data-cleansing.md) </span><span class="sxs-lookup"><span data-stu-id="ff386-159">[Data Cleansing](../../2014/data-quality-services/data-cleansing.md) </span></span>  
 [<span data-ttu-id="ff386-160">Trasformazione DQS Cleansing</span><span class="sxs-lookup"><span data-stu-id="ff386-160">DQS Cleansing Transformation</span></span>](../integration-services/data-flow/transformations/dqs-cleansing-transformation.md)  
  
  
