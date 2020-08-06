---
title: 'Passaggio 3: Aggiunta e configurazione di una gestione connessione OLE DB | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: e7b74cba-a0e5-4478-af12-3f81b9484e9e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bc4c885ce6c39c72031dd3b528a769cd47ac8f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628848"
---
# <a name="step-3-adding-and-configuring-an-ole-db-connection-manager"></a><span data-ttu-id="7da91-102">Passaggio 3: Aggiunta e configurazione di una gestione connessione OLE DB</span><span class="sxs-lookup"><span data-stu-id="7da91-102">Step 3: Adding and Configuring an OLE DB Connection Manager</span></span>
  <span data-ttu-id="7da91-103">Dopo aver aggiunto una gestione connessione file flat per connettersi all'origine dati, l'operazione successiva consiste nell'aggiunta di una gestione connessione OLE DB per connettersi alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="7da91-103">After you have added a Flat File connection manager to connect to the data source, the next task is to add an OLE DB connection manager to connect to the destination.</span></span> <span data-ttu-id="7da91-104">Una gestione connessione OLE DB abilita un pacchetto all'estrazione di dati o al caricamento di dati in un'origine dati compatibile con OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7da91-104">An OLE DB connection manager enables a package to extract data from or load data into any OLE DB-compliant data source.</span></span> <span data-ttu-id="7da91-105">Gestione connessione OLE DB consente di specificare il server, il metodo di autenticazione e il database predefinito per la connessione.</span><span class="sxs-lookup"><span data-stu-id="7da91-105">Using the OLE DB Connection manager, you can specify the server, the authentication method, and the default database for the connection.</span></span>  
  
 <span data-ttu-id="7da91-106">In questa lezione verrà creata una gestione connessione OLE DB tramite cui viene utilizzata l'autenticazione di Windows per connettersi all'istanza locale di **AdventureWorksDB2012**.</span><span class="sxs-lookup"><span data-stu-id="7da91-106">In this lesson, you will create an OLE DB connection manager that uses Windows Authentication to connect to the local instance of **AdventureWorksDB2012**.</span></span> <span data-ttu-id="7da91-107">Alla gestione connessione OLE DB creata faranno anche riferimento altri componenti che verranno creati più avanti in questa esercitazione, come la trasformazione Ricerca e la destinazione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="7da91-107">The OLE DB connection manager that you create will also be referenced by other components that you will create later in this tutorial, such as the Lookup transformation and the OLE DB destination.</span></span>  
  
### <a name="to-add-and-configure-an-ole-db-connection-manager-to-the-ssis-package"></a><span data-ttu-id="7da91-108">Per aggiungere e configurare una gestione connessione OLE DB al pacchetto SSIS</span><span class="sxs-lookup"><span data-stu-id="7da91-108">To add and configure an OLE DB Connection Manager to the SSIS package</span></span>  
  
1.  <span data-ttu-id="7da91-109">Fare clic con il pulsante destro del mouse in un punto qualsiasi dell'area **Gestioni connessioni** e quindi fare clic su **Nuova connessione OLE DB**.</span><span class="sxs-lookup"><span data-stu-id="7da91-109">Right-click anywhere in the **Connection Managers** area, and then click **New OLE DB Connection**.</span></span>  
  
2.  <span data-ttu-id="7da91-110">Nella finestra di dialogo **Configura gestione connessione OLE DB** fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="7da91-110">In the **Configure OLE DB Connection Manager** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="7da91-111">Per **Nome server**, immettere **localhost**.</span><span class="sxs-lookup"><span data-stu-id="7da91-111">For **Server name**, enter **localhost**.</span></span>  
  
     <span data-ttu-id="7da91-112">Quando si specifica localhost come nome server, la gestione connessione stabilisce una connessione all'istanza predefinita di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="7da91-112">When you specify localhost as the server name, the connection manager connects to the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the local computer.</span></span> <span data-ttu-id="7da91-113">Per utilizzare un'istanza remota di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], sostituire localhost con il nome del server a cui si desidera connettersi.</span><span class="sxs-lookup"><span data-stu-id="7da91-113">To use a remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], replace localhost with the name of the server to which you want to connect.</span></span>  
  
4.  <span data-ttu-id="7da91-114">Verificare che l'opzione **Usa autenticazione di Windows** sia selezionata nel gruppo **Accesso al server** .</span><span class="sxs-lookup"><span data-stu-id="7da91-114">In the **Log on to the server** group, verify that **Use Windows Authentication** is selected.</span></span>  
  
5.  <span data-ttu-id="7da91-115">Nella casella **selezionare o immettere un nome di database** nel gruppo **Connetti a un database** Digitare o selezionare `AdventureWorksDW2012` .</span><span class="sxs-lookup"><span data-stu-id="7da91-115">In the **Connect to a database** group, in the **Select or enter a database name** box, type or select `AdventureWorksDW2012`.</span></span>  
  
6.  <span data-ttu-id="7da91-116">Fare clic su **Test connessione** per verificare che le impostazioni di connessione specificate siano valida.</span><span class="sxs-lookup"><span data-stu-id="7da91-116">Click **Test Connection** to verify that the connection settings you have specified are valid.</span></span>  
  
7.  <span data-ttu-id="7da91-117">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7da91-117">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="7da91-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7da91-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="7da91-119">Nel riquadro **Connessioni dati** della finestra di dialogo **Configura gestione connessione OLE DB** verificare che sia selezionato **localhost.AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="7da91-119">In the **Data Connections** pane of the **Configure OLE DB Connection Manager** dialog box, verify that **localhost.AdventureWorksDW2012** is selected.</span></span>  
  
10. <span data-ttu-id="7da91-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7da91-120">Click **OK**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="7da91-121">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="7da91-121">Next Task in Lesson</span></span>  
 [<span data-ttu-id="7da91-122">Passaggio 4: Aggiunta di un'attività Flusso di dati al pacchetto</span><span class="sxs-lookup"><span data-stu-id="7da91-122">Step 4: Adding a Data Flow Task to the Package</span></span>](lesson-1-4-adding-a-data-flow-task-to-the-package.md)  
  
## <a name="see-also"></a><span data-ttu-id="7da91-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7da91-123">See Also</span></span>  
 [<span data-ttu-id="7da91-124">Gestione connessione OLE DB</span><span class="sxs-lookup"><span data-stu-id="7da91-124">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
