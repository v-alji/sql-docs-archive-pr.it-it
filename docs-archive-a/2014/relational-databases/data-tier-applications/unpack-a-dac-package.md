---
title: Decompressione di un pacchetto di applicazione livello dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- wizard [DAC], unpack
- data-tier application [SQL Server], unpack
- How to [DAC], unpack
- unpack DAC
ms.assetid: 697b69b3-f157-4e22-ac4e-f65c5fc2d0ad
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ba0930f79a47696a6c9a9c1bfe028316601f64b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637888"
---
# <a name="unpack-a-dac-package"></a><span data-ttu-id="bda3b-102">Decompressione di un pacchetto di applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="bda3b-102">Unpack a DAC Package</span></span>
  <span data-ttu-id="bda3b-103">Utilizzare la finestra di dialogo per la decompressione dell'applicazione livello dati per decomprimere gli script e i file da un pacchetto di applicazioni livello dati (DAC).</span><span class="sxs-lookup"><span data-stu-id="bda3b-103">Use the Unpack Data-tier Application dialog box to unzip the scripts and files from a data-tier application (DAC) package.</span></span> <span data-ttu-id="bda3b-104">Gli script e i file vengono copiati in una cartella dove è possibile controllarli prima che il pacchetto venga utilizzato per distribuire l'applicazione del livello dati in un sistema di produzione.</span><span class="sxs-lookup"><span data-stu-id="bda3b-104">The scripts and files are placed in a folder where they can be reviewed before the package is used to deploy the DAC into a production system.</span></span> <span data-ttu-id="bda3b-105">È inoltre possibile confrontare il contenuto di un pacchetto di applicazione livello dati con il contenuto di un altro pacchetto decompresso in un'altra cartella.</span><span class="sxs-lookup"><span data-stu-id="bda3b-105">The contents of one DAC can also be compared with the contents of another package unpacked to another folder.</span></span>  
  
1.  <span data-ttu-id="bda3b-106">**Prima di iniziare:**  [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="bda3b-106">**Before you begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="bda3b-107">**Per decomprimere un'applicazione livello dati tramite la**  [Finestra di dialogo per la decompressione dell'applicazione livello dati](#UnpackDACDial), [Verifica del contenuto di un pacchetto di applicazione livello dati](#ExamDACPack)</span><span class="sxs-lookup"><span data-stu-id="bda3b-107">**To unpack a DAC, using:**  [Unpack Data-tier Application Dialog](#UnpackDACDial), [Examine the Contents of a DAC Package](#ExamDACPack)</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bda3b-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="bda3b-108">Security</span></span>  
 <span data-ttu-id="bda3b-109">È consigliabile evitare di distribuire un pacchetto di applicazione livello dati proveniente da origini sconosciute o non attendibili.</span><span class="sxs-lookup"><span data-stu-id="bda3b-109">We recommend that you do not deploy a DAC package from unknown or untrusted sources.</span></span> <span data-ttu-id="bda3b-110">Tali pacchetti DAC possono contenere codice dannoso che potrebbe eseguire codice [!INCLUDE[tsql](../../includes/tsql-md.md)] indesiderato o causare errori modificando lo schema.</span><span class="sxs-lookup"><span data-stu-id="bda3b-110">Such DACs could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema.</span></span> <span data-ttu-id="bda3b-111">Prima di utilizzare un pacchetto di applicazione livello dati proveniente da un'origine sconosciuta o non attendibile, distribuirlo in un'istanza di prova isolata del [!INCLUDE[ssDE](../../includes/ssde-md.md)], decomprimere il pacchetto di applicazione livello dati ed esaminare il codice, ad esempio stored procedure o altro codice definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="bda3b-111">Before you use a DAC from an unknown or untrusted source, deploy it on an isolated test instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], unpack the DAC and examine the code, such as stored procedures or other user-defined code.</span></span>  
  
##  <a name="unpack-data-tier-application-dialog"></a><a name="UnpackDACDial"></a> <span data-ttu-id="bda3b-112">la finestra di dialogo per la decompressione dell'applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="bda3b-112">Unpack Data-tier Application Dialog</span></span>  
 <span data-ttu-id="bda3b-113">**Per decomprimere un file del pacchetto di applicazione livello dati**</span><span class="sxs-lookup"><span data-stu-id="bda3b-113">**To Unpack a DAC Package File**</span></span>  
  
-   <span data-ttu-id="bda3b-114">In **Esplora risorse**passare al percorso di un file del pacchetto di applicazione livello dati (con estensione dacpac).</span><span class="sxs-lookup"><span data-stu-id="bda3b-114">In **Windows Explorer**, navigate to the location of a DAC package (.dacpac) file.</span></span>  
  
