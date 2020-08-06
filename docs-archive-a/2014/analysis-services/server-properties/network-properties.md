---
title: Proprietà di rete | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LingerTimeout property
- EnableNagleAlgorithm property
- MinPendingAcceptExCount property
- MaxPendingSendCount property
- EnableBinaryXML property
- MinPendingReceiveCount property
- MaxCompletedReceiveCount property
- DisableNonblockingMode property
- RequestSizeThreshold property
- CompressionLevel property
- ReceiveBufferSize property
- EnableCompression property
- ServerSendTimeout property
- IPV4Support property
- MaxPendingReceiveCount property
- MaxPendingAcceptExCount property
- IPV6Support property
- MaxAllowedRequestSize property
- ServerReceiveTimeout property
- EnableLingerOnClose property
- InitialConnectTimeout property
- SendBufferSize property
- ScatterReceiveMultiplier property
- network properties [Analysis Services]
ms.assetid: ef4251e2-abe5-4c5b-9868-7549782d0244
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10ad5bbbcffdfc3d3c4fefe3111e4c4425919915
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628014"
---
# <a name="network-properties"></a><span data-ttu-id="23957-102">Proprietà di rete</span><span class="sxs-lookup"><span data-stu-id="23957-102">Network Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="23957-103">supporta le proprietà del server elencate nelle tabelle seguenti.</span><span class="sxs-lookup"><span data-stu-id="23957-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="23957-104">Per altre informazioni sulle proprietà aggiuntive del server e sulla relativa impostazione, vedere [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="23957-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="23957-105">**Si applica a:** modalità server multidimensionale e tabulare</span><span class="sxs-lookup"><span data-stu-id="23957-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="general"></a><span data-ttu-id="23957-106">Generale</span><span class="sxs-lookup"><span data-stu-id="23957-106">General</span></span>  
 `ListenOnlyOnLocalConnections`  
 <span data-ttu-id="23957-107">Proprietà booleana che stabilisce se lo stato di attesa viene applicato solo alle connessioni locali, ad esempio localhost.</span><span class="sxs-lookup"><span data-stu-id="23957-107">A Boolean property that identifies whether to listen only on local connections, for example localhost.</span></span>  
  
## <a name="listener"></a><span data-ttu-id="23957-108">Listener</span><span class="sxs-lookup"><span data-stu-id="23957-108">Listener</span></span>  
 `IPV4Support`  
 <span data-ttu-id="23957-109">Proprietà a valore integer a 32 bit con segno che definisce il supporto per il protocollo IPv4.</span><span class="sxs-lookup"><span data-stu-id="23957-109">A signed 32-bit integer property that defines support for IPv4 protocol.</span></span> <span data-ttu-id="23957-110">Questa proprietà può assumere uno dei valori elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="23957-110">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="23957-111">Valore</span><span class="sxs-lookup"><span data-stu-id="23957-111">Value</span></span>|<span data-ttu-id="23957-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23957-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="23957-113">*0*</span><span class="sxs-lookup"><span data-stu-id="23957-113">*0*</span></span>|<span data-ttu-id="23957-114">IPv4 disabilitato; i client non possono connettersi.</span><span class="sxs-lookup"><span data-stu-id="23957-114">IPv4 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="23957-115">*1*</span><span class="sxs-lookup"><span data-stu-id="23957-115">*1*</span></span>|<span data-ttu-id="23957-116">(Impostazione predefinita) IPv4 non richiesto; il server non si avvia se non può restare in attesa di IPv4.</span><span class="sxs-lookup"><span data-stu-id="23957-116">(Default) IPv4 is required; server won't start if it cannot listen to IPv4.</span></span>|  
|<span data-ttu-id="23957-117">*2*</span><span class="sxs-lookup"><span data-stu-id="23957-117">*2*</span></span>|<span data-ttu-id="23957-118">Il protocollo IPv4 è facoltativo; il server prova a rimanere in attesa di IPv4 ma si avvia anche se non vi riesce.</span><span class="sxs-lookup"><span data-stu-id="23957-118">IPv4 is optional; server tries to listen to IPv4 but starts even if unable to.</span></span>|  
  
 `IPV6Support`  
 <span data-ttu-id="23957-119">Proprietà a valore integer a 32 bit con segno che definisce il supporto per il protocollo IPv6.</span><span class="sxs-lookup"><span data-stu-id="23957-119">A signed 32-bit integer property that defines support for IPv6 protocol.</span></span> <span data-ttu-id="23957-120">Questa proprietà può assumere uno dei valori elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="23957-120">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="23957-121">Valore</span><span class="sxs-lookup"><span data-stu-id="23957-121">Value</span></span>|<span data-ttu-id="23957-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23957-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="23957-123">*0*</span><span class="sxs-lookup"><span data-stu-id="23957-123">*0*</span></span>|<span data-ttu-id="23957-124">IPv6 disabilitato; i client non possono connettersi.</span><span class="sxs-lookup"><span data-stu-id="23957-124">IPv6 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="23957-125">*1*</span><span class="sxs-lookup"><span data-stu-id="23957-125">*1*</span></span>|<span data-ttu-id="23957-126">(Impostazione predefinita) IPv6 non richiesto; il server non si avvia se non può restare in attesa di IPv6.</span><span class="sxs-lookup"><span data-stu-id="23957-126">(Default) IPv6 is required; server won't start if it cannot listen to IPv6.</span></span>|  
