---
title: Modello a oggetti SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- object models [SMO]
- SMO [SQL Server], object model
- SQL Server Management Objects, object model
ms.assetid: bd6e59b6-ca46-42c0-adb2-c9d64cf6e00b
author: stevestein
ms.author: sstein
ms.openlocfilehash: c973e381a6cc7de44a0072d012147271eaa609ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711860"
---
# <a name="smo-object-model"></a><span data-ttu-id="dfc71-102">Modello a oggetti SMO</span><span class="sxs-lookup"><span data-stu-id="dfc71-102">SMO Object Model</span></span>
  <span data-ttu-id="dfc71-103">Il modello a oggetti SMO è costituito da una gerarchia di oggetti.</span><span class="sxs-lookup"><span data-stu-id="dfc71-103">The SMO object model is made up of a hierarchy of objects.</span></span> <span data-ttu-id="dfc71-104">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> rappresenta l'oggetto di livello principale e tutti gli oggetti classe di istanza si trovano all'interno dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="dfc71-104">The <xref:Microsoft.SqlServer.Management.Smo.Server> object is the top level object and all instance class objects reside under the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span>  
  
 <span data-ttu-id="dfc71-105">La classe <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> è una classe di livello principale con una gerarchia di oggetti distinta.</span><span class="sxs-lookup"><span data-stu-id="dfc71-105">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> class is a top level class with a separate object hierarchy.</span></span> <span data-ttu-id="dfc71-106">L' <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> oggetto rappresenta [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Servizi e impostazioni di rete disponibili tramite il provider WMI.</span><span class="sxs-lookup"><span data-stu-id="dfc71-106">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object represents [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings available through the WMI Provider.</span></span>  
  
 <span data-ttu-id="dfc71-107">Oltre agli oggetti <xref:Microsoft.SqlServer.Management.Smo.Server> e <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>, sono disponibili diverse classi di utilità che rappresentano attività e operazioni, ad esempio <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup> o <xref:Microsoft.SqlServer.Management.Smo.Restore></span><span class="sxs-lookup"><span data-stu-id="dfc71-107">Besides the <xref:Microsoft.SqlServer.Management.Smo.Server> and <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> objects, there are several utility classes that represent tasks or operations, such as <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup>, or <xref:Microsoft.SqlServer.Management.Smo.Restore></span></span>  
  
 <span data-ttu-id="dfc71-108">Il modello a oggetti SMO è costituito da diversi spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dfc71-108">The SMO object model is made up of several namespaces.</span></span> <span data-ttu-id="dfc71-109">Per altre informazioni, vedere [Spazio dei nomi SMO](smo-object-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="dfc71-109">For more information, see [SMO Namespaces](smo-object-model-namespaces.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc71-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfc71-110">See Also</span></span>  
 <span data-ttu-id="dfc71-111">[Diagramma del modello a oggetti SMO](smo-object-model-diagram.md) </span><span class="sxs-lookup"><span data-stu-id="dfc71-111">[SMO Object Model Diagram](smo-object-model-diagram.md) </span></span>  
 <span data-ttu-id="dfc71-112">[Spazi dei nomi SMO](smo-object-model-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="dfc71-112">[SMO Namespaces](smo-object-model-namespaces.md) </span></span>  
 [<span data-ttu-id="dfc71-113">Concetti relativi al provider WMI per Gestione configurazione</span><span class="sxs-lookup"><span data-stu-id="dfc71-113">WMI Provider for Configuration Management Concepts</span></span>](../wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
