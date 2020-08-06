---
title: 'Attività 6: importazione di valori dal progetto cleane Supplier List | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fec0deef-a729-4ff1-b709-72d2b3f407ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b674cfb42ddf31c3b903a465d1be1b04e9a355ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625089"
---
# <a name="task-6-importing-values-from-the-cleanse-supplier-list-project"></a><span data-ttu-id="318e6-102">Attività 6: Importazione di valori dal progetto Cleanse Supplier List</span><span class="sxs-lookup"><span data-stu-id="318e6-102">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>
  <span data-ttu-id="318e6-103">In questa attività vengono importate le informazioni sulla qualità dei dati raccolte durante il processo di pulizia.</span><span class="sxs-lookup"><span data-stu-id="318e6-103">In this task, you import the data quality knowledge gathered during the cleansing process.</span></span> <span data-ttu-id="318e6-104">Per altri dettagli, vedere [importazione dei valori di un progetto di pulizia in un dominio](https://msdn.microsoft.com/library/hh479581.aspx) .</span><span class="sxs-lookup"><span data-stu-id="318e6-104">See [Importing Cleansing Project Values into a Domain](https://msdn.microsoft.com/library/hh479581.aspx) topic for more details.</span></span> <span data-ttu-id="318e6-105">È inoltre possibile esportare la Knowledge base in un file DQS prima di pubblicare la Knowledge base **Suppliers** aggiornata.</span><span class="sxs-lookup"><span data-stu-id="318e6-105">You also export the knowledge base into a DQS file before publishing the updated **Suppliers** knowledge base.</span></span>  
  
1.  <span data-ttu-id="318e6-106">Nella pagina principale del **client DQS**fare clic sulla **freccia a destra** accanto a **fornitori** in **Knowledge Base recenti** e quindi su **Gestione dominio**.</span><span class="sxs-lookup"><span data-stu-id="318e6-106">In the main page of **DQS Client**, click **right-arrow** next to **Suppliers** under **Recent Knowledge Bases** and click **Domain Management**.</span></span>  
  
2.  <span data-ttu-id="318e6-107">Fare clic su **Contact email** nell'elenco di domini e passare alla scheda **Domain values** nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="318e6-107">Click **Contact Email** in the list of domains, and switch to the **Domain Values** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="318e6-108">Fare clic sulla **freccia giù** accanto all'icona **Importa valori** sulla barra degli strumenti e fare clic su **Importa valori progetto**.</span><span class="sxs-lookup"><span data-stu-id="318e6-108">Click **down arrow** next to the **Import Values** icon on the toolbar and click **Import Project Values**.</span></span>  
  
     <span data-ttu-id="318e6-109">![Pulsante della barra degli strumenti Importa valori di progetto](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Pulsante della barra degli strumenti Importa valori di progetto")</span><span class="sxs-lookup"><span data-stu-id="318e6-109">![Import Project Values Toolbar Button](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Import Project Values Toolbar Button")</span></span>  
  
4.  <span data-ttu-id="318e6-110">Nella finestra di dialogo **Importa valori progetto** selezionare il progetto **Pulisci Supplier List** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="318e6-110">In the **Import Project Values** dialog box, select the **Cleanse Supplier List** project, and click **OK**.</span></span>  
  
5.  <span data-ttu-id="318e6-111">Si noti che tutti gli indirizzi di posta elettronica vengono importati insieme alle due correzioni apportate durante la pulizia interattiva.</span><span class="sxs-lookup"><span data-stu-id="318e6-111">Notice that all the emails are imported along with the two corrections you did during interactive cleansing.</span></span> <span data-ttu-id="318e6-112">Scorrere per visualizzare le due correzioni.</span><span class="sxs-lookup"><span data-stu-id="318e6-112">Scroll to see the two corrections.</span></span>  
  
    |<span data-ttu-id="318e6-113">Valore</span><span class="sxs-lookup"><span data-stu-id="318e6-113">Value</span></span>|<span data-ttu-id="318e6-114">Correggi in</span><span class="sxs-lookup"><span data-stu-id="318e6-114">Correct To</span></span>|  
    |-----------|----------------|  
    |bobby0@adventure-work.com|bobby0@adventure-works.com|  
    |tad0@adventure-work.com|tad0@adventure-works.com|  
  
6.  <span data-ttu-id="318e6-115">Ripetere il passaggio precedente dell'importazione dei valori del progetto per il dominio **Country** . si noti che è stata aggiunta una nuova voce per la correzione **dello stato United** a **Stati Uniti** (con ' s').</span><span class="sxs-lookup"><span data-stu-id="318e6-115">Repeat the previous step of importing project values for the **Country** domain and notice that a new entry is added for correcting **United State** to **United States** (with 's').</span></span>  
  
    |<span data-ttu-id="318e6-116">Valore</span><span class="sxs-lookup"><span data-stu-id="318e6-116">Value</span></span>|<span data-ttu-id="318e6-117">Correggi in</span><span class="sxs-lookup"><span data-stu-id="318e6-117">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="318e6-118">United State</span><span class="sxs-lookup"><span data-stu-id="318e6-118">United State</span></span>|<span data-ttu-id="318e6-119">Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="318e6-119">United States</span></span>|  
  
7.  <span data-ttu-id="318e6-120">Per visualizzare i valori di dominio precedenti, deselezionare la casella di controllo **Mostra solo nuovo** .</span><span class="sxs-lookup"><span data-stu-id="318e6-120">To see the old domain values, clear **Show Only New** checkbox.</span></span>  
  
8.  <span data-ttu-id="318e6-121">Ripetere il passaggio precedente per importare i valori di progetto per il dominio **Supplier Name** .</span><span class="sxs-lookup"><span data-stu-id="318e6-121">Repeat the previous step of importing project values for the **Supplier Name** domain.</span></span> <span data-ttu-id="318e6-122">Per impostazione predefinita, dopo l'importazione, verranno visualizzati solo i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="318e6-122">By default, after importing, you will only see the new values.</span></span> <span data-ttu-id="318e6-123">Per visualizzare tutti i valori, deselezionare la casella di controllo **Mostra solo nuovi** .</span><span class="sxs-lookup"><span data-stu-id="318e6-123">To see all the values, clear **Show Only New** check box.</span></span> <span data-ttu-id="318e6-124">La Knowledge base **Suppliers** è stata arricchita con i concetti appresi dall'attività di pulizia.</span><span class="sxs-lookup"><span data-stu-id="318e6-124">You have enriched the **Suppliers** knowledge base with what you learned from the cleansing activity.</span></span> <span data-ttu-id="318e6-125">Maggiore è l'attendibilità della Knowledge Base, migliori sono i risultati della pulizia.</span><span class="sxs-lookup"><span data-stu-id="318e6-125">The stronger the knowledge base is, the better the cleansing results are.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="318e6-126">Non è possibile importare valori per un dominio composito.</span><span class="sxs-lookup"><span data-stu-id="318e6-126">It is not possible import values for a composite domain.</span></span>  
  
9. <span data-ttu-id="318e6-127">Fare clic sull'icona **Esporta Knowledge base** sulla barra degli strumenti e quindi fare clic su **Esporta Knowledge base**.</span><span class="sxs-lookup"><span data-stu-id="318e6-127">Click **Export Knowledge Base** icon on the toolbar and then click **Export Knowledge Base**.</span></span>  
  
     <span data-ttu-id="318e6-128">![Menu Esporta Knowledge Base](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Menu Esporta Knowledge Base")</span><span class="sxs-lookup"><span data-stu-id="318e6-128">![Export Knowledge Base Menu](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Export Knowledge Base Menu")</span></span>  
  
10. <span data-ttu-id="318e6-129">Passare alla cartella tutorial, digitare **Suppliers. DQS** per il **nome del file**e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="318e6-129">Navigate to the Tutorial folder, type **Suppliers.dqs** for the **file name**, and click **Save**.</span></span> <span data-ttu-id="318e6-130">È possibile utilizzare questo file DQS per creare una nuova Knowledge Base basandosi su di esso.</span><span class="sxs-lookup"><span data-stu-id="318e6-130">You can use this DQS file to create a new knowledge base based on it.</span></span>  
  
11. <span data-ttu-id="318e6-131">Fare clic su **OK** per chiudere la finestra di messaggio **Esporta Knowledge base-fornitori** .</span><span class="sxs-lookup"><span data-stu-id="318e6-131">Click **OK** to close the **Export Knowledge Base - Suppliers** message box.</span></span>  
  
12. <span data-ttu-id="318e6-132">Fare clic su **fine** per completare l'attività.</span><span class="sxs-lookup"><span data-stu-id="318e6-132">Click **Finish** to finish the activity.</span></span>  
  
13. <span data-ttu-id="318e6-133">Fare clic su **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="318e6-133">Click **Publish**.</span></span>  
  
14. <span data-ttu-id="318e6-134">Fare clic su **OK** nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="318e6-134">Click **OK** on the message box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="318e6-135">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="318e6-135">Next Step</span></span>  
 [<span data-ttu-id="318e6-136">Lezione 3: Corrispondenza dei dati per rimuovere i duplicati dall'elenco fornitori</span><span class="sxs-lookup"><span data-stu-id="318e6-136">Lesson 3: Matching Data to Remove Duplicates from Supplier List</span></span>](../../2014/tutorials/lesson-3-matching-data-to-remove-duplicates-from-supplier-list.md)  
  
  
