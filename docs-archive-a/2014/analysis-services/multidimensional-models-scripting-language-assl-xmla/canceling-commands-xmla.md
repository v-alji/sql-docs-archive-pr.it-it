---
title: Annullamento di comandi (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- connections [XML for Analysis]
- associated connections [XML for Analysis]
- XML for Analysis, canceling
- associated sessions [XML for Analysis]
- canceling connections
- canceling commands
- canceling sessions
- SPID
- XMLA, canceling
- server process IDs [XML for Analysis]
- sessions [XML for Analysis]
ms.assetid: b59f8197-c33d-4e65-9022-848ccba540f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 003c70362c38ae1838b4679abf6485fa031a9143
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712580"
---
# <a name="canceling-commands-xmla"></a><span data-ttu-id="517b3-102">Annullamento di comandi (XMLA)</span><span class="sxs-lookup"><span data-stu-id="517b3-102">Canceling Commands (XMLA)</span></span>
  <span data-ttu-id="517b3-103">A seconda delle autorizzazioni amministrative dell'utente che ha emesso il comando, il comando [Annulla](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) in XML for Analysis (XMLA) può annullare un comando in una sessione, una sessione, una connessione, un processo server o una sessione o una connessione associata.</span><span class="sxs-lookup"><span data-stu-id="517b3-103">Depending on the administrative permissions of the user issuing the command, the [Cancel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) command in XML for Analysis (XMLA) can cancel a command on a session, a session, a connection, a server process, or an associated session or connection.</span></span>  
  
## <a name="canceling-commands"></a><span data-ttu-id="517b3-104">Annullamento di comandi</span><span class="sxs-lookup"><span data-stu-id="517b3-104">Canceling Commands</span></span>  
 <span data-ttu-id="517b3-105">Un utente può annullare il comando attualmente in esecuzione nel contesto della sessione corrente esplicita inviando un comando `Cancel` senza proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="517b3-105">A user can cancel the currently executing command within the context of the current explicit session by sending a `Cancel` command with no specified properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="517b3-106">Un comando in esecuzione in una sessione implicita non può essere annullato da un utente.</span><span class="sxs-lookup"><span data-stu-id="517b3-106">A command running in an implicit session cannot be canceled by a user.</span></span>  
  
### <a name="canceling-batch-commands"></a><span data-ttu-id="517b3-107">Annullamento di comandi batch</span><span class="sxs-lookup"><span data-stu-id="517b3-107">Canceling Batch Commands</span></span>  
 <span data-ttu-id="517b3-108">Se un utente annulla un comando `Batch`, tutti i comandi rimanenti non ancora eseguiti nel comando `Batch` vengono annullati.</span><span class="sxs-lookup"><span data-stu-id="517b3-108">If a user cancels a `Batch` command, then all remaining commands not yet executed within the `Batch` command are canceled.</span></span> <span data-ttu-id="517b3-109">Se il comando `Batch` è transazionale, di tutti i comandi eseguiti prima del comando `Cancel` viene eseguito il rollback.</span><span class="sxs-lookup"><span data-stu-id="517b3-109">If the `Batch` command was transactional, any commands that were executed before the `Cancel` command runs are rolled back.</span></span>  
  
## <a name="canceling-sessions"></a><span data-ttu-id="517b3-110">Annullamento di sessioni</span><span class="sxs-lookup"><span data-stu-id="517b3-110">Canceling Sessions</span></span>  
 <span data-ttu-id="517b3-111">Specificando un identificatore di sessione per una sessione esplicita nella proprietà [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) del `Cancel` comando, un amministratore del database o un amministratore del server può annullare una sessione, incluso il comando attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="517b3-111">By specifying a session identifier for an explicit session in the [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a database administrator or server administrator can cancel a session, including the currently executing command.</span></span> <span data-ttu-id="517b3-112">Un amministratore di database può annullare solo sessioni per i database per i quali dispone delle autorizzazioni amministrative.</span><span class="sxs-lookup"><span data-stu-id="517b3-112">A database administrator can only cancel sessions for databases on which he or she has administrative permissions.</span></span>  
  
 <span data-ttu-id="517b3-113">Un amministratore di database può recuperare le sessioni attive per un database specifico recuperando il set di righe dello schema DISCOVER_SESSIONS.</span><span class="sxs-lookup"><span data-stu-id="517b3-113">A database administrator can retrieve the active sessions for a specified database by retrieving the DISCOVER_SESSIONS schema rowset.</span></span> <span data-ttu-id="517b3-114">Per recuperare il set di righe dello schema DISCOVER_SESSIONS, l'amministratore del database utilizza il `Discover` metodo XMLA e specifica l'identificatore di database appropriato per la colonna di restrizione SESSION_CURRENT_DATABASE nella proprietà [restrictions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) del `Discover` metodo.</span><span class="sxs-lookup"><span data-stu-id="517b3-114">To retrieve the DISCOVER_SESSIONS schema rowset, the database administrator uses the XMLA `Discover` method and specifies the appropriate database identifier for the SESSION_CURRENT_DATABASE restriction column in the [Restrictions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) property of the `Discover` method.</span></span>  
  
## <a name="canceling-connections"></a><span data-ttu-id="517b3-115">Annullamento di connessioni</span><span class="sxs-lookup"><span data-stu-id="517b3-115">Canceling Connections</span></span>  
 <span data-ttu-id="517b3-116">Specificando un identificatore di connessione nella proprietà [ConnectionId](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) del `Cancel` comando, un amministratore del server può annullare tutte le sessioni associate a una determinata connessione, inclusi tutti i comandi in esecuzione, e annullare la connessione.</span><span class="sxs-lookup"><span data-stu-id="517b3-116">By specifying a connection identifier in the [ConnectionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) property of the `Cancel` command, a server administrator can cancel all of the sessions associated with a given connection, including all running commands, and cancel the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="517b3-117">Se l'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] non è in grado di individuare e annullare le sessioni associate a una connessione, ad esempio quando il data pump apre più sessioni fornendo una connettività HTTP, l'istanza non può annullare la connessione.</span><span class="sxs-lookup"><span data-stu-id="517b3-117">If the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cannot locate and cancel the sessions associated with a connection, such as when the data pump opens multiple sessions while providing HTTP connectivity, the instance cannot cancel the connection.</span></span> <span data-ttu-id="517b3-118">Se questa situazione si verifica durante l'esecuzione di un comando `Cancel`, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="517b3-118">If this case is encountered during the execution of a `Cancel` command, an error occurs.</span></span>  
  
 <span data-ttu-id="517b3-119">Un amministratore del server può recuperare le connessioni attive per un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] recuperando il set di righe dello schema DISCOVER_CONNECTIONS tramite il metodo `Discover` XMLA.</span><span class="sxs-lookup"><span data-stu-id="517b3-119">A server administrator can retrieve the active connections for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance by retrieving the DISCOVER_CONNECTIONS schema rowset using the XMLA `Discover` method.</span></span>  
  
## <a name="canceling-server-processes"></a><span data-ttu-id="517b3-120">Annullamento di processi del server</span><span class="sxs-lookup"><span data-stu-id="517b3-120">Canceling Server Processes</span></span>  
 <span data-ttu-id="517b3-121">Specificando un identificatore di processo del server (SPID) nella proprietà [SPID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) del `Cancel` comando, un amministratore del server può annullare i comandi associati a un determinato SPID.</span><span class="sxs-lookup"><span data-stu-id="517b3-121">By specifying a server process identifier (SPID) in the [SPID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a server administrator can cancel the commands associated with a given SPID.</span></span>  
  
## <a name="canceling-associated-sessions-and-connections"></a><span data-ttu-id="517b3-122">Annullamento di sessioni e connessioni associate</span><span class="sxs-lookup"><span data-stu-id="517b3-122">Canceling Associated Sessions and Connections</span></span>  
 <span data-ttu-id="517b3-123">È possibile impostare la proprietà [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) su true per annullare le connessioni, le sessioni e i comandi associati alla connessione, alla sessione o allo SPID specificati nel `Cancel` comando.</span><span class="sxs-lookup"><span data-stu-id="517b3-123">You can set the [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) property to true to cancel the connections, sessions, and commands associated with the connection, session, or SPID specified in the `Cancel` command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="517b3-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="517b3-124">See Also</span></span>  
 <span data-ttu-id="517b3-125">[Metodo Discover &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span><span class="sxs-lookup"><span data-stu-id="517b3-125">[Discover Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span></span>  
 [<span data-ttu-id="517b3-126">Sviluppo con XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="517b3-126">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
