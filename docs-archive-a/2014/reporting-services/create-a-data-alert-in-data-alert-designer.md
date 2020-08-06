---
title: Creare un avviso dati nella finestra di progettazione Avviso dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8464ab9d-afe1-4490-955f-9f3319bcbf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19c3001d4663848c009a353baa068f237d4a0b5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719721"
---
# <a name="create-a-data-alert-in-data-alert-designer"></a><span data-ttu-id="fdeb2-102">Creare un avviso dati nella finestra di progettazione Avviso dati</span><span class="sxs-lookup"><span data-stu-id="fdeb2-102">Create a Data Alert in Data Alert Designer</span></span>
  <span data-ttu-id="fdeb2-103">Le definizioni di avviso dati vengono create nella finestra di progettazione Avviso dati.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-103">You create data alert definitions in Data Alert Designer.</span></span> <span data-ttu-id="fdeb2-104">Dopo aver salvato le definizioni di avviso, è possibile riaprirle, modificarle, quindi salvare di nuovo nella finestra di progettazione Avviso dati.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-104">After you save the alert definitions, you can reopen, edit, and then resave them in Data Alert Designer.</span></span> <span data-ttu-id="fdeb2-105">Per informazioni sulla modifica delle definizioni di avviso, vedere [Gestire gli avvisi dati in Gestione avvisi dati](manage-my-data-alerts-in-data-alert-manager.md) e [Modificare un avviso dati nella finestra di progettazione di avvisi](edit-a-data-alert-in-alert-designer.md).</span><span class="sxs-lookup"><span data-stu-id="fdeb2-105">For information about editing alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md) and [Edit a Data Alert in Alert Designer](edit-a-data-alert-in-alert-designer.md).</span></span>

### <a name="to-create-a-data-alert-definition"></a><span data-ttu-id="fdeb2-106">Per creare una definizione di avviso dati</span><span class="sxs-lookup"><span data-stu-id="fdeb2-106">To create a data alert definition</span></span>

1.  <span data-ttu-id="fdeb2-107">Individuare la raccolta di SharePoint in cui è contenuto il report per il quale si desidera creare una definizione di avviso dati.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-107">Locate the SharePoint library that contains the report that you want to create a data alert definition for.</span></span>

2.  <span data-ttu-id="fdeb2-108">Fare clic sul report.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-108">Click the report.</span></span>

     <span data-ttu-id="fdeb2-109">Il report verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-109">The report runs.</span></span> <span data-ttu-id="fdeb2-110">Se il report è con parametri, verificare che in esso vengano visualizzati i dati per i quali si desidera ricevere messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-110">If the report is parameterized, verify that the report shows the data that you want to receive alert messages about.</span></span> <span data-ttu-id="fdeb2-111">Se non vengono visualizzati i valori o le colonne di interesse per l'utente, potrebbe essere necessario eseguire nuovamente il report, utilizzando valori dei parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-111">If you do not see the columns or values you are interested in, you might want to rerun the report, using different parameter values.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="fdeb2-112">I valori dei parametri scelti per l'esecuzione del report vengono salvati nella definizione di avviso e verranno utilizzati quando il report viene eseguito di nuovo come passaggio nell'elaborazione della definizione di avviso.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-112">The parameter values you chose to run the report are saved in the alert definition and will be used when report is rerun as a step in processing the alert definition.</span></span> <span data-ttu-id="fdeb2-113">Per utilizzare valori dei parametri diversi, è necessario creare una nuova definizione di avviso.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-113">To use different parameter values, you must create a new alert definition.</span></span>

