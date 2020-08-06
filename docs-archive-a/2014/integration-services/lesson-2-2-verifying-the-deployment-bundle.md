---
title: 'Passaggio 2: Verifica del pacchetto di distribuzione | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6c13f5c9-c75e-4e52-94dc-2d2db2c578fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f452a87154175ac05a050761d8f12b6bfe61cd8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624821"
---
# <a name="step-2-verifying-the-deployment-bundle"></a><span data-ttu-id="36af8-102">Passaggio 2: Verifica del pacchetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="36af8-102">Step 2: Verifying the Deployment Bundle</span></span>
  <span data-ttu-id="36af8-103">Nella lezione 1 è stato creato il progetto Deployment Tutorial a cui sono stati aggiungi pacchetti e file ausiliari. Nell'attività precedente è stata compilata un'utilità di distribuzione per il progetto.</span><span class="sxs-lookup"><span data-stu-id="36af8-103">In lesson 1, you created the Deployment Tutorial project and added packages and ancillary files to the project; in the previous task you built a deployment utility for the project.</span></span>  
  
 <span data-ttu-id="36af8-104">In questa attività si procederà alla verifica dei contenuti del pacchetto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="36af8-104">In this task, you will verify the contents of the deployment bundle.</span></span> <span data-ttu-id="36af8-105">Quest'ultimo rappresenta la cartella che verrà copiata nel computer di destinazione e utilizzata per installare i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="36af8-105">The deployment bundle is the folder that you will copy to the destination computer and use to install packages.</span></span> <span data-ttu-id="36af8-106">Se è stato usato il valore predefinito, ovvero bin\Deployment, come percorso dell'utilità di distribuzione, il pacchetto di distribuzione si trova nella cartella Bin\Deployment all'interno della cartella Deployment Tutorial del progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36af8-106">If you used the default value-bin\Deployment-as the location of the deployment utility, the deployment bundle is the Bin\Deployment folder within the Deployment Tutorial folder in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
### <a name="to-verify-the-content-of-deployment-bundle"></a><span data-ttu-id="36af8-107">Per verificare il contenuto del pacchetto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="36af8-107">To verify the content of deployment bundle</span></span>  
  
1.  <span data-ttu-id="36af8-108">Individuare la cartella bin\Deployment nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="36af8-108">Locate the bin\Deployment folder on your computer.</span></span>  
  
2.  <span data-ttu-id="36af8-109">Verificare che siano presenti i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="36af8-109">Verify that the following files are present:</span></span>  
  
    -   <span data-ttu-id="36af8-110">DataTransfer.dtsx</span><span class="sxs-lookup"><span data-stu-id="36af8-110">DataTransfer.dtsx</span></span>  
  
    -   <span data-ttu-id="36af8-111">datatransferconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="36af8-111">datatransferconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="36af8-112">Deployment Tutorial.SSISDeploymentManifest</span><span class="sxs-lookup"><span data-stu-id="36af8-112">Deployment Tutorial.SSISDeploymentManifest</span></span>  
  
    -   <span data-ttu-id="36af8-113">LoadXMLData.dtsx</span><span class="sxs-lookup"><span data-stu-id="36af8-113">LoadXMLData.dtsx</span></span>  
  
    -   <span data-ttu-id="36af8-114">loadxmldataconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="36af8-114">loadxmldataconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="36af8-115">NewCustomers.txt</span><span class="sxs-lookup"><span data-stu-id="36af8-115">NewCustomers.txt</span></span>  
  
    -   <span data-ttu-id="36af8-116">orders.xml</span><span class="sxs-lookup"><span data-stu-id="36af8-116">orders.xml</span></span>  
  
    -   <span data-ttu-id="36af8-117">orders.xsd</span><span class="sxs-lookup"><span data-stu-id="36af8-117">orders.xsd</span></span>  
  
    -   <span data-ttu-id="36af8-118">Readme.txt</span><span class="sxs-lookup"><span data-stu-id="36af8-118">Readme.txt</span></span>  
  
3.  <span data-ttu-id="36af8-119">Fare clic con il pulsante destro del mouse su Deployment Tutorial.SSISDeploymentManifest, scegliere **Apri con**, quindi fare clic su **Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="36af8-119">Right-click Deployment Tutorial.SSISDeploymentManifest, point **to Open With**, and then click **Internet Explorer**.</span></span> <span data-ttu-id="36af8-120">È inoltre possibile aprire il file in un editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="36af8-120">You can also open the file in a text editor such as Notepad.</span></span> <span data-ttu-id="36af8-121">Il codice XML dovrebbe risultare analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="36af8-121">The XML code of the file should be the following:</span></span>  
  
     `<?xml version="1.0"?><DTSDeploymentManifest GeneratedBy="Domain\UserName" GeneratedFromProjectName="Deployment Tutorial" GeneratedDate="2006-02-24T13:29:02.6537669-08:00" AllowConfigurationChanges="true"><Package>DataTransfer.dtsx</Package><Package>LoadXMLData.dtsx</Package><ConfigurationFile>datatransferconfig.dtsconfig</ConfigurationFile><ConfigurationFile>loadxmldataconfig.dtsconfig</ConfigurationFile><MiscellaneousFile>Readme.txt</MiscellaneousFile><MiscellaneousFile>orders.xml</MiscellaneousFile><MiscellaneousFile>NewCustomers.txt</MiscellaneousFile><MiscellaneousFile>orders.xsd</MiscellaneousFile></DTSDeploymentManifest>`  
  
4.  <span data-ttu-id="36af8-122">Verificare che il valore dell' `AllowConfigurationChanges` attributo sia **true** e che il codice XML includa un `Package` elemento per ognuno dei due pacchetti, un `MiscellaneousFile` elemento per ognuno dei quattro file non pacchetto e un `ConfigurationFile` elemento per ognuno dei due file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="36af8-122">Verify that the value of the `AllowConfigurationChanges` attribute is **true** and the XML includes a `Package` element for each of the two packages, a `MiscellaneousFile` element for each of the four non-package files, and a `ConfigurationFile` element for each of the two XML configuration files.</span></span>  
  
5.  <span data-ttu-id="36af8-123">Chiudere Internet Explorer o l'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="36af8-123">Exit Internet Explorer or the text editor.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="36af8-124">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="36af8-124">Next Lesson</span></span>  
 [<span data-ttu-id="36af8-125">Lezione 3: Installazione di pacchetti</span><span class="sxs-lookup"><span data-stu-id="36af8-125">Lesson 3: Installing Packages</span></span>](../integration-services/lesson-3-install-ssis-package.md)  
  
<span data-ttu-id="36af8-126">![Integration Services icona (piccola)](media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="36af8-126">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="36af8-127">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="36af8-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="36af8-128">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="36af8-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="36af8-129">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="36af8-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
