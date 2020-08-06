---
title: Pianificare i criteri | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 59417a54-55f1-4468-ba41-368aa852c2d4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 1bce1b9d650606e9485899c34c72ca6b27a72dae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720448"
---
# <a name="schedule-the-policies"></a><span data-ttu-id="7b217-102">Pianificazione criteri</span><span class="sxs-lookup"><span data-stu-id="7b217-102">Schedule the Policies</span></span>
  <span data-ttu-id="7b217-103">In questa attività verrà eseguita la pianificazione dei criteri per procedure consigliate importati nell'attività precedente.</span><span class="sxs-lookup"><span data-stu-id="7b217-103">In this task, you will schedule the best practices policies that you imported in the previous task.</span></span>  
  
### <a name="to-schedule-the-best-practices-policies"></a><span data-ttu-id="7b217-104">Per pianificare i criteri per procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="7b217-104">To schedule the best practices policies</span></span>  
  
1.  <span data-ttu-id="7b217-105">In Esplora oggetti espandere **gestione**, **Gestione criteri**e **criteri, fare**clic con il pulsante destro del mouse su criteri per procedure consigliate e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7b217-105">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Policies**, right-click a best practices policy, and then click **Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7b217-106">In alternativa, per individuare facilmente i criteri associati alle procedure consigliate e per ordinare le categorie procedure consigliate, espandere **gestione**, **Gestione criteri**, quindi fare clic su **criteri**.</span><span class="sxs-lookup"><span data-stu-id="7b217-106">As an alternative, to easily see which policies are associated with best practices and to sort the best practices categories, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span> <span data-ttu-id="7b217-107">Scegliere **Dettagli Esplora oggetti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="7b217-107">On the **View** menu, click **Object Explorer Details**.</span></span> <span data-ttu-id="7b217-108">Nel riquadro **dettagli Esplora oggetti** fare clic sull'intestazione **categoria** per ordinare i criteri per categoria.</span><span class="sxs-lookup"><span data-stu-id="7b217-108">In the **Object Explorer Details** pane, click the **Category** heading to sort the policies by category.</span></span> <span data-ttu-id="7b217-109">I criteri per procedure consigliate prevedono il prefisso **Microsoft Best Practices**.</span><span class="sxs-lookup"><span data-stu-id="7b217-109">The best practices policies have the prefix **Microsoft Best Practices**.</span></span> <span data-ttu-id="7b217-110">Fare clic con il pulsante destro del mouse sui criteri che si desidera configurare, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7b217-110">Right-click the policy that you want to configure, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7b217-111">Nella pagina **generale** della finestra di dialogo **Apri criteri** , nell'elenco **modalità di valutazione** , fare clic **su pianificazione**.</span><span class="sxs-lookup"><span data-stu-id="7b217-111">On the **General** page of the **Open Policy** dialog box, in the **Evaluation Mode** list, click **On schedule**.</span></span>  
  
3.  <span data-ttu-id="7b217-112">Accanto alla casella **pianificazione** fare clic su **Seleziona** per specificare una pianificazione esistente oppure fare clic su **nuova** per creare una nuova pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7b217-112">Next to the **Schedule** box, click **Pick** to specify an existing schedule, or click **New** to create a new schedule.</span></span>  
  
4.  <span data-ttu-id="7b217-113">Dopo aver configurato una pianificazione, è possibile selezionare la casella di controllo **abilitato** nella parte superiore della pagina per abilitare i criteri pianificati.</span><span class="sxs-lookup"><span data-stu-id="7b217-113">After you have configured a schedule, you can select the **Enabled** check box near the top of the page to enable the scheduled policy.</span></span>  
  
5.  <span data-ttu-id="7b217-114">Ripetere i passaggi da 1 a 4 per tutti i criteri che si desidera pianificare.</span><span class="sxs-lookup"><span data-stu-id="7b217-114">Repeats steps 1 through 4 for each policy that you want to schedule.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7b217-115">Per visualizzare i risultati di valutazione dopo l'esecuzione di criteri pianificati, aprire il log Cronologia criteri nell'istanza di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7b217-115">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="7b217-116">Per aprire il log, fare clic con il pulsante destro del mouse su **Gestione criteri**, quindi scegliere **Visualizza cronologia**.</span><span class="sxs-lookup"><span data-stu-id="7b217-116">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="7b217-117">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7b217-117">Summary</span></span>  
 <span data-ttu-id="7b217-118">I criteri pianificati sono stati configurati per essere eseguiti in un'istanza singola di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b217-118">You configured scheduled policies to run on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7b217-119">Se si desidera distribuire i criteri pianificati in più istanze, continuare con la prossima attività in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="7b217-119">If you want to deploy scheduled policies to multiple instances, continue to the next task in this tutorial.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7b217-120">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7b217-120">Next Steps</span></span>  
 [<span data-ttu-id="7b217-121">Distribuzione di criteri pianificati in istanze multiple</span><span class="sxs-lookup"><span data-stu-id="7b217-121">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
  
