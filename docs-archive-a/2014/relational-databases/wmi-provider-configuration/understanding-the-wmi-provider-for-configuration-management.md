---
title: Informazioni sul provider WMI per la gestione della configurazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- WMI Provider for Configuration Management, operations supported
ms.assetid: 92323972-7943-4208-bbf4-050774fb6027
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0f4f38265093fdb0c27d6bd49ff64ba4b572111e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623066"
---
# <a name="understanding-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="c743a-102">Informazioni sul provider WMI per la gestione della configurazione</span><span class="sxs-lookup"><span data-stu-id="c743a-102">Understanding the WMI Provider for Configuration Management</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="c743a-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]fornisce il provider WMI per la gestione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="c743a-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="c743a-104">Consente di utilizzare WMI (Strumentazione gestione Windows) per gestire i servizi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il client [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e impostazioni di rete server e alias del server.</span><span class="sxs-lookup"><span data-stu-id="c743a-104">This lets you use Windows Management Instrumentation (WMI) to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client and server network settings, and server aliases.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="c743a-105">i servizi, le impostazioni di rete e gli alias sono rappresentati da oggetti WMI nello spazio dei nomi root\Microsoft\SqlServer\ComputerManagement*nn* del computer.</span><span class="sxs-lookup"><span data-stu-id="c743a-105">services, network settings, and aliases are represented by WMI objects in the root\Microsoft\SqlServer\ComputerManagement*nn* namespace of the computer.</span></span> <span data-ttu-id="c743a-106">Una volta stabilita una connessione con il provider WMI nel computer specificato, è possibile eseguire query su servizi, impostazioni di rete e alias utilizzando WQL o un linguaggio di scripting.</span><span class="sxs-lookup"><span data-stu-id="c743a-106">After a connection is established with the WMI provider on the specified computer, the services, network settings, and aliases can be queried using WQL or a scripting language.</span></span>  
  
 <span data-ttu-id="c743a-107">Il provider WMI è un provider di istanze</span><span class="sxs-lookup"><span data-stu-id="c743a-107">The WMI Provider is an instance provider.</span></span> <span data-ttu-id="c743a-108">Fornisce istanze delle [classi WMI](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) e supporta le operazioni asincrone seguenti.</span><span class="sxs-lookup"><span data-stu-id="c743a-108">It supplies instances of the [WMI Classes](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) and supports the following asynchronous operations.</span></span>  
  
 <span data-ttu-id="c743a-109">Recupero di istanze</span><span class="sxs-lookup"><span data-stu-id="c743a-109">Instance retrieval</span></span>  
 <span data-ttu-id="c743a-110">Recupero di un'istanza di un tipo di classe specifica.</span><span class="sxs-lookup"><span data-stu-id="c743a-110">Retrieval of a particular class type instance.</span></span>  
  
 <span data-ttu-id="c743a-111">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="c743a-111">Enumeration</span></span>  
 <span data-ttu-id="c743a-112">Enumerazione di tutte le istanze di un tipo di classe.</span><span class="sxs-lookup"><span data-stu-id="c743a-112">Enumeration of all instances of a class type.</span></span>  
  
 <span data-ttu-id="c743a-113">Modifica</span><span class="sxs-lookup"><span data-stu-id="c743a-113">Modification</span></span>  
 <span data-ttu-id="c743a-114">Modifica di una determinata istanza di un tipo di classe.</span><span class="sxs-lookup"><span data-stu-id="c743a-114">Modification of a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="c743a-115">Le classi includono metodi che consentono la modifica delle relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="c743a-115">Classes have methods that allow the modification of their properties.</span></span>  
  
 <span data-ttu-id="c743a-116">Eliminazione</span><span class="sxs-lookup"><span data-stu-id="c743a-116">Deletion</span></span>  
 <span data-ttu-id="c743a-117">Rimozione di una determinata istanza di un tipo di classe.</span><span class="sxs-lookup"><span data-stu-id="c743a-117">Removing a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="c743a-118">Elaborazione di query</span><span class="sxs-lookup"><span data-stu-id="c743a-118">Query processing</span></span>  
 <span data-ttu-id="c743a-119">Enumerazione di istanze di un tipo di classe basata su un filtro.</span><span class="sxs-lookup"><span data-stu-id="c743a-119">Enumeration of instances of a class type based on a filter.</span></span>  
  
 <span data-ttu-id="c743a-120">Per esempi di applicazioni di gestione che utilizzano il provider WMI per la gestione della configurazione, vedere [utilizzo di WQL e di linguaggi di scripting con il provider WMI per la gestione della configurazione](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c743a-120">For examples of management application using the WMI Provider for Configuration Management, see [Using WQL and Scripting Languages with the WMI Provider for Configuration Management](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span></span>  
  
 <span data-ttu-id="c743a-121">Per ulteriori informazioni sulla programmazione di applicazioni di gestione utilizzando il provider WMI, vedere la documentazione di WMI in [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="c743a-121">For more information about programming management applications using the WMI Provider, see the WMI documentation in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c743a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c743a-122">See Also</span></span>  
 <span data-ttu-id="c743a-123">[Utilizzo del provider WMI per la gestione della configurazione](working-with-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="c743a-123">[Working with the WMI Provider for Configuration Management](working-with-the-wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="c743a-124">Uso di WQL e di linguaggi di scripting con il provider WMI per la gestione della configurazione</span><span class="sxs-lookup"><span data-stu-id="c743a-124">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>](using-wql-and-scripting-languages-with-the-wmi-provider.md)  
  
  
