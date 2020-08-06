---
title: Cerca server (Server di rete) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.browseservers.network.f1
ms.assetid: a59ffcd6-4b69-4c5c-9740-699ccb2183fb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0ba5e4e5dd6d9a6541a98e0cb30229d7335bac24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630078"
---
# <a name="browse-for-servers-network-servers"></a><span data-ttu-id="eed96-102">Cerca server (Server di rete)</span><span class="sxs-lookup"><span data-stu-id="eed96-102">Browse for Servers (Network Servers)</span></span>
  <span data-ttu-id="eed96-103">Se si esegue la connessione a un componente di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] senza conoscere il nome esatto dell'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], nella casella **Nome server** fare clic su **Cerca** per aprire la finestra di dialogo **Cerca server**.</span><span class="sxs-lookup"><span data-stu-id="eed96-103">If you are connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] component and you do not know the exact name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance, click **Browse for more** in the **Server name** box to open the **Browse for Servers** dialog box.</span></span>  
  
 <span data-ttu-id="eed96-104">Questa finestra di dialogo verrà popolata automaticamente dal servizio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser in esecuzione nei computer server.</span><span class="sxs-lookup"><span data-stu-id="eed96-104">This dialog is populated by the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service on the server computers.</span></span> <span data-ttu-id="eed96-105">È possibile che il nome di un'istanza non compaia nell'elenco per diverse ragioni:</span><span class="sxs-lookup"><span data-stu-id="eed96-105">There are several reasons why the name of an instance might not appear in the list:</span></span>  
  
-   <span data-ttu-id="eed96-106">Il servizio [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser potrebbe non essere in esecuzione nel computer sul quale è eseguito [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eed96-106">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service might not be running on the computer running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="eed96-107">La porta UDP 1434 potrebbe essere bloccata da un firewall.</span><span class="sxs-lookup"><span data-stu-id="eed96-107">UDP port 1434 might be blocked by a firewall.</span></span>  
  
-   <span data-ttu-id="eed96-108">Il flag **HideInstance** potrebbe non essere impostato.</span><span class="sxs-lookup"><span data-stu-id="eed96-108">The **HideInstance** flag might be set.</span></span>  
  
 <span data-ttu-id="eed96-109">Per connettersi a un'istanza che non compare nell'elenco, digitare una stringa di connessione completa per l'istanza, compreso il numero della porta TCP/IP o il nome pipe delle named pipe.</span><span class="sxs-lookup"><span data-stu-id="eed96-109">To connect to an instance that does not appear in the list, type a full connection string for the instance, including the TCP/IP port number or the named pipes pipe name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="eed96-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="eed96-110">Options</span></span>  
 <span data-ttu-id="eed96-111">**Selezionare l'istanza di SQL Server in rete con cui stabilire la connessione**</span><span class="sxs-lookup"><span data-stu-id="eed96-111">**Select a SQL Server instance in the network for your connection**</span></span>  
 <span data-ttu-id="eed96-112">Indicare il server a cui si desidera connettersi facendo clic sull'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] visualizzata nell'albero.</span><span class="sxs-lookup"><span data-stu-id="eed96-112">Designate the server you want to connect to by clicking on the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance displayed in the tree.</span></span> <span data-ttu-id="eed96-113">È possibile mostrare o nascondere parti della visualizzazione albero facendo clic sui nodi contrassegnati con un **+** **-** simbolo o.</span><span class="sxs-lookup"><span data-stu-id="eed96-113">You can show or hide portions of the tree view by clicking on the nodes marked with a **+** or **-** symbol.</span></span>  
  
  
