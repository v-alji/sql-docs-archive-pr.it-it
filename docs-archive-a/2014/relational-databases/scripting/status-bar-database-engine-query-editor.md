---
title: Barra di stato (editor di query del Motore di database)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e7f2d6f4-bb94-4cf5-a096-c34397e679af
author: rothja
ms.author: jroth
ms.openlocfilehash: 743ae0a4152daee19aa67f85337ae4077a3ed7f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636015"
---
# <a name="status-bar-database-engine-query-editor"></a><span data-ttu-id="ce968-102">Barra di stato (editor di query del Motore di database)</span><span class="sxs-lookup"><span data-stu-id="ce968-102">Status Bar (Database Engine Query Editor)</span></span>
  <span data-ttu-id="ce968-103">La barra di stato delle finestre dell'editor di query di [!INCLUDE[ssDE](../../includes/ssde-md.md)] può apparire di colore diverso in modo da indicare a quale istanza di [!INCLUDE[ssDE](../../includes/ssde-md.md)] è connessa ciascuna finestra.</span><span class="sxs-lookup"><span data-stu-id="ce968-103">The status bar of [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor windows can be color coded to indicate which instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] each window is connected to.</span></span>  
  
1.  <span data-ttu-id="ce968-104">**Prima di iniziare:**  [Colori della barra di stato](#StatusBarColors)</span><span class="sxs-lookup"><span data-stu-id="ce968-104">**Before you begin:**  [Status Bar Colors](#StatusBarColors)</span></span>  
  
2.  <span data-ttu-id="ce968-105">**Per impostare un colore di stato per un server in:**  [Esplora oggetti](#SetOEServerColor), [Server registrato](#SetRegServerColor)</span><span class="sxs-lookup"><span data-stu-id="ce968-105">**To set a server status color in:**  [Object Explorer](#SetOEServerColor), [Registered Server](#SetRegServerColor)</span></span>  
  
3.  <span data-ttu-id="ce968-106">**Per usare un colore di stato:**  [Aprire l'editor di query con un colore per il server](#OpenServerColor), [Aprire l'editor di query specificando un colore di stato](#OpenSpecColor)</span><span class="sxs-lookup"><span data-stu-id="ce968-106">**To use a status color:**  [Open Query Editor Using a Server Color](#OpenServerColor), [Open a Query Editor Specifying a Status Color](#OpenSpecColor)</span></span>  
  
##  <a name="status-bar-colors"></a><a name="StatusBarColors"></a> <span data-ttu-id="ce968-107">Colori della barra di stato</span><span class="sxs-lookup"><span data-stu-id="ce968-107">Status Bar Colors</span></span>  
 <span data-ttu-id="ce968-108">È possibile associare un colore della barra di stato a uno specifico nodo server in **Esplora oggetti** o **Server registrati**.</span><span class="sxs-lookup"><span data-stu-id="ce968-108">You can associate a status bar color with a specific server node in either **Object Explorer** or **Registered Servers**.</span></span> <span data-ttu-id="ce968-109">È possibile specificare i colori solo per nodi server connessi a un'istanza di [!INCLUDE[ssDE](../../includes/ssde-md.md)], non ai nodi server per altre tecnologie SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ce968-109">The colors can only be specified for server nodes connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], not server nodes for other SQL Server technologies.</span></span> <span data-ttu-id="ce968-110">È inoltre possibile specificare anche un colore della barra di stato personalizzato ogni volta che si connette una nuova finestra dell'editor di query di [!INCLUDE[ssDE](../../includes/ssde-md.md)] a un'istanza di [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce968-110">You can also specify a custom status bar color each time you connect a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="ce968-111">È quindi possibile aprire una finestra dell'editor di query utilizzando il colore di stato definito per il nodo server oppure specificare un colore univoco per la finestra in questione.</span><span class="sxs-lookup"><span data-stu-id="ce968-111">You can then open a query editor window using either the status color defined for the server node, or specify a unique color for that editor window.</span></span>  
  
 <span data-ttu-id="ce968-112">L'impostazione di un colore della barra di stato personalizzato per un nodo server in Esplora oggetti deve essere effettuata al momento di effettuare la connessione.</span><span class="sxs-lookup"><span data-stu-id="ce968-112">Setting a custom status bar color for a server node in Object Explorer must be done when making the connection.</span></span> <span data-ttu-id="ce968-113">Per modificare il colore associato a un nodo server esistente, è necessario disconnettersi e quindi riconnettersi specificando il nuovo colore.</span><span class="sxs-lookup"><span data-stu-id="ce968-113">To change the color associated with an existing server node, you must disconnect and then reconnect specifying the new color.</span></span>  
  
##  <a name="set-the-status-color-for-a-server-in-object-explorer"></a><a name="SetOEServerColor"></a> <span data-ttu-id="ce968-114">Impostare il colore di stato per un server in Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="ce968-114">Set the Status Color for a Server in Object Explorer</span></span>  
 <span data-ttu-id="ce968-115">**Per impostare un colore di stato per un server in Esplora oggetti**</span><span class="sxs-lookup"><span data-stu-id="ce968-115">**To set a server status color in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="ce968-116">In **Esplora oggetti** fare clic sul pulsante **Connetti**, quindi selezionare **Motore di database...**</span><span class="sxs-lookup"><span data-stu-id="ce968-116">In **Object Explorer**, select the **Connect** button and then select **Database Engine...**.</span></span>  
  
2.  <span data-ttu-id="ce968-117">Nella finestra di dialogo **Connetti al server** selezionare **Opzioni >>** .</span><span class="sxs-lookup"><span data-stu-id="ce968-117">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
3.  <span data-ttu-id="ce968-118">Selezionare la casella di controllo **Usa colore personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="ce968-118">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="ce968-119">Per selezionare il colore, fare clic sul pulsante **Seleziona...**</span><span class="sxs-lookup"><span data-stu-id="ce968-119">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="ce968-120">Selezionare un colore di base o personalizzato, quindi scegliere OK.</span><span class="sxs-lookup"><span data-stu-id="ce968-120">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="ce968-121">Immettere le altre informazioni di connessione, quindi fare clic sul pulsante **Connetti** .</span><span class="sxs-lookup"><span data-stu-id="ce968-121">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
##  <a name="set-the-status-color-for-a-registered-server"></a><a name="SetRegServerColor"></a> <span data-ttu-id="ce968-122">Impostare il colore di stato per un server registrato</span><span class="sxs-lookup"><span data-stu-id="ce968-122">Set the Status Color For a Registered Server</span></span>  
 <span data-ttu-id="ce968-123">**Per impostare il colore di stato per un server registrato**</span><span class="sxs-lookup"><span data-stu-id="ce968-123">**To set a server color For a Registered Server**</span></span>  
  
1.  <span data-ttu-id="ce968-124">In **Server registrati** fare clic con il pulsante destro del mouse sul nodo server desiderato, quindi scegliere **Proprietà...**</span><span class="sxs-lookup"><span data-stu-id="ce968-124">In **Registered Servers**, right click the server node and then select **Properties...**.</span></span>  
  
2.  <span data-ttu-id="ce968-125">Nella finestra di dialogo **Modifica proprietà registrazione server** selezionare la scheda **Proprietà connessione** .</span><span class="sxs-lookup"><span data-stu-id="ce968-125">On the **Edit Server Registration Properties** dialog, select the **Connection Properties** tab.</span></span>  
  
3.  <span data-ttu-id="ce968-126">Selezionare la casella di controllo **Usa colore personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="ce968-126">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="ce968-127">Per selezionare il colore, fare clic sul pulsante **Seleziona...**</span><span class="sxs-lookup"><span data-stu-id="ce968-127">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="ce968-128">Selezionare un colore di base o personalizzato, quindi scegliere OK.</span><span class="sxs-lookup"><span data-stu-id="ce968-128">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="ce968-129">Fare clic sul pulsante **Salva** nella finestra di dialogo **Modifica proprietà registrazione server** .</span><span class="sxs-lookup"><span data-stu-id="ce968-129">Select the **Save** button on the **Edit Server Registration Properties** dialog.</span></span>  
  
##  <a name="open-an-editor-using-a-server-color"></a><a name="OpenServerColor"></a> <span data-ttu-id="ce968-130">Aprire un editor utilizzando un colore di server</span><span class="sxs-lookup"><span data-stu-id="ce968-130">Open An Editor Using a Server Color</span></span>  
 <span data-ttu-id="ce968-131">**Per aprire una finestra di editor utilizzando un colore di server**</span><span class="sxs-lookup"><span data-stu-id="ce968-131">**To open an editor window using a server color**</span></span>  
  
-   <span data-ttu-id="ce968-132">Fare clic con il pulsante destro del mouse su un nodo server in **Esplora oggetti** o **Server registrati**, quindi scegliere **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ce968-132">Right-click a server node in either **Object Explorer** or **Registered Servers**, and select **New Query**.</span></span>  
  
-   <span data-ttu-id="ce968-133">In alternativa, evidenziare un nodo server, quindi fare clic sul pulsante **Nuova query** della barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="ce968-133">Alternatively, highlight a server node, and then select the **New Query** toolbar button.</span></span>  
  
-   <span data-ttu-id="ce968-134">La barra di stato della finestra dell'editor utilizzerà il colore definito per il server associato.</span><span class="sxs-lookup"><span data-stu-id="ce968-134">The status bar in the editor window will use the color defined for the associated server.</span></span>  
  
##  <a name="open-an-editor-specifying-a-status-color"></a><a name="OpenSpecColor"></a> <span data-ttu-id="ce968-135">Aprire un editor specificando un colore di stato</span><span class="sxs-lookup"><span data-stu-id="ce968-135">Open an Editor Specifying a Status Color</span></span>  
 <span data-ttu-id="ce968-136">**Per aprire una finestra di editor specificando un colore di stato**</span><span class="sxs-lookup"><span data-stu-id="ce968-136">**To open an editor window specifying a status color**</span></span>  
  
-   <span data-ttu-id="ce968-137">Scegliere **Nuovo** dal menu **File**, quindi selezionare **Query del motore di database**.</span><span class="sxs-lookup"><span data-stu-id="ce968-137">Open the **File** menu, select **New**, and then select **Database Engine Query**.</span></span>  
  
-   <span data-ttu-id="ce968-138">Nella finestra di dialogo **Connetti al server** selezionare **Opzioni >>** .</span><span class="sxs-lookup"><span data-stu-id="ce968-138">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
-   <span data-ttu-id="ce968-139">Selezionare la casella di controllo **Usa colore personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="ce968-139">Select the **Use custom color** check box.</span></span>  
  
-   <span data-ttu-id="ce968-140">Per selezionare il colore, fare clic sul pulsante **Seleziona...**</span><span class="sxs-lookup"><span data-stu-id="ce968-140">To select the color, select the **Select...** button.</span></span>  
  
-   <span data-ttu-id="ce968-141">Selezionare un colore di base o personalizzato, quindi scegliere OK.</span><span class="sxs-lookup"><span data-stu-id="ce968-141">Select either a basic or custom color, then select OK.</span></span>  
  
-   <span data-ttu-id="ce968-142">Immettere le altre informazioni di connessione, quindi fare clic sul pulsante **Connetti** .</span><span class="sxs-lookup"><span data-stu-id="ce968-142">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce968-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce968-143">See Also</span></span>  
 [<span data-ttu-id="ce968-144">Editor di query e di testo &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ce968-144">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](../scripting/query-and-text-editors-sql-server-management-studio.md)  
  
  
