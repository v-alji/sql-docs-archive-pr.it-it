---
title: Installare SQL Server 2014 usando un file di configurazione | Microsoft Docs
ms.custom: ''
ms.date: 01/20/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: a832153a-6775-4bed-83f0-55790766d885
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a2f09ad6253762fe5b525f6c918931f4806c84c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713436"
---
# <a name="install-sql-server-2014-using-a-configuration-file"></a><span data-ttu-id="2a989-102">Installare SQL Server 2014 tramite un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2a989-102">Install SQL Server 2014 Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2a989-103">Il programma di installazione consente di generare un file di configurazione in base all'impostazione predefinita del sistema e ai dati di input inseriti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2a989-103">Setup provides the ability to generate a configuration file based upon the system default and run-time inputs.</span></span> <span data-ttu-id="2a989-104">È possibile utilizzare il file di configurazione per distribuire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in tutta l'organizzazione con la stessa configurazione,</span><span class="sxs-lookup"><span data-stu-id="2a989-104">You can use the configuration file to deploy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] throughout the enterprise with the same configuration.</span></span> <span data-ttu-id="2a989-105">nonché standardizzare le installazioni manuali nell'organizzazione creando un file batch che consente di avviare Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="2a989-105">You can also standardize manual installations throughout the enterprise, by creating a batch file that launches Setup.exe.</span></span>  
  
 <span data-ttu-id="2a989-106">Il programma di installazione supporta l'utilizzo del file di configurazione solo tramite il prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="2a989-106">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="2a989-107">L'ordine di elaborazione dei parametri durante l'utilizzo del file di configurazione viene indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2a989-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="2a989-108">Il file di configurazione sovrascrive le impostazioni predefinite in un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2a989-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="2a989-109">I valori della riga di comando sovrascrivono quelli presenti nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2a989-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="2a989-110">Il file di configurazione può essere utilizzato per tenere traccia dei parametri e dei valori per ogni installazione</span><span class="sxs-lookup"><span data-stu-id="2a989-110">The configuration file can be used to track the parameters and values for each installation.</span></span> <span data-ttu-id="2a989-111">e consente pertanto di verificare e controllare le installazioni.</span><span class="sxs-lookup"><span data-stu-id="2a989-111">This makes the configuration file useful for verifying and auditing the installations.</span></span>  
  
## <a name="configuration-file-structure"></a><span data-ttu-id="2a989-112">Struttura dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2a989-112">Configuration File Structure</span></span>  
 <span data-ttu-id="2a989-113">Il file ConfigurationFile.ini è un file di testo con parametri (coppia nome/valore) e commenti descrittivi.</span><span class="sxs-lookup"><span data-stu-id="2a989-113">The ConfigurationFile.ini file is a text file with parameters (name/value pair) and descriptive comments.</span></span>  
  
 <span data-ttu-id="2a989-114">Di seguito è riportato un esempio di un file ConfigurationFile.ini:</span><span class="sxs-lookup"><span data-stu-id="2a989-114">The following is an example of a ConfigurationFile.ini file:</span></span>  
  
```  
; Microsoft SQL Server Configuration file  
[OPTIONS]  
; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE.   
; This is a required parameter.   
ACTION="Install"  
; Specifies features to install, uninstall, or upgrade.   
; The list of top-level features include SQL, AS, RS, IS, and Tools.   
; The SQL feature will install the database engine, replication, and full-text.   
; The Tools feature will install Management Tools, Books online,   
; SQL Server Data Tools, and other shared components.   
FEATURES=SQL,Tools  
```  
  
#### <a name="how-to-generate-a-configuration-file"></a><span data-ttu-id="2a989-115">Modalità di generazione di un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2a989-115">How to generate a configuration file</span></span>  
  
1.  <span data-ttu-id="2a989-116">Inserire il supporto di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a989-116">Insert the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span> <span data-ttu-id="2a989-117">Nella cartella radice fare doppio clic sul file Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="2a989-117">From the root folder, double-click Setup.exe.</span></span> <span data-ttu-id="2a989-118">Per eseguire l'installazione da una condivisione di rete, individuare la cartella radice nella condivisione, quindi fare doppio clic sul file Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="2a989-118">To install from a network share, locate the root folder on the share, and then double-click Setup.exe.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2a989-119">Express Edition non crea automaticamente un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2a989-119">Express Edition setup does not create a configuration file automatically.</span></span> <span data-ttu-id="2a989-120">Il comando seguente avvia l'installazione e crea un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2a989-120">The following command will start  setup and create a configuration file.</span></span>  
    >   
    >  <span data-ttu-id="2a989-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span><span class="sxs-lookup"><span data-stu-id="2a989-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span></span>  
  
