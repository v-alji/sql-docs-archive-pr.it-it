---
title: Protocolli client-proprietà TCP e IP (scheda protocollo) | Microsoft Docs
description: Informazioni su come specificare le opzioni TCP/IP in Microsoft SQL Server Configuration Manager, ad esempio il parametro Keep Alive e il numero di porta predefinito.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], client protocols
- client protocols [SQL Server]
ms.assetid: d04f1bce-069c-4a02-b561-c87c3282be36
author: rothja
ms.author: jroth
ms.openlocfilehash: dfcf0348dc863970384a40cc9e773481adeedb35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722135"
---
# <a name="client-protocols---tcp-and-ip-properties-protocol-tab"></a><span data-ttu-id="7ec35-103">Protocolli client e Proprietà TCP IP (scheda Protocollo)</span><span class="sxs-lookup"><span data-stu-id="7ec35-103">Client Protocols - TCP and IP Properties (Protocol Tab)</span></span>
  <span data-ttu-id="7ec35-104">In Gestione configurazione [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], usare la scheda **Protocollo** della finestra di dialogo **Proprietà TCP/IP** per visualizzare o specificare le opzioni illustrate di seguito.</span><span class="sxs-lookup"><span data-stu-id="7ec35-104">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, use the **Protocol** tab on the **TCP/IP Properties** dialog box to view or specify the following options.</span></span> <span data-ttu-id="7ec35-105">Per eseguire la connessione a una porta diversa, digitare il numero della porta nella casella **Porta predefinita** .</span><span class="sxs-lookup"><span data-stu-id="7ec35-105">To connect to a different port, type the port number in the **Default Port** box.</span></span> <span data-ttu-id="7ec35-106">Per altre informazioni sulle stringhe di connessione, vedere [Creazione di una stringa di connessione valida tramite TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span><span class="sxs-lookup"><span data-stu-id="7ec35-106">For more information about connection strings, see [Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7ec35-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7ec35-107">Options</span></span>  
 <span data-ttu-id="7ec35-108">**Porta predefinita**</span><span class="sxs-lookup"><span data-stu-id="7ec35-108">**Default Port**</span></span>  
 <span data-ttu-id="7ec35-109">Specifica la porta utilizzata dalla libreria di rete TCP/IP per tentare la connessione all'istanza di destinazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ec35-109">Specifies the port that the TCP/IP Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7ec35-110">La porta predefinita è la 1433.</span><span class="sxs-lookup"><span data-stu-id="7ec35-110">The default value port is 1433.</span></span>  
  
 <span data-ttu-id="7ec35-111">Quando esegue la connessione a un'istanza predefinita di [!INCLUDE[ssDE](../../includes/ssde-md.md)], il client utilizza questo valore.</span><span class="sxs-lookup"><span data-stu-id="7ec35-111">When connecting to a default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client uses this value.</span></span> <span data-ttu-id="7ec35-112">Se un'istanza predefinita è stata configurata per restare in attesa su una porta diversa, modificare il valore della porta impostando 1433.</span><span class="sxs-lookup"><span data-stu-id="7ec35-112">If a default instance has been configured to listen on a different port, change this value to that port number.</span></span>  
  
 <span data-ttu-id="7ec35-113">Quando esegue la connessione a un'istanza denominata di [!INCLUDE[ssDE](../../includes/ssde-md.md)], il client tenta di ottenere il numero di porta dal servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser in esecuzione nel computer server.</span><span class="sxs-lookup"><span data-stu-id="7ec35-113">When connecting to a named instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client will attempt to obtain the port number from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service running on the server computer.</span></span> <span data-ttu-id="7ec35-114">Se il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser non è in esecuzione, è necessario fornire il numero di porta mediante questa impostazione o come parte della stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="7ec35-114">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service is not running, the port number must be provided through this setting, or as part of the connection string.</span></span>  
  
 <span data-ttu-id="7ec35-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="7ec35-115">**Enabled**</span></span>  
 <span data-ttu-id="7ec35-116">I valori possibili sono **Yes** e **No**.</span><span class="sxs-lookup"><span data-stu-id="7ec35-116">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="7ec35-117">**Keep-alive**</span><span class="sxs-lookup"><span data-stu-id="7ec35-117">**Keep Alive**</span></span>  
 <span data-ttu-id="7ec35-118">Questo parametro determina l'intervallo in millisecondi fra i tentativi effettuati da TCP per verificare l'integrità di una connessione inattiva mediante l'invio di un pacchetto **KEEPALIVE** .</span><span class="sxs-lookup"><span data-stu-id="7ec35-118">This parameter (in milliseconds) controls how often TCP attempts to verify that an idle connection is still intact by sending a **KEEPALIVE** packet.</span></span> <span data-ttu-id="7ec35-119">Il valore predefinito è 30000 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="7ec35-119">The default is 30000 milliseconds.</span></span>  
  
 <span data-ttu-id="7ec35-120">**Intervallo keep-alive**</span><span class="sxs-lookup"><span data-stu-id="7ec35-120">**Keep Alive Interval**</span></span>  
 <span data-ttu-id="7ec35-121">Questo parametro determina l'intervallo in millisecondi tra le ritrasmissioni **KEEPALIVE** finché non viene ricevuta una risposta.</span><span class="sxs-lookup"><span data-stu-id="7ec35-121">This parameter (in milliseconds) determines the interval separating **KEEPALIVE** retransmissions until a response is received.</span></span> <span data-ttu-id="7ec35-122">Il valore predefinito è 1000 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="7ec35-122">The default is 1000 milliseconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec35-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ec35-123">See Also</span></span>  
 <span data-ttu-id="7ec35-124">[Scelta di un protocollo di rete](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="7ec35-124">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 <span data-ttu-id="7ec35-125">[Nuovo alias &#40;scheda alias&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span><span class="sxs-lookup"><span data-stu-id="7ec35-125">[New Alias &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span></span>  
 [<span data-ttu-id="7ec35-126">Proprietà &#60;Alias&#62; &#40;scheda Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="7ec35-126">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
  
