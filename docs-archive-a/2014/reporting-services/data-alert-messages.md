---
title: Messaggi di avviso dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6819720c-d848-4b90-9b51-89501b4f4645
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d50c3dd24c0057f695a9318c5eef7ad9e7540a45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630355"
---
# <a name="data-alert-messages"></a><span data-ttu-id="88586-102">Messaggi di avviso dati</span><span class="sxs-lookup"><span data-stu-id="88586-102">Data Alert Messages</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="88586-103">Gli avvisi dati di Reporting Services consentono di recapitare due tipi di messaggi di avviso dati tramite posta elettronica: messaggi con risultati degli avvisi dati e messaggi con descrizioni degli errori.</span><span class="sxs-lookup"><span data-stu-id="88586-103">data alerts deliver two types of data alert messages by email: Messages with data alert results and messages with error descriptions.</span></span> <span data-ttu-id="88586-104">I messaggi con i risultati consentono di tenere informati tutti i destinatari sulle modifiche ai dati dei report di interesse comune e importanti per le decisioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="88586-104">Messages with results keep all recipients informed about changes in report data that is of common interest and important to business decisions.</span></span> <span data-ttu-id="88586-105">Se per qualche motivo si verifica un errore e i risultati non sono disponibili, viene inviato il messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="88586-105">If for some reason an error occurs and the results are not available, the error message is sent instead.</span></span>

 <span data-ttu-id="88586-106">Il proprietario della definizione di avviso dati può inoltre visualizzare le informazioni sull'istanza di avviso dati in Gestione avvisi dati.</span><span class="sxs-lookup"><span data-stu-id="88586-106">The owner of the data alert definition also can view information about the data alert instance in Data Alert Manager.</span></span> <span data-ttu-id="88586-107">Per altre informazioni, vedere [Gestione avvisi dati per utenti di SharePoint](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span><span class="sxs-lookup"><span data-stu-id="88586-107">For more information, see [Data Alert Manager for SharePoint Users](../../2014/reporting-services/data-alert-manager-for-sharepoint-users.md).</span></span>

##  <a name="data-alert-messages"></a><a name="DataAlertMessages"></a><span data-ttu-id="88586-108">Messaggi di avviso dati</span><span class="sxs-lookup"><span data-stu-id="88586-108">Data Alert Messages</span></span>
 <span data-ttu-id="88586-109">Nelle figure seguenti sono illustrati un messaggio di avviso dati con risultati e un messaggio di avviso con una descrizione di un errore.</span><span class="sxs-lookup"><span data-stu-id="88586-109">The following pictures show a data alert message with results and an alert message with an error description.</span></span>

 <span data-ttu-id="88586-110">**Messaggio dei risultati**</span><span class="sxs-lookup"><span data-stu-id="88586-110">**Results message**</span></span>

 <span data-ttu-id="88586-111">![Messaggio di posta elettronica di avviso dati con risultati](media/rs-alertmessageresults.gif "Messaggio di posta elettronica di avviso dati con risultati")</span><span class="sxs-lookup"><span data-stu-id="88586-111">![Data alert e-mail message with results](media/rs-alertmessageresults.gif "Data alert e-mail message with results")</span></span>

 <span data-ttu-id="88586-112">**Messaggio di errore**</span><span class="sxs-lookup"><span data-stu-id="88586-112">**Error message**</span></span>

 <span data-ttu-id="88586-113">![Messaggio di avviso dati con messaggio di errore](media/rs-alertmessageerrror.gif "Messaggio di avviso dati con messaggio di errore")</span><span class="sxs-lookup"><span data-stu-id="88586-113">![Data alert message with error message](media/rs-alertmessageerrror.gif "Data alert message with error message")</span></span>

 <span data-ttu-id="88586-114">I messaggi includono gli stessi tipi di informazioni.</span><span class="sxs-lookup"><span data-stu-id="88586-114">The messages include the same types of information.</span></span>

1.  <span data-ttu-id="88586-115">**Per conto di** contiene il nome dell'utente che ha creato la definizione di avviso dati.</span><span class="sxs-lookup"><span data-stu-id="88586-115">**On behalf of** contains the name of the person who created the data alert definition.</span></span>

2.  <span data-ttu-id="88586-116">Se nella definizione di avviso è stata fornita una descrizione, viene visualizzata al di sotto di **Per conto di**.</span><span class="sxs-lookup"><span data-stu-id="88586-116">If you provided a description in the alert definition, it displays below **On behalf of**.</span></span>

3.  <span data-ttu-id="88586-117">**Risultati degli avvisi** indica le righe nel feed di dati del report che soddisfano le regole specificate nella definizione di avviso in formato tabulare, in alternativa contiene una descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="88586-117">**Alert Results** display the rows in the report data feed that satisfy the rules specified in the alert definition in a tabular format or display an error description.</span></span> <span data-ttu-id="88586-118">Non vi sono limiti al numero di righe visualizzate.</span><span class="sxs-lookup"><span data-stu-id="88586-118">There is no limit on the number of rows that displays.</span></span>

