---
title: Ruolo di SOAP in Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- SOAP [Reporting Services], role in Reporting Services
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: f229c3ef-f2ca-448f-98f1-b8df350b9992
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05445eb1c95c5761595944867b6d0c20a6f1a412
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716096"
---
# <a name="the-role-of-soap-in-reporting-services"></a><span data-ttu-id="1887d-102">Ruolo di SOAP in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1887d-102">The Role of SOAP in Reporting Services</span></span>
  <span data-ttu-id="1887d-103">Il servizio Web ReportServer utilizza la messaggistica SOAP (Simple Object Access Protocol) per inviare comandi basati su testo in una rete.</span><span class="sxs-lookup"><span data-stu-id="1887d-103">The Report Server Web service uses Simple Object Access Protocol (SOAP) messaging to send text-based commands over a network.</span></span> <span data-ttu-id="1887d-104">Questi comandi sono in formato di testo XML e vengono inviati nel World Wide Web utilizzando HTTP.</span><span class="sxs-lookup"><span data-stu-id="1887d-104">These commands take the form of XML text that is sent over the World Wide Web using HTTP.</span></span> <span data-ttu-id="1887d-105">Grazie all'utilizzo di SOAP come protocollo di comunicazione, il servizio Web ReportServer consente alle applicazioni e ai componenti di scambiare dati con il server di report utilizzando un'infrastruttura aperta molto diffusa.</span><span class="sxs-lookup"><span data-stu-id="1887d-105">By using SOAP as its communication protocol, the Report Server Web service allows applications and components to exchange data with the report server using an open and widely accepted infrastructure.</span></span> <span data-ttu-id="1887d-106">Lo standard SOAP è definito nel sito www.w3.org/TR/SOAP (informazioni in lingua inglese).</span><span class="sxs-lookup"><span data-stu-id="1887d-106">The SOAP standard is defined at www.w3.org/TR/SOAP.</span></span>  
  
 <span data-ttu-id="1887d-107">Qualsiasi applicazione client può essere utilizzata come client SOAP a condizione che supporti SOAP e che sia in grado di inviare richieste SOAP.</span><span class="sxs-lookup"><span data-stu-id="1887d-107">Any client application can act as a SOAP client as long as it is SOAP-aware and can send SOAP requests.</span></span> <span data-ttu-id="1887d-108">Gestione report è un client SOAP.</span><span class="sxs-lookup"><span data-stu-id="1887d-108">Report Manager is one such SOAP client.</span></span> <span data-ttu-id="1887d-109">Questo client fornisce un'interfaccia per il database del server di report in cui vengono archiviati tutti i report e il contenuto correlato ai report.</span><span class="sxs-lookup"><span data-stu-id="1887d-109">It provides an interface to the report server database in which all reports and report-related content is stored.</span></span> <span data-ttu-id="1887d-110">Gli utenti finali possono utilizzare l'applicazione per esplorare e gestire report e cartelle nello spazio dei nomi del server di report.</span><span class="sxs-lookup"><span data-stu-id="1887d-110">End users can use the application to browse through and manage reports and folders in the report server namespace.</span></span> <span data-ttu-id="1887d-111">Gestione report è basato sull'infrastruttura del servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="1887d-111">Report Manager is built on the Report Server Web service infrastructure.</span></span>  
  
 <span data-ttu-id="1887d-112">Un server di report funge da server SOAP, un servizio che supporta SOAP in grado di accettare le richieste dai client SOAP e di creare risposte appropriate.</span><span class="sxs-lookup"><span data-stu-id="1887d-112">A report server acts as a SOAP server, a SOAP-aware service that can accept requests from SOAP clients and create appropriate responses.</span></span> <span data-ttu-id="1887d-113">Il server gestisce le richieste e restituisce al client risposte codificate.</span><span class="sxs-lookup"><span data-stu-id="1887d-113">The server handles the requests and sends encoded responses back to the client.</span></span>  
  
 <span data-ttu-id="1887d-114">I messaggi SOAP in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] possono avere formati diversi, a seconda del tipo di richiesta effettuata dal client.</span><span class="sxs-lookup"><span data-stu-id="1887d-114">SOAP messages in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] take many different forms, depending on the type of request made by the client.</span></span> <span data-ttu-id="1887d-115">Nell'esempio seguente viene rappresentata una semplice richiesta client SOAP per la rimozione di un elemento dal database del server di report.</span><span class="sxs-lookup"><span data-stu-id="1887d-115">The following example represents a simple SOAP client request to remove an item from the report server database.</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItem xmlns="https://www.microsoft.com/sql/ReportingServer">  
            <item>/Samples/Report1</item>  
        </DeleteItem>  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="1887d-116">SOAP  richiede che i messaggi siano inseriti in un elemento `Envelope` e che il blocco del messaggio sia inserito in un elemento `Body`.</span><span class="sxs-lookup"><span data-stu-id="1887d-116">The SOAP itself requires that messages be put into an `Envelope` element, with the bulk of the message inside a `Body` element.</span></span> <span data-ttu-id="1887d-117">In questo esempio il corpo contiene una chiamata al metodo <xref:ReportService2010.ReportingService2010.DeleteItem%2A> che accetta un parametro stringa che rappresenta il percorso dell'elemento da eliminare.</span><span class="sxs-lookup"><span data-stu-id="1887d-117">In this example, the body contains a call to the <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method, which takes a string parameter representing the path of the item to delete.</span></span> <span data-ttu-id="1887d-118">È possibile creare una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classe proxy client che incapsula tutte le operazioni SOAP nei metodi.</span><span class="sxs-lookup"><span data-stu-id="1887d-118">You can create a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] client proxy class that encapsulates all SOAP operations into methods.</span></span> <span data-ttu-id="1887d-119">Il [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] metodo seguente rappresenta l'esempio SOAP fornito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1887d-119">The following [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] method represents the SOAP example given earlier.</span></span>  
  
```  
public void DeleteItem(string item);  
```  
  
 <span data-ttu-id="1887d-120">La risposta dal server può essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="1887d-120">The response from the server might look like the following:</span></span>  
  
```  
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <soap:Body>  
        <DeleteItemResponse xmlns="https://www.microsoft.com/sql/ReportingServer" />  
    </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="1887d-121">Il metodo <xref:ReportService2010.ReportingService2010.DeleteItem%2A> non restituisce alcun valore, pertanto viene restituita una risposta vuota.</span><span class="sxs-lookup"><span data-stu-id="1887d-121">The <xref:ReportService2010.ReportingService2010.DeleteItem%2A> method has no return value, so an empty response is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1887d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1887d-122">See Also</span></span>  
 <span data-ttu-id="1887d-123">[Accesso all'API SOAP](accessing-the-soap-api.md) </span><span class="sxs-lookup"><span data-stu-id="1887d-123">[Accessing the SOAP API](accessing-the-soap-api.md) </span></span>  
 <span data-ttu-id="1887d-124">[Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="1887d-124">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="1887d-125">[Reporting Services server di report](../reporting-services-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="1887d-125">[Reporting Services Report Server](../reporting-services-report-server.md) </span></span>  
 [<span data-ttu-id="1887d-126">Servizio Web ReportServer</span><span class="sxs-lookup"><span data-stu-id="1887d-126">Report Server Web Service</span></span>](report-server-web-service.md)  
  
  
