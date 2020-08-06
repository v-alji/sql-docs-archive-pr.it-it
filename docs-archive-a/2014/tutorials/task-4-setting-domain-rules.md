---
title: 'Attività 4: impostazione delle regole di dominio | Microsoft Docs'
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3a7162ba-cf2f-481f-830d-bb6a02823827
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 42bdbd0228fdd3515f68ce830581f445242768e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624445"
---
# <a name="task-4-setting-domain-rules"></a><span data-ttu-id="d7c3f-102">Attività 4: Impostazione delle regole di dominio</span><span class="sxs-lookup"><span data-stu-id="d7c3f-102">Task 4: Setting Domain Rules</span></span>
  <span data-ttu-id="d7c3f-103">In questa attività viene creata una regola per il dominio di **posta elettronica di contatto** per verificare se l'indirizzo di posta elettronica termina con \*\* \@ Adventure-Works.com\*\*.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-103">In this task, you create a rule for the **Contact Email** domain to verify if the email address ends with **\@adventure-works.com**.</span></span> <span data-ttu-id="d7c3f-104">Per ulteriori informazioni sulla pagina, vedere l'argomento [creazione di una regola di dominio](https://msdn.microsoft.com/library/hh510397.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d7c3f-104">See [Creating a Domain Rule](https://msdn.microsoft.com/library/hh510397.aspx) topic for more details on the page.</span></span>  
  
1.  <span data-ttu-id="d7c3f-105">Fare clic su **Contact email** nell' **elenco di domini**.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-105">Click **Contact Email** in the **Domain list**.</span></span>  
  
2.  <span data-ttu-id="d7c3f-106">Passare alla scheda **regole di dominio** nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-106">Switch to the **Domain Rules** tab in the right pane.</span></span>  
  
     <span data-ttu-id="d7c3f-107">![Pulsante della barra degli strumenti Aggiungi nuova regola di dominio](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Pulsante della barra degli strumenti Aggiungi nuova regola di dominio")</span><span class="sxs-lookup"><span data-stu-id="d7c3f-107">![Add a New Domain Rule Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-01.jpg "Add a New Domain Rule Toolbar Button")</span></span>  
  
3.  <span data-ttu-id="d7c3f-108">Nel riquadro destro fare clic sul pulsante **Aggiungi una nuova regola di dominio** sulla barra degli strumenti (vedere l'immagine) per aggiungere una regola.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-108">In the right pane, click **Add a new domain rule** button on the toolbar (see the image) to add a rule.</span></span>  
  
4.  <span data-ttu-id="d7c3f-109">Digitare **email Validation** per il **nome della regola** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-109">Type **Email Validation** for the **rule name** and press **ENTER**.</span></span> <span data-ttu-id="d7c3f-110">Per impostazione predefinita, la casella di controllo **attiva** deve essere selezionata.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-110">The **Active** check box should be checked by default.</span></span> <span data-ttu-id="d7c3f-111">Questo controllo consente di disattivare temporaneamente una regola.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-111">This control allows you to deactivate a rule temporarily.</span></span>  
  
5.  <span data-ttu-id="d7c3f-112">Nel riquadro **Compila una regola** fare clic sulla **freccia in giù**e selezionare il **valore termina con**.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-112">In the **Build a Rule** pane, click **down arrow**, and select **Value ends with**.</span></span>  
  
6.  <span data-ttu-id="d7c3f-113">Digitare \*\* \@ Adventure-Works.com\*\* nella casella di testo e premere **Tab**.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-113">Type **\@adventure-works.com** in the text box and press **TAB**.</span></span> <span data-ttu-id="d7c3f-114">È possibile aggiungere altre condizioni facendo clic sul pulsante **Aggiungi una nuova condizione al pulsante della** barra degli strumenti della clausola selezionata nel riquadro **Compila una regola** .</span><span class="sxs-lookup"><span data-stu-id="d7c3f-114">You can add more conditions by clicking **Add a new condition to the selected clause** toolbar button in the **Build a Rule** pane.</span></span>  
  
     <span data-ttu-id="d7c3f-115">![Regola di convalida posta elettronica](../../2014/tutorials/media/et-settingdomainrules-02.jpg "Regola di convalida posta elettronica")</span><span class="sxs-lookup"><span data-stu-id="d7c3f-115">![Email Validation Rule](../../2014/tutorials/media/et-settingdomainrules-02.jpg "Email Validation Rule")</span></span>  
  
7.  <span data-ttu-id="d7c3f-116">Fare clic sul pulsante **Esegui la regola del dominio selezionato sui dati di test** sulla barra degli strumenti nel riquadro destro per testare la regola rispetto ai dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-116">Click **Run the selected domain rule on test data** button on the toolbar in the right pane to test the rule against sample data.</span></span>  
  
     <span data-ttu-id="d7c3f-117">![Pulsante della barra degli strumenti sull'esecuzione della regola di dominio nel test dei dati](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Pulsante della barra degli strumenti sull'esecuzione della regola di dominio nel test dei dati")</span><span class="sxs-lookup"><span data-stu-id="d7c3f-117">![Run the Domain Rule on Test Data Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-03.jpg "Run the Domain Rule on Test Data Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="d7c3f-118">Nella finestra di dialogo **testa regola di dominio** fare clic sul pulsante **Aggiungi un nuovo termine di test per la regola di dominio** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-118">In the **Test Domain Rule** dialog box, click **Adds a new testing term for the domain rule** button on the toolbar.</span></span>  
  
     <span data-ttu-id="d7c3f-119">![Finestra di dialogo Esegui la regola di dominio](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Finestra di dialogo Esegui la regola di dominio")</span><span class="sxs-lookup"><span data-stu-id="d7c3f-119">![Test Domain Rule Dialog Box](../../2014/tutorials/media/et-settingdomainrules-04.jpg "Test Domain Rule Dialog Box")</span></span>  
  
9. <span data-ttu-id="d7c3f-120">Digitare **frank7 \@ Adventure-Works.com** (un valore valido) nella colonna **Contact email** .</span><span class="sxs-lookup"><span data-stu-id="d7c3f-120">Type **frank7\@adventure-works.com** (a valid value) in the **Contact Email** column.</span></span>  
  
10. <span data-ttu-id="d7c3f-121">Ripetere i due passaggi precedenti per aggiungere **joe2 \@ Adventure-Work.com** (un valore non valido senza ' s').</span><span class="sxs-lookup"><span data-stu-id="d7c3f-121">Repeat previous two steps to add **joe2\@adventure-work.com** (an invalid value with no 's').</span></span>  
  
11. <span data-ttu-id="d7c3f-122">Fare clic sull'ultimo pulsante (**testa la regola di dominio su tutti i termini**) sulla barra degli strumenti per testare i dati di input rispetto alla regola.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-122">Click the last button (**Test the domain rule on all the terms**) on the toolbar to test the input data against the rule.</span></span>  
  
     <span data-ttu-id="d7c3f-123">![Pulsante della barra degli strumenti Testa la regola di dominio su tutti i termini](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Pulsante della barra degli strumenti Testa la regola di dominio su tutti i termini")</span><span class="sxs-lookup"><span data-stu-id="d7c3f-123">![Test the Domain Rule on All Terms Toolbar Button](../../2014/tutorials/media/et-settingdomainrules-05.jpg "Test the Domain Rule on All Terms Toolbar Button")</span></span>  
  
12. <span data-ttu-id="d7c3f-124">Si noti che la prima voce viene visualizzata come un elemento valido e la seconda come un elemento non valido.</span><span class="sxs-lookup"><span data-stu-id="d7c3f-124">Notice that the first entry is shown as a valid item and the second one as an invalid item.</span></span>  
  
     <span data-ttu-id="d7c3f-125">![Risultati di Testa regole di dominio](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Risultati di Testa regole di dominio")</span><span class="sxs-lookup"><span data-stu-id="d7c3f-125">![Test Domain Rule Results](../../2014/tutorials/media/et-settingdomainrules-06.jpg "Test Domain Rule Results")</span></span>  
  
13. <span data-ttu-id="d7c3f-126">Fare clic su **Chiudi** per chiudere la finestra di dialogo **testa regola di dominio** .</span><span class="sxs-lookup"><span data-stu-id="d7c3f-126">Click **Close** to close the **Test Domain Rule** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d7c3f-127">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="d7c3f-127">Next Step</span></span>  
 [<span data-ttu-id="d7c3f-128">Attività 5: Impostazione delle relazioni basate su termini</span><span class="sxs-lookup"><span data-stu-id="d7c3f-128">Task 5: Setting Term Based Relationships</span></span>](../../2014/tutorials/task-5-setting-term-based-relationships.md)  
  
  
