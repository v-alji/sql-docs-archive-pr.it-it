---
title: Usare SQL Server eventi estesi (XEvent) per monitorare Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b57cc2fe-52dc-4fa9-8554-5a866e25c6d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9d12d9bc8d6a56702e1b44f8404b25681a1033f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635247"
---
# <a name="use-sql-server-extended-events-xevents-to-monitor-analysis-services"></a><span data-ttu-id="03921-102">Utilizzare eventi estesi di SQL Server (XEvent) per il monitoraggio di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="03921-102">Use SQL Server Extended Events (XEvents) to Monitor Analysis Services</span></span>
  <span data-ttu-id="03921-103">Analysis Services fornisce funzionalità di traccia tramite l'utilizzo degli [eventi estesi](../../relational-databases/extended-events/extended-events.md).</span><span class="sxs-lookup"><span data-stu-id="03921-103">Analysis Services provides tracing capabilities through the usage of [Extended Events](../../relational-databases/extended-events/extended-events.md).</span></span>  
  
 <span data-ttu-id="03921-104">Eventi estesi è un'infrastruttura evento estremamente scalabile e configurabile per i sistemi server.</span><span class="sxs-lookup"><span data-stu-id="03921-104">Extended Events is an event infrastructure that is highly scalable and configurable for server systems.</span></span> <span data-ttu-id="03921-105">Si tratta di un sistema di monitoraggio delle prestazioni leggero in cui vengono utilizzate poche risorse per le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="03921-105">Extended Events is a light weight performance monitoring system that uses very few performance resources.</span></span>  
  
 <span data-ttu-id="03921-106">Tutti gli eventi di Analysis Services possono essere acquisiti e indirizzati a consumer specifici, come definito negli [eventi estesi](../../relational-databases/extended-events/extended-events.md), tramite XEvent.</span><span class="sxs-lookup"><span data-stu-id="03921-106">All Analysis Services events can be captured and target to specific consumers, as defined in [Extended Events](../../relational-databases/extended-events/extended-events.md), through XEvents.</span></span>  
  
## <a name="initiating-extended-events-in-analysis-services"></a><span data-ttu-id="03921-107">Avvio di eventi estesi in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="03921-107">Initiating Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="03921-108">La traccia di eventi estesi viene abilitata utilizzando una specifica XMLA simile per creare un comando script dell'oggetto come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="03921-108">Extended Event tracing is enabled using a similar XMLA create object script command as shown below:</span></span>  
  
```  
<Execute ...>  
   <Command>  
      <Batch ...>  
         <Create ...>  
            <ObjectDefinition>  
               <Trace>  
                  <ID>trace_id</ID>  
                  <Name>trace_name</Name>  
                  <ddl300_300:XEvent>  
                     <event_session ...>  
                        <event package="AS" name="AS_event">  
                           <action package="PACKAGE0" .../>  
                        </event>  
                        <target package="PACKAGE0" name="asynchronous_file_target">  
                           <parameter name="filename" value="data_filename.xel"/>  
                           <parameter name="metadatafile" value="metadata_filename.xem"/>  
                        </target>  
                     </event_session>  
                  </ddl300_300:XEvent>  
               </Trace>  
            </ObjectDefinition>  
         </Create>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="03921-109">A seconda delle necessità di traccia, gli elementi seguenti devono essere definiti dall'utente:</span><span class="sxs-lookup"><span data-stu-id="03921-109">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="03921-110">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="03921-110">*trace_id*</span></span>  
 <span data-ttu-id="03921-111">Consente di definire l'identificatore univoco per questa traccia.</span><span class="sxs-lookup"><span data-stu-id="03921-111">Defines the unique identifier for this trace.</span></span>  
  
 <span data-ttu-id="03921-112">*trace_name*</span><span class="sxs-lookup"><span data-stu-id="03921-112">*trace_name*</span></span>  
 <span data-ttu-id="03921-113">Nome fornito a questa traccia; generalmente una definizione leggibile della traccia.</span><span class="sxs-lookup"><span data-stu-id="03921-113">The name given to this trace; usually a human readable definition of the trace.</span></span> <span data-ttu-id="03921-114">È pratica comune usare il valore *trace_id* come nome.</span><span class="sxs-lookup"><span data-stu-id="03921-114">It is a common practice to use the *trace_id* value as the name.</span></span>  
  
 <span data-ttu-id="03921-115">*AS_event*</span><span class="sxs-lookup"><span data-stu-id="03921-115">*AS_event*</span></span>  
 <span data-ttu-id="03921-116">Evento di Analysis Services da esporre.</span><span class="sxs-lookup"><span data-stu-id="03921-116">The Analysis Services event to be exposed.</span></span> <span data-ttu-id="03921-117">Vedere [Eventi di traccia di Analysis Services](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) per i nomi degli eventi.</span><span class="sxs-lookup"><span data-stu-id="03921-117">See [Analysis Services Trace Events](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) for names of the events.</span></span>  
  
 <span data-ttu-id="03921-118">*data_filename*</span><span class="sxs-lookup"><span data-stu-id="03921-118">*data_filename*</span></span>  
 <span data-ttu-id="03921-119">Nome del file in cui sono contenuti i dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="03921-119">The name of the file that contains the events data.</span></span> <span data-ttu-id="03921-120">Nel nome è incluso un suffisso timestamp per evitare la sovrascrittura dei dati qualora la traccia venga inviata ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="03921-120">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
 <span data-ttu-id="03921-121">*metadata_filename*</span><span class="sxs-lookup"><span data-stu-id="03921-121">*metadata_filename*</span></span>  
 <span data-ttu-id="03921-122">Nome del file in cui sono contenuti i metadati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="03921-122">The name of the file that contains the events metadata.</span></span> <span data-ttu-id="03921-123">Nel nome è incluso un suffisso timestamp per evitare la sovrascrittura dei dati qualora la traccia venga inviata ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="03921-123">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
## <a name="stopping-extended-events-in-analysis-services"></a><span data-ttu-id="03921-124">Arresto di eventi estesi in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="03921-124">Stopping Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="03921-125">Per arrestare l'oggetto traccia di eventi estesi è necessario eliminare tale oggetto utilizzando una specifica XMLA simile per eliminare un comando script dell'oggetto come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="03921-125">To stop the Extended Events tracing object you need to delete that object using a similar XMLA delete object script command as shown below:</span></span>  
  
```  
<Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <Command>  
      <Batch ...>  
         <Delete ...>  
            <Object>  
               <TraceID>trace_id</TraceID>  
            </Object>  
         </Delete>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="03921-126">A seconda delle necessità di traccia, gli elementi seguenti devono essere definiti dall'utente:</span><span class="sxs-lookup"><span data-stu-id="03921-126">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="03921-127">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="03921-127">*trace_id*</span></span>  
 <span data-ttu-id="03921-128">Consente di definire l'identificatore univoco della traccia da eliminare.</span><span class="sxs-lookup"><span data-stu-id="03921-128">Defines the unique identifier for the trace to be deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03921-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03921-129">See Also</span></span>  
 [<span data-ttu-id="03921-130">Eventi estesi</span><span class="sxs-lookup"><span data-stu-id="03921-130">Extended Events</span></span>](../../relational-databases/extended-events/extended-events.md)  
  
  
