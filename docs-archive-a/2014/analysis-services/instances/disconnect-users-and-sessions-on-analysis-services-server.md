---
title: Disconnettere utenti e sessioni nel server Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ending user activity [Analysis Services]
- connections [Analysis Services]
- sessions [Analysis Services]
ms.assetid: 3b0145a2-f21d-4dd0-a09e-83afeb2ff4a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: bac20b663b0a65902c70e7a3c3bfe3f27b7bf061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714748"
---
# <a name="disconnect-users-and-sessions-on-analysis-services-server"></a><span data-ttu-id="8b73a-102">Disconnettere utenti e sessioni sul server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8b73a-102">Disconnect Users and Sessions on Analysis Services Server</span></span>
  <span data-ttu-id="8b73a-103">Nell'ambito della gestione del carico di lavoro, un amministratore di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] può terminare l'attività dell'utente</span><span class="sxs-lookup"><span data-stu-id="8b73a-103">An administrator of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] may want to end user activity as part of workload management.</span></span> <span data-ttu-id="8b73a-104">annullando sessioni e connessioni.</span><span class="sxs-lookup"><span data-stu-id="8b73a-104">You do this by canceling sessions and connections.</span></span> <span data-ttu-id="8b73a-105">Le sessioni possono essere create automaticamente durante l'esecuzione di una query (implicite) oppure denominate dall'amministratore al momento della creazione (esplicite).</span><span class="sxs-lookup"><span data-stu-id="8b73a-105">Sessions can be formed automatically when a query is run (implicit), or named at the time of creation by the administrator (explicit).</span></span> <span data-ttu-id="8b73a-106">Le connessioni sono circuiti aperti per l'esecuzione delle query.</span><span class="sxs-lookup"><span data-stu-id="8b73a-106">Connections are open conduits over which queries can be run.</span></span> <span data-ttu-id="8b73a-107">È possibile terminare sia le sessioni che le connessioni mentre sono attive.</span><span class="sxs-lookup"><span data-stu-id="8b73a-107">Both sessions and connections can be ended while they are active.</span></span> <span data-ttu-id="8b73a-108">Ad esempio, un amministratore può terminare l'elaborazione di una sessione se il processo richiede tempi troppo lunghi o non è certo che il comando in esecuzione sia stato registrato correttamente.</span><span class="sxs-lookup"><span data-stu-id="8b73a-108">For example, an administrator may want to end processing for a session if the processing is taking too long or if some doubt has arisen as to whether the command being executed was written correctly.</span></span>  
  
## <a name="ending-sessions-and-connections"></a><span data-ttu-id="8b73a-109">Terminazione di sessioni e connessioni</span><span class="sxs-lookup"><span data-stu-id="8b73a-109">Ending Sessions and Connections</span></span>  
 <span data-ttu-id="8b73a-110">Per gestire sessioni e connessioni, è possibile utilizzare viste a gestione dinamica (DMV) e XMLA:</span><span class="sxs-lookup"><span data-stu-id="8b73a-110">To manage sessions and connections, you can use Dynamic Management Views (DMVs) and XMLA:</span></span>  
  
1.  <span data-ttu-id="8b73a-111">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi a un'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="8b73a-111">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to an Analysis Services instance.</span></span>  
  
2.  <span data-ttu-id="8b73a-112">Incollare una delle query DMV seguenti in una finestra Query MDX per ottenere un elenco di tutti i comandi, le sessioni e le connessioni attualmente in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="8b73a-112">Paste any one of the following DMV queries in an MDX query window to get a list of all sessions, connections, and commands that are currently executing:</span></span>  
  
     `Select * from $System.Discover_Sessions`  
  
     `Select * from $System.Discover_Connections`  
  
     `Select * from $System.Discover_Commands`  
  
