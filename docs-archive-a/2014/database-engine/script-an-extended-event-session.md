---
title: Creare uno script per una sessione di eventi estesi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f9fdde-1f13-4292-a4fc-55da826be3b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 11adc60ae7c7e0f8b8012d06f56c83874d3708ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627376"
---
# <a name="script-an-extended-event-session"></a><span data-ttu-id="fc96b-102">Creare uno script per una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="fc96b-102">Script an Extended Event Session</span></span>
  <span data-ttu-id="fc96b-103">In questo argomento viene descritto come creare uno script per una sessione eventi.</span><span class="sxs-lookup"><span data-stu-id="fc96b-103">This topic describes how to script an event session.</span></span> <span data-ttu-id="fc96b-104">È possibile esportare, modificare o eliminare la sessione eventi oppure eliminare e creare la sessione eventi nelle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc96b-104">You can export, alter, or drop the event session, or drop and create the event session to the following:</span></span>  
  
-   <span data-ttu-id="fc96b-105">**Nuova finestra editor di query**</span><span class="sxs-lookup"><span data-stu-id="fc96b-105">**New Query Editor Window**</span></span>  
  
-   <span data-ttu-id="fc96b-106">**File**</span><span class="sxs-lookup"><span data-stu-id="fc96b-106">**File**</span></span>  
  
-   <span data-ttu-id="fc96b-107">**Appunti**</span><span class="sxs-lookup"><span data-stu-id="fc96b-107">**Clipboard**</span></span>  
  
-   <span data-ttu-id="fc96b-108">**Processo agente**</span><span class="sxs-lookup"><span data-stu-id="fc96b-108">**Agent Job**</span></span>  
  
### <a name="to-script-an-existing-event-session"></a><span data-ttu-id="fc96b-109">Per creare uno script per una sessione eventi esistente</span><span class="sxs-lookup"><span data-stu-id="fc96b-109">To script an existing event session</span></span>  
  
1.  <span data-ttu-id="fc96b-110">In Esplora oggetti espandere il nodo **Gestione** , quindi espandere **Eventi estesi**.</span><span class="sxs-lookup"><span data-stu-id="fc96b-110">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="fc96b-111">Fare clic con il pulsante destro del mouse sulla sessione di cui si desidera eseguire lo script, scegliere Crea **script per sessione**, scegliere **crea a**, quindi selezionare la posizione in cui si desidera creare lo script per la sessione.</span><span class="sxs-lookup"><span data-stu-id="fc96b-111">Right-click the session you want to script, point to **Script Session as**, point to **CREATE to**, and then select where you want to script the session.</span></span>  
  
### <a name="to-script-a-new-event-session"></a><span data-ttu-id="fc96b-112">Per creare uno script per una nuova sessione eventi</span><span class="sxs-lookup"><span data-stu-id="fc96b-112">To script a new event session</span></span>  
  
1.  <span data-ttu-id="fc96b-113">In Esplora oggetti espandere il nodo **Gestione** , quindi espandere **Eventi estesi**.</span><span class="sxs-lookup"><span data-stu-id="fc96b-113">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="fc96b-114">Fare clic con il pulsante destro del mouse su **Sessioni**, quindi scegliere **Nuova sessione**.</span><span class="sxs-lookup"><span data-stu-id="fc96b-114">Right-click **Sessions**, and then click **New Session**.</span></span>  
  
3.  <span data-ttu-id="fc96b-115">Nell'interfaccia utente **nuova sessione** creare la sessione eventi, quindi selezionare la posizione in cui si desidera creare lo script della sessione eventi dall'elenco a discesa **script** .</span><span class="sxs-lookup"><span data-stu-id="fc96b-115">In the **New Session** UI, create the event session, and then select where you want to script the event session from the **Script** drop-down list.</span></span>  
  
### <a name="to-script-a-modified-event-session"></a><span data-ttu-id="fc96b-116">Per creare uno script per una sessione eventi modificata</span><span class="sxs-lookup"><span data-stu-id="fc96b-116">To script a modified event session</span></span>  
  
1.  <span data-ttu-id="fc96b-117">In Esplora oggetti espandere il nodo **Gestione** , quindi espandere **Eventi estesi**.</span><span class="sxs-lookup"><span data-stu-id="fc96b-117">In Object Explorer, expand the **Management** node, and then expand **Extended Events**.</span></span>  
  
2.  <span data-ttu-id="fc96b-118">Fare clic con il pulsante destro del mouse sulla sessione che si desidera modificare, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fc96b-118">Right-click the session you want to modify, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="fc96b-119">Nella finestra di dialogo **Proprietà sessione** modificare la sessione eventi, quindi selezionare la posizione in cui si desidera creare lo script della sessione modificata dall'elenco a discesa **script** .</span><span class="sxs-lookup"><span data-stu-id="fc96b-119">In the **Session Properties** dialog box, modify the event session, and then select where you want to script the modified session from the **Script** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc96b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc96b-120">See Also</span></span>  
 [<span data-ttu-id="fc96b-121">Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="fc96b-121">Extended Events</span></span>](../relational-databases/extended-events/extended-events.md)  
  
  
