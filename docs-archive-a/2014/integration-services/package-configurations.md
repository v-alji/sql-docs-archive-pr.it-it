---
title: Configurazioni pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package configuration syntax [Integration Services]
- SQL Server Integration Services packages, configurations
- SSIS packages, configurations
- XML [Integration Services]
- Integration Services packages, configurations
- configuration syntax [Integration Services]
- indirect configurations [Integration Services]
- configurations [Integration Services]
- direct configurations [Integration Services]
- packages [Integration Services], configurations
ms.assetid: d20e0311-1fc9-4ddc-a381-6d127cf11b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d22dbfedcf4cf7084e1667586f9774926f3b2a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637987"
---
# <a name="package-configurations"></a><span data-ttu-id="45066-102">SSIS</span><span class="sxs-lookup"><span data-stu-id="45066-102">Package Configurations</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="45066-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] offre configurazioni di pacchetto che è possibile usare per aggiornare i valori delle proprietà in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="45066-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides package configurations that you can use to update the values of properties at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45066-104">Le configurazioni sono disponibili per il modello di distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="45066-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="45066-105">I parametri vengono utilizzati al posto delle configurazioni per il modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="45066-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="45066-106">Con il modello di distribuzione del progetto è possibile distribuire i progetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] al server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45066-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="45066-107">Per altre informazioni sui modelli di distribuzione, vedere [Distribuzione di progetti e pacchetti](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="45066-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="45066-108">Una configurazione è una coppia proprietà/valore che viene aggiunta a un pacchetto completo.</span><span class="sxs-lookup"><span data-stu-id="45066-108">A configuration is a property/value pair that you add to a completed package.</span></span> <span data-ttu-id="45066-109">In genere, si crea un pacchetto, si impostano le proprietà per gli oggetti di pacchetto durante lo sviluppo del pacchetto e quindi si aggiunge la configurazione al pacchetto.</span><span class="sxs-lookup"><span data-stu-id="45066-109">Typically, you create a package set properties on the package objects during package development, and then add the configuration to the package.</span></span> <span data-ttu-id="45066-110">Quando il pacchetto viene eseguito, ottiene i nuovi valori della proprietà dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="45066-110">When the package runs, it gets the new values of the property from the configuration.</span></span> <span data-ttu-id="45066-111">Utilizzando ad esempio una configurazione, è possibile modificare la stringa di connessione di una gestione connessione o aggiornare il valore di una variabile.</span><span class="sxs-lookup"><span data-stu-id="45066-111">For example, by using a configuration, you can change the connection string of a connection manager, or update the value of a variable.</span></span>  
  
 <span data-ttu-id="45066-112">Le configurazioni di pacchetto offrono i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="45066-112">Package configurations provide the following benefits:</span></span>  
  
-   <span data-ttu-id="45066-113">Le configurazioni semplificano lo spostamento di pacchetti dall'ambiente di sviluppo all'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="45066-113">Configurations make it easier to move packages from a development environment to a production environment.</span></span> <span data-ttu-id="45066-114">Tramite una configurazione è ad esempio possibile aggiornare il percorso di un file di origine o modificare il nome di un database o di un server.</span><span class="sxs-lookup"><span data-stu-id="45066-114">For example, a configuration can update the path of a source file, or change the name of a database or server.</span></span>  
  
-   <span data-ttu-id="45066-115">Le configurazioni risultano utili per la distribuzione di pacchetti in più server diversi.</span><span class="sxs-lookup"><span data-stu-id="45066-115">Configurations are useful when you deploy packages to many different servers.</span></span> <span data-ttu-id="45066-116">La configurazione di ogni pacchetto distribuito può ad esempio includere una variabile che specifica un diverso valore di spazio su disco. Se lo spazio su disco disponibile non soddisfa tale valore, il pacchetto non verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="45066-116">For example, a variable in the configuration for each deployed package can contain a different disk space value, and if the available disk space does not meet this value, the package does not run.</span></span>  
  
