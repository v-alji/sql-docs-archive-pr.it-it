---
title: Installare Riesecuzione distribuita usando un file di configurazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3259232c-6963-4c9c-9d10-ae42aa262eef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7757cce29c2e6b3ce4f1e91fc97cbf8be02ae521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720880"
---
# <a name="install-distributed-replay-using-a-configuration-file"></a><span data-ttu-id="e7ee2-102">Installare i componenti Riesecuzione distribuita tramite un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e7ee2-102">Install Distributed Replay Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e7ee2-103">Il programma di installazione consente di generare un file di configurazione in base alle impostazioni predefinite del sistema e ai dati di input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e7ee2-103">Setup provides the ability to generate a configuration file based on user input and system defaults.</span></span> <span data-ttu-id="e7ee2-104">Se si specifica che si desidera installare gli strumenti di gestione, è possibile utilizzare il file di configurazione per distribuire i tre componenti Riesecuzione distribuita, ovvero lo strumento di amministrazione, il controller di Riesecuzione distribuita e il client Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="e7ee2-104">If you specify that you want the Management tools installed, you can use the configuration file to deploy the three Distributed Replay components (administration tool, Distributed Replay controller, and the Distributed Replay client).</span></span> <span data-ttu-id="e7ee2-105">Sono supportate le operazioni di installazione, ripristino e disinstallazione dei componenti Riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="e7ee2-105">It supports Installing, repairing, and uninstalling of the Distributed Replay components.</span></span>  
  
 <span data-ttu-id="e7ee2-106">Il programma di installazione supporta l'utilizzo del file di configurazione solo tramite la riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e7ee2-106">Setup supports the use of the configuration file only through the command-line.</span></span> <span data-ttu-id="e7ee2-107">L'ordine di elaborazione dei parametri durante l'utilizzo del file di configurazione viene indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e7ee2-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="e7ee2-108">Il file di configurazione sovrascrive le impostazioni predefinite in un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e7ee2-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="e7ee2-109">I valori della riga di comando sovrascrivono quelli presenti nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e7ee2-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="e7ee2-110">Per ulteriori informazioni sull'utilizzo di un file di configurazione, vedere [Install SQL Server 2014 using a Configuration file](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="e7ee2-110">For more information about how to use a configuration file, see [Install SQL Server 2014 Using a Configuration File](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e7ee2-111">Dopo aver installato i componenti Riesecuzione distribuita, è necessario creare regole del firewall nei computer controller e client e concedere a ogni computer client autorizzazioni nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e7ee2-111">After you install Distributed Replay you must create firewall rules on the controller and client computers, and grant each client computer permissions on the target server.</span></span> <span data-ttu-id="e7ee2-112">Per altre informazioni, vedere [Completare i passaggi successivi all'installazione](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span><span class="sxs-lookup"><span data-stu-id="e7ee2-112">For more information, see [Complete the Post-Installation Steps](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span></span>  
  
### <a name="to-generate-a-configuration-file"></a><span data-ttu-id="e7ee2-113">Per generare un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e7ee2-113">To generate a configuration file</span></span>  
  
1.  <span data-ttu-id="e7ee2-114">Seguire l'Installazione guidata nella pagina **Inizio installazione** .</span><span class="sxs-lookup"><span data-stu-id="e7ee2-114">Follow the Setup wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="e7ee2-115">Il percorso del file di configurazione viene specificato nella pagina **Inizio installazione** nella sezione relativa al percorso del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e7ee2-115">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span>  
  
2.  <span data-ttu-id="e7ee2-116">Annullare l'installazione senza completarla per generare il file INI.</span><span class="sxs-lookup"><span data-stu-id="e7ee2-116">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
### <a name="to-install-distributed-replay-using-the-configuration-file"></a><span data-ttu-id="e7ee2-117">Per installare i componenti Riesecuzione distribuita tramite il file di configurazione</span><span class="sxs-lookup"><span data-stu-id="e7ee2-117">To Install Distributed Replay Using the Configuration File</span></span>  
  
-   <span data-ttu-id="e7ee2-118">Eseguire l'installazione tramite il prompt dei comandi e specificare il file ConfigurationFile.ini utilizzando il parametro ConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="e7ee2-118">Run the installation through the command prompt and supply the ConfigurationFile.ini using the ConfigurationFile parameter.</span></span>  
  
 <span data-ttu-id="e7ee2-119">**Sintassi di esempio**</span><span class="sxs-lookup"><span data-stu-id="e7ee2-119">**Sample Syntax**</span></span>  
  
 <span data-ttu-id="e7ee2-120">Di seguito viene fornito un esempio di come specificare il file di configurazione al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="e7ee2-120">Following is an example on how to specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /CTLRSVCPASSWORD="ctlrsvcpswd" /CLTSVCPASSWORD="cltsvcpswd" / ConfigurationFile=ConfigurationFile.INI\  
```  
  
> [!NOTE]  
>  <span data-ttu-id="e7ee2-121">È necessario specificare entrambe le password nella riga di comando perché non è possibile configurarle nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e7ee2-121">You must specify both passwords in the command line because you cannot configure them in the configuration file.</span></span>  
  
  