4.  <span data-ttu-id="88586-119">**Vai a report** è un collegamento al report in base al quale viene compilata la definizione di avviso.</span><span class="sxs-lookup"><span data-stu-id="88586-119">**Go to report** is a link to the report that the alert definition is built upon.</span></span> <span data-ttu-id="88586-120">Se il collegamento non è valido perché il report è stato spostato o eliminato, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="88586-120">If the link is not valid because the report was moved or deleted, an error message displays.</span></span>

5.  <span data-ttu-id="88586-121">**Regole** indica le regole e le clausole nella definizione di avviso.</span><span class="sxs-lookup"><span data-stu-id="88586-121">**Rule(s)** lists the rules and clauses in the alert definition.</span></span> <span data-ttu-id="88586-122">Queste informazioni consentono di verificare e comprendere i risultati degli avvisi e di identificare le regole nella definizione di avviso dati che potrebbe essere necessario modificare per restringere o ampliare i risultati.</span><span class="sxs-lookup"><span data-stu-id="88586-122">This information helps you verify and understand the alert results and identify rules in the data alert definition that you might want to change to narrow or broaden results.</span></span>

6.  <span data-ttu-id="88586-123">**Parametri report** indica i parametri e i valori dei parametri usati per l'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="88586-123">**Report parameters** list the parameters and parameter values that were used when the report was run.</span></span> <span data-ttu-id="88586-124">I parametri e i valori dei parametri aiutano a comprendere i risultati degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="88586-124">Parameters and parameter values help you understand the alert results.</span></span>

7.  <span data-ttu-id="88586-125">**Contextual values** (Valori contestuali) indica i nomi e i valori degli elementi del report esterni alle aree dati del report.</span><span class="sxs-lookup"><span data-stu-id="88586-125">**Contextual values** list the names and values of report items that are outside of the report data regions.</span></span> <span data-ttu-id="88586-126">Tali elementi sono in genere costituiti da caselle di testo.</span><span class="sxs-lookup"><span data-stu-id="88586-126">The items are typically text boxes.</span></span> <span data-ttu-id="88586-127">Ad esempio, una casella di testo con un valore costante come l'oggetto o la descrizione di un report.</span><span class="sxs-lookup"><span data-stu-id="88586-127">For example, a text box with a constant value such as the subject or description of a report.</span></span>

 <span data-ttu-id="88586-128">L'unica differenza tra i due tipi di messaggi è l'elemento 5, **Risultati degli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="88586-128">The only difference between the two message types is item 5, **Alert Results**.</span></span> <span data-ttu-id="88586-129">Se si verifica un errore quando viene creato un messaggio di avviso o un'istanza di avviso dati, in **Risultati degli avvisi** viene visualizzato un messaggio di errore che descrive il problema.</span><span class="sxs-lookup"><span data-stu-id="88586-129">If an error occurs when a data alert instance or data alert message is created, **Alert Results** displays an error message that describes the problem.</span></span> <span data-ttu-id="88586-130">Il messaggio di errore, inviato a tutti i destinatari, serve per comunicare che i risultati degli avvisi attesi e che potrebbero essere necessari per prendere decisioni aziendali non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="88586-130">The error message, sent to all recipients, let them know that the alert results that they are expecting and might rely on to make business decisions are not available.</span></span>

 

##  <a name="related-tasks"></a><a name="HowTo"></a> <span data-ttu-id="88586-131">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="88586-131">Related Tasks</span></span>
 <span data-ttu-id="88586-132">In questa sezione vengono elencate le procedure in cui viene illustrato come creare e modificare le definizioni di avviso dati che forniscono molte delle informazioni incluse nei messaggi di avviso dati.</span><span class="sxs-lookup"><span data-stu-id="88586-132">This section lists procedures that show you how to create and edit the data alert definitions that provide much of the information that you see in data alert messages.</span></span>

-   [<span data-ttu-id="88586-133">Creare un avviso dati nella finestra di progettazione Avviso dati</span><span class="sxs-lookup"><span data-stu-id="88586-133">Create a Data Alert in Data Alert Designer</span></span>](create-a-data-alert-in-data-alert-designer.md)

-   [<span data-ttu-id="88586-134">Modificare un avviso dati nella finestra di progettazione di avvisi</span><span class="sxs-lookup"><span data-stu-id="88586-134">Edit a Data Alert in Alert Designer</span></span>](edit-a-data-alert-in-alert-designer.md)



## <a name="see-also"></a><span data-ttu-id="88586-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88586-135">See Also</span></span>
 <span data-ttu-id="88586-136">[Finestra di progettazione Avviso dati](../../2014/reporting-services/data-alert-designer.md) [Reporting Services avvisi dati](../ssms/agent/alerts.md)</span><span class="sxs-lookup"><span data-stu-id="88586-136">[Data Alert Designer](../../2014/reporting-services/data-alert-designer.md) [Reporting Services Data Alerts](../ssms/agent/alerts.md)</span></span>