-   <span data-ttu-id="45066-117">Le configurazioni rendono i pacchetti più flessibili.</span><span class="sxs-lookup"><span data-stu-id="45066-117">Configurations make packages more flexible.</span></span> <span data-ttu-id="45066-118">Una configurazione, ad esempio, può aggiornare il valore di una variabile utilizzata in un'espressione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="45066-118">For example, a configuration can update the value of a variable that is used in a property expression.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="45066-119">supporta diversi metodi di archiviazione delle configurazioni di pacchetto, ad esempio file XML, tabelle di un database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e variabili di ambiente e di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="45066-119">supports several different methods of storing package configurations, such as XML files, tables in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, and environment and package variables.</span></span>  
  
 <span data-ttu-id="45066-120">Ogni configurazione corrisponde a una coppia proprietà/valore.</span><span class="sxs-lookup"><span data-stu-id="45066-120">Each configuration is a property/value pair.</span></span> <span data-ttu-id="45066-121">Il file di configurazione XML e i tipi di configurazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] possono includere più configurazioni.</span><span class="sxs-lookup"><span data-stu-id="45066-121">The XML configuration file and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration types can include multiple configurations.</span></span>  
  
 <span data-ttu-id="45066-122">Le configurazioni vengono incluse quando si crea un'utilità di distribuzione per l'installazione di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="45066-122">The configurations are included when you create a package deployment utility for installing packages.</span></span> <span data-ttu-id="45066-123">Quando si installano i pacchetti, le configurazioni possono venire aggiornate in un passaggio dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="45066-123">When you install the packages, the configurations can be updated as a step in the package installation.</span></span>  
  
## <a name="understanding-how-package-configurations-are-applied-at-run-time"></a><span data-ttu-id="45066-124">Informazioni sull'applicazione delle configurazioni dei pacchetti in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="45066-124">Understanding How Package Configurations Are Applied at Run Time</span></span>  
 <span data-ttu-id="45066-125">Quando si usa l'utilità del prompt dei comandi **dtexec** (dtexec.exe) per eseguire un pacchetto distribuito, le configurazioni di pacchetto vengono applicate due volte,</span><span class="sxs-lookup"><span data-stu-id="45066-125">When you use the **dtexec** command prompt utility (dtexec.exe) to run a deployed package, the utility applies package configurations twice.</span></span> <span data-ttu-id="45066-126">ovvero prima e dopo l'applicazione delle opzioni specificate nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="45066-126">The utility applies configurations both before and after it applies the options that you specified on command line.</span></span>  
  
 <span data-ttu-id="45066-127">Durante il caricamento e l'esecuzione del pacchetto da parte dell'utilità, gli eventi si verificano nel seguente ordine:</span><span class="sxs-lookup"><span data-stu-id="45066-127">As the utility loads and runs the package, events occur in the following order:</span></span>  
  
1.  <span data-ttu-id="45066-128">Il pacchetto viene caricato con l'utilità **dtexec** .</span><span class="sxs-lookup"><span data-stu-id="45066-128">The **dtexec** utility loads the package.</span></span>  
  
2.  <span data-ttu-id="45066-129">L'utilità consente di applicare le configurazioni specificate nel pacchetto in fase di progettazione, nell'ordine indicato nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="45066-129">The utility applies the configurations that were specified in the package at design time and in the order that is specified in the package.</span></span> <span data-ttu-id="45066-130">L'unica eccezione è rappresentata dalle configurazioni Variabile pacchetto padre,</span><span class="sxs-lookup"><span data-stu-id="45066-130">(The one exception to this is the Parent Package Variables configurations.</span></span> <span data-ttu-id="45066-131">le quali vengono applicate dall'utilità solo una volta e in una fase successiva del processo.</span><span class="sxs-lookup"><span data-stu-id="45066-131">The utility applies these configurations only once and later in the process.)</span></span>  
  
3.  <span data-ttu-id="45066-132">L'utilità applica quindi le opzioni specificate nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="45066-132">The utility then applies any options that you specified on the command line.</span></span>  
  
