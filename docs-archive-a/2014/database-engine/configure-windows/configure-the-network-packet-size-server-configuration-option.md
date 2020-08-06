---
title: Configurare l'opzione di configurazione del server network packet size | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default packet size
- size [SQL Server], packets
- packets [SQL Server], size
- network packet size option
ms.assetid: 236985bf-fc4a-4a57-98f7-a71ef977fd7b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 69e5963675349bceff6a0ee022f6dc28da03db59
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715695"
---
# <a name="configure-the-network-packet-size-server-configuration-option"></a><span data-ttu-id="b861b-102">Configurare l'opzione di configurazione del server network packet size</span><span class="sxs-lookup"><span data-stu-id="b861b-102">Configure the network packet size Server Configuration Option</span></span>
  <span data-ttu-id="b861b-103">In questo argomento viene descritto come configurare l' `network packet size` opzione di configurazione del server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b861b-103">This topic describes how to configure the `network packet size` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b861b-104">L' `network packet size` opzione consente di impostare le dimensioni del pacchetto (in byte) utilizzate nell'intera rete.</span><span class="sxs-lookup"><span data-stu-id="b861b-104">The `network packet size` option sets the packet size (in bytes) that is used across the whole network.</span></span> <span data-ttu-id="b861b-105">I pacchetti sono i blocchi di dati di dimensioni fisse utilizzati per il trasferimento delle richieste e delle risposte tra client e server.</span><span class="sxs-lookup"><span data-stu-id="b861b-105">Packets are the fixed-size chunks of data that transfer requests and results between clients and servers.</span></span> <span data-ttu-id="b861b-106">Le dimensioni predefinite del pacchetto sono di 4.096 byte.</span><span class="sxs-lookup"><span data-stu-id="b861b-106">The default packet size is 4,096 bytes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b861b-107">È consigliabile modificare le dimensioni dei pacchetti solo se si è certi che l'operazione determinerà un miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b861b-107">Do not change the packet size unless you are certain that it will improve performance.</span></span> <span data-ttu-id="b861b-108">Per la maggior parte delle applicazioni, le dimensioni predefinite risultano ottimali.</span><span class="sxs-lookup"><span data-stu-id="b861b-108">For most applications, the default packet size is best.</span></span>  
  
 <span data-ttu-id="b861b-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="b861b-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b861b-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="b861b-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b861b-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b861b-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b861b-112">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="b861b-112">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="b861b-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b861b-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b861b-114">**Per configurare l'opzione network packet size tramite:**</span><span class="sxs-lookup"><span data-stu-id="b861b-114">**To configure the network packet size option, using:**</span></span>  
  
     [<span data-ttu-id="b861b-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b861b-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b861b-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b861b-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="b861b-117">**Completamento:**  [Dopo la configurazione dell'opzione network packet size](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="b861b-117">**Follow Up:**  [After you configure the network packet size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b861b-118">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b861b-118">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b861b-119">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b861b-119">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b861b-120">Il valore massimo consentito per network packet size per le connessioni crittografate è di 16.383 byte.</span><span class="sxs-lookup"><span data-stu-id="b861b-120">The maximum network packet size for encrypted connections is 16,383 bytes.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="b861b-121">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="b861b-121">Recommendations</span></span>  
  
-   <span data-ttu-id="b861b-122">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b861b-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="b861b-123">Se in un'applicazione vengono eseguite operazioni di copia bulk o inviate e ricevute quantità elevate di dati text o image, l'utilizzo di pacchetti di dimensioni maggiori rispetto a quelle predefinite potrebbe determinare un miglioramento delle prestazioni, poiché viene ridotto il numero di operazioni di lettura e scrittura di rete.</span><span class="sxs-lookup"><span data-stu-id="b861b-123">If an application does bulk copy operations or sends or receives large amounts of text or image data, a packet size larger than the default might improve efficiency because it results in fewer network read-and-write operations.</span></span> <span data-ttu-id="b861b-124">Se in un'applicazione vengono inviate e ricevute quantità limitate di dati, è possibile impostare le dimensioni del pacchetto su 512 byte, un valore sufficiente per la maggior parte dei trasferimenti di dati.</span><span class="sxs-lookup"><span data-stu-id="b861b-124">If an application sends and receives small amounts of information, the packet size can be set to 512 bytes, which is sufficient for most data transfers.</span></span>  
  
-   <span data-ttu-id="b861b-125">Nei sistemi che usano protocolli di rete diversi, è consigliabile impostare le dimensioni pacchetto di rete corrispondenti al protocollo usato più di frequente.</span><span class="sxs-lookup"><span data-stu-id="b861b-125">On systems that are using different network protocols, set network packet size to the size for the most common protocol used.</span></span> <span data-ttu-id="b861b-126">L'opzione network packet size determina un miglioramento delle prestazioni della rete se i protocolli di rete supportano pacchetti di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="b861b-126">The network packet size option improves network performance when network protocols support larger packets.</span></span> <span data-ttu-id="b861b-127">Le applicazioni client possono modificare tale valore.</span><span class="sxs-lookup"><span data-stu-id="b861b-127">Client applications can override this value.</span></span>  
  
-   <span data-ttu-id="b861b-128">È inoltre possibile richiedere di modificare le dimensioni dei pacchetti tramite le funzioni OLE DB, ODBC (Open Database Connectivity) e DB-Library.</span><span class="sxs-lookup"><span data-stu-id="b861b-128">You can also call OLE DB, Open Database Connectivity (ODBC), and DB-Library functions request a change the packet size.</span></span> <span data-ttu-id="b861b-129">Se il server non supporta le dimensioni del pacchetto richieste, un messaggio di avviso verrà inviato al client da [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b861b-129">If the server cannot support the requested packet size, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will send a warning message to the client.</span></span> <span data-ttu-id="b861b-130">In alcuni casi la modifica delle dimensioni dei pacchetti potrebbe provocare un errore del collegamento di comunicazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b861b-130">In some circumstances, changing the packet size might lead to a communication link failure, such as the following:</span></span>  
  
     `Native Error: 233, no process is on the other end of the pipe.`  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b861b-131">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b861b-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b861b-132">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b861b-132">Permissions</span></span>  
 <span data-ttu-id="b861b-133">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="b861b-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="b861b-134">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="b861b-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="b861b-135">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="b861b-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b861b-136">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b861b-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="b861b-137">Per configurare l'opzione network packet size</span><span class="sxs-lookup"><span data-stu-id="b861b-137">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="b861b-138">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b861b-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="b861b-139">Fare clic sul nodo **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="b861b-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="b861b-140">In **Rete**selezionare un valore per la casella **Dimensioni pacchetto di rete** .</span><span class="sxs-lookup"><span data-stu-id="b861b-140">Under **Network**, select a value for the **Network Packet Size** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b861b-141">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b861b-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-network-packet-size-option"></a><span data-ttu-id="b861b-142">Per configurare l'opzione network packet size</span><span class="sxs-lookup"><span data-stu-id="b861b-142">To configure the network packet size option</span></span>  
  
1.  <span data-ttu-id="b861b-143">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b861b-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b861b-144">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="b861b-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b861b-145">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b861b-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b861b-146">In questo esempio viene illustrato come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `network packet size` su `6500` byte.</span><span class="sxs-lookup"><span data-stu-id="b861b-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `network packet size` option to `6500` bytes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'network packet size', 6500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="b861b-147">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="b861b-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-network-packet-size-option"></a><a name="FollowUp"></a> <span data-ttu-id="b861b-148">Completamento: Dopo la configurazione dell'opzione network packet size</span><span class="sxs-lookup"><span data-stu-id="b861b-148">Follow Up: After you configure the network packet size option</span></span>  
 <span data-ttu-id="b861b-149">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="b861b-149">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b861b-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b861b-150">See Also</span></span>  
 <span data-ttu-id="b861b-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b861b-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="b861b-152">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b861b-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="b861b-153">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b861b-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
