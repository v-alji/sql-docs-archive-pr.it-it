---
title: "Procedura: Distribuire un'estensione per l'elaborazione dati in Progettazione report | Microsoft Docs"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: 3614e601-004e-4a16-8388-836ffd67e9dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56bd56e9d8eeeeff1781f22b42cf0eb1ce706fa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725279"
---
# <a name="how-to-deploy-a-data-processing-extension-to-report-designer"></a><span data-ttu-id="1f895-102">Procedura: Distribuire un'estensione per l'elaborazione dati in Progettazione report</span><span class="sxs-lookup"><span data-stu-id="1f895-102">How to: Deploy a Data Processing Extension to Report Designer</span></span>
  <span data-ttu-id="1f895-103">In Progettazione report vengono utilizzate le estensioni per l'elaborazione dati per il recupero e l'elaborazione dei dati durante la progettazione dei report.</span><span class="sxs-lookup"><span data-stu-id="1f895-103">Report Designer uses data processing extensions for retrieving and processing data while you are designing reports.</span></span> <span data-ttu-id="1f895-104">È necessario distribuire l'assembly di estensioni per l'elaborazione dati in Progettazione report come assembly privato.</span><span class="sxs-lookup"><span data-stu-id="1f895-104">You should deploy your data processing extension assembly to Report Designer as a private assembly.</span></span> <span data-ttu-id="1f895-105">È inoltre necessario immettere una voce nel file di configurazione di Progettazione report, RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="1f895-105">You also need to make an entry in the Report Designer configuration file, RSReportDesigner.config.</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="1f895-106">Per distribuire un assembly dell'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="1f895-106">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="1f895-107">Copiare l'assembly dal percorso di gestione temporanea nella directory di Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="1f895-107">Copy your assembly from your staging location to the Report Designer directory.</span></span> <span data-ttu-id="1f895-108">Il percorso predefinito della directory di Progettazione report è C:\Programmi\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="1f895-108">The default location of the Report Designer directory is C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span>  
  