2.  <span data-ttu-id="2a989-122">Seguire la procedura guidata nella pagina **Inizio installazione** .</span><span class="sxs-lookup"><span data-stu-id="2a989-122">Follow the wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="2a989-123">Il percorso del file di configurazione viene specificato nella pagina **Inizio installazione** nella sezione relativa al percorso del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2a989-123">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span> <span data-ttu-id="2a989-124">Per ulteriori informazioni su come installare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [install SQL Server 2014 dall'installazione guidata &#40;&#41;di ](install-sql-server-from-the-installation-wizard-setup.md)installazione.</span><span class="sxs-lookup"><span data-stu-id="2a989-124">For more information about how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
3.  <span data-ttu-id="2a989-125">Annullare l'installazione senza completarla per generare il file INI.</span><span class="sxs-lookup"><span data-stu-id="2a989-125">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a989-126">L'infrastruttura del programma di installazione scrive tutti i parametri appropriati per le azioni eseguite, ad eccezione delle informazioni riservate come le password.</span><span class="sxs-lookup"><span data-stu-id="2a989-126">The setup infrastructure writes out all the appropriate parameters for the actions that were run, with the exception of sensitive information such as passwords.</span></span> <span data-ttu-id="2a989-127">Anche il parametro /IAcceptSQLServerLicenseTerms non viene scritto nel file di configurazione, di conseguenza è necessario apportare una modifica al file oppure fornire un valore al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="2a989-127">The /IAcceptSQLServerLicenseTerms parameter is also not written out to the configuration file and requires either a modification of the configuration file or a value to be supplied at the command prompt.</span></span> <span data-ttu-id="2a989-128">Per altre informazioni, vedere [Installare SQL Server 2014 dal prompt dei comandi](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="2a989-128">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span> <span data-ttu-id="2a989-129">Viene inoltre incluso un valore per i parametri booleani per cui non viene in genere fornito alcun valore attraverso il prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="2a989-129">In addition, a value is included for Boolean parameters where a value is usually not supplied through the command prompt.</span></span>  
  
## <a name="using-the-configuration-file-to-install-ssnoversion"></a><span data-ttu-id="2a989-130">Utilizzo del file di configurazione per installare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a989-130">Using the Configuration File to Install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="2a989-131">Il file di configurazione può essere utilizzato solo nelle installazioni da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="2a989-131">You can only use the configuration file on command-line installations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a989-132">Se è necessario apportare modifiche al file di configurazione, è consigliabile crearne una copia e utilizzare quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="2a989-132">If you need to make changes to the configuration file, we recommend that you make a copy and work with the copy.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-install-a-stand-alone-ssnoversion-instance"></a><span data-ttu-id="2a989-133">Modalità di utilizzo di un file di configurazione per installare un'istanza autonoma di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a989-133">How to use a configuration file to install a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance</span></span>  
  
-   <span data-ttu-id="2a989-134">Eseguire l'installazione tramite il prompt dei comandi e specificare il file ConfigurationFile.ini utilizzando il parametro *ConfigurationFile* .</span><span class="sxs-lookup"><span data-stu-id="2a989-134">Run the installation through the command prompt and supply the ConfigurationFile.ini using the *ConfigurationFile* parameter.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-prepare-and-complete-an-image-of-a-stand-alone-ssnoversion-instance-sysprep"></a><span data-ttu-id="2a989-135">Modalità di utilizzo di un file di configurazione per preparare e completare un'immagine di un'istanza autonoma di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SysPrep)</span><span class="sxs-lookup"><span data-stu-id="2a989-135">How to use a configuration file to prepare and complete an image of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (SysPrep)</span></span>  
  
1.  <span data-ttu-id="2a989-136">Per preparare una o più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e configurarle nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="2a989-136">To prepare one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and configure them on the same machine.</span></span>  
  
    -   <span data-ttu-id="2a989-137">Eseguire **Preparazione immagine di un'istanza autonoma di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** nella pagina **Avanzate** di Centro installazione e acquisire il file di configurazione della preparazione immagine.</span><span class="sxs-lookup"><span data-stu-id="2a989-137">Run **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="2a989-138">Utilizzare lo stesso file di configurazione della preparazione immagine come un modello per preparare più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a989-138">Use the same prepare image configuration file as a template to prepare more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="2a989-139">Eseguire **Completamento immagine di un'istanza autonoma predisposta di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** nella pagina **Avanzate** di Centro installazione per configurare le istanze predisposte nel computer.</span><span class="sxs-lookup"><span data-stu-id="2a989-139">Run **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center to configure a prepared instances on the machine.</span></span>  
  
2.  <span data-ttu-id="2a989-140">Per preparare un'immagine del sistema operativo comprendente un'istanza predisposta non configurata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando lo strumento SysPrep di Windows.</span><span class="sxs-lookup"><span data-stu-id="2a989-140">To prepare an image of the operating system including an unconfigured prepared instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], using Windows SysPrep tool.</span></span>  
  
    -   <span data-ttu-id="2a989-141">Eseguire **Preparazione immagine di un'istanza autonoma di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** nella pagina Avanzate di Centro installazione e acquisire il file di configurazione della preparazione immagine.</span><span class="sxs-lookup"><span data-stu-id="2a989-141">Run the **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the Advanced page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="2a989-142">Eseguire **Completamento immagine di un'istanza autonoma predisposta di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** nella pagina **Avanzate** di Centro installazione, ma annullarlo nella pagina **Inizio completamento** dopo avere acquisito il file di configurazione del completamento.</span><span class="sxs-lookup"><span data-stu-id="2a989-142">Run the **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center, but cancel it on the **Ready to Complete** page after capturing the complete configuration file.</span></span>  
  
    -   <span data-ttu-id="2a989-143">Il file di configurazione del completamento immagine può essere archiviato con l'immagine Windows per rendere automatica la configurazione delle istanze predisposte.</span><span class="sxs-lookup"><span data-stu-id="2a989-143">The complete image configuration file can be stored with the Windows image for automating the configuration of the prepared instances.</span></span>  
  
