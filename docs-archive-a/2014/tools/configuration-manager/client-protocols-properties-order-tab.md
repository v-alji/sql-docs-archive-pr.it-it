---
title: Proprietà-protocolli client (scheda ordine) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client protocols [SQL Server]
ms.assetid: 64fd7135-1756-4885-bed9-9ab8997ecc6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: a367cff3495389d1a707ed108ba75e1e736538b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713648"
---
# <a name="client-protocols-properties-order-tab"></a><span data-ttu-id="4d69f-102">Proprietà - Protocolli client (scheda Ordine)</span><span class="sxs-lookup"><span data-stu-id="4d69f-102">Client Protocols Properties (Order Tab)</span></span>
  <span data-ttu-id="4d69f-103">Usare la pagina **Ordine**della finestra di dialogo **Proprietà protocolli client** per visualizzare e abilitare i protocolli client.</span><span class="sxs-lookup"><span data-stu-id="4d69f-103">Use the **Order**page on the **Client Protocols Properties** dialog box to view and enable the client protocols.</span></span>  
  
 <span data-ttu-id="4d69f-104">Fare clic su un protocollo e quindi su **Abilita** o **Disabilita** per spostare il protocollo selezionato nell'elenco **Protocolli disabilitati** o **Protocolli abilitati** .</span><span class="sxs-lookup"><span data-stu-id="4d69f-104">Click a protocol, and then click **Enable** or **Disable** to move the selected protocol to the **Disabled Protocols** or **Enabled Protocols** list.</span></span>  
  
 <span data-ttu-id="4d69f-105">I protocolli vengono utilizzati nell'ordine dell'elenco, ovvero viene effettuato un tentativo di connessione con il primo protocollo, quindi con il secondo e così via. Per spostare un protocollo verso l'alto o verso il basso nell'elenco **Protocolli abilitati** , fare clic sui pulsanti freccia.</span><span class="sxs-lookup"><span data-stu-id="4d69f-105">Protocols are tried in the order listed, attempting to connect using the top protocol first, and then the second listed protocol, etc. Move protocols up or down the **Enabled Protocols** list, by clicking the up arrow and down arrow buttons.</span></span> <span data-ttu-id="4d69f-106">Se ci si connette a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un client installato nello stesso computer, verrà sempre eseguito un primo tentativo di connessione con il protocollo **Shared Memory**, se abilitato.</span><span class="sxs-lookup"><span data-stu-id="4d69f-106">When connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer, the **Shared Memory** protocol will always be tried first, if enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d69f-107">Queste impostazioni non vengono usate da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient.</span><span class="sxs-lookup"><span data-stu-id="4d69f-107">These settings are not used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient.</span></span> <span data-ttu-id="4d69f-108">L'ordine dei protocolli per .NET SqlClient è TCP, quindi named pipe e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="4d69f-108">The protocol order for .NET SqlClient is first TCP, and then named pipes, which cannot be changed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4d69f-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4d69f-109">Options</span></span>  
 <span data-ttu-id="4d69f-110">**Protocolli disabilitati**</span><span class="sxs-lookup"><span data-stu-id="4d69f-110">**Disabled Protocols**</span></span>  
 <span data-ttu-id="4d69f-111">Include un elenco dei protocolli installati ma non in uso.</span><span class="sxs-lookup"><span data-stu-id="4d69f-111">Lists protocols which are installed but are not currently used.</span></span>  
  
 <span data-ttu-id="4d69f-112">**Protocolli abilitati**</span><span class="sxs-lookup"><span data-stu-id="4d69f-112">**Enabled Protocols**</span></span>  
 <span data-ttu-id="4d69f-113">Elenca i protocolli disponibili per [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i client di questo computer.</span><span class="sxs-lookup"><span data-stu-id="4d69f-113">Lists protocols which are available for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this computer.</span></span>  
  
 **>**  
 <span data-ttu-id="4d69f-114">Abilita il protocollo selezionato nella casella **Protocolli disabilitati** , spostandolo nella casella **Protocolli abilitati** .</span><span class="sxs-lookup"><span data-stu-id="4d69f-114">Enables the currently highlighted protocol in the **Disabled Protocols** box, moving it to the **Enabled Protocols** box.</span></span>  
  
 **\<**  
 <span data-ttu-id="4d69f-115">Disabilita il protocollo selezionato nella casella **Protocolli abilitati** , spostandolo nella casella **Protocolli disabilitati** .</span><span class="sxs-lookup"><span data-stu-id="4d69f-115">Disables the currently highlighted protocol in the **Enabled Protocols** box, moving it to the **Disabled Protocols** box.</span></span>  
  
 <span data-ttu-id="4d69f-116">Freccia in su</span><span class="sxs-lookup"><span data-stu-id="4d69f-116">Up arrow</span></span>  
 <span data-ttu-id="4d69f-117">Sposta il protocollo selezionato verso l'alto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4d69f-117">Moves the highlighted protocol up in the list.</span></span> <span data-ttu-id="4d69f-118">In tal modo, è possibile aumentare le priorità in base alla quale la libreria di rete tenterà di utilizzare il protocollo selezionato per le connessioni.</span><span class="sxs-lookup"><span data-stu-id="4d69f-118">This allows you to increase the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="4d69f-119">Freccia GIÙ</span><span class="sxs-lookup"><span data-stu-id="4d69f-119">Down arrow</span></span>  
 <span data-ttu-id="4d69f-120">Sposta il protocollo selezionato verso il basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4d69f-120">Moves the highlighted protocol down in the list.</span></span> <span data-ttu-id="4d69f-121">In tal modo, è possibile diminuire il grado di priorità in base alla quale la libreria di rete tenterà di utilizzare il protocollo selezionato per le connessioni.</span><span class="sxs-lookup"><span data-stu-id="4d69f-121">This allows you to decrease the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="4d69f-122">**Abilita protocollo di memoria condivisa**</span><span class="sxs-lookup"><span data-stu-id="4d69f-122">**Enable Shared Memory Protocol**</span></span>  
 <span data-ttu-id="4d69f-123">Abilita il protocollo di memoria condivisa, che, se abilitato, viene sempre usato per primo per tentare una connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un client installato nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="4d69f-123">Enables the shared memory protocol which is always tried first (if enabled), when connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d69f-124">Se il protocollo viene specificato tramite un prefisso o come parte della stringa di connessione, viene eseguito un tentativo solo con il protocollo specificato.</span><span class="sxs-lookup"><span data-stu-id="4d69f-124">If the protocol is specified through a prefix or as part of the connection string, only the specified protocol is attempted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d69f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d69f-125">See Also</span></span>  
 [<span data-ttu-id="4d69f-126">Scelta di un protocollo di rete</span><span class="sxs-lookup"><span data-stu-id="4d69f-126">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
