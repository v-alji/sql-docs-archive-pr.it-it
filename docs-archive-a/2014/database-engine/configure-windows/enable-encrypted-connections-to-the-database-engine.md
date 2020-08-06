---
title: Abilitare le connessioni crittografate al motore di database (Gestione configurazione SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], encrypted
- SSL [SQL Server]
- Secure Sockets Layer (SSL)
- encryption [SQL Server], connections
- cryptography [SQL Server], connections
- certificates [SQL Server], installing
- requesting encrypted connections
- installing certificates
- security [SQL Server], encryption
ms.assetid: e1e55519-97ec-4404-81ef-881da3b42006
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1653df929e3f8bc67158a0685ce07b8ba65de6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724923"
---
# <a name="enable-encrypted-connections-to-the-database-engine-sql-server-configuration-manager"></a><span data-ttu-id="150be-102">Abilitazione di connessioni crittografate al Motore di database (Gestione configurazione SQL Server)</span><span class="sxs-lookup"><span data-stu-id="150be-102">Enable Encrypted Connections to the Database Engine (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="150be-103">In questo argomento viene descritto come abilitare connessioni crittografate per un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] specificando un certificato per il [!INCLUDE[ssDE](../../includes/ssde-md.md)] tramite Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="150be-103">This topic describes how to enable encrypted connections for an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] by specifying a certificate for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="150be-104">È necessario che sia disponibile un certificato per il computer server e che il computer client sia impostato per considerare attendibile l'autorità radice del certificato.</span><span class="sxs-lookup"><span data-stu-id="150be-104">The server computer must have a certificate provisioned, and the client machine must be set up to trust the certificate's root authority.</span></span> <span data-ttu-id="150be-105">Il processo di provisioning consiste nell'installazione di un certificato tramite l'importazione in Windows.</span><span class="sxs-lookup"><span data-stu-id="150be-105">Provisioning is the process of installing a certificate by importing it into Windows.</span></span>  
  
 <span data-ttu-id="150be-106">Il certificato deve essere emesso per l'opzione **Autenticazione server**.</span><span class="sxs-lookup"><span data-stu-id="150be-106">The certificate must be issued for **Server Authentication**.</span></span> <span data-ttu-id="150be-107">Il nome del certificato deve essere il nome di dominio completo (FQDN) del computer.</span><span class="sxs-lookup"><span data-stu-id="150be-107">The name of the certificate must be the fully qualified domain name (FQDN) of the computer.</span></span>  
  
 <span data-ttu-id="150be-108">I certificati per gli utenti vengono archiviati nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="150be-108">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="150be-109">Per installare un certificato utilizzato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è necessario eseguire Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con lo stesso account utente del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a meno che il servizio sia in esecuzione con l'account LocalSystem, NetworkService o LocalService e sia pertanto consentito utilizzare un account amministrativo.</span><span class="sxs-lookup"><span data-stu-id="150be-109">To install a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service unless the service is running as LocalSystem, NetworkService, or LocalService, in which case you may use an administrative account.</span></span>  
  
 <span data-ttu-id="150be-110">Il client deve essere in grado di verificare la proprietà del certificato utilizzato dal server.</span><span class="sxs-lookup"><span data-stu-id="150be-110">The client must be able to verify the ownership of the certificate used by the server.</span></span> <span data-ttu-id="150be-111">Se il client dispone del certificato chiave pubblica dell'autorità di certificazione che ha firmato il certificato del server, non sono necessarie ulteriori operazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="150be-111">If the client has the public key certificate of the certification authority that signed the server certificate, no further configuration is necessary.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="150be-112">Windows sono inclusi i certificati chiave pubblica di numerose autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="150be-112">Windows includes the public key certificates of many certification authorities.</span></span> <span data-ttu-id="150be-113">Se il certificato del server è stato firmato da un'autorità di certificazione pubblica o privata per la quale il client non dispone del certificato chiave pubblica, è necessario installare il certificato chiave pubblica dell'autorità di certificazione che ha firmato il certificato del server.</span><span class="sxs-lookup"><span data-stu-id="150be-113">If the server certificate was signed by a public or private certification authority for which the client does not have the public key certificate, you must install the public key certificate of the certification authority that signed the server certificate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="150be-114">Per utilizzare la crittografia in un cluster di failover, è necessario installare il certificato server con il nome DNS completo del server virtuale in tutti i nodi del cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="150be-114">To use encryption with a failover cluster, you must install the server certificate with the fully qualified DNS name of the virtual server on all nodes in the failover cluster.</span></span> <span data-ttu-id="150be-115">Ad esempio, se si dispone di un cluster a due nodi, con nodi denominati test1. *\<your company>* . com e test2. *\<your company>* . com e si dispone di un server virtuale denominato Virtsql, è necessario installare un certificato per *\<your company>* virtsql. com in entrambi i nodi.</span><span class="sxs-lookup"><span data-stu-id="150be-115">For example, if you have a two-node cluster, with nodes named test1.*\<your company>*.com and test2.*\<your company>*.com, and you have a virtual server named virtsql, you need to install a certificate for virtsql.*\<your company>*.com on both nodes.</span></span> <span data-ttu-id="150be-116">È possibile impostare il valore dell'opzione **ForceEncryption**su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="150be-116">You can set the value of the **ForceEncryption**option to **Yes**.</span></span>  
  
 <span data-ttu-id="150be-117">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="150be-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="150be-118">**Per abilitare connessioni crittografate:**</span><span class="sxs-lookup"><span data-stu-id="150be-118">**To enable encrypted connections:**</span></span>  
  
     [<span data-ttu-id="150be-119">Eseguire il provisioning di (installare) un certificato nel server</span><span class="sxs-lookup"><span data-stu-id="150be-119">Provision (install) a certificate on the server</span></span>](#Provision)  
  
     [<span data-ttu-id="150be-120">Esportare il certificato del server</span><span class="sxs-lookup"><span data-stu-id="150be-120">Export the server certificate</span></span>](#Export)  
  
     [<span data-ttu-id="150be-121">Configurare il server in modo che accetti connessioni crittografate</span><span class="sxs-lookup"><span data-stu-id="150be-121">Configure the server to accept encrypted connections</span></span>](#ConfigureServerConnections)  
  
     [<span data-ttu-id="150be-122">Configurare il client in modo che richieda connessioni crittografate</span><span class="sxs-lookup"><span data-stu-id="150be-122">Configure the client to request encrypted connections</span></span>](#ConfigureClientConnections)  
  
     [<span data-ttu-id="150be-123">Crittografare una connessione da SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="150be-123">Encrypt a connection from SQL Server Management Studio</span></span>](#EncryptConnection)  
  
##  <a name="SSMSProcedure"></a>  
  
###  <a name="to-provision-install-a-certificate-on-the-server"></a><a name="Provision"></a><span data-ttu-id="150be-124">Per eseguire il provisioning (installare) un certificato nel server</span><span class="sxs-lookup"><span data-stu-id="150be-124">To provision (install) a certificate on the server</span></span>  
  
1.  <span data-ttu-id="150be-125">Dal menu **Start** fare clic su **Esegui**, quindi nella casella **Apri** digitare `MMC` e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="150be-125">On the **Start** menu, click **Run**, and in the **Open** box, type `MMC` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="150be-126">Nella console MMC scegliere **Aggiungi/Rimuovi snap-in** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="150be-126">In the MMC console, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="150be-127">Nella finestra di dialogo **Aggiungi/Rimuovi snap-in** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="150be-127">In the **Add/Remove Snap-in** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="150be-128">Nella finestra di dialogo **Aggiungi snap-in autonomo** fare clic su **Certificati**e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="150be-128">In the **Add Standalone Snap-in** dialog box, click **Certificates**, click **Add**.</span></span>  
  
5.  <span data-ttu-id="150be-129">Nella finestra di dialogo **Snap-in certificati** fare clic su **Account del computer**e quindi su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="150be-129">In the **Certificates snap-in** dialog box, click **Computer account**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="150be-130">Nella finestra di dialogo **Aggiungi snap-in autonomo** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="150be-130">In the **Add Standalone Snap-in** dialog box, click **Close.**</span></span>  
  
7.  <span data-ttu-id="150be-131">Nella finestra di dialogo **Aggiungi/Rimuovi snap-in** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="150be-131">In the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="150be-132">Nello snap-in **Certificati** espandere **Certificati**e **Personale**, fare clic con il pulsante destro del mouse su **Certificati**, scegliere **Tutte le attività**e quindi fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="150be-132">In the **Certificates** snap-in, expand **Certificates**, expand **Personal**, and then right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
9. <span data-ttu-id="150be-133">Completare l' **Importazione guidata certificati**per aggiungere un certificato al computer e chiudere la console MMC.</span><span class="sxs-lookup"><span data-stu-id="150be-133">Complete the **Certificate Import Wizard**, to add a certificate to the computer, and close the MMC console.</span></span> <span data-ttu-id="150be-134">Per ulteriori informazioni sull'aggiunta di un certificato a un computer, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="150be-134">For more information about adding a certificate to a computer, see your Windows documentation.</span></span>  
  
###  <a name="to-export-the-server-certificate"></a><a name="Export"></a> <span data-ttu-id="150be-135">Per esportare il certificato del server</span><span class="sxs-lookup"><span data-stu-id="150be-135">To export the server certificate</span></span>  
  
1.  <span data-ttu-id="150be-136">Nello snap-in **Certificati** individuare il certificato nella cartella **Certificati** / **Personale** , fare clic con il pulsante destro del mouse su **Certificato**, scegliere **Tutte le attività**e quindi fare clic su **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="150be-136">From the **Certificates** snap-in, locate the certificate in the **Certificates** / **Personal** folder, right-click the **Certificate**, point to **All Tasks**, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="150be-137">Completare l' **Esportazione guidata certificati**e archiviare il file di certificato in una posizione appropriata.</span><span class="sxs-lookup"><span data-stu-id="150be-137">Complete the **Certificate Export Wizard**, storing the certificate file in a convenient location.</span></span>  
  
###  <a name="to-configure-the-server-to-accept-encrypted-connections"></a><a name="ConfigureServerConnections"></a> <span data-ttu-id="150be-138">Per configurare il server in modo che accetti connessioni crittografate</span><span class="sxs-lookup"><span data-stu-id="150be-138">To configure the server to accept encrypted connections</span></span>  
  
1.  <span data-ttu-id="150be-139">In **Gestione configurazione SQL Server** espandere **Configurazione di rete SQL Server**, fare clic con il pulsante destro del mouse su **Protocolli per**  _\<server instance>_ e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="150be-139">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, right-click **Protocols for** _\<server instance>_, and then select**Properties**.</span></span>  
  
2.  <span data-ttu-id="150be-140">Nella finestra di dialogo **protocolli per** _\<instance name>_ **proprietà** , nella scheda **certificato** , selezionare il certificato desiderato dall'elenco a discesa per la casella **certificato** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="150be-140">In the **Protocols for**_\<instance name>_ **Properties** dialog box, on the **Certificate** tab, select the desired certificate from the drop down for the **Certificate** box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="150be-141">Nella casella **ForceEncryption** della scheda **Flag** selezionare **Sì**e quindi fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="150be-141">On the **Flags** tab, in the **ForceEncryption** box, select **Yes**, and then click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="150be-142">Riavviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="150be-142">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
###  <a name="to-configure-the-client-to-request-encrypted-connections"></a><a name="ConfigureClientConnections"></a> <span data-ttu-id="150be-143">Per configurare il client in modo che richieda connessioni crittografate</span><span class="sxs-lookup"><span data-stu-id="150be-143">To configure the client to request encrypted connections</span></span>  
  
1.  <span data-ttu-id="150be-144">Copiare il certificato originale o il file di certificato esportato nel computer client.</span><span class="sxs-lookup"><span data-stu-id="150be-144">Copy either the original certificate or the exported certificate file to the client computer.</span></span>  
  
2.  <span data-ttu-id="150be-145">Nel computer client usare lo snap-in **Certificati** per installare il certificato radice o il file di certificato esportato.</span><span class="sxs-lookup"><span data-stu-id="150be-145">On the client computer, use the **Certificates** snap-in to install either the root certificate or the exported certificate file.</span></span>  
  
3.  <span data-ttu-id="150be-146">Nel riquadro della console fare clic con il pulsante destro del mouse su **Configurazione SQL Server Native Client**e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="150be-146">In the console pane, right-click **SQL Server Native Client Configuration**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="150be-147">Nella casella **Imponi crittografia protocolli** della pagina **Flag** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="150be-147">On the **Flags** page, in the **Force protocol encryption** box, click **Yes**.</span></span>  
  
###  <a name="to-encrypt-a-connection-from-sql-server-management-studio"></a><a name="EncryptConnection"></a><span data-ttu-id="150be-148">Per crittografare una connessione da SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="150be-148">To encrypt a connection from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="150be-149">Nella barra degli strumenti di Esplora oggetti fare clic su **Connetti**e quindi su **Motore di database**.</span><span class="sxs-lookup"><span data-stu-id="150be-149">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="150be-150">Nella finestra di dialogo **Connetti al server** completare le informazioni di connessione e quindi fare clic su **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="150be-150">In the **Connect to Server** dialog box, complete the connection information, and then click **Options**.</span></span>  
  
3.  <span data-ttu-id="150be-151">Nella scheda **Proprietà connessione** fare clic su **Crittografa connessione**.</span><span class="sxs-lookup"><span data-stu-id="150be-151">On the **Connection Properties** tab, click **Encrypt connection**.</span></span>  
  
  
