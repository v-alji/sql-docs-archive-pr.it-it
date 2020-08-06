---
title: Gestione connessione FTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- FTP connection manager
- connections [Integration Services], FTP
- connection managers [Integration Services], FTP
ms.assetid: c4f43455-29ca-44ba-ac7f-ea729b1daf93
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a402f399ba4b7e69fc1d3cbca9dd64b32217ced1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713399"
---
# <a name="ftp-connection-manager"></a><span data-ttu-id="15215-102">gestione connessione FTP</span><span class="sxs-lookup"><span data-stu-id="15215-102">FTP Connection Manager</span></span>
  <span data-ttu-id="15215-103">Una gestione connessione FTP consente la connessione di un pacchetto a un server FTP (File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="15215-103">An FTP connection manager enables a package to connect to a File Transfer Protocol (FTP) server.</span></span> <span data-ttu-id="15215-104">Questa gestione connessione viene usata dall'attività FTP inclusa in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15215-104">The FTP task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="15215-105">Quando si aggiunge una gestione connessione FTP a un pacchetto, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea una gestione connessione che in fase di esecuzione verrà risolta in una connessione FTP, imposta le proprietà della gestione connessione e quindi la aggiunge alla raccolta `Connections` del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="15215-105">When you add an FTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that can be resolved as an FTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="15215-106">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `FTP`.</span><span class="sxs-lookup"><span data-stu-id="15215-106">The `ConnectionManagerType` property of the connection manager is set to `FTP`.</span></span>  
  
 <span data-ttu-id="15215-107">Per configurare la gestione connessione FTP, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="15215-107">You can configure the FTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="15215-108">Specificare il nome e la porta del server.</span><span class="sxs-lookup"><span data-stu-id="15215-108">Specify a server name and server port.</span></span>  
  
-   <span data-ttu-id="15215-109">Specificare l'accesso anonimo oppure un nome utente e una password per l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="15215-109">Specify anonymous access, or provide a user name and a password for basic authentication.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="15215-110">La gestione connessione FTP supporta solo l'autenticazione anonima e l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="15215-110">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="15215-111">Non supporta l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="15215-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="15215-112">Impostare il timeout, il numero di tentativi e la quantità di dati da copiare di volta in volta.</span><span class="sxs-lookup"><span data-stu-id="15215-112">Set the time-out, number of retries, and the amount of data to copy at a time.</span></span>  
  
-   <span data-ttu-id="15215-113">Indicare se la gestione connessione FTP utilizza la modalità attiva o passiva.</span><span class="sxs-lookup"><span data-stu-id="15215-113">Indicate whether the FTP connection manager uses passive or active mode.</span></span>  
  
 <span data-ttu-id="15215-114">A seconda della configurazione del sito FTP a cui si connette, può essere necessario modificare i seguenti valori predefiniti della gestione connessione FTP:</span><span class="sxs-lookup"><span data-stu-id="15215-114">Depending on the configuration of the FTP site to which the FTP connection manager connects, you may need to change the following default values of the connection manager:</span></span>  
  
-   <span data-ttu-id="15215-115">La porta del server è impostata su 21.</span><span class="sxs-lookup"><span data-stu-id="15215-115">The server port is set to 21.</span></span> <span data-ttu-id="15215-116">È necessario specificare la porta su cui è in ascolto il sito FTP.</span><span class="sxs-lookup"><span data-stu-id="15215-116">You should specify the port that the FTP site listens to.</span></span>  
  
-   <span data-ttu-id="15215-117">Il nome utente è impostato su "anonymous".</span><span class="sxs-lookup"><span data-stu-id="15215-117">The user name is set to "anonymous".</span></span> <span data-ttu-id="15215-118">È necessario specificare le credenziali richieste dal sito FTP.</span><span class="sxs-lookup"><span data-stu-id="15215-118">You should provide the credentials that the FTP site requires.</span></span>  
  
## <a name="activepassive-modes"></a><span data-ttu-id="15215-119">Modalità attiva e passiva</span><span class="sxs-lookup"><span data-stu-id="15215-119">Active/Passive Modes</span></span>  
 <span data-ttu-id="15215-120">La gestione connessione FTP può inviare e ricevere file utilizzando la modalità attiva o passiva.</span><span class="sxs-lookup"><span data-stu-id="15215-120">An FTP connection manager can send and receive files using either active mode or passive mode.</span></span> <span data-ttu-id="15215-121">Nella modalità attiva la connessione dati viene aperta dal server, mentre nella modalità passiva la connessione dati viene aperta dal client.</span><span class="sxs-lookup"><span data-stu-id="15215-121">In active mode, the server initiates the data connection, and in passive mode, the client initiates the data connection.</span></span>  
  
## <a name="configuration-of-the-ftp-connection-manager"></a><span data-ttu-id="15215-122">Configurazione della gestione connessione FTP</span><span class="sxs-lookup"><span data-stu-id="15215-122">Configuration of the FTP Connection Manager</span></span>  
 <span data-ttu-id="15215-123">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="15215-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="15215-124">Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vedere [Editor gestione connessione FTP](../ftp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="15215-124">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [FTP Connection Manager Editor](../ftp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="15215-125">Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere l'articolo relativo a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="15215-125">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15215-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15215-126">See Also</span></span>  
 <span data-ttu-id="15215-127">[Attività FTP](../control-flow/ftp-task.md) </span><span class="sxs-lookup"><span data-stu-id="15215-127">[FTP Task](../control-flow/ftp-task.md) </span></span>  
 [<span data-ttu-id="15215-128">Connessioni in Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="15215-128">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
