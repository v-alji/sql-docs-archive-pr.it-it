---
title: Creare un dominio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.createdomain.f1
ms.assetid: 5c4828f5-bd51-4c29-b3de-87b7d2f2d3e5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fad6abd795aa9412bb71d251623d92d3e13b889c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624974"
---
# <a name="create-a-domain"></a><span data-ttu-id="34c41-102">Creazione di un dominio</span><span class="sxs-lookup"><span data-stu-id="34c41-102">Create a Domain</span></span>
  <span data-ttu-id="34c41-103">In questo argomento viene descritto come creare un dominio in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="34c41-103">This topic describes how to create a domain in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="34c41-104">I valori nel dominio sono una rappresentazione semantica dei dati in un campo.</span><span class="sxs-lookup"><span data-stu-id="34c41-104">The values in the domain are a semantic representation of the data in a field.</span></span> <span data-ttu-id="34c41-105">Per altre informazioni sui domini, vedere [Gestione di un dominio](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="34c41-105">For more information on domains, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
 <span data-ttu-id="34c41-106">Sono disponibili due modi per creare un nuovo dominio.</span><span class="sxs-lookup"><span data-stu-id="34c41-106">There are two ways to create a new domain.</span></span> <span data-ttu-id="34c41-107">Il primo viene utilizzato durante il passaggio di mapping dell'attività di individuazione delle informazioni, quando è in corso l'analisi di un campione di dati per aggiungere informazioni a una Knowledge Base nuova o esistente.</span><span class="sxs-lookup"><span data-stu-id="34c41-107">The first is during the Map step of the knowledge discovery activity, when you are in the process of analyzing a data sample to add knowledge to a new or existing knowledge base.</span></span> <span data-ttu-id="34c41-108">Il secondo viene utilizzato durante l'attività di gestione del dominio, quando anziché modificare un dominio esistente, se ne crea uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="34c41-108">The second is during the domain management activity, when instead of changing an existing domain, you create a new one.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="34c41-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="34c41-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="34c41-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="34c41-110">Prerequisites</span></span>  
 <span data-ttu-id="34c41-111">Per creare un dominio, è necessario avere creato e aperto una Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="34c41-111">To create a domain, you must have created and opened a knowledge base.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="34c41-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="34c41-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="34c41-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="34c41-113">Permissions</span></span>  
 <span data-ttu-id="34c41-114">Per creare un dominio, è necessario disporre del ruolo dqs_kb_editor o dqs_administrator nel database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="34c41-114">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to create a domain.</span></span>  
  
##  <a name="create-a-domain-in-the-knowledge-discovery-activity"></a><a name="Discovery"></a> <span data-ttu-id="34c41-115">Creare un dominio nell'attività di individuazione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="34c41-115">Create a Domain in the Knowledge Discovery Activity</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="34c41-116">[Eseguire l'applicazione Data Quality Client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="34c41-116">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="34c41-117">Nella schermata iniziale di [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , fare clic su **Apri Knowledge Base** , quindi selezionare una Knowledge Base o fare clic su **Nuova Knowledge Base** e immettere le proprietà per la nuova Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="34c41-117">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
3.  <span data-ttu-id="34c41-118">Selezionare **Individuazione informazioni** come attività, quindi fare clic su **Crea** per creare la nuova Knowledge Base, oppure **Apri** per aprirne una esistente.</span><span class="sxs-lookup"><span data-stu-id="34c41-118">Select **Knowledge Discovery** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
4.  <span data-ttu-id="34c41-119">Nella pagina **Mappa** specificare una connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="34c41-119">On the **Map** page, specify a connection to the data source.</span></span> <span data-ttu-id="34c41-120">Per ulteriori informazioni, vedere [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="34c41-120">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span></span>  
  
5.  <span data-ttu-id="34c41-121">Nella tabella **Mapping** selezionare una colonna di origine dall'elenco a discesa per la **Colonna di origine** di una riga vuota.</span><span class="sxs-lookup"><span data-stu-id="34c41-121">In the **Mappings** table, select a source column from the drop-down list for the **Source Column** column of an empty row.</span></span> <span data-ttu-id="34c41-122">Se non esiste alcun dominio corrispondente, fare clic sull'icona **Crea un dominio** .</span><span class="sxs-lookup"><span data-stu-id="34c41-122">If no corresponding domain exists, click the **Create a Domain** icon.</span></span>  
  
##  <a name="create-a-domain-in-the-domain-management-activity"></a><a name="DomainManagement"></a><span data-ttu-id="34c41-123">Creare un dominio nell'attività di gestione del dominio</span><span class="sxs-lookup"><span data-stu-id="34c41-123">Create a Domain in the Domain Management Activity</span></span>  
  
1.  <span data-ttu-id="34c41-124">Nella schermata iniziale di [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , fare clic su **Apri Knowledge Base** , quindi selezionare una Knowledge Base o fare clic su **Nuova Knowledge Base** e immettere le proprietà per la nuova Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="34c41-124">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
2.  <span data-ttu-id="34c41-125">Selezionare **Gestione dominio** come attività, quindi fare clic su **Crea** per creare la nuova Knowledge Base, oppure **Apri** per aprirne una esistente.</span><span class="sxs-lookup"><span data-stu-id="34c41-125">Select **Domain Management** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
3.  <span data-ttu-id="34c41-126">Nella pagina **Gestione dominio** fare clic sull'icona **Crea un dominio** sopra l'elenco di domini.</span><span class="sxs-lookup"><span data-stu-id="34c41-126">On the **Domain Management** page, click the **Create a Domain** icon above the Domain list.</span></span>  
  
##  <a name="set-domain-properties"></a><a name="Properties"></a><span data-ttu-id="34c41-127">Impostare le proprietà del dominio</span><span class="sxs-lookup"><span data-stu-id="34c41-127">Set Domain Properties</span></span>  
  
1.  <span data-ttu-id="34c41-128">Nella finestra di dialogo **Crea dominio** immettere un nome univoco per la Knowledge Base e una descrizione di un massimo di 256 caratteri.</span><span class="sxs-lookup"><span data-stu-id="34c41-128">In the **Create Domain** dialog box, enter a name that is unique to the knowledge base and a description up to 256 characters.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="34c41-129">Per ulteriori informazioni sulle proprietà del dominio, vedere [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span><span class="sxs-lookup"><span data-stu-id="34c41-129">For more information about domain properties, see [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span></span>  
  
2.  <span data-ttu-id="34c41-130">Dall'elenco **Tipo di dati** selezionare un tipo di dati per i valori nel dominio.</span><span class="sxs-lookup"><span data-stu-id="34c41-130">From the **Data Type** list, select a data type for the values in the domain.</span></span> <span data-ttu-id="34c41-131">Il tipo di dati può essere **Stringa** (valore predefinito), **Data**, **Intero**o **Decimale**.</span><span class="sxs-lookup"><span data-stu-id="34c41-131">The data type can be **String** (the default), **Date**, **Integer**, or **Decimal**.</span></span>  
  
3.  <span data-ttu-id="34c41-132">Selezionare **Utilizza valori iniziali** per specificare che venga restituito il valore iniziale in un gruppo di sinonimi anziché un valore di cui è sinonimo.</span><span class="sxs-lookup"><span data-stu-id="34c41-132">Select **Use Leading Values** to specify that the leading value in a group of synonyms will be output instead of a value that is a synonym to it.</span></span> <span data-ttu-id="34c41-133">Deselezionare **Utilizza valori iniziali** per specificare che ogni valore di sinonimo verrà restituito nella forma corretta e non verrà sostituito dal valore iniziale per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="34c41-133">Deselect **Use Leading Values** to specify that each synonym value is output in its correct or corrected form, and is not replaced by the leading value for its group.</span></span>  
  
4.  <span data-ttu-id="34c41-134">Se il tipo di dati è **Stringa**, selezionare **Normalizza stringa** per rimuovere i caratteri speciali nei valori di dominio migliorando la probabilità di corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="34c41-134">If the data type is **String**, select **Normalize String** to remove special characters in the domain values, which may improve the likelihood of matches.</span></span>  
  
5.  <span data-ttu-id="34c41-135">Dall'elenco a discesa **Formato output in** selezionare la formattazione che verrà applicata alla restituzione dei valori dei dati nel dominio.</span><span class="sxs-lookup"><span data-stu-id="34c41-135">From the **Format Output to** drop-down list, select the formatting that will be applied when the data values in the domain are output.</span></span> <span data-ttu-id="34c41-136">La formattazione è specifica del tipo di dati selezionato nel passaggio 2, come mostrato nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="34c41-136">The formatting is specific to the data type selected in step 2, as shown in the following list:</span></span>  
  
    -   <span data-ttu-id="34c41-137">Per un valore stringa, è possibile specificare di restituire la stringa tutta in maiuscole, tutta in minuscole o solo con l'iniziale maiuscola.</span><span class="sxs-lookup"><span data-stu-id="34c41-137">For a string value, you can specify that the string be output as upper case, lower case, or capitalized.</span></span>  
  
    -   <span data-ttu-id="34c41-138">Per un valore data, è possibile specificare il formato del giorno, del mese e dell'anno.</span><span class="sxs-lookup"><span data-stu-id="34c41-138">For a date value, you can specify the format of the day, month, and year.</span></span>  
  
    -   <span data-ttu-id="34c41-139">Per un valore intero, è possibile specificare il tipo di maschera del formato da applicare.</span><span class="sxs-lookup"><span data-stu-id="34c41-139">For an integer value, you can specify the type of format mask to be applied.</span></span>  
  
    -   <span data-ttu-id="34c41-140">Per un valore decimale, è possibile specificare la precisione e il tipo di maschera del formato da applicare.</span><span class="sxs-lookup"><span data-stu-id="34c41-140">For a decimal value, you can specify the accuracy and the type of format mask to be applied.</span></span>  
  
     <span data-ttu-id="34c41-141">Se si seleziona **Nessuno** nell'elenco a discesa **Formato output in** non verrà applicato alcun formato tra quelli elencati.</span><span class="sxs-lookup"><span data-stu-id="34c41-141">Selecting **None** in the **Format Output to** drop-down list means none of the formats in the list will be applied.</span></span>  
  
6.  <span data-ttu-id="34c41-142">Se il tipo di dati è **Stringa**, nell'elenco a discesa **Lingua** selezionare la lingua da utilizzare per il correttore ortografico se viene abilitato.</span><span class="sxs-lookup"><span data-stu-id="34c41-142">If the data type is **String**, in the **Language** drop-down list, select which language version of the speller you want to apply if you enable the speller.</span></span>  
  
7.  <span data-ttu-id="34c41-143">Se il tipo di dati è **Stringa**, selezionare **Abilita correttore ortografico** per eseguire il correttore ortografico su tutti i valori stringa durante l'inserimento nel dominio.</span><span class="sxs-lookup"><span data-stu-id="34c41-143">If the data type is **String**, select **Enable Speller** to run the Speller on all string values when populating the domain.</span></span>  
  
8.  <span data-ttu-id="34c41-144">Se il tipo di dati è **Stringa**, selezionare **Disabilita algoritmi di errore sintassi** per popolare il dominio senza verificare la presenza di errori di sintassi nei valori stringa.</span><span class="sxs-lookup"><span data-stu-id="34c41-144">If the data type is **String**, select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span>  
  
9. <span data-ttu-id="34c41-145">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="34c41-145">Click **OK**.</span></span>  
  
10. <span data-ttu-id="34c41-146">Fare clic su **Fine** per completare l'attività di gestione del dominio, come descritto in [Sospensione dell'attività di gestione del dominio](../../2014/data-quality-services/end-the-domain-management-activity.md).</span><span class="sxs-lookup"><span data-stu-id="34c41-146">Click **Finish** to complete the domain management activity, as described in [End the Domain Management Activity](../../2014/data-quality-services/end-the-domain-management-activity.md).</span></span>  
  
##  <a name="follow-up-after-creating-a-domain"></a><a name="FollowUp"></a> <span data-ttu-id="34c41-147">Completamento: fasi successive alla creazione di un dominio</span><span class="sxs-lookup"><span data-stu-id="34c41-147">Follow Up: After Creating a Domain</span></span>  
 <span data-ttu-id="34c41-148">Dopo avere creato un dominio, è possibile eseguire ulteriori attività di gestione del dominio, quali l'individuazione delle informazioni per aggiungere informazioni al dominio o l'aggiunta di criteri di corrispondenza al dominio.</span><span class="sxs-lookup"><span data-stu-id="34c41-148">After you create a domain, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="34c41-149">Per altre informazioni, vedere [Eseguire l'individuazione delle informazioni](../../2014/data-quality-services/perform-knowledge-discovery.md), [Gestione di un dominio](../../2014/data-quality-services/managing-a-domain.md) o [Creare criteri di corrispondenza](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="34c41-149">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
