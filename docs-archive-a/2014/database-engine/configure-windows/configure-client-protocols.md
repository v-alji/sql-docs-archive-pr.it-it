---
title: Configurazione di protocolli client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default protocols
- network protocols [SQL Server], client configuration
- TCP/IP [SQL Server], client protocols
- disabling client protocols
- ordering protocols [SQL Server]
- protocols [SQL Server], order for client computers
- configure client protocols
- client protocols [SQL Server]
- protocols [SQL Server], client configuration
ms.assetid: 3dfa2702-ba65-43b4-a777-6727846e133a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2eb223815c3e3af50813e02d3ded60573c327155
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638106"
---
# <a name="configure-client-protocols"></a><span data-ttu-id="3858a-102">configurazione di protocolli client</span><span class="sxs-lookup"><span data-stu-id="3858a-102">Configure Client Protocols</span></span>
  <span data-ttu-id="3858a-103">In questo argomento viene descritto come configurare i protocolli client utilizzati dalle applicazioni client in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3858a-103">This topic describes how to configure client protocols used by client applications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="3858a-104">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supporta le comunicazioni client con il protocollo di rete TCP/IP e il protocollo Named Pipes.</span><span class="sxs-lookup"><span data-stu-id="3858a-104">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supports client communication with the TCP/IP network protocol and the named pipes protocol.</span></span> <span data-ttu-id="3858a-105">Se il client si connette a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] nello stesso computer, è inoltre disponibile il protocollo Shared Memory.</span><span class="sxs-lookup"><span data-stu-id="3858a-105">The shared memory protocol is also available if the client is connecting to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the same computer.</span></span> <span data-ttu-id="3858a-106">La selezione del protocollo può essere in genere eseguita in tre modi.</span><span class="sxs-lookup"><span data-stu-id="3858a-106">There are three common methods of selecting the protocol.</span></span>  
  
