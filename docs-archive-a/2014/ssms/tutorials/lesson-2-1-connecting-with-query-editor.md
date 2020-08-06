---
title: Connessione all'editor di query | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: 48725f54-a7b6-4b79-948e-965c1fe4eef1
author: stevestein
ms.author: sstein
ms.openlocfilehash: b50783450dfb9516c78a465806ee322d7a575377
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630213"
---
# <a name="connecting-with-query-editor"></a><span data-ttu-id="de557-102">Connessione all'editor di query</span><span class="sxs-lookup"><span data-stu-id="de557-102">Connecting with Query Editor</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="de557-103">consente di scrivere e modificare codice quando non si è connessi dal server.</span><span class="sxs-lookup"><span data-stu-id="de557-103">permits you to write or edit code while disconnected from the server.</span></span> <span data-ttu-id="de557-104">Ciò risulta utile quando il server non è disponibile o quando si desidera risparmiare risorse di rete o di server limitate.</span><span class="sxs-lookup"><span data-stu-id="de557-104">This can be useful when the server is not available or when you want to conserve scarce server or network resources.</span></span> <span data-ttu-id="de557-105">È inoltre possibile connettere l'editor di query a una nuova istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] senza la necessità di avviare una nuova finestra dell'editor di query o di immettere nuovamente il codice.</span><span class="sxs-lookup"><span data-stu-id="de557-105">You can also change the connection of Query Editor to a new instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without opening a new Query Editor window or retyping your code.</span></span>  
  
## <a name="coding-offline"></a><span data-ttu-id="de557-106">Codifica offline</span><span class="sxs-lookup"><span data-stu-id="de557-106">Coding Offline</span></span>  
  
#### <a name="to-write-code-offline-and-then-connect-to-different-servers"></a><span data-ttu-id="de557-107">Per scrivere codice offline e quindi connettersi a server diversi</span><span class="sxs-lookup"><span data-stu-id="de557-107">To write code offline and then connect to different servers</span></span>  
  
1.  <span data-ttu-id="de557-108">Sulla barra degli strumenti di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] fare clic su **Query del motore di database** per aprire l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="de557-108">On the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] toolbar, click **Database Engine Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="de557-109">Nella finestra di dialogo **Connetti al motore di database** fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="de557-109">In the **Connect to Database Engine** dialog box, click **Cancel**.</span></span> <span data-ttu-id="de557-110">Verrà avviato l'editor di query e la barra del titolo indicherà che l'editor non è connesso a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de557-110">The Query Editor opens, and the title bar for the Query Editor indicates that you are not connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="de557-111">Nel riquadro del codice digitare la seguente istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="de557-111">In the code pane, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    SELECT * FROM Production.Product;  
    GO  
    ```  
  
     <span data-ttu-id="de557-112">A questo punto è possibile stabilire la connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] facendo clic su **Connetti**, **Esegui**, **Analizza**o **Visualizza piano di esecuzione stimato**disponibili nel menu **Query** , sulla barra degli strumenti dell'editor di query o nel menu di scelta rapida facendo clic con il pulsante destro del mouse nella finestra dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="de557-112">At this point you can connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by clicking **Connect**, **Execute**, **Parse**, or **Display Estimated Execution Plan**, all of which are available from either the **Query** menu, the Query Editor toolbar, or from the shortcut menu when you right-click in the Query Editor window.</span></span> <span data-ttu-id="de557-113">Per questa procedura verrà utilizzata la barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="de557-113">For this practice, we'll use the toolbar.</span></span>  
  
4.  <span data-ttu-id="de557-114">Sulla barra degli strumenti fare clic sul pulsante **Esegui** per visualizzare la finestra di dialogo **Connetti al motore di database** .</span><span class="sxs-lookup"><span data-stu-id="de557-114">On the toolbar, click the **Execute** button to open the **Connect to Database Engine** dialog box.</span></span>  
  
5.  <span data-ttu-id="de557-115">Nella casella di testo **Nome server** digitare il nome del server e fare clic su **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="de557-115">In the **Server name** text box, type your server name, and then click **Options**.</span></span>  
  
6.  <span data-ttu-id="de557-116">Nella scheda **Proprietà connessione** , nell'elenco **Connetti al database** selezionare [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="de557-116">On the **Connection Properties** tab, in the **Connect to database** list, browse the server to select [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] and then click **Connect**.</span></span>  
  
7.  <span data-ttu-id="de557-117">Per visualizzare un'altra finestra dell'editor di query con la stessa connessione, fare clic su **Nuova query**sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="de557-117">To open another Query Editor window with the same connection, on the toolbar click **New Query**.</span></span>  
  
8.  <span data-ttu-id="de557-118">Per cambiare le connessioni, fare clic con il pulsante destro del mouse nella finestra dell'editor di query, scegliere **Connessione**e quindi **Cambia connessione**.</span><span class="sxs-lookup"><span data-stu-id="de557-118">To change connections, right-click in the Query Editor window, point to **Connection**, and then click **Change Connection**.</span></span>  
  
9. <span data-ttu-id="de557-119">Nella finestra di dialogo **Connetti a SQL Server** selezionare un'altra istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se disponibile e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="de557-119">In the **Connect to SQL Server** dialog box, select another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] if available, and then click **Connect**.</span></span>  
  
 <span data-ttu-id="de557-120">Questa nuova caratteristica dell'editor di query consente di eseguire facilmente lo stesso codice su diversi server.</span><span class="sxs-lookup"><span data-stu-id="de557-120">This new feature of Query Editor enables you to easily run the same code on several servers.</span></span> <span data-ttu-id="de557-121">Ciò può risultare utile per le azioni di manutenzione che coinvolgono server simili.</span><span class="sxs-lookup"><span data-stu-id="de557-121">This may be useful for maintenance actions involving similar servers.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="de557-122">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="de557-122">Next Task in Lesson</span></span>  
 [<span data-ttu-id="de557-123">Aggiunta dei rientri</span><span class="sxs-lookup"><span data-stu-id="de557-123">Adding Indentation</span></span>](lesson-2-2-adding-indentation.md)  
  
  