-   <span data-ttu-id="bda3b-115">Utilizzare uno di questi due metodi per aprire la finestra di dialogo per la decompressione dell'applicazione livello dati:</span><span class="sxs-lookup"><span data-stu-id="bda3b-115">Use one of these two methods to open the Unpack Data-tier Application dialog:</span></span>  
  
    1.  <span data-ttu-id="bda3b-116">Fare clic con il pulsante destro del mouse sul file del pacchetto di applicazione livello dati (con estensione dacpac) e scegliere **Decomprimi**.</span><span class="sxs-lookup"><span data-stu-id="bda3b-116">Right-click the DAC package (.dacpac) file and select **Unpack**.</span></span>  
  
    2.  <span data-ttu-id="bda3b-117">Fare doppio clic sul file del pacchetto di applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="bda3b-117">Double-click the DAC package file.</span></span>  
  
-   <span data-ttu-id="bda3b-118">Completare le finestre di dialogo:</span><span class="sxs-lookup"><span data-stu-id="bda3b-118">Complete the dialogs:</span></span>  
  
    -   [<span data-ttu-id="bda3b-119">Decomprimi file di pacchetto DAC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="bda3b-119">Unpack Microsoft SQL Server DAC Package File</span></span>](#Unpack)  
  
    -   [<span data-ttu-id="bda3b-120">Sfoglia cartella</span><span class="sxs-lookup"><span data-stu-id="bda3b-120">Browse for Folder</span></span>](#Browse)  
  
###  <a name="unpack-microsoft-sql-server-dac-package-file"></a><a name="Unpack"></a> <span data-ttu-id="bda3b-121">Decomprimi file di pacchetto DAC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="bda3b-121">Unpack Microsoft SQL Server DAC Package File</span></span>  
 <span data-ttu-id="bda3b-122">Utilizzare questa pagina per specificare la cartella di destinazione nella quale copiare i file decompressi, quindi eseguire l'operazione di decompressione.</span><span class="sxs-lookup"><span data-stu-id="bda3b-122">Use this page to specify the destination folder in which to place the unpacked files, and then run the unpack operation.</span></span>  
  
 <span data-ttu-id="bda3b-123">**I file verranno decompressi nella cartella seguente** : consente di specificare il percorso completo della cartella per i file decompressi.</span><span class="sxs-lookup"><span data-stu-id="bda3b-123">**Files will be unpacked to this folder:** - Specify the full path to the folder for the unpacked files.</span></span> <span data-ttu-id="bda3b-124">Se la cartella esiste e se ne conosce il percorso completo, digitare il percorso nella casella.</span><span class="sxs-lookup"><span data-stu-id="bda3b-124">If the folder exists and you know the full path, type the path in the box.</span></span> <span data-ttu-id="bda3b-125">In caso contrario, fare clic sul pulsante **Sfoglia** per passare a una cartella o crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="bda3b-125">If not, click the **Browse** button to navigate to a folder or create a new folder.</span></span>  
  
 <span data-ttu-id="bda3b-126">**Sfoglia** : apre la pagina **Sfoglia cartella** in cui è possibile scegliere una cartella spostandosi all'interno della gerarchia dei file oppure creare una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="bda3b-126">**Browse** - Opens the **Browse for Folder** page where you can choose a folder by navigating the file hierarchy, or create a new folder.</span></span>  
  
 <span data-ttu-id="bda3b-127">**Decomprimi** : avvia l'operazione di decompressione.</span><span class="sxs-lookup"><span data-stu-id="bda3b-127">**Unpack** - Starts the unpack operation.</span></span>  
  
 <span data-ttu-id="bda3b-128">**Annulla** : chiude la finestra di dialogo senza decomprimere il pacchetto di applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="bda3b-128">**Cancel** - Terminates the dialog box without unpacking the DAC package.</span></span>  
  
###  <a name="browse-for-folder"></a><a name="Browse"></a> <span data-ttu-id="bda3b-129">Sfoglia cartella</span><span class="sxs-lookup"><span data-stu-id="bda3b-129">Browse for Folder</span></span>  
 <span data-ttu-id="bda3b-130">Utilizzare questa pagina per scegliere la cartella di destinazione per l'operazione di decompressione.</span><span class="sxs-lookup"><span data-stu-id="bda3b-130">Use this page to choose the destination folder for the unpack operation.</span></span> <span data-ttu-id="bda3b-131">Facoltativamente, è inoltre possibile creare una nuova cartella.</span><span class="sxs-lookup"><span data-stu-id="bda3b-131">Optionally, you can also create a new folder.</span></span>  
  
 <span data-ttu-id="bda3b-132">**Elenco di cartelle** : visualizza la gerarchia dei file per il computer.</span><span class="sxs-lookup"><span data-stu-id="bda3b-132">**Folder list** - Displays the file hierarchy for your computer.</span></span> <span data-ttu-id="bda3b-133">Espandere i nodi per passare alla cartella nella quale decomprimere il pacchetto DAC.</span><span class="sxs-lookup"><span data-stu-id="bda3b-133">Expand the nodes to navigate to the folder in which to unpack the DAC package.</span></span> <span data-ttu-id="bda3b-134">Fare clic sulla cartella e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="bda3b-134">Click on the folder and then click **OK**.</span></span>  
  
 <span data-ttu-id="bda3b-135">**Crea nuova cartella** : apre una finestra di dialogo nella quale è possibile specificare il nome per una nuova cartella da creare nella cartella attualmente selezionata nella gerarchia di cartelle.</span><span class="sxs-lookup"><span data-stu-id="bda3b-135">**Make New Folder** - Opens a dialog in which you can specify the name for a new folder to be created in the folder you have currently selected in the folder hierarchy.</span></span>  
  
 <span data-ttu-id="bda3b-136">**OK** : imposta il percorso della cartella selezionato nella casella **I file verranno decompressi nella cartella seguente** della pagina **Decomprimi file pacchetto DAC** e torna a tale pagina.</span><span class="sxs-lookup"><span data-stu-id="bda3b-136">**OK** - Places the path to the folder you selected in the **Files will be unpacked to this folder** box of the **Unpack DAC Package File** page and returns you to that page.</span></span>  
  
 <span data-ttu-id="bda3b-137">**Annulla** : chiude la finestra di dialogo senza selezionare una cartella.</span><span class="sxs-lookup"><span data-stu-id="bda3b-137">**Cancel** - Terminates the dialog box without selecting a folder.</span></span>  
  
##  <a name="examine-the-contents-of-a-dac-package"></a><a name="ExamDACPack"></a> <span data-ttu-id="bda3b-138">la verifica del contenuto di un pacchetto di applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="bda3b-138">Examine the Contents of a DAC Package</span></span>  
 <span data-ttu-id="bda3b-139">Dopo aver decompresso il pacchetto, è possibile esaminare i file generati dalla finestra di dialogo per la **decompressione dell'applicazione livello dati** .</span><span class="sxs-lookup"><span data-stu-id="bda3b-139">After unpacking the package, you can examine the files produced by the **Unpack Data-tier Application** dialog.</span></span> <span data-ttu-id="bda3b-140">Tramite questa finestra di dialogo è possibile compilare i file seguenti nella cartella di destinazione selezionata:</span><span class="sxs-lookup"><span data-stu-id="bda3b-140">The dialog box builds the following files in the selected destination folder:</span></span>  
  
1.  <span data-ttu-id="bda3b-141">Uno script Transact-SQL contenente le istruzioni per la creazione degli oggetti definiti nell'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="bda3b-141">A Transact-SQL script that contains the statements for creating the objects defined in the DAC.</span></span> <span data-ttu-id="bda3b-142">Il nome del file è *NomeDAC*.sql, dove *NomeDAC* indica il nome del pacchetto DAC.</span><span class="sxs-lookup"><span data-stu-id="bda3b-142">The file name is *DACName*.sql, where *DACName* is the name of the DAC.</span></span>  
  
2.  <span data-ttu-id="bda3b-143">Tutti i file XML del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="bda3b-143">All XML files from the package.</span></span>  
  
3.  <span data-ttu-id="bda3b-144">Tutti i file della sezione Extra Files dell'applicazione livello dati, quali i file di pre-distribuzione o di post-distribuzione dell'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="bda3b-144">All files from the Extra Files section of the DAC, such as the DAC pre-deployment or post-deployment files.</span></span>  
  
 <span data-ttu-id="bda3b-145">Per altre informazioni, vedere [Validate a DAC Package](validate-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="bda3b-145">For more information, see [Validate a DAC Package](validate-a-dac-package.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda3b-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bda3b-146">See Also</span></span>  
 <span data-ttu-id="bda3b-147">[Applicazioni livello dati](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="bda3b-147">[Data-tier Applications](data-tier-applications.md) </span></span>  
 <span data-ttu-id="bda3b-148">[Distribuire un'applicazione livello dati](deploy-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="bda3b-148">[Deploy a Data-tier Application](deploy-a-data-tier-application.md) </span></span>  
 [<span data-ttu-id="bda3b-149">Aggiornare un'applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="bda3b-149">Upgrade a Data-tier Application</span></span>](upgrade-a-data-tier-application.md)  
  
  
