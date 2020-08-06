---
title: 'Attività 1: creazione di una Knowledge base e di domini | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 7d74a60b-8933-4038-bcbb-4e9dcc4f70e9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce1b22e3d677e831a1d518dacc1267ad0e6be236
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714927"
---
# <a name="task-1-creating-a-knowledge-base-and-domains"></a><span data-ttu-id="3f2bc-102">Attività 1: Creazione di una Knowledge Base e dei domini</span><span class="sxs-lookup"><span data-stu-id="3f2bc-102">Task 1: Creating a Knowledge Base and Domains</span></span>
  <span data-ttu-id="3f2bc-103">In questa attività verrà creata la Knowledge base **Suppliers** e verranno creati i domini utilizzati per la pulizia dei dati e la corrispondenza dei dati per rimuovere i duplicati.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-103">In this task, you create the **Suppliers** knowledge base and create domains that is used for cleansing data and matching data to remove duplicates.</span></span>  
  
1.  <span data-ttu-id="3f2bc-104">Avviare **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-104">Launch **Data Quality Client**.</span></span> <span data-ttu-id="3f2bc-105">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2012**, fare clic su **Data Quality Services**, quindi su **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-105">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2012**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="3f2bc-106">Nella finestra di dialogo **Connetti al server** selezionare l'istanza del server di database in cui è installato DQS, quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-106">In the **Connect to Server** dialog box, select the database server instance on which the DQS is installed, and click **Connect**.</span></span>  
  
     <span data-ttu-id="3f2bc-107">![Finestra di dialogo Connetti al server](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Finestra di dialogo Connetti al server")</span><span class="sxs-lookup"><span data-stu-id="3f2bc-107">![Connect to Server Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-01.jpg "Connect to Server Dialog Box")</span></span>  
  
3.  <span data-ttu-id="3f2bc-108">Nella home page Data Quality Client, nel riquadro **Gestione Knowledge base** , fare clic su **nuova Knowledge base**.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-108">In the Data Quality Client home page, in the **Knowledge Base Management** pane, click **New Knowledge Base**.</span></span>  
  
     <span data-ttu-id="3f2bc-109">![Gestione Knowledge Base - Nuova KB](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Gestione Knowledge Base - Nuova KB")</span><span class="sxs-lookup"><span data-stu-id="3f2bc-109">![Knowledge Base Management - New KB](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-02.jpg "Knowledge Base Management - New KB")</span></span>  
  
4.  <span data-ttu-id="3f2bc-110">Immettere **Suppliers** per **nome** della Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-110">Enter **Suppliers** for **Name** of the knowledge base.</span></span>  
  
     <span data-ttu-id="3f2bc-111">![Nuova Knowledge Base - Gestione dominio](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "Nuova Knowledge Base - Gestione dominio")</span><span class="sxs-lookup"><span data-stu-id="3f2bc-111">![New Knowledge Base - Domain Management](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-03.jpg "New Knowledge Base - Domain Management")</span></span>  
  
5.  <span data-ttu-id="3f2bc-112">Verificare che il campo **Crea Knowledge base da** sia impostato su **nessuno** perché la Knowledge base **Suppliers** viene creata da zero.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-112">Confirm that **Create Knowledge Base from** field is set to **None** since you are creating the **Suppliers** knowledge base from scratch.</span></span>  
  
6.  <span data-ttu-id="3f2bc-113">Verificare che sia selezionata l'opzione **Gestione dominio** per l' **attività** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-113">Confirm that **Domain Management** is selected for the **Activity** and click **Next**.</span></span> <span data-ttu-id="3f2bc-114">L'attività Gestione dominio consente di creare e gestire domini nella Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-114">The Domain Management activity lets you create and manage domains in the knowledge base.</span></span>  
  
7.  <span data-ttu-id="3f2bc-115">Nella finestra **Gestione dominio** fare clic sul pulsante della barra degli strumenti **Crea un dominio** per creare un dominio.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-115">In the **Domain Management** window, click **Create a domain** toolbar button to create a domain.</span></span>  
  
     <span data-ttu-id="3f2bc-116">![Pulsante della barra degli strumenti Crea dominio](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Pulsante della barra degli strumenti Crea dominio")</span><span class="sxs-lookup"><span data-stu-id="3f2bc-116">![Create Domain Toolbar Button](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-04.jpg "Create Domain Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="3f2bc-117">Nella finestra di dialogo **Crea dominio** digitare **Supplier ID** per il **nome di dominio**e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-117">In the **Create Domain** dialog box, type **Supplier ID** for the **Domain Name**, and click **OK**.</span></span>  
  
     <span data-ttu-id="3f2bc-118">![Finestra di dialogo Crea dominio](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Finestra di dialogo Crea dominio")</span><span class="sxs-lookup"><span data-stu-id="3f2bc-118">![Create Domain Dialog Box](../../2014/tutorials/media/et-creatingaknowledgebaseanddomains-05.jpg "Create Domain Dialog Box")</span></span>  
  
9. <span data-ttu-id="3f2bc-119">Ripetere il passaggio precedente per creare i seguenti domini con tutte le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-119">Repeat previous step to create the following domains with all the default settings.</span></span> <span data-ttu-id="3f2bc-120">Per semplificare l'esercitazione, impostare il tipo di **dati** di tutti i domini come **stringa**.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-120">To keep the tutorial simple, you set the **Data Type** of all the domains as **String**.</span></span> <span data-ttu-id="3f2bc-121">Gli altri tipi di dati consentiti sono Integer, Decimal e Data.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-121">The other allowed data types are: Integer, Decimal, and Date.</span></span> <span data-ttu-id="3f2bc-122">Quando si seleziona l'opzione **Usa valori iniziali** (impostazione predefinita), tutti i sinonimi vengono sostituiti con il valore principale del gruppo di sinonimi nell'output.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-122">When the **Use Leading Values** option is selected (default), all synonyms are replaced with the leading value of the synonym group in the output.</span></span> <span data-ttu-id="3f2bc-123">L'impostazione dell'opzione **Normalizza stringa** (impostazione predefinita) consente di rimuovere tutti i caratteri speciali nei valori di dominio.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-123">Setting **Normalize String** option (default) removes any special characters in the domain values.</span></span> <span data-ttu-id="3f2bc-124">L'opzione **Format output to** consente di selezionare la formattazione applicata quando vengono restituiti i valori dei dati nel dominio.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-124">The **Format Output to** option lets you select the formatting that is applied when the data values in the domain are output.</span></span> <span data-ttu-id="3f2bc-125">Selezionare **Abilita correttore ortografico** (impostazione predefinita) per eseguire il correttore ortografico su tutti i valori stringa durante il popolamento del dominio.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-125">Select **Enable Speller** (default) to run Speller on all string values when populating the domain.</span></span> <span data-ttu-id="3f2bc-126">L'impostazione della **lingua** specifica la versione della lingua del **correttore ortografico** che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-126">The **Language** setting specifies which language version of the **Speller** you want to apply.</span></span> <span data-ttu-id="3f2bc-127">Selezionare **Disabilita algoritmi di errore sintassi** per popolare il dominio senza verificare la presenza di errori di sintassi nei valori stringa.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-127">Select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span> <span data-ttu-id="3f2bc-128">Per ulteriori informazioni, vedere l'argomento relativo alla [creazione di un dominio](https://msdn.microsoft.com/library/hh510401.aspx) in MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="3f2bc-128">See [Create a Domain](https://msdn.microsoft.com/library/hh510401.aspx) topic in the MSDN library for more details.</span></span>  
  
    -   <span data-ttu-id="3f2bc-129">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="3f2bc-129">Supplier Name</span></span>  
  
    -   <span data-ttu-id="3f2bc-130">Indirizzo di posta elettronica del contatto</span><span class="sxs-lookup"><span data-stu-id="3f2bc-130">Contact Email</span></span>  
  
    -   <span data-ttu-id="3f2bc-131">Riga indirizzo</span><span class="sxs-lookup"><span data-stu-id="3f2bc-131">Address Line</span></span>  
  
    -   <span data-ttu-id="3f2bc-132">Città</span><span class="sxs-lookup"><span data-stu-id="3f2bc-132">City</span></span>  
  
    -   <span data-ttu-id="3f2bc-133">State</span><span class="sxs-lookup"><span data-stu-id="3f2bc-133">State</span></span>  
  
    -   <span data-ttu-id="3f2bc-134">Paese</span><span class="sxs-lookup"><span data-stu-id="3f2bc-134">Country</span></span>  
  
    -   <span data-ttu-id="3f2bc-135">Zip</span><span class="sxs-lookup"><span data-stu-id="3f2bc-135">Zip</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="3f2bc-136">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3f2bc-136">Next Step</span></span>  
 [<span data-ttu-id="3f2bc-137">Attività 2: Aggiunta manuale di valori di dominio</span><span class="sxs-lookup"><span data-stu-id="3f2bc-137">Task 2: Adding Domain Values Manually</span></span>](../../2014/tutorials/task-2-adding-domain-values-manually.md)  
  
  
