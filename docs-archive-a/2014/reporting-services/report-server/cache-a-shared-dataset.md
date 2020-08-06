---
title: Memorizzare nella cache un set di dati condiviso | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c2d8c81a-da1e-4a8a-9845-fff9a0903d24
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d4757d82425368efcb6a0a555c6cfe1deacf48c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630314"
---
# <a name="cache-a-shared-dataset"></a><span data-ttu-id="eb128-102">Memorizzare nella cache un set di dati condiviso</span><span class="sxs-lookup"><span data-stu-id="eb128-102">Cache a Shared Dataset</span></span>
  <span data-ttu-id="eb128-103">Per ottimizzare le prestazioni, è possibile configurare le proprietà relative alla memorizzazione nella cache per un set di dati condiviso.</span><span class="sxs-lookup"><span data-stu-id="eb128-103">One way to improve performance is to configure caching properties for a shared dataset.</span></span> <span data-ttu-id="eb128-104">Quando un set di dati condiviso viene memorizzato nella cache, una copia dei risultati di query viene salvata per un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="eb128-104">When a shared dataset is cached, a copy of the query results is saved for a specified period of time.</span></span> <span data-ttu-id="eb128-105">Il primo utente che richiede un report che utilizza il set di dati condiviso deve attendere il completamento dei risultati di query e di tutte le elaborazioni prima di visualizzare il report.</span><span class="sxs-lookup"><span data-stu-id="eb128-105">The first user who requests a report that uses the shared dataset must wait for the query results and all processing to complete before viewing the report.</span></span> <span data-ttu-id="eb128-106">Gli utenti successivi che richiedono il report all'interno del periodo di memorizzazione nella cache otterranno prestazioni migliori perché la query e l'elaborazione sono già state eseguite.</span><span class="sxs-lookup"><span data-stu-id="eb128-106">Subsequent users who request the report within the caching period will experience improved performance because the query and processing has already occurred.</span></span> <span data-ttu-id="eb128-107">È inoltre possibile specificare un piano di aggiornamento della cache per eseguire la query e memorizzare nella cache i risultati fino alla scadenza della cache specificata.</span><span class="sxs-lookup"><span data-stu-id="eb128-107">You can also specify a cache refresh plan to run the query and cache the results until the specified cache expiration.</span></span>  
  
 <span data-ttu-id="eb128-108">Gli utenti che eseguono report in base a un set di dati condiviso o a piani di aggiornamento della cache creano la cache delle query e in entrambi i casi, la disponibilità della cache dipende dalle opzioni di scadenza della stessa.</span><span class="sxs-lookup"><span data-stu-id="eb128-108">Users running reports based on a shared dataset or cache refresh plans create the query cache and in both cases, the cache is available based on the cache expiration options.</span></span>  
  
 <span data-ttu-id="eb128-109">Sono presenti restrizioni sui tipi di set di dati condivisi che è possibile memorizzare nella cache.</span><span class="sxs-lookup"><span data-stu-id="eb128-109">There are restrictions on the types of shared datasets that you can cache.</span></span> <span data-ttu-id="eb128-110">I risultati di query, ad esempio, non possono essere memorizzati nella cache quando i dati variano in base all'identità utente o vengono recuperati utilizzando il token di sicurezza dell'utente che richiede il report.</span><span class="sxs-lookup"><span data-stu-id="eb128-110">For example, the query results cannot be cached if the data varies based on the user identity or if data is retrieved using the security token of the user who requests the report.</span></span> <span data-ttu-id="eb128-111">Per altre informazioni, vedere [Memorizzare nella cache set di dati condivisi &#40;SSRS&#41;](cache-shared-datasets-ssrs.md) e [Memorizzazione dei report nella cache &#40;SSRS&#41;](caching-reports-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="eb128-111">For more information, see [Cache Shared Datasets &#40;SSRS&#41;](cache-shared-datasets-ssrs.md) and [Caching Reports &#40;SSRS&#41;](caching-reports-ssrs.md).</span></span>  
  
### <a name="to-schedule-the-expiration-of-a-cached-report"></a><span data-ttu-id="eb128-112">Per pianificare la scadenza di un report memorizzato nella cache</span><span class="sxs-lookup"><span data-stu-id="eb128-112">To schedule the expiration of a cached report</span></span>  
  
1.  <span data-ttu-id="eb128-113">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="eb128-113">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="eb128-114">In Gestione report passare al set di dati condiviso per cui si desidera impostare le proprietà relative alla memorizzazione nella cache, posizionare il puntatore del mouse sull'elemento, quindi fare clic sulla freccia a discesa.</span><span class="sxs-lookup"><span data-stu-id="eb128-114">In Report Manager, navigate to the shared dataset for which you want to set caching properties, hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="eb128-115">Scegliere **Gestisci**dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="eb128-115">In the drop-down menu, click **Manage**.</span></span>  
  
4.  <span data-ttu-id="eb128-116">Nel riquadro a sinistra, fare clic su **Memorizzazione nella cache**.</span><span class="sxs-lookup"><span data-stu-id="eb128-116">In the left frame, click **Caching**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eb128-117">Se viene visualizzato l'errore **Le credenziali utilizzate per eseguire il set di dati condiviso non sono associate**, l'opzione relativa alla memorizzazione nella cache del set di dati condiviso verrà disabilitata.</span><span class="sxs-lookup"><span data-stu-id="eb128-117">If you see the error **Credentials used to run the shared dataset are not stored**, the cache shared dataset option will be disabled.</span></span> <span data-ttu-id="eb128-118">È necessario modificare l'origine dati per archiviare le credenziali o modificare il set di dati condiviso per utilizzare un'origine dati diversa che consenta di archiviare le credenziali.</span><span class="sxs-lookup"><span data-stu-id="eb128-118">You need modify the data source to store credentials or modify the shared dataset to use a different data source that does store credentials.</span></span>  
  
5.  <span data-ttu-id="eb128-119">Selezionare **Memorizza nella cache set di dati condiviso**.</span><span class="sxs-lookup"><span data-stu-id="eb128-119">Select **Cache share dataset**.</span></span>  
  
6.  <span data-ttu-id="eb128-120">Selezionare l'opzione che determina la scadenza della cache dopo 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="eb128-120">Select the option to expire the cache after 30 minutes.</span></span> <span data-ttu-id="eb128-121">È inoltre possibile scegliere che la cache scada in base a una determinata pianificazione.</span><span class="sxs-lookup"><span data-stu-id="eb128-121">You can also choose for the cache to expire on a specified schedule.</span></span>  
  
7.  <span data-ttu-id="eb128-122">Fare clic su **Apply**.</span><span class="sxs-lookup"><span data-stu-id="eb128-122">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb128-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb128-123">See Also</span></span>  
 [<span data-ttu-id="eb128-124">Gestire set di dati condivisi</span><span class="sxs-lookup"><span data-stu-id="eb128-124">Manage Shared Datasets</span></span>](../report-data/manage-shared-datasets.md)  
  
  
