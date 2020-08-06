---
title: Gestione di connessioni e sessioni (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- statefulness [XML for Analysis]
- statelessness [XML for Analysis]
- XML for Analysis, sessions
- states [XML for Analysis]
- XMLA, sessions
- sessions [XML for Analysis]
ms.assetid: b83bb3ff-09be-4fda-9d1d-6248e04ffb21
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7bfe876f6874193fd0885f16d91caa9f6fe8b172
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627474"
---
# <a name="managing-connections-and-sessions-xmla"></a><span data-ttu-id="01418-102">Gestione di connessioni e sessioni (XMLA)</span><span class="sxs-lookup"><span data-stu-id="01418-102">Managing Connections and Sessions (XMLA)</span></span>
  <span data-ttu-id="01418-103">*Informazioni sullo stato* è una condizione durante la quale il server conserva l'identità e il contesto di un client tra le chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="01418-103">*Statefulness* is a condition during which the server preserves the identity and context of a client between method calls.</span></span> <span data-ttu-id="01418-104">L' *assenza* di stato è una condizione durante la quale il server non memorizza l'identità e il contesto di un client al termine di una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="01418-104">*Statelessness* is a condition during which the server does not remember the identity and context of a client after a method call finishes.</span></span>  
  
 <span data-ttu-id="01418-105">Per fornire informazioni sullo stato, XML for Analysis (XMLA) supporta le *sessioni* che consentono di eseguire insieme una serie di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="01418-105">To provide statefulness, XML for Analysis (XMLA) supports *sessions* that allow a series of statements to be performed together.</span></span> <span data-ttu-id="01418-106">Un esempio di tale serie di istruzioni potrebbe essere la creazione di un membro calcolato da utilizzare in query successive.</span><span class="sxs-lookup"><span data-stu-id="01418-106">An example of such a series of statements would be the creation of a calculated member that is to be used in subsequent queries.</span></span>  
  
 <span data-ttu-id="01418-107">In genere le sessioni in XMLA si comportano nel modo indicato dalla specifica OLE DB 2.6 e descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="01418-107">In general, sessions in XMLA follow the following behavior outlined by the OLE DB 2.6 specification:</span></span>  
  
-   <span data-ttu-id="01418-108">Le sessioni definiscono l'ambito del contesto dei comandi e delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="01418-108">Sessions define transaction and command context scope.</span></span>  
  
-   <span data-ttu-id="01418-109">È possibile eseguire più comandi nel contesto di una singola sessione.</span><span class="sxs-lookup"><span data-stu-id="01418-109">Multiple commands can be run in the context of a single session.</span></span>  
  
-   <span data-ttu-id="01418-110">Il supporto per le transazioni nel contesto XMLA è tramite comandi specifici del provider inviati con il metodo [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) .</span><span class="sxs-lookup"><span data-stu-id="01418-110">Support for transactions in the XMLA context is through provider-specific commands sent with the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
 <span data-ttu-id="01418-111">XMLA definisce una modalità per supportare sessioni in un ambiente Web in modo analogo all'approccio utilizzato dal protocollo DAV (Distributed Authoring and Versioning) per implementare il blocco in un ambiente a regime di controllo libero.</span><span class="sxs-lookup"><span data-stu-id="01418-111">XMLA defines a way to support sessions in a Web environment in a mode similar to the approach used by the Distributed Authoring and Versioning (DAV) protocol to implement locking in a loosely coupled environment.</span></span> <span data-ttu-id="01418-112">L'analogia con il protocollo DAV consiste nel fatto che è consentita la scadenza delle sessioni nel provider per diversi motivi, ad esempio se si verifica un timeout o un errore di connessione.</span><span class="sxs-lookup"><span data-stu-id="01418-112">This implementation parallels DAV in that the provider is allowed to expire sessions for various reasons (for example, a timeout or connection error).</span></span> <span data-ttu-id="01418-113">Quando le sessioni sono supportate, i servizi Web devono essere consapevoli e pronti per gestire di set interrotti di comandi che devono essere riavviati.</span><span class="sxs-lookup"><span data-stu-id="01418-113">When sessions are supported, Web services must be aware and ready to handle interrupted sets of commands that must be restarted.</span></span>  
  
 <span data-ttu-id="01418-114">La specifica SOAP (Simple Object Access Protocol ) definita dal World Wide Web Consortium (W3C) consiglia l'utilizzo di intestazioni SOAP per la compilazione di nuovi protocolli nella parte superiore dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="01418-114">The World Wide Web Consortium (W3C) Simple Object Access Protocol (SOAP) specification recommends using SOAP headers for building up new protocols on top of SOAP messages.</span></span> <span data-ttu-id="01418-115">Nella tabella seguente vengono elencati gli elementi dell'intestazione SOAP e gli attributi che XMLA definisce per avviare, gestire e chiudere una sessione.</span><span class="sxs-lookup"><span data-stu-id="01418-115">The following table lists the SOAP header elements and attributes that XMLA defines for initiating, maintaining, and closing a session.</span></span>  
  
|<span data-ttu-id="01418-116">Intestazione SOAP</span><span class="sxs-lookup"><span data-stu-id="01418-116">SOAP header</span></span>|<span data-ttu-id="01418-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01418-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="01418-118">BeginSession</span><span class="sxs-lookup"><span data-stu-id="01418-118">BeginSession</span></span>|<span data-ttu-id="01418-119">Questa intestazione richiede al provider di creare una nuova sessione.</span><span class="sxs-lookup"><span data-stu-id="01418-119">This header requests the provider to create a new session.</span></span> <span data-ttu-id="01418-120">Il provider deve rispondere costruendo una nuova sessione e restituendo l'ID di sessione come parte dell'intestazione Session nella risposta SOAP.</span><span class="sxs-lookup"><span data-stu-id="01418-120">The provider should respond by constructing a new session and returning the session ID as part of the Session header in the SOAP response.</span></span>|  
|<span data-ttu-id="01418-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="01418-121">SessionId</span></span>|<span data-ttu-id="01418-122">Area del valore che contiene l'ID di sessione da utilizzare in ogni chiamata al metodo per il resto della sessione.</span><span class="sxs-lookup"><span data-stu-id="01418-122">The value area contains the session ID that must be used in each method call for the rest of the session.</span></span> <span data-ttu-id="01418-123">Nella risposta SOAP il provider invia questo tag, che deve essere inviato inoltre anche dal client con ogni elemento dell'intestazione Session.</span><span class="sxs-lookup"><span data-stu-id="01418-123">The provider in the SOAP response sends this tag and the client must also send this attribute with each Session header element.</span></span>|  
|<span data-ttu-id="01418-124">sessione</span><span class="sxs-lookup"><span data-stu-id="01418-124">Session</span></span>|<span data-ttu-id="01418-125">Per ogni chiamata al metodo che si verifica nella sessione, questa intestazione deve essere utilizzata e l'ID di sessione deve essere incluso nell'area del valore dell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="01418-125">For every method call that occurs in the session, this header must be used, and the session ID must be included in the value area of the header.</span></span>|  
|<span data-ttu-id="01418-126">EndSession</span><span class="sxs-lookup"><span data-stu-id="01418-126">EndSession</span></span>|<span data-ttu-id="01418-127">Per terminare la sessione, utilizzare questa intestazione.</span><span class="sxs-lookup"><span data-stu-id="01418-127">To terminate the session, use this header.</span></span> <span data-ttu-id="01418-128">L'ID di sessione deve essere incluso con l'area del valore.</span><span class="sxs-lookup"><span data-stu-id="01418-128">The session ID must be included with the value area.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="01418-129">Un ID di sessione non garantisce che una sessione rimanga valida.</span><span class="sxs-lookup"><span data-stu-id="01418-129">A session ID does not guarantee that a session stays valid.</span></span> <span data-ttu-id="01418-130">Se la sessione scade (ad esempio se si verifica un timeout o se la connessione si interrompe), il provider può scegliere di terminare le azioni di tale sessione e di eseguirne il rollback.</span><span class="sxs-lookup"><span data-stu-id="01418-130">If the session expires (for example, if it times out or the connection is lost), the provider can choose to end and roll back that session's actions.</span></span> <span data-ttu-id="01418-131">Di conseguenza, tutte le chiamate al metodo successive eseguite dal client su un ID di sessione avranno esito negativo e restituiranno un errore che indica che la sessione non è valida.</span><span class="sxs-lookup"><span data-stu-id="01418-131">As a result, all subsequent method calls from the client on a session ID fail with an error signaling a session that is not valid.</span></span> <span data-ttu-id="01418-132">Un client deve gestire questa condizione e deve essere preparato per inviare nuovamente le chiamate al metodo della sessione a partire dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="01418-132">A client should handle this condition and be prepared to resend the session method calls from the beginning.</span></span>  
  
## <a name="legacy-code-example"></a><span data-ttu-id="01418-133">Codice di esempio legacy</span><span class="sxs-lookup"><span data-stu-id="01418-133">Legacy Code Example</span></span>  
 <span data-ttu-id="01418-134">Nell'esempio seguente viene illustrato come sono supportate le sessioni.</span><span class="sxs-lookup"><span data-stu-id="01418-134">The following example shows how sessions are supported.</span></span>  
  
1.  <span data-ttu-id="01418-135">Per avviare la sessione, aggiungere un'intestazione BeginSession in SOAP alla chiamata al metodo XMLA in uscita dal client.</span><span class="sxs-lookup"><span data-stu-id="01418-135">To begin the session, add a BeginSession header in SOAP to the outbound XMLA method call from the client.</span></span> <span data-ttu-id="01418-136">L'area del valore è inizialmente vuota perché l'ID di sessione non è ancora noto.</span><span class="sxs-lookup"><span data-stu-id="01418-136">The value area is initially blank because the session ID is not yet known.</span></span>  
  
    ```  
    <SOAP-ENV:Envelope  
       xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
       SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
       <SOAP-ENV:Header>  
          <XA:BeginSession  
             xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
             xsi:type="xsd:int"  
             mustUnderstand="1"/>  
       </SOAP-ENV:Header>  
       <SOAP-ENV:Body>  
          ...<!-- Discover or Execute call goes here.-->  
       </SOAP-ENV:Body>  
    </SOAP-ENV:Envelope>  
    ```  
  
2.  <span data-ttu-id="01418-137">Il messaggio di risposta SOAP del provider include l'ID sessione nell'area dell'intestazione restituita, utilizzando il tag di intestazione XMLA \<SessionId> .</span><span class="sxs-lookup"><span data-stu-id="01418-137">The SOAP response message from the provider includes the session ID in the return header area, using the XMLA header tag \<SessionId>.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
3.  <span data-ttu-id="01418-138">Per ogni chiamata al metodo nella sessione, l'intestazione Session deve essere aggiunta e deve contenere l'ID di sessione restituito dal provider.</span><span class="sxs-lookup"><span data-stu-id="01418-138">For each method call in the session, the Session header must be added, containing the session ID returned from the provider.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:Session  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
4.  <span data-ttu-id="01418-139">Al termine della sessione, \<EndSession> viene usato il tag, che contiene il valore dell'ID di sessione correlato.</span><span class="sxs-lookup"><span data-stu-id="01418-139">When the session is complete, the \<EndSession> tag is used, containing the related session ID value.</span></span>  
  
    ```  
    <SOAP-ENV:Header>  
       <XA:EndSession  
          xmlns:XA="urn:schemas-microsoft-com:xml-analysis"  
          xsi:type="xsd:int"  
          mustUnderstand="1"  
          SessionId="581"/>  
    </SOAP-ENV:Header>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="01418-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01418-140">See Also</span></span>  
 [<span data-ttu-id="01418-141">Sviluppo con XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="01418-141">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