2.  <span data-ttu-id="1f895-109">Dopo aver copiato il file di assembly, aprire il file RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="1f895-109">After the assembly file is copied, open the RSReportDesigner.config file.</span></span> <span data-ttu-id="1f895-110">Anche questo file si trova nella directory di Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="1f895-110">The RSReportDesigner.config file is also located in the Report Designer directory.</span></span> <span data-ttu-id="1f895-111">È necessario immettere una voce nel file di configurazione per il file di assembly dell'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="1f895-111">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="1f895-112">È possibile aprire il file di configurazione con [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o con un semplice editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="1f895-112">You can open the configuration file with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or with a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="1f895-113">Individuare l'elemento **Data** nel file RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="1f895-113">Locate the **Data** element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="1f895-114">È necessario immettere una voce per l'estensione per l'elaborazione dati appena creata nel percorso seguente:</span><span class="sxs-lookup"><span data-stu-id="1f895-114">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="1f895-115">Aggiungere una voce per l'estensione per l'elaborazione dati che includa un elemento **Extension** con i valori per gli `Name` `Type` attributi, e `Visible` .</span><span class="sxs-lookup"><span data-stu-id="1f895-115">Add an entry for your data processing extension which includes an **Extension** element with values for the `Name`, `Type`, and `Visible` attributes.</span></span> <span data-ttu-id="1f895-116">La voce può essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="1f895-116">Your entry might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="1f895-117">Il valore per `Name` è il nome univoco dell'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="1f895-117">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="1f895-118">Il valore per `Type` è un elenco delimitato da virgole che include una voce per lo spazio dei nomi completo della classe che implementa le interfacce <xref:Microsoft.ReportingServices.Interfaces.IExtension> e <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection>, seguito dal nome dell'assembly, senza l'estensione dll.</span><span class="sxs-lookup"><span data-stu-id="1f895-118">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="1f895-119">Per impostazione predefinita, le estensioni per l'elaborazione dati sono visibili.</span><span class="sxs-lookup"><span data-stu-id="1f895-119">By default, data processing extensions are visible.</span></span> <span data-ttu-id="1f895-120">Per nascondere un'estensione dalle interfacce utente, ad esempio Progettazione report, aggiungere un `Visible` attributo all'elemento **Extension** e impostarlo su `false` .</span><span class="sxs-lookup"><span data-stu-id="1f895-120">To hide an extension from user interfaces, such as Report Designer, add a `Visible` attribute to the **Extension** element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="1f895-121">Aggiungere infine un gruppo di codice per l'assembly personalizzato che conceda l'autorizzazione **FullTrust** per l'estensione.</span><span class="sxs-lookup"><span data-stu-id="1f895-121">Finally, add a code group for your custom assembly that grants **FullTrust** permission for your extension.</span></span> <span data-ttu-id="1f895-122">A tale scopo, aggiungere il gruppo di codice al file rspreviewpolicy.config che, per impostazione predefinita, si trova in C:\Programmi\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="1f895-122">You do this by adding the code group to the rspreviewpolicy.config file located by default in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span> <span data-ttu-id="1f895-123">Il gruppo di codice può essere simile a quanto riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1f895-123">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="1f895-124">L'appartenenza URL è solo una delle diverse condizioni di appartenenza selezionabili per l'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="1f895-124">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="1f895-125">Per altre informazioni sulla sicurezza dall'accesso di codice in [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)], vedere [Sviluppo sicuro &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span><span class="sxs-lookup"><span data-stu-id="1f895-125">For more information about code access security in [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="generic-query-designer"></a><span data-ttu-id="1f895-126">Progettazione query standard</span><span class="sxs-lookup"><span data-stu-id="1f895-126">Generic Query Designer</span></span>  
 <span data-ttu-id="1f895-127">In Progettazione report è disponibile una finestra Progettazione query standard che è possibile utilizzare con le estensioni per l'elaborazione dati personalizzate.</span><span class="sxs-lookup"><span data-stu-id="1f895-127">Report Designer provides a generic query designer that you can use with custom data processing extensions.</span></span> <span data-ttu-id="1f895-128">Questa finestra di progettazione è costituita da due riquadri, uno per le query e uno per i risultati.</span><span class="sxs-lookup"><span data-stu-id="1f895-128">This designer consists of two panes: a query pane and a results pane.</span></span> <span data-ttu-id="1f895-129">È possibile utilizzare la finestra Progettazione query standard per scrivere query non supportate dall'interfaccia grafica.</span><span class="sxs-lookup"><span data-stu-id="1f895-129">You can use the generic designer to write queries that are not supported by the graphical interface.</span></span> <span data-ttu-id="1f895-130">Diversamente dalla finestra Progettazione query con interfaccia grafica, l'interfaccia standard di Progettazione query non controlla la sintassi della query né ristruttura la query.</span><span class="sxs-lookup"><span data-stu-id="1f895-130">Unlike the graphical query designer, the generic query designer does not check query syntax or restructure the query.</span></span>  
  
#### <a name="to-enable-the-generic-query-designer-for-a-custom-extension"></a><span data-ttu-id="1f895-131">Per abilitare la finestra Progettazione query standard per un'estensione personalizzata</span><span class="sxs-lookup"><span data-stu-id="1f895-131">To enable the generic query designer for a custom extension</span></span>  
  
-   <span data-ttu-id="1f895-132">Aggiungere la voce seguente al file RSReportDesigner.config nell'elemento della **finestra di progettazione** , sostituendo l' `Name` attributo con il nome specificato nelle voci precedenti.</span><span class="sxs-lookup"><span data-stu-id="1f895-132">Add the following entry to the RSReportDesigner.config file under the **Designer** element, replacing the `Name` attribute with the name that you provided in previous entries.</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="1f895-133">Verifica della distribuzione</span><span class="sxs-lookup"><span data-stu-id="1f895-133">Verifying the Deployment</span></span>  
 <span data-ttu-id="1f895-134">Per poter verificare la distribuzione, è necessario chiudere tutte le istanze di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="1f895-134">Before you can verify deployment, you must close all instances of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] on your local computer.</span></span> <span data-ttu-id="1f895-135">Dopo aver chiuso tutte le sessioni correnti, è possibile verificare se l'estensione per l'elaborazione dati è stata distribuita correttamente in Progettazione report creando un nuovo progetto report in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1f895-135">After you have ended all current sessions, you can verify whether your data processing extension was deployed successfully to Report Designer by creating a new report project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="1f895-136">Quando si crea un nuovo set di dati per il report, l'estensione dovrebbe essere inclusa nell'elenco dei tipi di origini dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="1f895-136">Your extension should be included in the list of available data source types when you create a new data set for your report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f895-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f895-137">See Also</span></span>  
 <span data-ttu-id="1f895-138">[Distribuzione di un'estensione per l'elaborazione dati](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="1f895-138">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="1f895-139">[Estensioni di Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="1f895-139">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="1f895-140">[Implementazione di un'estensione per l'elaborazione dati](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="1f895-140">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="1f895-141">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1f895-141">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
