---
title: Creare criteri Nome Finance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 56b2c852-fd69-4cd2-9b5d-977467b94fd9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 44ffff45f126d2ad9b73c5b8410b8f89ad2b0604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624667"
---
# <a name="create-the-finance-name-policy"></a><span data-ttu-id="79484-102">Creazione di criteri Nome Finance</span><span class="sxs-lookup"><span data-stu-id="79484-102">Create the Finance Name Policy</span></span>
  <span data-ttu-id="79484-103">In questa attività verrà creato un database denominato Finance, quindi una condizione per cui tutti i nomi di tabella devono iniziare con le lettere **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="79484-103">In this task, you will create a database named Finance, and then create a condition that requires all tables to start with the letters **fintbl**.</span></span> <span data-ttu-id="79484-104">Verranno quindi creati i criteri e una categoria di criteri per applicare uno standard di denominazione per le tabelle del database Finance.</span><span class="sxs-lookup"><span data-stu-id="79484-104">Then, you will create a policy and policy category to enforce a naming standard for tables in the Finance database.</span></span>  
  
### <a name="to-create-the-finance-database"></a><span data-ttu-id="79484-105">Per creare il database Finance</span><span class="sxs-lookup"><span data-stu-id="79484-105">To create the Finance database</span></span>  
  
1.  <span data-ttu-id="79484-106">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]aprire una finestra di query ed eseguire l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="79484-106">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window and execute the following statement:</span></span>  
  
    ```  
    CREATE DATABASE Finance ;  
    GO  
    ```  
  
2.  <span data-ttu-id="79484-107">In Esplora oggetti fare clic su **Database**, quindi premere F5 per aggiornare l'elenco dei database.</span><span class="sxs-lookup"><span data-stu-id="79484-107">In Object Explorer, click **Databases**, and then press F5 to refresh the list of databases.</span></span>  
  
### <a name="to-create-the-finance-tables-condition"></a><span data-ttu-id="79484-108">Per creare la condizione Tabelle Finance</span><span class="sxs-lookup"><span data-stu-id="79484-108">To create the Finance Tables condition</span></span>  
  
1.  <span data-ttu-id="79484-109">In Esplora oggetti espandere **Gestione**, espandere **Gestione criteri**, fare clic con il pulsante destro del mouse su **Condizioni**e quindi scegliere **Nuova condizione**.</span><span class="sxs-lookup"><span data-stu-id="79484-109">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Conditions**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="79484-110">Nella finestra di dialogo **Crea nuova condizione** , nella casella **Nome** digitare **Tabelle Finance**.</span><span class="sxs-lookup"><span data-stu-id="79484-110">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Tables**.</span></span>  
  
3.  <span data-ttu-id="79484-111">Nell'elenco **Facet** selezionare **Nome a più parti**.</span><span class="sxs-lookup"><span data-stu-id="79484-111">In the **Facet** list, select **Multipart Name**.</span></span>  
  
4.  <span data-ttu-id="79484-112">Nella casella **campo** dell'area **espressione** selezionare \*\* \@ nome\*\*. nella casella **operatore** selezionare **like**e nella casella **valore** digitare **' fintbl%'** per forzare tutti i nomi di tabella in modo che inizino con le lettere **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="79484-112">In the **Expression** area, in the **Field** box, select **\@Name**; in the **Operator** box, select **Like**; and in the **Value** box, type **'fintbl%'** to force all table names to start with the letters **fintbl**.</span></span>  
  
5.  <span data-ttu-id="79484-113">Nella pagina **Descrizione** digitare **I nomi di tabella del database Finance devono iniziare con fintbl**e quindi scegliere **OK** per creare la condizione.</span><span class="sxs-lookup"><span data-stu-id="79484-113">On the **Description** page, type **Finance table names must begin with fintbl**, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-finance-name-policy"></a><span data-ttu-id="79484-114">Per creare i criteri Nome Finance</span><span class="sxs-lookup"><span data-stu-id="79484-114">To create the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="79484-115">In Esplora oggetti fare clic con il pulsante destro del mouse su **Criteri**, quindi scegliere **Nuovi criteri**.</span><span class="sxs-lookup"><span data-stu-id="79484-115">In Object Explorer, right-click **Policies**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="79484-116">Nella finestra di dialogo **Crea nuovi criteri** , nella casella **Nome** digitare **Nome Finance**.</span><span class="sxs-lookup"><span data-stu-id="79484-116">In the **Create New Policy** dialog box, in the **Name** box, type **Finance Name**.</span></span>  
  
3.  <span data-ttu-id="79484-117">Nell'elenco **Condizione di controllo** selezionare **Tabelle Finance**.</span><span class="sxs-lookup"><span data-stu-id="79484-117">In the **Check condition** list, select **Finance Tables**.</span></span> <span data-ttu-id="79484-118">Questa opzione è disponibile nell'area **Nome a più parti** .</span><span class="sxs-lookup"><span data-stu-id="79484-118">This is in the **Multipart Name** area.</span></span>  
  
