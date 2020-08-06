---
title: Classi e proprietà del provider WMI per eventi del server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- event classes [WMI]
- WMI Provider for Server Events, events listed
- classes [WMI]
ms.assetid: e2916cd7-a3ed-41e6-97b4-2ee060754cbe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 471e77cb7afa4e6aed441dcbbc8b3b70064f6737
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723639"
---
# <a name="wmi-provider-for-server-events-classes-and-properties"></a><span data-ttu-id="7be01-102">Classi e proprietà del provider WMI per eventi del server</span><span class="sxs-lookup"><span data-stu-id="7be01-102">WMI Provider for Server Events Classes and Properties</span></span>
  <span data-ttu-id="7be01-103">Gli eventi del server seguenti costituiscono il modello di programmazione per il provider WMI per eventi del server.</span><span class="sxs-lookup"><span data-stu-id="7be01-103">The following server events make up the programming model for the WMI Provider for Server Events.</span></span> <span data-ttu-id="7be01-104">Esistono due principali categorie di eventi che è possibile sottoporre a query eseguendo le query WQL sul provider:</span><span class="sxs-lookup"><span data-stu-id="7be01-104">There are two main categories of events that can be queried by issuing WQL queries against the provider.</span></span> <span data-ttu-id="7be01-105">eventi DDL (Data Definition Language) ed eventi di traccia.</span><span class="sxs-lookup"><span data-stu-id="7be01-105">These are data definition language (DDL) events and trace events.</span></span> <span data-ttu-id="7be01-106">Anche gli eventi di Service Broker QUEUE_ACTIVATION e BROKER_QUEUE_DISABLED possono essere sottoposti a query.</span><span class="sxs-lookup"><span data-stu-id="7be01-106">The QUEUE_ACTIVATION and BROKER_QUEUE_DISABLED service broker events can also be queried.</span></span> <span data-ttu-id="7be01-107">Si noti la natura inclusiva dei diagrammi ad albero seguenti.</span><span class="sxs-lookup"><span data-stu-id="7be01-107">Note the inclusive nature of the following tree diagrams.</span></span> <span data-ttu-id="7be01-108">L'evento DDL_ASSEMBLY_EVENTS, ad esempio, include un evento ALTER_ASSEMBLY, CREATE_ASSEMBLY e DROP_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="7be01-108">The DDL_ASSEMBLY_EVENTS event, for example, includes any ALTER_ASSEMBLY, CREATE_ASSEMBLY, and DROP_ASSEMBLY event.</span></span> <span data-ttu-id="7be01-109">Allo stesso modo, l'evento TRC_FULL_TEXT include un evento FT_CRAWL_ABORTED, FT_CRAWL_STARTED e FT_CRAWL_STOPPED.</span><span class="sxs-lookup"><span data-stu-id="7be01-109">Similarly, the TRC_FULL_TEXT event includes any FT_CRAWL_ABORTED, FT_CRAWL_STARTED, and FT_CRAWL_STOPPED event.</span></span> <span data-ttu-id="7be01-110">ALL_EVENTS include tutti gli eventi DDL, gli eventi di traccia, QUEUE_ACTIVATION e BROKER_QUEUE_DISABLED.</span><span class="sxs-lookup"><span data-stu-id="7be01-110">ALL_EVENTS covers all DDL events, trace events, QUEUE_ACTIVATION, and BROKER_QUEUE_DISABLED.</span></span>  
  
 <span data-ttu-id="7be01-111">Per informazioni sulle proprietà che possono essere sottoposte a query da un evento o un gruppo di eventi, fare riferimento allo schema dell'evento.</span><span class="sxs-lookup"><span data-stu-id="7be01-111">To learn which properties can be queried from an event or event group, refer to the event schema.</span></span> <span data-ttu-id="7be01-112">Per impostazione predefinita, lo schema dell'evento viene installato nella directory seguente: [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]Tools\Binn\schemas\sqlserver\2006\11\events\events.xsd.</span><span class="sxs-lookup"><span data-stu-id="7be01-112">By default, the event schema is installed in the following directory: [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]Tools\Binn\schemas\sqlserver\2006\11\events\events.xsd.</span></span>  
  
 <span data-ttu-id="7be01-113">In alternativa, è possibile fare riferimento allo schema dell'evento pubblicato in [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100) .</span><span class="sxs-lookup"><span data-stu-id="7be01-113">Alternatively, you can refer to the event schema published at [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
 <span data-ttu-id="7be01-114">Ad esempio, dall'evento ALTER_DATABASE si evince che l'evento padre è DDL_SERVER_LEVEL_EVENTS e che le proprietà sono `TSQLCommand` e `DatabaseName`.</span><span class="sxs-lookup"><span data-stu-id="7be01-114">For example, by referring to the ALTER_DATABASE event, you will learn that its parent event is DDL_SERVER_LEVEL_EVENTS and its properties are `TSQLCommand` and `DatabaseName`.</span></span> <span data-ttu-id="7be01-115">L'evento eredita inoltre le proprietà `SQLInstance`, `PostTime`, `ComputerName`, `SPID` e `LoginName`.</span><span class="sxs-lookup"><span data-stu-id="7be01-115">The event also inherits the properties `SQLInstance`, `PostTime`, `ComputerName`, `SPID`, and `LoginName`.</span></span> <span data-ttu-id="7be01-116">L'evento non dispone di eventi figli.</span><span class="sxs-lookup"><span data-stu-id="7be01-116">The event has no children events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7be01-117">Le stored procedure di sistema che eseguono operazioni di tipo DDL possono inoltre attivare le notifiche degli eventi.</span><span class="sxs-lookup"><span data-stu-id="7be01-117">System stored procedures that perform DDL-like operations can also fire event notifications.</span></span> <span data-ttu-id="7be01-118">Testare le notifiche degli eventi per determinarne le risposte alle stored procedure di sistema eseguite.</span><span class="sxs-lookup"><span data-stu-id="7be01-118">Test your event notifications to determine their responses to system stored procedures that are run.</span></span> <span data-ttu-id="7be01-119">Ad esempio, l'istruzione CREATE TYPE e **sp_addtype** stored procedure genereranno una notifica degli eventi creata in un evento di CREATE_TYPE.</span><span class="sxs-lookup"><span data-stu-id="7be01-119">For example, the CREATE TYPE statement and **sp_addtype** stored procedure will both fire an event notification that is created on a CREATE_TYPE event.</span></span> <span data-ttu-id="7be01-120">Per ulteriori informazioni, vedere[eventi DDL](../../relational-databases/triggers/ddl-events.md).</span><span class="sxs-lookup"><span data-stu-id="7be01-120">For more information, see[DDL Events](../../relational-databases/triggers/ddl-events.md).</span></span>  
  
 <span data-ttu-id="7be01-121">**Eventi e gruppi di eventi del linguaggio di definizione dei dati**</span><span class="sxs-lookup"><span data-stu-id="7be01-121">**Data Definition Language Events and Event Groups**</span></span>  
  
 <span data-ttu-id="7be01-122">![Albero degli eventi del provider WMI per eventi del server](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "Albero degli eventi del provider WMI per eventi del server")</span><span class="sxs-lookup"><span data-stu-id="7be01-122">![WMI Provider for Server Events Event Tree](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "WMI Provider for Server Events Event Tree")</span></span>  
  
 <span data-ttu-id="7be01-123">**Eventi e gruppi di eventi di traccia**</span><span class="sxs-lookup"><span data-stu-id="7be01-123">**Trace Events and Event Groups**</span></span>  
  
 <span data-ttu-id="7be01-124">![Eventi di traccia e gruppi di eventi](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "Eventi di traccia e gruppi di eventi")</span><span class="sxs-lookup"><span data-stu-id="7be01-124">![Trace events and event groups](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "Trace events and event groups")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be01-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7be01-125">See Also</span></span>  
 <span data-ttu-id="7be01-126">[Concetti relativi al provider WMI per eventi del server](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="7be01-126">[WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span></span>  
 [<span data-ttu-id="7be01-127">Utilizzo di WQL con il provider WMI per eventi del server</span><span class="sxs-lookup"><span data-stu-id="7be01-127">Using WQL with the WMI Provider for Server Events</span></span>](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md)  
  
  
