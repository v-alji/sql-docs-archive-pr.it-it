---
title: 'Lesson 3: Defining a Data-Driven Subscription (Lezione 3: Definizione di una sottoscrizione guidata dai dati) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 89197b9b-7502-4fe2-bea3-ed7943eebf3b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d1bbc25bdd08b369180e31378a6d25a595badbcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726580"
---
# <a name="lesson-3-defining-a-data-driven-subscription"></a><span data-ttu-id="30270-102">Lesson 3: Defining a Data-Driven Subscription</span><span class="sxs-lookup"><span data-stu-id="30270-102">Lesson 3: Defining a Data-Driven Subscription</span></span>
  <span data-ttu-id="30270-103">In questa lezione verranno utilizzate le pagine di sottoscrizione guidate dai dati per connettersi a un'origine dei dati di sottoscrizione, verrà compilata una query che recupera i dati di sottoscrizione e sarà eseguito il mapping tra il set di risultati e le opzioni di recapito e del report.</span><span class="sxs-lookup"><span data-stu-id="30270-103">In this lesson, you use the data-driven subscription pages to connect to a subscription data source, build a query that retrieves subscription data, and map the result set to report and delivery options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30270-104">Prima di iniziare, verificare che il servizio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="30270-104">Before you start, verify that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent service is running.</span></span> <span data-ttu-id="30270-105">Se non è in esecuzione, non è possibile salvare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="30270-105">If it is not running, you cannot save the subscription.</span></span>  
  
 <span data-ttu-id="30270-106">In questa lezione si presuppone che le lezioni 1 e 2 siano state completate e che l'origine dati del report utilizzi credenziali archiviate.</span><span class="sxs-lookup"><span data-stu-id="30270-106">This lesson assumes you completed Lesson 1 and Lesson 2 and that the report data source uses stored credentials.</span></span>  <span data-ttu-id="30270-107">Per altre informazioni, vedere [Lezione 2: Modifica delle proprietà dell'origine dei dati del report](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md)</span><span class="sxs-lookup"><span data-stu-id="30270-107">For more information, see [Lesson 2: Modifying the Report Data Source Properties](../reporting-services/lesson-2-modifying-the-report-data-source-properties.md)</span></span>  
  
 <span data-ttu-id="30270-108">In questo argomento</span><span class="sxs-lookup"><span data-stu-id="30270-108">In this topic:</span></span>  
  