#### <a name="how-to-install-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="2a989-144">Modalità di installazione di un cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando il file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2a989-144">How to install a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="2a989-145">Opzione di installazione integrata (creazione di un cluster di failover a nodo singolo in un nodo e utilizzo di AddNode per i nodi aggiuntivi):</span><span class="sxs-lookup"><span data-stu-id="2a989-145">Integrated Install option (create a single node failover cluster on a node and for additional nodes, run AddNode on them):</span></span>  
  
    -   <span data-ttu-id="2a989-146">Eseguire l'opzione per l'installazione del cluster di failover e acquisire il file di configurazione in cui sono elencate tutte le impostazioni di installazione.</span><span class="sxs-lookup"><span data-stu-id="2a989-146">Run the "Install a Failover Cluster" option and capture the configuration file that lists all the installation settings.</span></span>  
  
    -   <span data-ttu-id="2a989-147">Eseguire l'installazione del cluster di failover da riga di comando specificando il parametro *ConfigurationFile* .</span><span class="sxs-lookup"><span data-stu-id="2a989-147">Run the command-line failover cluster install by supplying the *ConfigurationFile* parameter.</span></span>  
  
    -   <span data-ttu-id="2a989-148">In un nodo da aggiungere eseguire AddNode per acquisire il file ConfigurationFile.ini applicabile al cluster di failover esistente.</span><span class="sxs-lookup"><span data-stu-id="2a989-148">On an additional node to be added, run AddNode to capture the ConfigurationFile.ini file applicable to the existing failover cluster.</span></span>  
  
    -   <span data-ttu-id="2a989-149">Eseguire AddNode dalla riga di comando in tutti i nodi aggiuntivi per cui verrà creato il join del cluster di failover, specificando lo stesso file di configurazione utilizzando il parametro ConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="2a989-149">Run the command-line AddNode on all the additional nodes that will join the failover cluster, by supplying the same configuration file using the ConfigurationFile parameter.</span></span>  
  
