---
title: Sottoscrivere e verificare criteri Nome Finance | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 126b4c4c-2a1c-4701-a0ad-8de23fbd7306
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2bfe6f463d03fe8b95f000dc6f34dc0718a7729f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624097"
---
# <a name="subscribe-to-and-check-the-finance-name-policy"></a><span data-ttu-id="a0db9-102">Sottoscrizione e verifica di criteri Nome Finance</span><span class="sxs-lookup"><span data-stu-id="a0db9-102">Subscribe to and Check the Finance Name Policy</span></span>
  <span data-ttu-id="a0db9-103">In questa attività verrà configurato il database Finance per la sottoscrizione della categoria di criteri Finance.</span><span class="sxs-lookup"><span data-stu-id="a0db9-103">In this task, you will configure the Finance database to subscribe to the Finance policy category.</span></span> <span data-ttu-id="a0db9-104">Verranno quindi verificati i criteri Nome Finance.</span><span class="sxs-lookup"><span data-stu-id="a0db9-104">Then, you will test the Finance Name policy.</span></span>  
  
### <a name="to-subscribe-to-the-finance-policy-category"></a><span data-ttu-id="a0db9-105">Per sottoscrivere la categoria di criteri Finance</span><span class="sxs-lookup"><span data-stu-id="a0db9-105">To subscribe to the Finance policy category</span></span>  
  
1.  <span data-ttu-id="a0db9-106">In Esplora oggetti espandere **database**, fare clic con il pulsante destro del mouse `Finance` , scegliere **criteri**, quindi fare clic su **categorie**.</span><span class="sxs-lookup"><span data-stu-id="a0db9-106">In Object Explorer, expand **Databases**, right-click `Finance`, point to **Policies**, and then click **Categories**.</span></span>  
  
2.  <span data-ttu-id="a0db9-107">Selezionare la casella di controllo **sottoscritto** per la `Finance` categoria.</span><span class="sxs-lookup"><span data-stu-id="a0db9-107">Select the **Subscribed** checkbox for the `Finance` category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-enforcement-of-the-finance-name-policy"></a><span data-ttu-id="a0db9-108">Per verificare l'applicazione dei criteri Nome Finance</span><span class="sxs-lookup"><span data-stu-id="a0db9-108">To test the enforcement of the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="a0db9-109">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]aprire una finestra di query.</span><span class="sxs-lookup"><span data-stu-id="a0db9-109">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window.</span></span> <span data-ttu-id="a0db9-110">Eseguire le istruzioni seguenti che consentono di creare una tabella che viola i criteri **Nome Finance** .</span><span class="sxs-lookup"><span data-stu-id="a0db9-110">Execute the following statements that try to create a table that violates the **Finance Name** policy.</span></span> <span data-ttu-id="a0db9-111">La tabella viola i criteri perché il nome della tabella non inizia con le lettere **fintbl**.</span><span class="sxs-lookup"><span data-stu-id="a0db9-111">The table violates the policy because the table name does not begin with the letters **fintbl**.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE NewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="a0db9-112">Si noti che i criteri impediscono la creazione della tabella e restituiscono un messaggio informativo indicante il nome dei criteri.</span><span class="sxs-lookup"><span data-stu-id="a0db9-112">Notice that the policy prevents the table from being created and returns an informational message that provides the policy name.</span></span>  
  
2.  <span data-ttu-id="a0db9-113">Per specificare un nome valido, modificare il codice nel modo indicato di seguito ed eseguire nuovamente l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="a0db9-113">To provide a valid name, modify the code as follows and run the statement again.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE fintblNewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="a0db9-114">Questa modifica consente la creazione della tabella.</span><span class="sxs-lookup"><span data-stu-id="a0db9-114">This time, the table is created.</span></span>  
  
### <a name="to-apply-the-policy-to-the-whole-server"></a><span data-ttu-id="a0db9-115">Per applicare i criteri all'intero server</span><span class="sxs-lookup"><span data-stu-id="a0db9-115">To apply the policy to the whole server</span></span>  
  
1.  <span data-ttu-id="a0db9-116">Solo il database Finance sottoscrive attualmente la categoria di criteri Finance.</span><span class="sxs-lookup"><span data-stu-id="a0db9-116">Currently, only the Finance database subscribes to the Finance policy category.</span></span> <span data-ttu-id="a0db9-117">In molti casi è più facile applicare la categoria di criteri all'intero server.</span><span class="sxs-lookup"><span data-stu-id="a0db9-117">In many cases, it is easier to apply the policy category to the whole server.</span></span> <span data-ttu-id="a0db9-118">In Esplora oggetti espandere **Gestione**, fare clic con il pulsante destro del mouse su **Gestione criteri**e scegliere **Gestione categorie**.</span><span class="sxs-lookup"><span data-stu-id="a0db9-118">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="a0db9-119">Nella finestra di dialogo **Gestione categorie di criteri** individuare la categoria Finance e selezionare la casella di controllo **Imponi sottoscrizioni di database** per la categoria.</span><span class="sxs-lookup"><span data-stu-id="a0db9-119">In the **Manage Policy Categories** dialog box, locate the Finance category, and select the **Mandate Database Subscriptions** checkbox for the Finance category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)] <span data-ttu-id="a0db9-120">La categoria Finance si applica ora a tutti i database, ma la condizione creata in precedenza limita i criteri Nome Finance al database Finance.</span><span class="sxs-lookup"><span data-stu-id="a0db9-120">Now the Finance category applies to all databases, but the condition that you have created restricts the Finance Name policy to the Finance database.</span></span> <span data-ttu-id="a0db9-121">In questo esempio viene illustrato come utilizzare combinazioni complesse di condizioni per i criteri in modalità valide per molti server.</span><span class="sxs-lookup"><span data-stu-id="a0db9-121">This shows how you can use complex combinations of conditions to target policies in ways that will apply correctly on many servers.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="a0db9-122">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a0db9-122">Summary</span></span>  
 <span data-ttu-id="a0db9-123">In questa esercitazione è stato illustrato come creare condizioni, criteri e gruppi di criteri della gestione basata su criteri e come applicare filtri e verificare la conformità delle destinazioni della gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="a0db9-123">This tutorial has shown you how to create Policy-Based Management conditions, policies and policy groups, and how to apply filters and check the compliance of Policy-Based Management targets.</span></span>  
  
## <a name="next"></a><span data-ttu-id="a0db9-124">Prossima</span><span class="sxs-lookup"><span data-stu-id="a0db9-124">Next</span></span>  
 <span data-ttu-id="a0db9-125">L'esercitazione è completata.</span><span class="sxs-lookup"><span data-stu-id="a0db9-125">This tutorial is finished.</span></span> <span data-ttu-id="a0db9-126">Per tornare all'inizio, selezionare [Esercitazione: Amministrazione di server tramite la gestione basata su criteri](tutorial-administering-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="a0db9-126">To return to the start, click [Tutorial: Administering Servers by Using Policy-Based Management](tutorial-administering-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="a0db9-127">Per un elenco delle esercitazioni, vedere [esercitazioni per SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="a0db9-127">For a list of tutorials, see [Tutorials for SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0db9-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0db9-128">See Also</span></span>  
 [<span data-ttu-id="a0db9-129">Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="a0db9-129">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