4.  <span data-ttu-id="45066-133">A questo punto l'utilità ricarica le configurazioni specificate nel pacchetto in fase di progettazione, nell'ordine indicato nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="45066-133">The utility then reloads the configurations that were specified in the package at design time and in the order specified in the package.</span></span> <span data-ttu-id="45066-134">L'unica eccezione a questa regola è di nuovo rappresentata dalle configurazioni Variabile pacchetto padre.</span><span class="sxs-lookup"><span data-stu-id="45066-134">(Again, the exception to this rule is the Parent Package Variables configurations).</span></span> <span data-ttu-id="45066-135">L'utilità utilizza quindi le opzioni della riga di comando specificate per ricaricare le configurazioni.</span><span class="sxs-lookup"><span data-stu-id="45066-135">The utility uses any command-line options that were specified to reload the configurations.</span></span> <span data-ttu-id="45066-136">È pertanto possibile che vengano ricaricati valori diversi da posizioni differenti.</span><span class="sxs-lookup"><span data-stu-id="45066-136">Therefore, different values might be reloaded from a different location.</span></span>  
  
5.  <span data-ttu-id="45066-137">L'utilità consente di applicare le configurazioni Variabile pacchetto padre.</span><span class="sxs-lookup"><span data-stu-id="45066-137">The utility applies the Parent Package Variable configurations.</span></span>  
  
6.  <span data-ttu-id="45066-138">L'utilità consente l'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="45066-138">The utility runs the package.</span></span>  
  
 <span data-ttu-id="45066-139">Il modo in cui l'utilità **dtexec** applica le configurazioni influisce sulle seguenti opzioni della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="45066-139">The way in which the **dtexec** utility applies configurations affects the following command-line options:</span></span>  
  
-   <span data-ttu-id="45066-140">È possibile usare l'opzione **/Connection** o **/Set** in fase di esecuzione per caricare le configurazioni di pacchetto da una posizione diversa da quella specificata in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="45066-140">You can use the **/Connection** or **/Set** option at run time to load package configurations from a location other than the location that you specified at design time.</span></span>  
  
-   <span data-ttu-id="45066-141">È possibile usare l'opzione **/ConfigFile** per caricare configurazioni aggiuntive non specificate in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="45066-141">You can use the **/ConfigFile** option to load additional configurations that you did not specify at design time.</span></span>  
  
 <span data-ttu-id="45066-142">Tali opzioni della riga di comando presentano tuttavia alcune restrizioni.</span><span class="sxs-lookup"><span data-stu-id="45066-142">However, these command-line options do have some restrictions:</span></span>  
  
-   <span data-ttu-id="45066-143">Non è possibile usare l'opzione **/Set** o **/Connection** per ignorare valori singoli impostati anche da una configurazione.</span><span class="sxs-lookup"><span data-stu-id="45066-143">You cannot use the **/Set** or the **/Connection** option to override single values that are also set by a configuration.</span></span>  
  
