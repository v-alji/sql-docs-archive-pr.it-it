---
title: Creare o eliminare un alias server per l'uso da un client (Gestione configurazione SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- server alias
helpviewer_keywords:
- aliases [SQL Server], deleting
- aliases [SQL Server], creating
ms.assetid: b687e376-ee33-470d-b65a-87246bfefe6f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bead257b40c33e3640b18890a7d109d774131123
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629610"
---
# <a name="create-or-delete-a-server-alias-for-use-by-a-client-sql-server-configuration-manager"></a><span data-ttu-id="1f7a0-102">Creazione o eliminazione di un alias server per l'utilizzo da parte di un client (Gestione configurazione SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1f7a0-102">Create or Delete a Server Alias for Use by a Client (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="1f7a0-103">In questo argomento viene illustrato come creare o eliminare un alias del server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-103">This topic describes how to create or delete a server alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="1f7a0-104">Un alias rappresenta un nome alternativo che può essere utilizzato per stabilire una connessione.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-104">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="1f7a0-105">L'alias incapsula gli elementi necessari di una stringa di connessione e li espone con un nome scelto dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-105">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="1f7a0-106">Gli alias possono essere utilizzati con qualsiasi applicazione client.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-106">Aliases can be used with any client application.</span></span> <span data-ttu-id="1f7a0-107">Grazie alla creazione di alias server, il computer client può connettersi a più server utilizzando protocolli di rete diversi, senza dover specificare ogni volta i dettagli relativi al protocollo e alla connessione.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-107">By creating server aliases, your client computer can connect to multiple servers using different network protocols, without having to specify the protocol and connection details for each one.</span></span> <span data-ttu-id="1f7a0-108">È inoltre possibile disporre di più protocolli di rete abilitati simultaneamente, anche se è necessario utilizzarli solo occasionalmente.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-108">In addition, you can also have different network protocols enabled all the time, even if you only need to use them occasionally.</span></span> <span data-ttu-id="1f7a0-109">Se il server è stato configurato per restare in attesa su una named pipe o un numero di porta non predefinito ed è stato disabilitato il servizio SQL Server Browser, creare un alias per specificare il nuovo numero di porta o la nuova named pipe.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-109">If you have configured the server to listen on a non-default port number or named pipe, and you have disabled the SQL Server Browser service, create an alias that specifies the new port number or named pipe.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1f7a0-110">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="1f7a0-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-create-an-alias"></a><span data-ttu-id="1f7a0-111">Per creare un alias</span><span class="sxs-lookup"><span data-stu-id="1f7a0-111">To create an alias</span></span>  
  
1.  <span data-ttu-id="1f7a0-112">In Gestione configurazione SQL Server espandere **Configurazione SQL Server Native Client**, fare clic con il pulsante destro del mouse su **Alias**e quindi scegliere **Nuovo alias**.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-112">In SQL Server Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Aliases**, and then click **New Alias**.</span></span>  
  
2.  <span data-ttu-id="1f7a0-113">Nella casella **Nome alias** digitare il nome dell'alias.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-113">In the **Alias Name** box, type the name of the alias.</span></span> <span data-ttu-id="1f7a0-114">Le applicazioni client utilizzeranno questo nome durante la connessione.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-114">Client applications use this name when they connect.</span></span>  
  
3.  <span data-ttu-id="1f7a0-115">Nella casella **Server** digitare il nome o l'indirizzo IP di un server.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-115">In the **Server** box, type the name or IP address of a server.</span></span> <span data-ttu-id="1f7a0-116">Per un'istanza denominata, aggiungere il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-116">For a named instance append the instance name.</span></span>  
  
4.  <span data-ttu-id="1f7a0-117">Nella casella **Protocollo** selezionare il protocollo usato per questo alias.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-117">In the **Protocol** box, select the protocol used for this alias.</span></span> <span data-ttu-id="1f7a0-118">La selezione di un protocollo comporta la modifica del titolo della casella delle proprietà facoltative in Numero porta, Nome pipe o Stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-118">Selecting a protocol, changes the title of the optional properties box to Port No, Pipe Name, or Connection String.</span></span>  
  
 <span data-ttu-id="1f7a0-119">Le stringhe di connessione descritte nella guida di Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono essere utili per i programmatori nella creazione di stringhe di connessione personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-119">The connection strings described in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager Help can be useful for programmers who create their own connection strings.</span></span> <span data-ttu-id="1f7a0-120">Per accedere a queste informazioni, nella finestra di dialogo **Nuovo alias** premere F1 o fare clic su **Guida**.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-120">To access this information, in the **New Alias** dialog box, press F1, or click **Help**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f7a0-121">Se un alias configurato si connette a un'istanza o a un server non valido, disabilitare e quindi riabilitare il protocollo di rete associato.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-121">If a configured alias is connecting to the wrong server or instance, disable and then reenable the associated network protocol.</span></span> <span data-ttu-id="1f7a0-122">In questo modo, vengono eliminate tutte le informazioni memorizzate nella cache relative alla connessione e il client può connettersi in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-122">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>  
  
#### <a name="to-delete-an-alias"></a><span data-ttu-id="1f7a0-123">Per eliminare un alias</span><span class="sxs-lookup"><span data-stu-id="1f7a0-123">To delete an alias</span></span>  
  
1.  <span data-ttu-id="1f7a0-124">In Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] espandere **Configurazione SQL Server Native Client**e quindi fare clic su **Alias**.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-124">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, and then click **Aliases**.</span></span>  
  
2.  <span data-ttu-id="1f7a0-125">Nel riquadro dei dettagli fare clic con il pulsante destro del mouse sulla tabella da eliminare, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="1f7a0-125">In the details pane, right-click the alias that you want to delete, and then click **Delete**.</span></span>  
  
  