3.  <span data-ttu-id="fdeb2-114">Scegliere **Nuovo avviso dati** dal menu **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-114">On the **Actions** menu, click **New Data Alert**.</span></span>

     <span data-ttu-id="fdeb2-115">L'immagine seguente illustra il menu **Azioni** .</span><span class="sxs-lookup"><span data-stu-id="fdeb2-115">The following picture shows the **Actions** menu.</span></span>

     <span data-ttu-id="fdeb2-116">![Aprire Alert Designer dalla raccolta di SharePoint](media/rs-openalertdesigneriw.gif "Aprire Alert Designer dalla raccolta di SharePoint")</span><span class="sxs-lookup"><span data-stu-id="fdeb2-116">![Open Alert Designer from SharePoint library](media/rs-openalertdesigneriw.gif "Open Alert Designer from SharePoint library")</span></span>

     <span data-ttu-id="fdeb2-117">La finestra di progettazione Avviso dati viene visualizzata, con le prime 100 righe del primo feed di dati generato dal report in una tabella.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-117">The Data Alert Designer opens, showing the first 100 rows of the first data feed that the report generates in a table.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="fdeb2-118">Se l'opzione **Nuovo avviso dati** non viene visualizzata, il servizio avvisi non è configurato nel sito di SharePoint oppure l'edizione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] non include gli avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-118">If you do not see the **New Data Alert** option, the alerting service is not configured on the SharePoint site or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] edition does not include data alerts.</span></span> <span data-ttu-id="fdeb2-119">Per altre informazioni, vedere [Servizio SharePoint di Reporting Services e applicazioni di servizio](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span><span class="sxs-lookup"><span data-stu-id="fdeb2-119">For more information, see [Reporting Services SharePoint Service and Service Applications](../../2014/reporting-services/reporting-services-sharepoint-service-and-service-applications.md).</span></span>
    > 
    >  <span data-ttu-id="fdeb2-120">Se l'opzione **Nuovo avviso dati** è visualizzata in grigio, l'origine dati del report è configurata per l'utilizzo di credenziali di sicurezza integrata o per la richiesta di credenziali.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-120">If the **New Data Alert** option is grayed, the report data source is configured to use integrated security credentials or prompt for credentials.</span></span> <span data-ttu-id="fdeb2-121">Per rendere disponibile l'opzione **Nuovo avviso dati** , è necessario aggiornare l'origine dati per usare credenziali archiviate o nessuna credenziale.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-121">To make the **New Data Alert** option available, you must update the data source to use stored credentials or no credentials.</span></span>

     <span data-ttu-id="fdeb2-122">Il nome del feed di dati viene visualizzato nell'elenco a discesa **Nome dati report** .</span><span class="sxs-lookup"><span data-stu-id="fdeb2-122">The name of the data feed appears in **Report data name** drop-down list.</span></span>

4.  <span data-ttu-id="fdeb2-123">Facoltativamente, selezionare un feed di dati diverso nell'elenco a discesa **Nome dati report** .</span><span class="sxs-lookup"><span data-stu-id="fdeb2-123">Optionally, select a different data feed in the **Report data name** drop-down list.</span></span>

     <span data-ttu-id="fdeb2-124">Se non viene generato alcun feed di dati dal report, non è possibile creare una definizione di avviso per tale report.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-124">If no data feed is generated from the report, you cannot create an alert definition for the report.</span></span> <span data-ttu-id="fdeb2-125">Il layout del report determina il contenuto di ogni feed di dati.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-125">The layout of the report determines the content of each data feed.</span></span> <span data-ttu-id="fdeb2-126">Per altre informazioni, vedere [Generazione di feed di dati dai report &#40;Generatore report e SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fdeb2-126">For more information see, [Generating Data Feeds from Reports &#40;Report Builder and SSRS&#41;](report-builder/generating-data-feeds-from-reports-report-builder-and-ssrs.md).</span></span>

5.  <span data-ttu-id="fdeb2-127">Facoltativamente, nella casella di testo **Nome avviso** aggiornare il nome predefinito per renderlo più significativo.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-127">Optionally, in the **Alert name** text box, update the default name to be more meaningful.</span></span>

     <span data-ttu-id="fdeb2-128">Il nome predefinito della definizione di avviso corrisponde al nome del report.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-128">The default name of the alert definition is the name of the report.</span></span> <span data-ttu-id="fdeb2-129">Non è necessario che i nomi delle definizioni di avviso siano univoci, ma l'utilizzo di nomi uguali ne renderebbe difficile la distinzione quando si visualizza l'elenco di avvisi in Gestione avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-129">Alert definition names do not have to be unique, which can make it difficult to tell them apart when you later view the list of your alerts in Data Alert Manager.</span></span> <span data-ttu-id="fdeb2-130">È consigliabile utilizzare nomi significativi e univoci per le definizioni di avviso.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-130">It is recommended that you use meaningful and unique names for your alert definitions.</span></span>

6.  <span data-ttu-id="fdeb2-131">Facoltativamente, cambiare l'opzione dei dati predefiniti da **any data in the data feed has** (alcuni dati nel feed di dati hanno) in **no data in the data feed has** (nessun dato del feed di dati ha).</span><span class="sxs-lookup"><span data-stu-id="fdeb2-131">Optionally, change the default data option from **any data in the data feed has** to **no data in the data feed has**.</span></span>

7.  <span data-ttu-id="fdeb2-132">Fare clic su **Aggiungi regola**.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-132">Click **Add rule**.</span></span>

     <span data-ttu-id="fdeb2-133">Verrà visualizzato un elenco delle colonne nel feed di dati.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-133">A list of the columns in the data feed appears.</span></span>

8.  <span data-ttu-id="fdeb2-134">Nell'elenco selezionare la colonna che si desidera utilizzare nella regola, quindi selezionare un operatore di confronto e immettere il valore soglia.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-134">In the list, select the column that you want to use in the rule, and then select a comparison operator and enter the threshold value.</span></span>

     <span data-ttu-id="fdeb2-135">A seconda del tipo di dati della colonna selezionata, vengono elencati operatori di confronto differenti.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-135">Depending on the data type of the selected column, different comparison operators are listed.</span></span> <span data-ttu-id="fdeb2-136">Se la colonna dispone di un tipo di dati relativo alla data, verrà visualizzata un'icona di calendario accanto al valore soglia per la regola.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-136">If the column has a date data type, a calendar icon displays next to threshold value for the rule.</span></span> <span data-ttu-id="fdeb2-137">È possibile immettere dati facendo clic su una data nel calendario o digitando la data.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-137">You can enter a data by clicking a date in the calendar or typing the date.</span></span>

     <span data-ttu-id="fdeb2-138">La finestra di progettazione Avviso Dati offre due modalità di confronto: **Modalità immissione valori** e **Modalità selezione campo**.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-138">Data Alert Designer provides two comparison modes: **Value Entry Mode** and **Field Selection Mode**.</span></span> <span data-ttu-id="fdeb2-139">La modalità predefinita è **Modalità immissione valori**.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-139">The default mode is **Value Entry Mode**.</span></span> <span data-ttu-id="fdeb2-140">È possibile aggiungere clausole OR solo quando è attiva la **Modalità immissione valori** e si sta usando il confronto di tipo **is** .</span><span class="sxs-lookup"><span data-stu-id="fdeb2-140">You can add OR clauses only when you are in **Value Entry Mode** and are using the **is** comparison.</span></span>

9. <span data-ttu-id="fdeb2-141">Per aggiungere una clausola OR, fare clic sulla freccia rivolta verso il basso, quindi su **Modalità immissione valori**.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-141">To add an OR clause, click the down-arrow, and then click **Value Entry Mode**.</span></span>

10. <span data-ttu-id="fdeb2-142">Digitare il valore di confronto.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-142">Type the comparison value.</span></span>

11. <span data-ttu-id="fdeb2-143">Facoltativamente, fare di nuovo clic sui puntini di sospensione **(...)** .</span><span class="sxs-lookup"><span data-stu-id="fdeb2-143">Optionally, click the ellipsis **(...)** again.</span></span>

     <span data-ttu-id="fdeb2-144">I puntini di sospensione **(...)** vengono visualizzati sulla riga contenente la prima clausola.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-144">The ellipsis **(...)** appears on the line that contains the first clause.</span></span>

     <span data-ttu-id="fdeb2-145">Una clausola OR viene aggiunta nella parte inferiore e all'interno della regola AND.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-145">An OR clause is added below and within the AND rule.</span></span>

12. <span data-ttu-id="fdeb2-146">Facoltativamente, fare clic sulla freccia rivolta verso il basso, selezionare **Modalità selezione campo**, quindi selezionare una colonna nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-146">Optionally, click the down-arrow, select **Field Selection Mode**, and then select a column in the list.</span></span>

     <span data-ttu-id="fdeb2-147">Si noterà che i puntini di sospensione **(...)** su cui si fa clic per aggiungere clausole OR sono scomparsi.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-147">You will notice that the ellipsis **(...)** that you click to add OR clauses has disappeared.</span></span>

13. <span data-ttu-id="fdeb2-148">Facoltativamente, fare di nuovo clic su **Aggiungi regola** per aggiungere altre regole.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-148">Optionally, click **Add rule** again to add additional rules.</span></span>

     <span data-ttu-id="fdeb2-149">Le regole vengono combinate tramite l'operatore logico AND.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-149">The rules are combined by using the AND logical operator.</span></span>

14. <span data-ttu-id="fdeb2-150">Selezionare un'opzione nell'elenco relativo alla ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-150">Select an option in the recurrence list.</span></span> <span data-ttu-id="fdeb2-151">In base al tipo di ricorrenza, immettere un intervallo.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-151">Depending on the type of recurrence, enter an interval.</span></span>

15. <span data-ttu-id="fdeb2-152">Facoltativamente, fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-152">Optionally, click **Advanced**.</span></span>

16. <span data-ttu-id="fdeb2-153">Facoltativamente, modificare la data di inizio del messaggio di avviso digitando una data diversa o aprendo il calendario, quindi facendo clic su una data nel calendario.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-153">Optionally, change the date that the alert message starts on by typing a different date or opening the calendar, and then clicking a date in the calendar.</span></span>

     <span data-ttu-id="fdeb2-154">La data di inizio predefinita è la data corrente.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-154">The default start date is the current date.</span></span>

17. <span data-ttu-id="fdeb2-155">Facoltativamente, selezionare la casella di controllo accanto a **Arresta avviso il**, quindi scegliere una data di fine per il messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-155">Optionally, select the checkbox located next to **Stop alert on**, and then choose a date to stop the alert message.</span></span>

     <span data-ttu-id="fdeb2-156">Per impostazione predefinita, un messaggio di avviso non dispone di alcuna data di fine.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-156">By default, an alert message has no stop date.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="fdeb2-157">L'arresto di un messaggio di avviso non comporta l'eliminazione della definizione di avviso.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-157">Stopping an alert message does not delete the alert definition.</span></span> <span data-ttu-id="fdeb2-158">Dopo avere arrestato un messaggio di avviso, è possibile riavviarlo aggiornando le date di inizio e di fine.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-158">After you stop an alert message, you can restart it by updating the start and stop dates.</span></span> <span data-ttu-id="fdeb2-159">Per informazioni sull'eliminazione delle definizioni di avviso, vedere [Gestire gli avvisi dati in Gestione avvisi dati](manage-my-data-alerts-in-data-alert-manager.md).</span><span class="sxs-lookup"><span data-stu-id="fdeb2-159">For information about deleting alert definitions, see [Manage My Data Alerts in Data Alert Manager](manage-my-data-alerts-in-data-alert-manager.md).</span></span>

18. <span data-ttu-id="fdeb2-160">Facoltativamente, deselezionare la casella di controllo **Invia un messaggio solo se cambiano i risultati degli avvisi** .</span><span class="sxs-lookup"><span data-stu-id="fdeb2-160">Optionally, clear the **Send message only if results change** checkbox.</span></span>

     <span data-ttu-id="fdeb2-161">Se si inviano messaggi di avviso frequentemente e non si desidera ricevere informazioni ridondanti, non deselezionare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-161">If you send alert messages frequently, redundant information might not be welcome and you should not clear this checkbox.</span></span>

19. <span data-ttu-id="fdeb2-162">Immettere gli indirizzi di posta elettronica dei destinatari dei messaggi di avviso.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-162">Enter the email addresses of alert message recipients.</span></span> <span data-ttu-id="fdeb2-163">Separare gli indirizzi con punti e virgola.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-163">Separate addresses with semicolons.</span></span>

     <span data-ttu-id="fdeb2-164">Se disponibile, l'indirizzo di posta elettronica dell'utente che ha creato la definizione di avviso viene aggiunto alla casella dei **destinatari** .</span><span class="sxs-lookup"><span data-stu-id="fdeb2-164">If the email address of the person who created the alert definition is available, it is added to the **Recipient(s)** box.</span></span>

20. <span data-ttu-id="fdeb2-165">Facoltativamente, nella casella di testo **Oggetto** aggiornare la riga dell'oggetto del messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-165">Optionally, in the **Subject** text box, update the Subject line of the alert message.</span></span>

     <span data-ttu-id="fdeb2-166">L'oggetto predefinito è \*\*avviso dati per \<data alert name> \*\*.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-166">The default Subject is **Data alert for \<data alert name>**.</span></span>

21. <span data-ttu-id="fdeb2-167">Facoltativamente, digitare una descrizione per il messaggio di avviso nella casella di testo **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="fdeb2-167">Optionally, in the **Description** text box, type a description of the alert message.</span></span>

22. <span data-ttu-id="fdeb2-168">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fdeb2-168">Click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdeb2-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdeb2-169">See Also</span></span>
 <span data-ttu-id="fdeb2-170">Gestione avvisi dati della [finestra di progettazione Avviso dati](../../2014/reporting-services/data-alert-designer.md) [per gli amministratori di avvisi](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services avvisi dati](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="fdeb2-170">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Data Alert Manager for Alerting Administrators](../../2014/reporting-services/data-alert-manager-for-alerting-administrators.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