-   <span data-ttu-id="45066-144">Non è possibile usare l'opzione **/ConfigFile** per caricare configurazioni che sostituiscono quelle specificate in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="45066-144">You cannot use the **/ConfigFile** option to load configurations that replace the configurations that you specified at design time.</span></span>  
  
 <span data-ttu-id="45066-145">Per ulteriori informazioni su queste opzioni e sulla differenza tra il comportamento di queste opzioni e le [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] versioni precedenti, vedere [modifiche del comportamento delle funzionalità di Integration Services in SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="45066-145">For more information about these options, and how the behavior of these options differs between [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] and earlier versions, see [Behavior Changes to Integration Services Features in SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span></span>  
  
## <a name="package-configuration-types"></a><span data-ttu-id="45066-146">Tipi di configurazioni di pacchetto</span><span class="sxs-lookup"><span data-stu-id="45066-146">Package Configuration Types</span></span>  
 <span data-ttu-id="45066-147">Nella tabella seguente vengono descritti i tipi di configurazione di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="45066-147">The following table describes the package configuration types.</span></span>  
  
|<span data-ttu-id="45066-148">Type</span><span class="sxs-lookup"><span data-stu-id="45066-148">Type</span></span>|<span data-ttu-id="45066-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45066-149">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="45066-150">File di configurazione XML</span><span class="sxs-lookup"><span data-stu-id="45066-150">XML configuration file</span></span>|<span data-ttu-id="45066-151">Le configurazioni sono incluse in un file XML.</span><span class="sxs-lookup"><span data-stu-id="45066-151">An XML file contains the configurations.</span></span> <span data-ttu-id="45066-152">Il file può includere più configurazioni.</span><span class="sxs-lookup"><span data-stu-id="45066-152">The XML file can include multiple configurations.</span></span>|  
|<span data-ttu-id="45066-153">Variabile di ambiente</span><span class="sxs-lookup"><span data-stu-id="45066-153">Environment variable</span></span>|<span data-ttu-id="45066-154">La configurazione è contenuta in una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="45066-154">An environment variable contains the configuration.</span></span>|  
|<span data-ttu-id="45066-155">Voce del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="45066-155">Registry entry</span></span>|<span data-ttu-id="45066-156">La configurazione è inclusa in una voce del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="45066-156">A Registry entry contains the configuration.</span></span>|  
|<span data-ttu-id="45066-157">Variabile pacchetto padre</span><span class="sxs-lookup"><span data-stu-id="45066-157">Parent package variable</span></span>|<span data-ttu-id="45066-158">La configurazione è contenuta in una variabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="45066-158">A variable in the package contains the configuration.</span></span> <span data-ttu-id="45066-159">Questo tipo di configurazione viene in genere utilizzato per l'aggiornamento di proprietà in pacchetti figlio.</span><span class="sxs-lookup"><span data-stu-id="45066-159">This configuration type is typically used to update properties in child packages.</span></span>|  
|<span data-ttu-id="45066-160">Tabella [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45066-160">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table</span></span>|<span data-ttu-id="45066-161">La configurazione è inclusa in una tabella di un database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45066-161">A table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database contains the configuration.</span></span> <span data-ttu-id="45066-162">La tabella può includere più configurazioni.</span><span class="sxs-lookup"><span data-stu-id="45066-162">The table can include multiple configurations.</span></span>|  
  
### <a name="xml-configuration-files"></a><span data-ttu-id="45066-163">File di configurazione XML</span><span class="sxs-lookup"><span data-stu-id="45066-163">XML Configuration Files</span></span>  
 <span data-ttu-id="45066-164">Se si seleziona il tipo di configurazione **File di configurazione XML** è possibile creare un nuovo file di configurazione, riusare un file esistente e aggiungere nuove configurazioni oppure riusare un file esistente sovrascrivendone il contenuto.</span><span class="sxs-lookup"><span data-stu-id="45066-164">If you select the **XML configuration file** configuration type, you can create a new configuration file, reuse an existing file and add new configurations, or reuse an existing file but overwrite existing file content.</span></span>  
  
 <span data-ttu-id="45066-165">Un file di configurazione XML è suddiviso in due sezioni:</span><span class="sxs-lookup"><span data-stu-id="45066-165">An XML configuration file includes two sections:</span></span>  
  
-   <span data-ttu-id="45066-166">Un'intestazione contenente informazioni sul file.</span><span class="sxs-lookup"><span data-stu-id="45066-166">A heading that contains information about the configuration file.</span></span> <span data-ttu-id="45066-167">Questa sezione include attributi quali la data di creazione del file e il nome dell'utente che ha generato il file.</span><span class="sxs-lookup"><span data-stu-id="45066-167">This element includes attributes such as when the file was created and the name of the person who generated the file.</span></span>  
  
-   <span data-ttu-id="45066-168">Elementi di configurazione contenenti informazioni su ogni configurazione.</span><span class="sxs-lookup"><span data-stu-id="45066-168">Configuration elements that contain information about each configuration.</span></span> <span data-ttu-id="45066-169">Questa sezione include attributi quali il percorso e il valore configurato di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="45066-169">This element includes attributes such as the property path and the configured value of a property.</span></span>  
  
 <span data-ttu-id="45066-170">Nel codice XML seguente viene illustrata la sintassi di un file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="45066-170">The following XML code demonstrates the syntax of an XML configuration file.</span></span> <span data-ttu-id="45066-171">Nell'esempio viene illustrata una configurazione per la proprietà Value di una variabile di tipo Integer denominata `MyVar`.</span><span class="sxs-lookup"><span data-stu-id="45066-171">This example shows a configuration for the Value property of an integer variable named `MyVar`.</span></span>  
  
```  
<?xml version="1.0"?>  
<DTSConfiguration>  
   <DTSConfigurationHeading>  
      <DTSConfigurationFileInfo  
          GeneratedBy="DomainName\UserName"  
          GeneratedFromPackageName="Package"  
          GeneratedFromPackageID="{2AF06766-817A-4E28-9878-0DE37A150648}"  
          GeneratedDate="2/01/2005 5:58:09 PM"/>  
   </DTSConfigurationHeading>  
   <Configuration ConfiguredType="Property" Path="\Package.Variables[User::MyVar].Value" ValueType="Int32">  
      <ConfiguredValue>0</ConfiguredValue>  
   </Configuration>  
</DTSConfiguration>  
  
```  
  
### <a name="registry-entry"></a><span data-ttu-id="45066-172">Voce del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="45066-172">Registry Entry</span></span>  
 <span data-ttu-id="45066-173">Se si desidera utilizzare una voce del Registro di sistema per archiviare la configurazione, è possibile utilizzare una chiave esistente oppure crearne una nuova in HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="45066-173">If you want to use a Registry entry to store the configuration, you can either use an existing key or create a new key in HKEY_CURRENT_USER.</span></span> <span data-ttu-id="45066-174">La chiave del Registro di sistema usata deve contenere un valore denominato `Value`.</span><span class="sxs-lookup"><span data-stu-id="45066-174">The Registry key that you use must have a value named `Value`.</span></span> <span data-ttu-id="45066-175">Il valore può essere un DWORD o una stringa.</span><span class="sxs-lookup"><span data-stu-id="45066-175">The value can be a DWORD or a string.</span></span>  
  
 <span data-ttu-id="45066-176">Se si seleziona il tipo di configurazione **Voce del Registro di sistema** , è necessario digitare il nome della chiave del Registro di sistema nella casella Voce del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="45066-176">If you select the **Registry entry** configuration type, you type the name of the Registry key in the Registry entry box.</span></span> <span data-ttu-id="45066-177">Il formato è \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="45066-177">The format is \<registry key>.</span></span> <span data-ttu-id="45066-178">Se si vuole usare una chiave del Registro di sistema che non si trova nella radice HKEY_CURRENT_USER, per identificare la chiave usare il formato \<Registry key\registry key\\...>.</span><span class="sxs-lookup"><span data-stu-id="45066-178">If you want to use a Registry key that is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span> <span data-ttu-id="45066-179">Per usare la chiave MyPackage in SSISPackages, ad esempio, digitare `SSISPackages\MyPackage`.</span><span class="sxs-lookup"><span data-stu-id="45066-179">For example, to use the MyPackage key located in SSISPackages, type `SSISPackages\MyPackage`.</span></span>  
  
### <a name="sql-server"></a><span data-ttu-id="45066-180">SQL Server</span><span class="sxs-lookup"><span data-stu-id="45066-180">SQL Server</span></span>  
 <span data-ttu-id="45066-181">Se si seleziona il tipo di configurazione **SQL Server** , è necessario specificare la connessione al database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in cui si desidera archiviare le configurazioni.</span><span class="sxs-lookup"><span data-stu-id="45066-181">If you select the **SQL Server** configuration type, you specify the connection to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database in which you want to store the configurations.</span></span> <span data-ttu-id="45066-182">È possibile salvare le configurazioni in una tabella esistente oppure creare una nuova tabella nel database specificato.</span><span class="sxs-lookup"><span data-stu-id="45066-182">You can save the configurations to an existing table or create a new table in the specified database.</span></span>  
  
 <span data-ttu-id="45066-183">L'istruzione SQL seguente illustra l'istruzione CREATE TABLE predefinita della Configurazione guidata pacchetto.</span><span class="sxs-lookup"><span data-stu-id="45066-183">The following SQL statement shows the default CREATE TABLE statement that the Package Configuration Wizard provides.</span></span>  
  
```  
CREATE TABLE [dbo].[SSIS Configurations]  
(  
ConfigurationFilter NVARCHAR(255) NOT NULL,  
ConfiguredValue NVARCHAR(255) NULL,  
PackagePath NVARCHAR(255) NOT NULL,  
ConfiguredValueType NVARCHAR(20) NOT NULL  
)  
  
```  
  
 <span data-ttu-id="45066-184">Il nome specificato per la configurazione corrisponde al valore archiviato nella colonna **ConfigurationFilter** .</span><span class="sxs-lookup"><span data-stu-id="45066-184">The name that you provide for the configuration is the value stored in the **ConfigurationFilter** column.</span></span>  
  
## <a name="direct-and-indirect-configurations"></a><span data-ttu-id="45066-185">Configurazioni dirette e indirette</span><span class="sxs-lookup"><span data-stu-id="45066-185">Direct and Indirect Configurations</span></span>  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="45066-186">dispone di configurazioni dirette e indirette.</span><span class="sxs-lookup"><span data-stu-id="45066-186">provides direct and indirect configurations.</span></span> <span data-ttu-id="45066-187">Se le configurazioni vengono specificate in modo diretto, in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] viene creato un collegamento diretto tra l'elemento di configurazione e la proprietà dell'oggetto di pacchetto.</span><span class="sxs-lookup"><span data-stu-id="45066-187">If you specify configurations directly, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] creates a direct link between the configuration item and the package object property.</span></span> <span data-ttu-id="45066-188">È consigliabile utilizzare le configurazioni dirette quando la posizione dell'origine non cambia.</span><span class="sxs-lookup"><span data-stu-id="45066-188">Direct configurations are a better choice when the location of the source does not change.</span></span> <span data-ttu-id="45066-189">Ad esempio, se per tutte le distribuzioni di pacchetto viene utilizzato sempre lo stesso percorso di file, è possibile specificare un file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="45066-189">For example, if you are sure that all deployments in the package use the same file path, you can specify an XML configuration file.</span></span>  
  
 <span data-ttu-id="45066-190">Nelle configurazioni indirette vengono utilizzate variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="45066-190">Indirect configurations use environment variables.</span></span> <span data-ttu-id="45066-191">Anziché specificare l'impostazione di configurazione in modo diretto, la configurazione punta a una variabile di ambiente, la quale contiene il valore di configurazione.</span><span class="sxs-lookup"><span data-stu-id="45066-191">Instead of specifying the configuration setting directly, the configuration points to an environment variable, which in turn contains the configuration value.</span></span> <span data-ttu-id="45066-192">È consigliabile utilizzare le configurazioni indirette quando la posizione della configurazione può essere diversa nelle varie distribuzioni di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="45066-192">Using indirect configurations is a better choice when the location of the configuration can change for each deployment of a package.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="45066-193">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="45066-193">Related Tasks</span></span>  
 [<span data-ttu-id="45066-194">Creazione di configurazioni dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="45066-194">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
## <a name="related-content"></a><span data-ttu-id="45066-195">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="45066-195">Related Content</span></span>  
  
-   <span data-ttu-id="45066-196">Articolo tecnico [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643)(Informazioni sulle configurazioni dei pacchetti di Integration Services) sul sito Web msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="45066-196">Technical article, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="45066-197">Intervento nel Blog sulla [creazione di pacchetti in configurazioni di pacchetti di codice](https://go.microsoft.com/fwlink/?LinkId=217663)in www.sqlis.com.</span><span class="sxs-lookup"><span data-stu-id="45066-197">Blog entry, [Creating packages in code - Package Configurations](https://go.microsoft.com/fwlink/?LinkId=217663), on www.sqlis.com.</span></span>  
  
-   <span data-ttu-id="45066-198">Intervento nel Blog relativo [all'esempio di API: aggiungere a livello di codice un file di configurazione a un pacchetto](https://go.microsoft.com/fwlink/?LinkId=217664), in Blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="45066-198">Blog entry, [API Sample - Programmatically add a configuration file to a package](https://go.microsoft.com/fwlink/?LinkId=217664), on blogs.msdn.com.</span></span>  
  
  