4.  <span data-ttu-id="79484-119">Nell'area **In base a** viene visualizzato un elenco di oggetti di database che hanno applicato i criteri.</span><span class="sxs-lookup"><span data-stu-id="79484-119">In the **Against** area you will see a list of the database objects that could apply this policy.</span></span> <span data-ttu-id="79484-120">Selezionare la casella di controllo **Ogni tabella**.</span><span class="sxs-lookup"><span data-stu-id="79484-120">Select the check box for **Every Table**.</span></span>  
  
5.  <span data-ttu-id="79484-121">Nell'area **Ogni database** espandere **Ogni**e fare clic su **Nuova condizione**.</span><span class="sxs-lookup"><span data-stu-id="79484-121">In the **Every Database** area, expand **Every**, and then click **New condition**.</span></span>  
  
6.  <span data-ttu-id="79484-122">Nella finestra di dialogo **Crea nuova condizione** , nella casella **Nome** digitare **Database Finance**.</span><span class="sxs-lookup"><span data-stu-id="79484-122">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Database**.</span></span>  
  
7.  <span data-ttu-id="79484-123">Nella casella **espressione** completare l'espressione in modo da includere il \*\* \@ nome = "Finance"\*\*, quindi fare clic su **OK** per chiudere la pagina della condizione.</span><span class="sxs-lookup"><span data-stu-id="79484-123">In the **Expression** box, complete the expression to include **\@Name = 'Finance'**, and then click **OK** to close the condition page.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="79484-124">Potrebbe essere necessario uscire dalla casella **Valore** premendo TAB per abilitare il pulsante **OK** .</span><span class="sxs-lookup"><span data-stu-id="79484-124">You might have to tab out of the **Value** box to enable the **OK** button.</span></span>  
  
8.  <span data-ttu-id="79484-125">Nell'elenco **Modalità di valutazione** selezionare **Su modifica: impedisci esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="79484-125">In the **Evaluation Mode** list, select **On change: prevent**.</span></span> <span data-ttu-id="79484-126">Questa opzione consente di applicare i criteri tramite la creazione di un trigger di database nel database Finance.</span><span class="sxs-lookup"><span data-stu-id="79484-126">This will enforce the policy by creating a database trigger on the Finance database.</span></span>  
  
9. <span data-ttu-id="79484-127">Selezionare l'elenco **Abilitato** .</span><span class="sxs-lookup"><span data-stu-id="79484-127">Select the **Enabled** list.</span></span> <span data-ttu-id="79484-128">(La casella **Abilitato** non si applica ai criteri **Su richiesta** .)</span><span class="sxs-lookup"><span data-stu-id="79484-128">(The **Enabled** box does not apply to **On demand** policies.)</span></span>  
  
10. <span data-ttu-id="79484-129">Nell'elenco **Restrizione server** selezionare **Nessuna**.</span><span class="sxs-lookup"><span data-stu-id="79484-129">In the **Server restriction** list, select **None**.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-create-the-finance-policy-category"></a><span data-ttu-id="79484-130">Per creare la categoria di criteri Finance</span><span class="sxs-lookup"><span data-stu-id="79484-130">To create the Finance policy category</span></span>  
  
1.  <span data-ttu-id="79484-131">In Esplora oggetti espandere **Gestione**, fare clic con il pulsante destro del mouse su **Gestione criteri**e scegliere **Gestione categorie**.</span><span class="sxs-lookup"><span data-stu-id="79484-131">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="79484-132">Nella finestra di dialogo **Gestisci categorie di criteri** , in **nome**, digitare `Finance` nella casella vuota, quindi deselezionare Imponi **sottoscrizioni di database**.</span><span class="sxs-lookup"><span data-stu-id="79484-132">In the **Manage Policy Categories** dialog box, under **Name**, type `Finance` in the blank box, and then clear **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="79484-133">Con**Imponi sottoscrizioni di database** ogni database nell'istanza verrà forzato alla sottoscrizione dei criteri appartenenti alla categoria di criteri.</span><span class="sxs-lookup"><span data-stu-id="79484-133">**Mandate Database Subscriptions** will force every database in the instance to subscribe to the policies that belong to this policy category.</span></span> <span data-ttu-id="79484-134">Ai fini di questa lezione, solo il database Finance deve sottoscrivere i criteri Nome Finance.</span><span class="sxs-lookup"><span data-stu-id="79484-134">For this lesson, only the Finance database should subscribe to the Finance Name policy.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="79484-135">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="79484-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="79484-136">Sottoscrizione e verifica di criteri Nome Finance</span><span class="sxs-lookup"><span data-stu-id="79484-136">Subscribe to and Check the Finance Name Policy</span></span>](lesson-2-2-subscribe-to-and-check-the-finance-name-policy.md)  
  
  
