---
title: Modificare una sessione Eventi estesi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
ms.assetid: 114ec05b-7eca-4c87-b276-25e37b84be39
author: rothja
ms.author: jroth
ms.openlocfilehash: 14be41e48262bc7ebc8aeeaf55185f5e35d0c72e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623279"
---
# <a name="alter-an-extended-events-session"></a><span data-ttu-id="dec17-102">Modificare una sessione Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="dec17-102">Alter an Extended Events Session</span></span>
  <span data-ttu-id="dec17-103">Dopo avere creato una sessione Eventi estesi, è possibile modificarla secondo necessità utilizzando la **Creazione guidata Eventi estesi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="dec17-103">After you create an Extended Events session, you can alter it according to your needs using the **SQL Server Extended Events Wizard**.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="dec17-104">Operazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="dec17-104">Before you Begin</span></span>  
 <span data-ttu-id="dec17-105">Non è possibile modificare una destinazione per sessioni attive e inattive né modificare le configurazioni delle proprietà avanzate per una sessione attiva.</span><span class="sxs-lookup"><span data-stu-id="dec17-105">You cannot alter a target for active and inactive sessions, and you cannot change the advanced properties configurations for an active session.</span></span>  
  
 <span data-ttu-id="dec17-106">È possibile apportare le modifiche seguenti alle sessioni di eventi attive e inattive:</span><span class="sxs-lookup"><span data-stu-id="dec17-106">You can make the following alterations to both active and inactive event sessions:</span></span>  
  
-   <span data-ttu-id="dec17-107">Aggiungere o rimuovere eventi dalla sessione e modificare le configurazioni degli eventi, ad esempio campi evento, filtri e azioni.</span><span class="sxs-lookup"><span data-stu-id="dec17-107">Add or remove events from the session, and alter the event configurations such as event fields, filters and actions.</span></span>  
  
-   <span data-ttu-id="dec17-108">Aggiungere o rimuovere una destinazione dalla sessione eventi.</span><span class="sxs-lookup"><span data-stu-id="dec17-108">Add or remove a target from the event session.</span></span>  
  
-   <span data-ttu-id="dec17-109">Abilitare l'opzione **Avvia la sessione eventi all'avvio del server** .</span><span class="sxs-lookup"><span data-stu-id="dec17-109">Enable the **Start the event session on server startup** option.</span></span>  
  
 <span data-ttu-id="dec17-110">È possibile apportare le modifiche aggiuntive seguenti a una sessioni eventi inattiva:</span><span class="sxs-lookup"><span data-stu-id="dec17-110">You can make the following additional alterations to an inactive event session:</span></span>  
  
-   <span data-ttu-id="dec17-111">Abilitare l'opzione **Rileva la relazione tra gli eventi** .</span><span class="sxs-lookup"><span data-stu-id="dec17-111">Enable the **Track the relationship between events** option.</span></span>  
  
-   <span data-ttu-id="dec17-112">Modificare la configurazione delle proprietà avanzate.</span><span class="sxs-lookup"><span data-stu-id="dec17-112">Change the advanced properties configuration.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dec17-113">La **Creazione guidata eventi estesi di SQL Server** non supporta la modifica delle sessioni evento.</span><span class="sxs-lookup"><span data-stu-id="dec17-113">The **SQL Server Extended Events Wizard** does not support event session modification.</span></span>  
  
## <a name="how-to-alter-an-extended-events-session-using-the-sql-server-extended-events-wizard"></a><span data-ttu-id="dec17-114">Modifica di una sessione Eventi estesi utilizzando la Creazione guidata Eventi estesi SQL Server</span><span class="sxs-lookup"><span data-stu-id="dec17-114">How to alter an Extended Events session using the SQL Server Extended Events Wizard</span></span>  
  
-   <span data-ttu-id="dec17-115">In Esplora oggetti espandere **Gestione**, **Eventi estesi**, quindi **Sessioni**.</span><span class="sxs-lookup"><span data-stu-id="dec17-115">In Object Explorer, expand **Management**, expand **Extended Events**, and then expand **Sessions**.</span></span>  
  
-   <span data-ttu-id="dec17-116">Fare clic con il pulsante destro del mouse sulla sessione che si vuole modificare, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="dec17-116">Right-click the session you want to alter, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="dec17-117">Nella finestra di dialogo **Proprietà** apportare le modifiche desiderate, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dec17-117">In the **Properties** dialog box, make the appropriate changes, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec17-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dec17-118">See Also</span></span>  
 <span data-ttu-id="dec17-119">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dec17-119">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="dec17-120">Creare una sessione Eventi estesi tramite l'editor di query</span><span class="sxs-lookup"><span data-stu-id="dec17-120">Create an Extended Events Session Using Query Editor</span></span>](../../database-engine/create-an-extended-events-session-using-query-editor.md)  
  
  