2.  <span data-ttu-id="2a989-150">Opzione di installazione avanzata (preparazione del cluster di failover in tutti i nodi del cluster ed esecuzione della funzionalità di completamento nel nodo proprietario del disco condiviso al termine della preparazione):</span><span class="sxs-lookup"><span data-stu-id="2a989-150">Advanced install option (prepare failover cluster on all failover cluster nodes, then, after preparing all the nodes, run complete on the node that owns the shared disk):</span></span>  
  
    -   <span data-ttu-id="2a989-151">Eseguire **Prepara** in uno dei nodi e acquisire il file ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="2a989-151">Run **Prepare** on one of the nodes, and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="2a989-152">Specificare lo stesso file ConfigurationFile.ini al programma di installazione in tutti i nodi che verranno preparati per il cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="2a989-152">Supply the same ConfigurationFile.ini file to Setup on all the nodes that will be prepared for the failover cluster.</span></span>  
  
    -   <span data-ttu-id="2a989-153">Dopo che i nodi sono stati preparati, eseguire un'operazione di completamento del cluster di failover nel nodo proprietario del disco condiviso e acquisire il file ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="2a989-153">After all the nodes have been prepared, run a complete failover cluster operation on the node that owns the shared disk and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="2a989-154">A questo punto è possibile specificare il file ConfigurationFile.ini per completare il cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="2a989-154">You can then supply this ConfigurationFile.ini file to complete the failover cluster.</span></span>  
  
#### <a name="how-to-add-or-remove-a-node-to-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="2a989-155">Modalità di aggiunta o rimozione di un nodo a un cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando il file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2a989-155">How to add or remove a node to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
-   <span data-ttu-id="2a989-156">Se si dispone di un file di configurazione utilizzato in precedenza per aggiungere un nodo a un cluster di failover o rimuoverlo, è possibile riutilizzarlo per aggiungere o rimuovere altri nodi.</span><span class="sxs-lookup"><span data-stu-id="2a989-156">If you have a configuration file that was previously used to add a node to or remove a node from a failover cluster, you can reuse that same file to add or remove additional nodes.</span></span>  
  
#### <a name="how-to-upgrade-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="2a989-157">Modalità di aggiornamento di un cluster di failover di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando il file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2a989-157">How to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="2a989-158">Eseguire l'aggiornamento nel nodo passivo e acquisire il file ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="2a989-158">Run upgrade on the passive node and capture the ConfigurationFile.ini file.</span></span> <span data-ttu-id="2a989-159">A questo scopo è possibile eseguire l'aggiornamento effettivo oppure uscire senza avere effettuato questa operazione.</span><span class="sxs-lookup"><span data-stu-id="2a989-159">You can do this either by performing the actual upgrade, or exiting at the end without doing the actual upgrade.</span></span>  
  
2.  <span data-ttu-id="2a989-160">In tutti i nodi aggiuntivi da aggiornare specificare il file ConfigurationFile.ini per completare il processo.</span><span class="sxs-lookup"><span data-stu-id="2a989-160">On all the additional nodes to be upgraded, supply the ConfigurationFile.ini file to complete the process.</span></span>  
  
## <a name="sample-syntax"></a><span data-ttu-id="2a989-161">Sintassi di esempio</span><span class="sxs-lookup"><span data-stu-id="2a989-161">Sample Syntax</span></span>  
 <span data-ttu-id="2a989-162">Di seguito vengono riportati alcuni esempi sull'utilizzo del file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="2a989-162">Following are some examples on how to use the configuration file:</span></span>  
  
-   <span data-ttu-id="2a989-163">Per specificare il file di configurazione al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="2a989-163">To specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /ConfigurationFile=MyConfigurationFile.INI  
```  
  
-   <span data-ttu-id="2a989-164">Per specificare le password al prompt dei comandi anziché nel file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="2a989-164">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
```  
Setup.exe /SQLSVCPASSWORD="************" /AGTSVCPASSWORD="************" /ASSVCPASSWORD="************" /ISSVCPASSWORD="************" /RSSVCPASSWORD="************" /ConfigurationFile=MyConfigurationFile.INI  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a989-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a989-165">See Also</span></span>  
 <span data-ttu-id="2a989-166">[Installare SQL Server 2014 dal prompt dei comandi](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="2a989-166">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="2a989-167">[Installazione del cluster di failover di SQL Server](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span><span class="sxs-lookup"><span data-stu-id="2a989-167">[SQL Server Failover Cluster Installation](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span></span>  
 [<span data-ttu-id="2a989-168">Aggiornare un cluster di failover di SQL Server</span><span class="sxs-lookup"><span data-stu-id="2a989-168">Upgrade a SQL Server Failover Cluster</span></span>](../../sql-server/failover-clusters/windows/upgrade-a-sql-server-failover-cluster-instance.md)  
  
  
