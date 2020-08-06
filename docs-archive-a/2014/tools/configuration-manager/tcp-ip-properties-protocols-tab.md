---
title: Proprietà TCP-IP (scheda protocolli) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], configuration options
ms.assetid: 007638fc-3a24-4460-adbe-545ded5d6f88
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d5bc28faddae9a86a6636b56b907b57a2d8711a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624500"
---
# <a name="tcp---ip-properties-protocols-tab"></a><span data-ttu-id="67a23-102">Proprietà TCP-IP (scheda protocolli)</span><span class="sxs-lookup"><span data-stu-id="67a23-102">TCP - IP Properties (Protocols Tab)</span></span>
  <span data-ttu-id="67a23-103">La finestra di dialogo **Proprietà - TCP/IP** consente di configurare le opzioni relative al protocollo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="67a23-103">Use the **TCP/IP Properties** dialog box to configure the options for the TCP/IP protocol.</span></span> <span data-ttu-id="67a23-104">Fare clic su **TCP/IP** nel riquadro sinistro per visualizzare le configurazioni dei singoli indirizzi IP nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="67a23-104">Click **TCP/IP** in the left pane, to show individual IP address configurations in the details pane.</span></span>  
  
 <span data-ttu-id="67a23-105">Per rendere effettive le modifiche, è necessario riavviare Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67a23-105">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted before the changes take effect.</span></span>  
  
## <a name="options"></a><span data-ttu-id="67a23-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="67a23-106">Options</span></span>  
 <span data-ttu-id="67a23-107">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="67a23-107">**Enabled**</span></span>  
 <span data-ttu-id="67a23-108">I valori possibili sono **Sì** e **No**.</span><span class="sxs-lookup"><span data-stu-id="67a23-108">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="67a23-109">**Keep-alive**</span><span class="sxs-lookup"><span data-stu-id="67a23-109">**Keep Alive**</span></span>  
 <span data-ttu-id="67a23-110">Specificare l'intervallo, in millisecondi, in cui i pacchetti keep-alive vengono trasmessi per verificare che il computer remoto sia ancora disponibile.</span><span class="sxs-lookup"><span data-stu-id="67a23-110">Specify the interval (milliseconds) in which keep-alive packets are transmitted to verify that the computer at the remote end of a connection is still available.</span></span>  
  
 <span data-ttu-id="67a23-111">**Attesa su tutti**</span><span class="sxs-lookup"><span data-stu-id="67a23-111">**Listen All**</span></span>  
 <span data-ttu-id="67a23-112">Specificare se SQL Server resterà in attesa su tutti gli indirizzi IP associati alle schede di rete del computer.</span><span class="sxs-lookup"><span data-stu-id="67a23-112">Specify whether SQL Server will listen on all the IP addresses that are bound to network cards on the computer.</span></span> <span data-ttu-id="67a23-113">Se è impostato su **No**, configurare separatamente ogni indirizzo IP usando la finestra di dialogo delle proprietà dei singoli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="67a23-113">If set to **No**, configure each IP address separately using the properties dialog box for each IP address.</span></span> <span data-ttu-id="67a23-114">Se è impostato su **Sì**, le impostazioni della casella delle proprietà relative a **IPAll** verranno applicate a tutti gli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="67a23-114">If set to **Yes**, the settings of the **IPAll** properties box will apply to all IP addresses.</span></span> <span data-ttu-id="67a23-115">Il valore predefinito è **Sì**.</span><span class="sxs-lookup"><span data-stu-id="67a23-115">Default value is **Yes**.</span></span>  
  
 <span data-ttu-id="67a23-116">**Nessun ritardo**</span><span class="sxs-lookup"><span data-stu-id="67a23-116">**No Delay**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="67a23-117">non implementa modifiche a questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="67a23-117">does not implement changes to this property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a23-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67a23-118">See Also</span></span>  
 <span data-ttu-id="67a23-119">[Scelta di un protocollo di rete](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="67a23-119">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="67a23-120">Creazione di una stringa di connessione valida con TCP/IP</span><span class="sxs-lookup"><span data-stu-id="67a23-120">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
  