|<span data-ttu-id="23957-127">*2*</span><span class="sxs-lookup"><span data-stu-id="23957-127">*2*</span></span>|<span data-ttu-id="23957-128">Il protocollo IPv6 è facoltativo; il server prova a rimanere in attesa di IPv6 ma si avvia anche se non vi riesce.</span><span class="sxs-lookup"><span data-stu-id="23957-128">IPv6 is optional; server tries to listen to IPv6 but starts even if unable to.</span></span>|  
  
 `MaxAllowedRequestSize`  
 <span data-ttu-id="23957-129">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-129">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RequestSizeThreshold`  
 <span data-ttu-id="23957-130">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-130">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerReceiveTimeout`  
 <span data-ttu-id="23957-131">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-131">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerSendTimeout`  
 <span data-ttu-id="23957-132">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-132">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="requests"></a><span data-ttu-id="23957-133">Requests</span><span class="sxs-lookup"><span data-stu-id="23957-133">Requests</span></span>  
 `EnableBinaryXML`  
 <span data-ttu-id="23957-134">Proprietà booleana che stabilisce se il server riconoscerà il formato xml binario per richieste.</span><span class="sxs-lookup"><span data-stu-id="23957-134">A Boolean property that specifies whether the server will recognize requests binary xml format.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="23957-135">Proprietà booleana che stabilisce se la compressione è abilitata per le richieste.</span><span class="sxs-lookup"><span data-stu-id="23957-135">A Boolean property that specifies whether compression is enabled for requests.</span></span>  
  
## <a name="responses"></a><span data-ttu-id="23957-136">Risposte</span><span class="sxs-lookup"><span data-stu-id="23957-136">Responses</span></span>  
 `CompressionLevel`  
 <span data-ttu-id="23957-137">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-137">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `EnableBinaryXML`  
 <span data-ttu-id="23957-138">Proprietà booleana che stabilisce se il server è abilitato per risposte xml binarie.</span><span class="sxs-lookup"><span data-stu-id="23957-138">A Boolean property that specifies whether the server is enabled for binary xml responses.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="23957-139">Proprietà booleana che stabilisce se la compressione è abilitata per risposte a richieste client.</span><span class="sxs-lookup"><span data-stu-id="23957-139">A Boolean property that specifies whether compression is enabled for responses to client requests.</span></span>  
  
## <a name="tcp"></a><span data-ttu-id="23957-140">TCP</span><span class="sxs-lookup"><span data-stu-id="23957-140">TCP</span></span>  
 `InitialConnectTimeout`  
 <span data-ttu-id="23957-141">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxCompletedReceiveCount`  
 <span data-ttu-id="23957-142">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingAcceptExCount`  
 <span data-ttu-id="23957-143">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-143">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingReceiveCount`  
 <span data-ttu-id="23957-144">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingSendCount`  
 <span data-ttu-id="23957-145">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-145">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingAcceptExCount`  
 <span data-ttu-id="23957-146">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingReceiveCount`  
 <span data-ttu-id="23957-147">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ScatterReceiveMultiplier`  
 <span data-ttu-id="23957-148">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ DisableNonblockingMode`  
 <span data-ttu-id="23957-149">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ EnableLingerOnClose`  
 <span data-ttu-id="23957-150">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\EnableNagleAlgorithm`  
 <span data-ttu-id="23957-151">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ LingerTimeout`  
 <span data-ttu-id="23957-152">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ ReceiveBufferSize`  
 <span data-ttu-id="23957-153">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-153">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ SendBufferSize`  
 <span data-ttu-id="23957-154">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23957-154">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23957-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23957-155">See Also</span></span>  
 <span data-ttu-id="23957-156">[Configurare le proprietà del server in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="23957-156">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="23957-157">Determinare la modalità server di un'istanza di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="23957-157">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