-   [<span data-ttu-id="30270-109">Avviare la creazione guidata sottoscrizione guidata dai dati</span><span class="sxs-lookup"><span data-stu-id="30270-109">Start the Data-Driven Subscription Wizard</span></span>](#bkmk_startwizard)  
  
-   [<span data-ttu-id="30270-110">Passaggio 1: Definire una descrizione</span><span class="sxs-lookup"><span data-stu-id="30270-110">Step 1 - Define a description</span></span>](#bkmk_definesubscription)  
  
-   [<span data-ttu-id="30270-111">Passaggio 2: Definire una connessione all'origine dati del Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="30270-111">Step 2 - Define a Connection to the Subscriber Data Source</span></span>](#bkmk_defineconnectiontosubscriber)  
  
-   [<span data-ttu-id="30270-112">Passaggio 3: Definire una query per il recupero dei dati del Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="30270-112">Step 3 - Define a Query to Retrieve Subscriber data</span></span>](#bkmk_definequery)  
  
-   [<span data-ttu-id="30270-113">Passaggio 4: Impostare le opzioni di recapito</span><span class="sxs-lookup"><span data-stu-id="30270-113">Step 4 - Set Delivery Options</span></span>](#bkmk_set_deliveryoptions)  
  
-   [<span data-ttu-id="30270-114">Passaggio 5: Configurare un valore del parametro per variare l'output del report</span><span class="sxs-lookup"><span data-stu-id="30270-114">Step 5 - Configure a Parameter Value to Very Report Output</span></span>](#bkmk_configure_parameter)  
  
-   [<span data-ttu-id="30270-115">Passaggio 6: Per pianificare una sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="30270-115">Step 6 - To Schedule a Subscription</span></span>](#bkmk_schedule_subscription)  
  
##  <a name="start-the-data-driven-subscription-wizard"></a><a name="bkmk_startwizard"></a><span data-ttu-id="30270-116">Avviare la creazione guidata sottoscrizione guidata dai dati</span><span class="sxs-lookup"><span data-stu-id="30270-116">Start the Data-Driven Subscription Wizard</span></span>  
  
1.  <span data-ttu-id="30270-117">In Gestione report fare clic su **Home**e passare alla cartella contenente il report **Ordini vendita** .</span><span class="sxs-lookup"><span data-stu-id="30270-117">In Report Manager, click **Home**, and navigate to the folder containing the **Sales Orders** report.</span></span>  
  
2.  <span data-ttu-id="30270-118">Nel menu di scelta rapida del report fare clic su **Gestisci**, quindi fare clic sulla scheda **Sottoscrizioni** .</span><span class="sxs-lookup"><span data-stu-id="30270-118">In the context menu of the report, click **Manage**, and then click the **Subscriptions** tab.</span></span>  
  
3.  <span data-ttu-id="30270-119">Fare clic su **nuova sottoscrizione guidata dai dati**.</span><span class="sxs-lookup"><span data-stu-id="30270-119">Click **New Data-driven Subscription**.</span></span> <span data-ttu-id="30270-120">Se il pulsante non è visualizzato, non si dispone delle autorizzazioni di Gestione contenuto.</span><span class="sxs-lookup"><span data-stu-id="30270-120">If you do not see this button, you do not have Content Manager permissions.</span></span>  
  
##  <a name="step-1---define-a-description"></a><a name="bkmk_definesubscription"></a><span data-ttu-id="30270-121">Passaggio 1: definire una descrizione</span><span class="sxs-lookup"><span data-stu-id="30270-121">Step 1 - Define a description</span></span>  
  
1.  <span data-ttu-id="30270-122">Digitare **Recapito ordine di vendita** nella descrizione.</span><span class="sxs-lookup"><span data-stu-id="30270-122">Type **Sales Order delivery** in description.</span></span>  
  
2.  <span data-ttu-id="30270-123">Selezionare **Condivisione file di Windows** per **Specificare la modalità di notifica ai destinatari**.</span><span class="sxs-lookup"><span data-stu-id="30270-123">Select **Windows FileShare** for **Specify how recipients are notified**.</span></span>  
  
3.  <span data-ttu-id="30270-124">Selezionare **Specificare solo per questa sottoscrizione**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="30270-124">Select **Specify for this subscription only**, and then click **Next**.</span></span>  
  
##  <a name="step-2---define-a-connection-to-the-subscriber-data-source"></a><a name="bkmk_defineconnectiontosubscriber"></a><span data-ttu-id="30270-125">Passaggio 2: definire una connessione all'origine dati del Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="30270-125">Step 2 - Define a Connection to the Subscriber Data Source</span></span>  
  
1.  <span data-ttu-id="30270-126">Selezionare **Microsoft SQL Server** come tipo di origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="30270-126">Select **Microsoft SQL Server** as the data source type.</span></span>  
  
2.  <span data-ttu-id="30270-127">In Stringa di connessione digitare la stringa di connessione seguente:</span><span class="sxs-lookup"><span data-stu-id="30270-127">In Connection string, type the following connection string:</span></span>  
  
    ```  
    data source=localhost; initial catalog=Subscribers  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="30270-128">Subscribers è il database creato nella lezione 1.</span><span class="sxs-lookup"><span data-stu-id="30270-128">Subscribers is the database you created in lesson 1.</span></span>  
  
3.  <span data-ttu-id="30270-129">Fare clic su **Credenziali archiviate in modo protetto nel server di report**.</span><span class="sxs-lookup"><span data-stu-id="30270-129">Click **Credentials stored securely in the report server**.</span></span>  
  
4.  <span data-ttu-id="30270-130">In **Nome utente** e **Password**digitare nome utente e password per il dominio.</span><span class="sxs-lookup"><span data-stu-id="30270-130">In **User Name** and **Password**, type your domain user name and password.</span></span> <span data-ttu-id="30270-131">In **Nome utente**specificare sia il dominio che l'account utente.</span><span class="sxs-lookup"><span data-stu-id="30270-131">Include both the domain and user account when specifying **User Name**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="30270-132">Le credenziali utilizzate per connettersi a un'origine dati del Sottoscrittore non vengono restituite a [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30270-132">Credentials used to connect to a subscriber data source are not passed back to [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="30270-133">Se in seguito si modifica la sottoscrizione, sarà necessario immettere nuovamente la password utilizzata per la connessione all'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="30270-133">If you modify the subscription later, you must retype the password used to connect to the data source.</span></span>  
  
5.  <span data-ttu-id="30270-134">Selezionare **Usa come credenziali di Windows per la connessione all'origine dei dati**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="30270-134">Select **Use as windows credentials when connecting to the data source**, and then click **Next**.</span></span>  
  
##  <a name="step-3---define-a-query-to-retrieve-subscriber-data"></a><a name="bkmk_definequery"></a><span data-ttu-id="30270-135">Passaggio 3: definire una query per recuperare i dati del Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="30270-135">Step 3 - Define a Query to Retrieve Subscriber data</span></span>  
  
1.  <span data-ttu-id="30270-136">Nella casella della query digitare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="30270-136">In the query box, type the following query:</span></span>  
  
    ```  
    Select * from OrderInfo  
    ```  
  
2.  <span data-ttu-id="30270-137">Specificare un timeout di 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="30270-137">Specify a time-out of 30 seconds.</span></span>  
  
3.  <span data-ttu-id="30270-138">Fare clic su **Convalida**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="30270-138">Click **Validate**, and then click **Next**.</span></span>  
  
##  <a name="step-4---set-delivery-options"></a><a name="bkmk_set_deliveryoptions"></a><span data-ttu-id="30270-139">Passaggio 4: impostare le opzioni di recapito</span><span class="sxs-lookup"><span data-stu-id="30270-139">Step 4 - Set Delivery Options</span></span>  
  
1.  <span data-ttu-id="30270-140">Per **Nome file**selezionare **Estrai il valore dal database**.</span><span class="sxs-lookup"><span data-stu-id="30270-140">For **File name**, select **Get the value from the database**.</span></span> <span data-ttu-id="30270-141">Selezionare il campo **Ordine**.</span><span class="sxs-lookup"><span data-stu-id="30270-141">Select the field **Order**.</span></span>  
  
2.  <span data-ttu-id="30270-142">Per **Percorso**selezionare **Specificare un valore statico**.</span><span class="sxs-lookup"><span data-stu-id="30270-142">For **Path**, select **Specify a static value**.</span></span> <span data-ttu-id="30270-143">In Valore impostazione digitare il nome di una condivisione file pubblica per la quale si dispone di autorizzazioni di scrittura, ad esempio `\\mycomputer\public\myreports`.</span><span class="sxs-lookup"><span data-stu-id="30270-143">In Setting Value, type the name of a public file share for which you have write permissions (for example, `\\mycomputer\public\myreports`).</span></span>  
  
3.  <span data-ttu-id="30270-144">Per **Formato di rendering**selezionare **Estrai il valore dal database**.</span><span class="sxs-lookup"><span data-stu-id="30270-144">For **Render Format**, select **Get the value from the database**.</span></span> <span data-ttu-id="30270-145">Selezionare **formato**.</span><span class="sxs-lookup"><span data-stu-id="30270-145">Select **Format**.</span></span>  
  
4.  <span data-ttu-id="30270-146">Per **Modalità scrittura**selezionare **Specificare un valore statico** e scegliere **Incremento automatico**.</span><span class="sxs-lookup"><span data-stu-id="30270-146">For **Write mode**, select **Specify a static value** and select **AutoIncrement**.</span></span>  
  
5.  <span data-ttu-id="30270-147">Per **Estensione file**selezionare **Specificare un valore statico** e scegliere **True**.</span><span class="sxs-lookup"><span data-stu-id="30270-147">For **File Extension**, select **Specify a static value** and select **True**.</span></span>  
  
6.  <span data-ttu-id="30270-148">Per **Nome utente**selezionare **Specificare un valore statico**.</span><span class="sxs-lookup"><span data-stu-id="30270-148">For **User name**, select **Specify a static value**.</span></span> <span data-ttu-id="30270-149">Digitare l'account utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="30270-149">Type your domain user account.</span></span> <span data-ttu-id="30270-150">Immetterlo nel formato `<domain>\<account>`.</span><span class="sxs-lookup"><span data-stu-id="30270-150">Enter it in this format: `<domain>\<account>`.</span></span> <span data-ttu-id="30270-151">L'account utente deve disporre delle autorizzazioni per il percorso configurato nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="30270-151">The user account needs to have permissions to the path you configured in the previous steps.</span></span>  
  
7.  <span data-ttu-id="30270-152">Per **Password**selezionare **Specificare un valore statico**.</span><span class="sxs-lookup"><span data-stu-id="30270-152">For **Password**, select **Specify a static value**.</span></span> <span data-ttu-id="30270-153">Digitare la password.</span><span class="sxs-lookup"><span data-stu-id="30270-153">Type your password.</span></span> <span data-ttu-id="30270-154">Prestare attenzione quando si digita la password</span><span class="sxs-lookup"><span data-stu-id="30270-154">Be sure that you type the password carefully.</span></span> <span data-ttu-id="30270-155">poiché non viene convalidata durante la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="30270-155">The wizard does not validate the password.</span></span>  
  
8.  <span data-ttu-id="30270-156">Fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="30270-156">Click **Next.**</span></span>  
  
##  <a name="step-5---configure-a-parameter-value-to-very-report-output"></a><a name="bkmk_configure_parameter"></a><span data-ttu-id="30270-157">Passaggio 5: configurare un valore di parametro per l'output del report</span><span class="sxs-lookup"><span data-stu-id="30270-157">Step 5 - Configure a Parameter Value to Very Report Output</span></span>  
  
1.  <span data-ttu-id="30270-158">Per **OrderNumber**selezionare **Estrai il valore dal database**.</span><span class="sxs-lookup"><span data-stu-id="30270-158">For **OrderNumber**, select **Get the value from the database**.</span></span> <span data-ttu-id="30270-159">In Valore selezionare **Ordine**.</span><span class="sxs-lookup"><span data-stu-id="30270-159">In Value, select **Order**.</span></span> <span data-ttu-id="30270-160">Fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="30270-160">Click **Next.**</span></span>  
  
##  <a name="step-6---to-schedule-a-subscription"></a><a name="bkmk_schedule_subscription"></a><span data-ttu-id="30270-161">Passaggio 6: per pianificare una sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="30270-161">Step 6 - To Schedule a Subscription</span></span>  
  
1.  <span data-ttu-id="30270-162">Fare clic su **In base a una pianificazione creata per questa sottoscrizione**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="30270-162">Click **On a schedule created for this subscription**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="30270-163">In **Dettagli pianificazione**fare clic su **Singola occorrenza**.</span><span class="sxs-lookup"><span data-stu-id="30270-163">In **Schedule Details**, click **Once**.</span></span>  
  
3.  <span data-ttu-id="30270-164">Specificare un'ora di inizio posticipata di alcuni minuti rispetto all'ora corrente.</span><span class="sxs-lookup"><span data-stu-id="30270-164">Specify a start time that is a few minutes ahead of the current time.</span></span>  
  
4.  <span data-ttu-id="30270-165">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="30270-165">Click **Finish**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="30270-166">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="30270-166">Next Steps</span></span>  
 <span data-ttu-id="30270-167">Quando la sottoscrizione viene eseguita, nella condivisione file specificata vengono recapitati quattro file di report, uno per ogni ordine nell'origine dati *Sottoscrittori* .</span><span class="sxs-lookup"><span data-stu-id="30270-167">When the subscription runs, four report files will be delivered to the file share you specified, one for each order in the *Subscribers* data source.</span></span> <span data-ttu-id="30270-168">Ogni recapito deve essere univoco in termini di dati (che devono essere specifici dell'ordine), di formato di visualizzazione e di formato di file.</span><span class="sxs-lookup"><span data-stu-id="30270-168">Each delivery should be unique in terms of data (the data should be order-specific), rendering format, and file format.</span></span> <span data-ttu-id="30270-169">È possibile aprire tutti i report dalla cartella condivisa per verificare che ogni versione sia personalizzata in base alle opzioni di sottoscrizione definite.</span><span class="sxs-lookup"><span data-stu-id="30270-169">You can open each report from the shared folder to verify that each version is customized based on the subscription options you defined.</span></span>  
  
 <span data-ttu-id="30270-170">![Elenco di file creati dalla sottoscrizione](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "Elenco di file creati dalla sottoscrizione")</span><span class="sxs-lookup"><span data-stu-id="30270-170">![List of files created by the subscription](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-filelist.gif "List of files created by the subscription")</span></span>  
  
 <span data-ttu-id="30270-171">La pagina di sottoscrizione in Gestione report conterrà la data dell' **Ultima esecuzione** e lo **Stato** della sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="30270-171">The subscription page in Report Manager will contain the **Last Run** date and **Status** of the subscription.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30270-172">Aggiornare la pagina dopo l'esecuzione della sottoscrizione per visualizzare le informazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="30270-172">Refresh the page after the subscription runs to see the updated information.</span></span>  
  
 <span data-ttu-id="30270-173">![Risultati della sottoscrizione in Gestione report](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Risultati della sottoscrizione in Gestione report")</span><span class="sxs-lookup"><span data-stu-id="30270-173">![Subscription results in Report Manager](../../2014/tutorials/media/ssrs-tutorial-datadriven-subscription-status-reportmanager.gif "Subscription results in Report Manager")</span></span>  
  
 <span data-ttu-id="30270-174">Questo passaggio conclude l'esercitazione relativa alla definizione di una sottoscrizione guidata dai dati.</span><span class="sxs-lookup"><span data-stu-id="30270-174">This step concludes the tutorial "Defining a Data-Driven Subscription".</span></span> <span data-ttu-id="30270-175">Per ulteriori informazioni sulle altre [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] esercitazioni, vedere [Reporting Services esercitazioni &#40;&#41;SSRS ](../reporting-services/reporting-services-tutorials-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="30270-175">To learn more about other [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] tutorials, see [Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services/reporting-services-tutorials-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30270-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30270-176">See Also</span></span>  
 <span data-ttu-id="30270-177">[Creare una sottoscrizione guidata dai dati &#40;esercitazione su SSRS&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="30270-177">[Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) </span></span>  
 <span data-ttu-id="30270-178">[Sottoscrizioni e recapito &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="30270-178">[Subscriptions and Delivery &#40;Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md) </span></span>  
 <span data-ttu-id="30270-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="30270-179">[Data-Driven Subscriptions](subscriptions/data-driven-subscriptions.md) </span></span>  
 <span data-ttu-id="30270-180">[Creazione, modifica ed eliminazione di una sottoscrizione guidata dai dati](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span><span class="sxs-lookup"><span data-stu-id="30270-180">[Create, Modify, and Delete a Data-Driven Subscription](subscriptions/create-modify-and-delete-data-driven-subscriptions.md) </span></span>  
 [<span data-ttu-id="30270-181">Utilizzare un'origine dei dati esterna per i dati del Sottoscrittore &#40;sottoscrizione guidata dai dati&#41;</span><span class="sxs-lookup"><span data-stu-id="30270-181">Use an External Data Source for Subscriber Data &#40;Data-Driven Subscription&#41;</span></span>](subscriptions/use-an-external-data-source-for-subscriber-data-data-driven-subscription.md)  
  
  
