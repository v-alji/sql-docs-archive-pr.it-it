---
title: Creare criteri Disattivata per impostazione predefinita | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 98fde3c5-297c-4d95-981e-95700bbf5ccd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16d0893c155627a41149263b5ce7b21a4a217b74
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624674"
---
# <a name="create-the-off-by-default-policy"></a><span data-ttu-id="637a0-102">Creazione di criteri Disattivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="637a0-102">Create the Off By Default Policy</span></span>
  <span data-ttu-id="637a0-103">Questa attività consente di creare una condizione denominata Posta disattivata basata sul facet Configurazione superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="637a0-103">This task creates a condition named Mail Off that is based on the Surface Area Configuration facet.</span></span> <span data-ttu-id="637a0-104">e di creare quindi un criterio denominato Disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="637a0-104">Then, it creates a policy named Off By Default.</span></span>  
  
### <a name="to-create-the-mail-off-condition"></a><span data-ttu-id="637a0-105">Per creare la condizione Posta disattivata</span><span class="sxs-lookup"><span data-stu-id="637a0-105">To create the Mail Off condition</span></span>  
  
1.  <span data-ttu-id="637a0-106">In Esplora oggetti espandere **Gestione**, **Gestione criteri**e **Facet**, fare clic con il pulsante destro del mouse su **Configurazione superficie di attacco**, quindi scegliere **Nuova condizione**.</span><span class="sxs-lookup"><span data-stu-id="637a0-106">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Facets**, right-click **Surface Area Configuration**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="637a0-107">Nella finestra di dialogo **Crea nuova condizione** digitare **Posta disattivata** nella casella **Nome**.</span><span class="sxs-lookup"><span data-stu-id="637a0-107">In the **Create New Condition** dialog box, in the **Name** box, type **Mail Off**.</span></span>  
  
3.  <span data-ttu-id="637a0-108">Nella casella **Facet** verificare che il facet **Configurazione superficie di attacco** sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="637a0-108">In the **Facet** box, confirm that **Surface Area Configuration** facet is selected.</span></span>  
  
4.  <span data-ttu-id="637a0-109">Nella casella **Campo** dell'area **Espressione** selezionare **\@DatabaseMailEnabled**, nella casella **Operatore selezionare\*\*\*\*=** e in **Valore** selezionare **False**.</span><span class="sxs-lookup"><span data-stu-id="637a0-109">In the **Expression** area, in the **Field** box, select **\@DatabaseMailEnabled**, in the **Operator** box select **=**, and in the **Value** select **False**.</span></span>  
  
5.  <span data-ttu-id="637a0-110">Nella pagina **Descrizione** digitare una descrizione per la condizione, quindi scegliere **OK** per creare la condizione.</span><span class="sxs-lookup"><span data-stu-id="637a0-110">On the **Description** page, type a description of the condition, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-off-by-default-policy"></a><span data-ttu-id="637a0-111">Per creare i criteri Disattivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="637a0-111">To create the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="637a0-112">In Esplora oggetti fare clic con il pulsante destro del mouse su **Configurazione superficie di attacco**, quindi scegliere **Nuovi criteri**.</span><span class="sxs-lookup"><span data-stu-id="637a0-112">In Object Explorer, right-click **Surface Area Configuration**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="637a0-113">Nella finestra di dialogo **Crea nuovi criteri** digitare **Disattivata per impostazione predefinita** nella casella **Nome**.</span><span class="sxs-lookup"><span data-stu-id="637a0-113">In the **Create New Policy** dialog box, in the **Name** box, type **Off By Default**.</span></span>  
  
3.  <span data-ttu-id="637a0-114">Lasciare deselezionata la casella di controllo **Abilitato** .</span><span class="sxs-lookup"><span data-stu-id="637a0-114">Leave the **Enabled** checkbox unchecked.</span></span> <span data-ttu-id="637a0-115">La casella di controllo **Abilitato** si applica ai criteri automatizzati e questi criteri verranno eseguiti su richiesta.</span><span class="sxs-lookup"><span data-stu-id="637a0-115">The **Enabled** checkbox applies to automated policies, and this policy will be executed on demand.</span></span>  
  
4.  <span data-ttu-id="637a0-116">Nella casella di controllo **Condizioni di controllo** scorrere verso il basso fino all'area **Configurazione superficie di attacco** , quindi selezionare **Posta disattivata** come condizione da controllare.</span><span class="sxs-lookup"><span data-stu-id="637a0-116">In the **Check condition** checkbox, scroll down to the **Surface Area Configuration** area, and then select **Mail Off** as the condition to check.</span></span>  
  
5.  <span data-ttu-id="637a0-117">La casella **In base alle destinazioni** sarà vuota perché si tratta di criteri con ambito server.</span><span class="sxs-lookup"><span data-stu-id="637a0-117">The **Against targets** box will be blank because this is a server-scoped policy.</span></span>  
  
6.  <span data-ttu-id="637a0-118">Nella casella di controllo **Modalità di valutazione** selezionare **Su richiesta** come modalità di valutazione.</span><span class="sxs-lookup"><span data-stu-id="637a0-118">In the **Evaluation Mode** checkbox, select **On demand** as the evaluation mode.</span></span>  
  
7.  <span data-ttu-id="637a0-119">Nella casella di controllo **Restrizione server** selezionare **Nessuna**.</span><span class="sxs-lookup"><span data-stu-id="637a0-119">In the **Server restriction** checkbox, select **None**.</span></span>  
  
8.  <span data-ttu-id="637a0-120">Nella pagina **Descrizione** digitare una descrizione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="637a0-120">On the **Description** page, type a description of the policy.</span></span>  
  
9. <span data-ttu-id="637a0-121">È possibile specificare un collegamento ipertestuale a una pagina Web per i criteri nell'area **Collegamento ipertestuale alla Guida aggiuntiva** .</span><span class="sxs-lookup"><span data-stu-id="637a0-121">You can provide a hyperlink to a Web page for your policies in the **Additional help hyperlink** area.</span></span> <span data-ttu-id="637a0-122">Nella casella **Testo da visualizzare** digitare il testo che verrà visualizzato per il collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="637a0-122">In the **Text to display** box, type the text that will appear for the hyperlink.</span></span>  
  
10. <span data-ttu-id="637a0-123">Nella casella **Indirizzo** digitare un collegamento ipertestuale a una pagina della Guida, ad esempio la home page per il reparto IT della società.</span><span class="sxs-lookup"><span data-stu-id="637a0-123">In the **Address** box, type a hyperlink to a Help page, such as the home page for the IT department of your company.</span></span>  
  
11. <span data-ttu-id="637a0-124">Per verificare l'indirizzo aprendo la pagina Web, fare clic su **Prova collegamento**.</span><span class="sxs-lookup"><span data-stu-id="637a0-124">To confirm the address by opening the Web page, click **Test Link**.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="637a0-125">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="637a0-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="637a0-126">Configurazione di un server per l'esecuzione di criteri Disattivata per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="637a0-126">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
  
