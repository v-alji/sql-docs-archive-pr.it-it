---
title: File e numeri di versione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Management Objects, versions
- components [SMO]
- files [SMO], components
- SMO [SQL Server], versions
- versions [SMO]
ms.assetid: 510907b6-e7a9-41bd-b892-d6d99a5118e1
author: stevestein
ms.author: sstein
ms.openlocfilehash: f1a7286f15af28f97e488b8b40fd745a0d320108
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628616"
---
# <a name="files-and-version-numbers"></a><span data-ttu-id="26bff-102">File e numeri di versione</span><span class="sxs-lookup"><span data-stu-id="26bff-102">Files and Version Numbers</span></span>
  <span data-ttu-id="26bff-103">Tutti i [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componenti SMO (Management Objects) richiesti vengono installati come parte di un'istanza del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client o del server.</span><span class="sxs-lookup"><span data-stu-id="26bff-103">All required [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Management Objects (SMO) components are installed as part of an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client or server.</span></span> <span data-ttu-id="26bff-104">SMO viene implementato in diversi assembly gestiti.</span><span class="sxs-lookup"><span data-stu-id="26bff-104">SMO is implemented in several managed assemblies.</span></span> <span data-ttu-id="26bff-105">È possibile sviluppare applicazioni SMO in un client o in un server.</span><span class="sxs-lookup"><span data-stu-id="26bff-105">You can develop SMO applications on either a client or a server.</span></span>  
  
|<span data-ttu-id="26bff-106">Directory</span><span class="sxs-lookup"><span data-stu-id="26bff-106">Directory</span></span>|<span data-ttu-id="26bff-107">File</span><span class="sxs-lookup"><span data-stu-id="26bff-107">File</span></span>|<span data-ttu-id="26bff-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26bff-108">Description</span></span>|  
|---------------|----------|-----------------|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="26bff-109">Microsoft.SqlServer.ConnectionInfo.dll</span><span class="sxs-lookup"><span data-stu-id="26bff-109">Microsoft.SqlServer.ConnectionInfo.dll</span></span>|<span data-ttu-id="26bff-110">Contiene supporto per la connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26bff-110">Contains support for connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="26bff-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span><span class="sxs-lookup"><span data-stu-id="26bff-111">Microsoft.SqlServer.ServiceBrokerEnum.dll</span></span>|<span data-ttu-id="26bff-112">Contiene supporto per la programmazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span><span class="sxs-lookup"><span data-stu-id="26bff-112">Contains support for programming the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service Broker.</span></span> <span data-ttu-id="26bff-113">È richiesto solo in programmi che accedono a Service Broker.</span><span class="sxs-lookup"><span data-stu-id="26bff-113">This is required only in programs that access the Service Broker.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="26bff-114">Microsoft.SqlServer.Smo.dll</span><span class="sxs-lookup"><span data-stu-id="26bff-114">Microsoft.SqlServer.Smo.dll</span></span>|<span data-ttu-id="26bff-115">Contiene la maggior parte delle classi SMO.</span><span class="sxs-lookup"><span data-stu-id="26bff-115">Contains the most of the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="26bff-116">Microsoft.SqlServer.SmoExtended.dll</span><span class="sxs-lookup"><span data-stu-id="26bff-116">Microsoft.SqlServer.SmoExtended.dll</span></span><br /><br /> <span data-ttu-id="26bff-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span><span class="sxs-lookup"><span data-stu-id="26bff-117">Microsoft.SqlServer.Management.Sdk.Sfc.dll</span></span><br /><br /> <span data-ttu-id="26bff-118">Microsoft.SqlServer.SqlEnum.dll</span><span class="sxs-lookup"><span data-stu-id="26bff-118">Microsoft.SqlServer.SqlEnum.dll</span></span>|<span data-ttu-id="26bff-119">Contiene il supporto per le classi SMO.</span><span class="sxs-lookup"><span data-stu-id="26bff-119">Contains support for the SMO classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="26bff-120">Microsoft.SqlServer.WmiEnum.dll</span><span class="sxs-lookup"><span data-stu-id="26bff-120">Microsoft.SqlServer.WmiEnum.dll</span></span>|<span data-ttu-id="26bff-121">Contiene le classi del provider Strumentazione gestione Windows (WMI, Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="26bff-121">Contains the Windows Management Instrumentation (WMI) Provider classes.</span></span> <span data-ttu-id="26bff-122">È richiesto solo per programmi che utilizzano le classi del Provider WMI.</span><span class="sxs-lookup"><span data-stu-id="26bff-122">This is required only for programs that use the WMI Provider classes.</span></span>|  
|[!INCLUDE[ssSampPathSDK](../../includes/sssamppathsdk-md.md)]|<span data-ttu-id="26bff-123">Microsoft.SqlServer.RegSvrEnum.dll</span><span class="sxs-lookup"><span data-stu-id="26bff-123">Microsoft.SqlServer.RegSvrEnum.dll</span></span>|<span data-ttu-id="26bff-124">Contiene le classi del server registrato.</span><span class="sxs-lookup"><span data-stu-id="26bff-124">Contains the Registered Server classes.</span></span> <span data-ttu-id="26bff-125">È richiesto solo per programmi che utilizzano le classi del server registrato.</span><span class="sxs-lookup"><span data-stu-id="26bff-125">This is required only for programs that use the Registered Server classes.</span></span>|  
  
  