-   <span data-ttu-id="3858a-107">Configurare tutte le applicazioni client in modo da utilizzare lo stesso protocollo di rete impostando l'ordine dei protocolli in Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3858a-107">Configure all client applications to use the same network protocol by setting the protocol order in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
-   <span data-ttu-id="3858a-108">Configurare una singola applicazione client in modo da utilizzare un protocollo di rete diverso tramite la creazione di un alias.</span><span class="sxs-lookup"><span data-stu-id="3858a-108">Configure a single client application to use a different network protocol by creating an alias.</span></span> <span data-ttu-id="3858a-109">Per altre informazioni, vedere [Creazione o eliminazione di un alias server per l'utilizzo da parte di un client &#40;Gestione configurazione SQL Server&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md).</span><span class="sxs-lookup"><span data-stu-id="3858a-109">For more information, see [Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md).</span></span>  
  
-   <span data-ttu-id="3858a-110">Alcune applicazioni client, ad esempio sqlcmd.exe, possono specificare il protocollo nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="3858a-110">Some client applications, such as sqlcmd.exe, can specify the protocol as part of the connection string.</span></span> <span data-ttu-id="3858a-111">Per altre informazioni, vedere [Connessione al Motore di database tramite sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="3858a-111">For more information, see [Connect to the Database Engine With sqlcmd](../../relational-databases/scripting/sqlcmd-connect-to-the-database-engine.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3858a-112">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="3858a-112">Using SQL Server Configuration Manager</span></span>  
  
###  <a name="to-enable-or-disable-a-client-protocol"></a><a name="EnableDisable"></a> <span data-ttu-id="3858a-113">Per attivare o disabilitare un protocollo client</span><span class="sxs-lookup"><span data-stu-id="3858a-113">To enable or disable a client protocol</span></span>  
  
1.  <span data-ttu-id="3858a-114">In Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] espandere **Configurazione SQL Server Native Client**, fare clic con il pulsante destro del mouse su **Protocolli client** e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3858a-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3858a-115">Fare clic su un protocollo nella casella **Protocolli disabilitati** e quindi su **Abilita** per abilitare il protocollo.</span><span class="sxs-lookup"><span data-stu-id="3858a-115">Click a protocol in the **Disabled Protocols** box, and then click **Enable**, to enable a protocol.</span></span>  
  
3.  <span data-ttu-id="3858a-116">Fare clic su un protocollo nella casella **Protocolli abilitati** e quindi su **Disabilita** per disabilitare il protocollo.</span><span class="sxs-lookup"><span data-stu-id="3858a-116">Click a protocol in the **Enabled Protocols** box, and then click **Disable**, to disable a protocol.</span></span>  
  
###  <a name="to-change-the-default-protocol-or-the-protocol-order-for-client-computers"></a><a name="ChangeDefault"></a> <span data-ttu-id="3858a-117">Per cambiare il protocollo predefinito o modificare l'ordine dei protocolli per i computer client</span><span class="sxs-lookup"><span data-stu-id="3858a-117">To change the default protocol or the protocol order for client computers</span></span>  
  
1.  <span data-ttu-id="3858a-118">In Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] espandere **Configurazione SQL Server Native Client**, fare clic con il pulsante destro del mouse su **Protocolli client** e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3858a-118">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3858a-119">Nella casella **Protocolli abilitati** fare clic su **Sposta su** o **Sposta giù** per modificare l'ordine in cui i protocolli vengono usati durante un tentativo di connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3858a-119">In the **Enabled Protocols** box, click **Move Up** or **Move Down**, to change the order in which protocols are tried, when attempting to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3858a-120">Il protocollo visualizzato in alto nella casella **Protocolli abilitati** è il protocollo predefinito.</span><span class="sxs-lookup"><span data-stu-id="3858a-120">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3858a-121">Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crea voci del Registro di sistema relative alle configurazioni dell'alias server e alla libreria di rete client predefinita.</span><span class="sxs-lookup"><span data-stu-id="3858a-121">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager creates registry entries for the server alias configurations and default client network library.</span></span> <span data-ttu-id="3858a-122">Tuttavia, le applicazioni non installano le librerie di rete client di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o i protocolli di rete.</span><span class="sxs-lookup"><span data-stu-id="3858a-122">However, the application does not install either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries or the network protocols.</span></span> <span data-ttu-id="3858a-123">Le librerie di rete client di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono installate durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], i protocolli di rete nell'ambito dell'installazione di Windows, oppure accedendo alla sezione **Reti** del **Pannello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="3858a-123">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network libraries are installed during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup; the network protocols are installed as part of Microsoft Windows Setup (or through **Networks** in **Control Panel**).</span></span> <span data-ttu-id="3858a-124">È possibile che un particolare protocollo di rete non sia disponibile tramite l'installazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="3858a-124">A particular network protocol may not be available as part of Windows Setup.</span></span> <span data-ttu-id="3858a-125">Per ulteriori informazioni sull'installazione di protocolli di rete specifici, vedere la documentazione del produttore.</span><span class="sxs-lookup"><span data-stu-id="3858a-125">For more information about installing these network protocols, see the vendor documentation.</span></span>  
  
###  <a name="to-configure-a-client-to-use-tcpip"></a><a name="Configure"></a> <span data-ttu-id="3858a-126">Per configurare un client per l'utilizzo di TCP/IP</span><span class="sxs-lookup"><span data-stu-id="3858a-126">To configure a client to use TCP/IP</span></span>  
  
1.  <span data-ttu-id="3858a-127">In Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] espandere **Configurazione SQL Server Native Client**, fare clic con il pulsante destro del mouse su **Protocolli client** e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3858a-127">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Client Protocols**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="3858a-128">Nella casella **Protocolli abilitati** fare clic sulle frecce SU e GIÙ per modificare l'ordine di utilizzo dei protocolli durante un tentativo di connessione a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3858a-128">In the **Enabled Protocols** box, click the up and down arrows to change the order in which protocols are tried, when attempting to connect to SQL Server.</span></span> <span data-ttu-id="3858a-129">Il protocollo visualizzato in alto nella casella **Protocolli abilitati** è il protocollo predefinito.</span><span class="sxs-lookup"><span data-stu-id="3858a-129">The top protocol in the **Enabled Protocols** box is the default protocol.</span></span>  
  
 <span data-ttu-id="3858a-130">Il protocollo Shared Memory viene abilitato separatamente selezionando la casella **Abilita protocollo Shared Memory**.</span><span class="sxs-lookup"><span data-stu-id="3858a-130">The shared memory protocol is enabled separately by checking the **Enabled Shared Memory Protocol** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3858a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3858a-131">See Also</span></span>  
 [<span data-ttu-id="3858a-132">Configurare l'opzione di configurazione del server remote login timeout</span><span class="sxs-lookup"><span data-stu-id="3858a-132">Configure the remote login timeout Server Configuration Option</span></span>](configure-the-remote-login-timeout-server-configuration-option.md)  
  
  
