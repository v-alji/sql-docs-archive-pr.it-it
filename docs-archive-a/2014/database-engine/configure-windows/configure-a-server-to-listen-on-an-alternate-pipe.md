---
title: Configurare un server per l'ascolto su una pipe alternativa (Gestione configurazione SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Named Pipes [SQL Server], configuring
- listening [SQL Server], pipes
- pipes [SQL Server], alternate
- alternate pipes [SQL Server]
ms.assetid: 914f7491-e2be-4b0d-b3aa-fe5409cdbafa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 57d70cf4cd1d7474b895aeb8cb144c885e8a0f99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624352"
---
# <a name="configure-a-server-to-listen-on-an-alternate-pipe-sql-server-configuration-manager"></a><span data-ttu-id="68c7c-102">Configurazione di un server per l'attesa su una pipe alternativa (Gestione configurazione SQL Server)</span><span class="sxs-lookup"><span data-stu-id="68c7c-102">Configure a Server to Listen on an Alternate Pipe (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="68c7c-103">In questo argomento viene illustrato come configurare un server per l'ascolto su una pipe alternativa in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68c7c-103">This topic describes how to configure a server to listen on an alternate pipe in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="68c7c-104">Per impostazione predefinita, l'istanza predefinita di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] è in attesa sulla named pipe \\\\.\pipe\sql\query.</span><span class="sxs-lookup"><span data-stu-id="68c7c-104">By default, the default instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on named pipe \\\\.\pipe\sql\query.</span></span> <span data-ttu-id="68c7c-105">Le istanze denominate del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e [!INCLUDE[ssEW](../../includes/ssew-md.md)] sono in attesa su altre pipe.</span><span class="sxs-lookup"><span data-stu-id="68c7c-105">Named instances of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] listen on other pipes.</span></span>  
  
 <span data-ttu-id="68c7c-106">È possibile connettersi a una named pipe specifica mediante un'applicazione client in tre modi differenti:</span><span class="sxs-lookup"><span data-stu-id="68c7c-106">There are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="68c7c-107">Avviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser sul server.</span><span class="sxs-lookup"><span data-stu-id="68c7c-107">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="68c7c-108">Creare un alias nel client, specificando la named pipe.</span><span class="sxs-lookup"><span data-stu-id="68c7c-108">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="68c7c-109">Programmare il client affinché si connetta utilizzando una stringa di connessione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="68c7c-109">Program the client to connect using a custom connection string.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="68c7c-110">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="68c7c-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-configure-the-named-pipe-used-by-the-sql-server-database-engine"></a><span data-ttu-id="68c7c-111">Per configurare l'utilizzo della named pipe mediante il Motore di database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="68c7c-111">To configure the named pipe used by the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="68c7c-112">Nel riquadro della console di Gestione configurazione SQL Server espandere **Configurazione di rete SQL Server** e quindi espandere **Protocolli per**  *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="68c7c-112">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, and then click expand **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="68c7c-113">Nel riquadro dei dettagli fare clic con il pulsante destro del mouse su **Named pipe**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="68c7c-113">In the details pane, right-click **Named Pipes**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="68c7c-114">Nel riquadro **Nome pipe** della scheda **Protocollo** , specificare la pipe su cui si desidera che il [!INCLUDE[ssDE](../../includes/ssde-md.md)] sia in attesa e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="68c7c-114">On the **Protocol** tab, in the **Pipe Name** box, type the pipe you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="68c7c-115">Nel riquadro della console fare clic su **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="68c7c-115">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="68c7c-116">Nel riquadro dei dettagli fare clic con il pulsante destro del mouse su **SQL Server (** \<instance name> **)** e quindi scegliere **Riavvia** per arrestare e riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68c7c-116">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="68c7c-117">Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in attesa su una pipe alternativa, è possibile connettersi a una named pipe specifica mediante un'applicazione client in tre modi differenti:</span><span class="sxs-lookup"><span data-stu-id="68c7c-117">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening on an alternate pipe, there are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="68c7c-118">Avviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser sul server.</span><span class="sxs-lookup"><span data-stu-id="68c7c-118">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="68c7c-119">Creare un alias nel client, specificando la named pipe.</span><span class="sxs-lookup"><span data-stu-id="68c7c-119">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="68c7c-120">Programmare il client affinché si connetta utilizzando una stringa di connessione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="68c7c-120">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68c7c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68c7c-121">See Also</span></span>  
 <span data-ttu-id="68c7c-122">[Creare o eliminare un alias server per l'uso da parte di un client &#40;Gestione configurazione SQL Server Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md) </span><span class="sxs-lookup"><span data-stu-id="68c7c-122">[Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md) </span></span>  
 [<span data-ttu-id="68c7c-123">Configurazione di rete del server</span><span class="sxs-lookup"><span data-stu-id="68c7c-123">Server Network Configuration</span></span>](server-network-configuration.md)  
  
  