3.  <span data-ttu-id="8b73a-113">Premere F5 per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="8b73a-113">Press F5 to execute the query.</span></span>  
  
     <span data-ttu-id="8b73a-114">La query DMV restituisce informazioni sulla sessione e sulla connessione in un set di risultati tabulare più facile da leggere e copiare.</span><span class="sxs-lookup"><span data-stu-id="8b73a-114">The DMV query returns session and connection information in a tabular result set that is easier read and copy from.</span></span>  
  
 <span data-ttu-id="8b73a-115">Tenere aperta la finestra Query.</span><span class="sxs-lookup"><span data-stu-id="8b73a-115">Keep the query window open.</span></span> <span data-ttu-id="8b73a-116">Nel passaggio successivo sarà necessario tornare a questa pagina per copiare i valori SPID della sessione da disconnettere.</span><span class="sxs-lookup"><span data-stu-id="8b73a-116">In the next step, you will want to return to this page to copy the SPIDs of the session you want to disconnect.</span></span>  
  
 <span data-ttu-id="8b73a-117">Per terminare una sessione, aprire una seconda finestra Query XMLA.</span><span class="sxs-lookup"><span data-stu-id="8b73a-117">To end a session, open a second XMLA query window.</span></span>  
  
1.  <span data-ttu-id="8b73a-118">Incollare la sintassi seguente in una finestra Query MDX, sostituendo il segnaposto ConnectionID, SessionID o SPID con un valore valido copiato dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="8b73a-118">Paste the following syntax into an MDX query window, replacing the ConnectionID, SessionID, or SPID placeholder with a valid value copied from the previous step.</span></span>  
  
    ```  
    <Cancel xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  
       <ConnectionID>111</ConnectionID>  
       <SessionID>222</SessionID>  
       <SPID>333</SPID>  
  
    <CancelAssociated>1</CancelAssociated>  
    </Cancel>  
  
    ```  
  
2.  <span data-ttu-id="8b73a-119">Premere F5 per eseguire il comando Annulla.</span><span class="sxs-lookup"><span data-stu-id="8b73a-119">Press F5 to execute the cancel command.</span></span>  
  
 <span data-ttu-id="8b73a-120">Se si modifica una connessione, saranno annullate tutte le sessioni e i valori SPID e la sessione host sarà chiusa.</span><span class="sxs-lookup"><span data-stu-id="8b73a-120">Ending a connection cancels all sessions and SPIDs, closing the host session.</span></span>  
  
 <span data-ttu-id="8b73a-121">Se si termina una sessione, saranno arrestati tutti i comandi (SPID) eseguiti nel corso di tale sessione.</span><span class="sxs-lookup"><span data-stu-id="8b73a-121">Ending a session stops all commands (SPIDs) that are running as part of that session.</span></span>  
  
 <span data-ttu-id="8b73a-122">Se si termina un SPID, sarà annullato un comando specifico.</span><span class="sxs-lookup"><span data-stu-id="8b73a-122">Ending a SPID cancels a particular commend.</span></span>  
  
 <span data-ttu-id="8b73a-123">In rari casi, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] non chiuderà una connessione se non è possibile rilevare tutte le sessioni e i valori SPID associati alla connessione, ad esempio nel caso in cui più sessioni siano aperte in uno scenario HTTP.</span><span class="sxs-lookup"><span data-stu-id="8b73a-123">In rare cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will not close a connection if it cannot track all the sessions and SPIDs associated with the connection (for example, when multiple sessions are open in an HTTP scenario).</span></span>  
  
 <span data-ttu-id="8b73a-124">Per altre informazioni sul codice XMLA a cui si fa riferimento in questo argomento, vedere [Metodo Execute &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) ed [Elemento Cancel &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="8b73a-124">For more information about the XMLA referenced in this topic, see [Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) and [Cancel Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b73a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b73a-125">See Also</span></span>  
 <span data-ttu-id="8b73a-126">[Gestione delle connessioni e delle sessioni &#40;&#41;XMLA](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span><span class="sxs-lookup"><span data-stu-id="8b73a-126">[Managing Connections and Sessions &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span></span>  
 <span data-ttu-id="8b73a-127">[Elemento BeginSession &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="8b73a-127">[BeginSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span></span>  
 <span data-ttu-id="8b73a-128">[Elemento EndSession &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="8b73a-128">[EndSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span></span>  
 [<span data-ttu-id="8b73a-129">Elemento Session &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="8b73a-129">Session Element &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/session-element-xmla)  
  
  
