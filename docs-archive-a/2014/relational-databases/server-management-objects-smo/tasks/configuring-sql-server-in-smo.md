---
title: Configurazione di SQL Server in SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server, configuring
- configuration options [SMO]
ms.assetid: 0a372643-15cb-45a7-8665-04f1215df8ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6da1bca0aec650c01553b42bc2f3628b0bf7282e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723679"
---
# <a name="configuring-sql-server-in-smo"></a><span data-ttu-id="ce19d-102">Configurazione di SQL Server in SMO</span><span class="sxs-lookup"><span data-stu-id="ce19d-102">Configuring SQL Server in SMO</span></span>
  <span data-ttu-id="ce19d-103">In SMO l'oggetto, l'oggetto, <xref:Microsoft.SqlServer.Management.Smo.Information> <xref:Microsoft.SqlServer.Management.Smo.Settings> l'oggetto <xref:Microsoft.SqlServer.Management.Smo.UserOptions> e l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Configuration> contengono impostazioni e informazioni per l'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce19d-103">In SMO, the <xref:Microsoft.SqlServer.Management.Smo.Information> object, the <xref:Microsoft.SqlServer.Management.Smo.Settings> object, the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object, and the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object contain settings and information for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ce19d-104">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sono disponibili varie proprietà tramite cui viene descritto il comportamento dell'istanza installata.</span><span class="sxs-lookup"><span data-stu-id="ce19d-104">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has numerous properties that describe the behavior of the installed instance.</span></span> <span data-ttu-id="ce19d-105">Le proprietà consentono di descrivere opzioni di avvio, impostazioni predefinite del server, file e directory, informazioni sul sistema e sul processore, prodotto e versioni, informazioni di connessione, opzioni per la memoria, selezioni relative a lingua e regole di confronto e modalità di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ce19d-105">The properties describe the startup options, the server defaults, files and directories, system and processor information, product and versions, connection information, memory options, language and collation selections, and the authentication mode.</span></span>  
  
## <a name="sql-server-configuration"></a><span data-ttu-id="ce19d-106">Configurazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="ce19d-106">SQL Server Configuration</span></span>  
 <span data-ttu-id="ce19d-107">Le proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Information> contengono informazioni sull'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], ad esempio processore e piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ce19d-107">The <xref:Microsoft.SqlServer.Management.Smo.Information> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], such as processor and platform.</span></span>  
  
 <span data-ttu-id="ce19d-108">Le proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Settings> contengono informazioni sull'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce19d-108">The <xref:Microsoft.SqlServer.Management.Smo.Settings> object properties contain information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ce19d-109">Oltre al profilo di posta e all'account del server, è possibile modificare il file e la directory di database predefiniti.</span><span class="sxs-lookup"><span data-stu-id="ce19d-109">The default database file and directory can be modified in addition to the Mail Profile and the Server Account.</span></span> <span data-ttu-id="ce19d-110">Queste proprietà rimangono valide per la durata della connessione.</span><span class="sxs-lookup"><span data-stu-id="ce19d-110">These properties remain for the duration of the connection.</span></span>  
  
 <span data-ttu-id="ce19d-111">Le proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.UserOptions> contengono informazioni sul comportamento delle connessioni correnti in relazione ad aritmetica, standard ANSI e transazioni.</span><span class="sxs-lookup"><span data-stu-id="ce19d-111">The <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object properties contain information about the current connections behavior relating to arithmetic, ANSI standards, and transactions.</span></span>  
  
 <span data-ttu-id="ce19d-112">È inoltre disponibile un set di opzioni di configurazione rappresentato dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="ce19d-112">There is also a set of configuration options that is represented by the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object.</span></span> <span data-ttu-id="ce19d-113">Contiene un set di proprietà che rappresentano le opzioni che possono essere modificate dalla stored procedure `sp_configure`.</span><span class="sxs-lookup"><span data-stu-id="ce19d-113">It contains a set of properties that represent the options that can be modified by the `sp_configure` stored procedure.</span></span> <span data-ttu-id="ce19d-114">Opzioni quali il **Boost di priorità**, l' **intervallo di recupero** e le dimensioni dei **pacchetti di rete**controllano le prestazioni dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce19d-114">Options such as **Priority Boost**, **Recovery Interval** and **Network Packet Size**control the performance of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ce19d-115">Molte di queste opzioni possono essere modificate dinamicamente, ma in alcuni casi il valore viene prima configurato, quindi modificato al riavvio dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce19d-115">Many of these options can be changed dynamically, but in some cases the value is first configured and then changed when the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
 <span data-ttu-id="ce19d-116">È presente una proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Configuration> per ogni opzione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ce19d-116">There is a <xref:Microsoft.SqlServer.Management.Smo.Configuration> object property for every configuration option.</span></span> <span data-ttu-id="ce19d-117">È possibile modificare l'impostazione di configurazione globale utilizzando l'oggetto <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty>.</span><span class="sxs-lookup"><span data-stu-id="ce19d-117">Using the <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> object you can modify the global configuration setting.</span></span> <span data-ttu-id="ce19d-118">Molte proprietà hanno valori massimi e minimi, anch'essi archiviati come proprietà <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty>.</span><span class="sxs-lookup"><span data-stu-id="ce19d-118">Many properties have maximum and minimum values that are also stored as <xref:Microsoft.SqlServer.Management.Smo.ConfigProperty> properties.</span></span> <span data-ttu-id="ce19d-119">Queste proprietà richiedono il <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> metodo per eseguire il commit della modifica nell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce19d-119">These properties require the <xref:Microsoft.SqlServer.Management.Smo.ConfigurationBase.Alter%2A> method to commit the change to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ce19d-120">Tutte le opzioni di configurazione nell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Configuration> devono essere modificate dall'amministratore del sistema.</span><span class="sxs-lookup"><span data-stu-id="ce19d-120">All of the configuration options in the <xref:Microsoft.SqlServer.Management.Smo.Configuration> object must be changed by the system administrator.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ce19d-121">Esempi</span><span class="sxs-lookup"><span data-stu-id="ce19d-121">Examples</span></span>  
 <span data-ttu-id="ce19d-122">Per gli esempi di codice seguenti, è necessario selezionare l'ambiente, il modello e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce19d-122">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="ce19d-123">Per ulteriori informazioni, vedere la pagina relativa alla [creazione di un progetto Visual Basic SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e alla [creazione di un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="ce19d-123">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="modifying-sql-server-configuration-options-in-visual-basic"></a><span data-ttu-id="ce19d-124">Modifica delle opzioni di configurazione di SQL Server in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce19d-124">Modifying SQL Server Configuration Options in Visual Basic</span></span>  
 <span data-ttu-id="ce19d-125">Nell'esempio di codice viene illustrato come aggiornare un'opzione di configurazione in Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="ce19d-125">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="ce19d-126">Vengono inoltre recuperate e visualizzate informazioni relative ai valori massimi e minimi per l'opzione di configurazione specificata.</span><span class="sxs-lookup"><span data-stu-id="ce19d-126">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="ce19d-127">Infine, viene segnalato all'utente se la modifica è stata apportata dinamicamente o se è stata archiviata fino al riavvio dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce19d-127">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure2](SMO How to#SMO_VBConfigure2)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-basic"></a><span data-ttu-id="ce19d-128">Modifica delle impostazioni di SQL Server in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce19d-128">Modifying SQL Server Settings in Visual Basic</span></span>  
 <span data-ttu-id="ce19d-129">Nell'esempio di codice vengono visualizzate informazioni sull'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> e e vengono <xref:Microsoft.SqlServer.Management.Smo.Settings> modificate le impostazioni nelle <xref:Microsoft.SqlServer.Management.Smo.Settings> proprietà e dell' <xref:Microsoft.SqlServer.Management.Smo.UserOptions> oggetto.</span><span class="sxs-lookup"><span data-stu-id="ce19d-129">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="ce19d-130">Nell'esempio l'oggetto <xref:Microsoft.SqlServer.Management.Smo.UserOptions> e l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Settings> hanno entrambi un metodo <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce19d-130">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="ce19d-131">È possibile eseguire i metodi <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> per questi oggetti singolarmente.</span><span class="sxs-lookup"><span data-stu-id="ce19d-131">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBConfigure1](SMO How to#SMO_VBConfigure1)]  -->  
  
## <a name="modifying-sql-server-settings-in-visual-c"></a><span data-ttu-id="ce19d-132">Modifica delle impostazioni di SQL Server in Visual C#</span><span class="sxs-lookup"><span data-stu-id="ce19d-132">Modifying SQL Server Settings in Visual C#</span></span>  
 <span data-ttu-id="ce19d-133">Nell'esempio di codice vengono visualizzate informazioni sull'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> e e vengono <xref:Microsoft.SqlServer.Management.Smo.Settings> modificate le impostazioni nelle <xref:Microsoft.SqlServer.Management.Smo.Settings> proprietà e dell' <xref:Microsoft.SqlServer.Management.Smo.UserOptions> oggetto.</span><span class="sxs-lookup"><span data-stu-id="ce19d-133">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="ce19d-134">Nell'esempio l'oggetto <xref:Microsoft.SqlServer.Management.Smo.UserOptions> e l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Settings> hanno entrambi un metodo <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce19d-134">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="ce19d-135">È possibile eseguire i metodi <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> per questi oggetti singolarmente.</span><span class="sxs-lookup"><span data-stu-id="ce19d-135">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
 `//Connect to the local, default instance of SQL Server.`  
  
```csharp
{  
            Server srv = new Server();  
            //Display all the configuration options.   
  
            foreach (ConfigProperty p in srv.Configuration.Properties)  
            {  
                Console.WriteLine(p.DisplayName);  
            }  
            Console.WriteLine("There are " + srv.Configuration.Properties.Count.ToString() + " configuration options.");  
            //Display the maximum and minimum values for ShowAdvancedOptions.   
            int min = 0;  
            int max = 0;  
            min = srv.Configuration.ShowAdvancedOptions.Minimum;  
            max = srv.Configuration.ShowAdvancedOptions.Maximum;  
            Console.WriteLine("Minimum and Maximum values are " + min + " and " + max + ".");  
            //Modify the value of ShowAdvancedOptions and run the Alter method.   
            srv.Configuration.ShowAdvancedOptions.ConfigValue = 0;  
            srv.Configuration.Alter();  
            //Display when the change takes place according to the IsDynamic property.   
            if (srv.Configuration.ShowAdvancedOptions.IsDynamic == true)  
            {  
                Console.WriteLine("Configuration option has been updated.");  
            }  
            else  
            {  
                Console.WriteLine("Configuration option will be updated when SQL Server is restarted.");  
            }  
        }  
```  
  
## <a name="modifying-sql-server-settings-in-powershell"></a><span data-ttu-id="ce19d-136">Modifica delle impostazioni di SQL Server in PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce19d-136">Modifying SQL Server Settings in PowerShell</span></span>  
 <span data-ttu-id="ce19d-137">Nell'esempio di codice vengono visualizzate informazioni sull'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> e e vengono <xref:Microsoft.SqlServer.Management.Smo.Settings> modificate le impostazioni nelle <xref:Microsoft.SqlServer.Management.Smo.Settings> proprietà e dell' <xref:Microsoft.SqlServer.Management.Smo.UserOptions> oggetto.</span><span class="sxs-lookup"><span data-stu-id="ce19d-137">The code example displays information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in <xref:Microsoft.SqlServer.Management.Smo.Information> and <xref:Microsoft.SqlServer.Management.Smo.Settings>, and modifies settings in <xref:Microsoft.SqlServer.Management.Smo.Settings> and <xref:Microsoft.SqlServer.Management.Smo.UserOptions>object properties.</span></span>  
  
 <span data-ttu-id="ce19d-138">Nell'esempio l'oggetto <xref:Microsoft.SqlServer.Management.Smo.UserOptions> e l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Settings> hanno entrambi un metodo <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce19d-138">In the example the <xref:Microsoft.SqlServer.Management.Smo.UserOptions> object and the <xref:Microsoft.SqlServer.Management.Smo.Settings> object both have an <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> method.</span></span> <span data-ttu-id="ce19d-139">È possibile eseguire i metodi <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> per questi oggetti singolarmente.</span><span class="sxs-lookup"><span data-stu-id="ce19d-139">You can run the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.Alter%2A> methods for these individually.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Display information about the instance of SQL Server in Information and Settings.  
"OS Version = " + $srv.Information.OSVersion  
"State = "+ $srv.Settings.State.ToString()  
  
#Display information specific to the current user in UserOptions.  
"Quoted Identifier support = " + $srv.UserOptions.QuotedIdentifier  
  
#Modify server settings in Settings.  
$srv.Settings.LoginMode = [Microsoft.SqlServer.Management.SMO.ServerLoginMode]::Integrated  
  
#Modify settings specific to the current connection in UserOptions.  
$srv.UserOptions.AbortOnArithmeticErrors = $true  
  
#Run the Alter method to make the changes on the instance of SQL Server.  
$srv.Alter()  
```  
  
## <a name="modifying-sql-server-configuration-options-in-powershell"></a><span data-ttu-id="ce19d-140">Modifica delle opzioni di configurazione di SQL Server in PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce19d-140">Modifying SQL Server Configuration Options in PowerShell</span></span>  
 <span data-ttu-id="ce19d-141">Nell'esempio di codice viene illustrato come aggiornare un'opzione di configurazione in Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="ce19d-141">The code example shows how to update a configuration option in Visual Basic .NET.</span></span> <span data-ttu-id="ce19d-142">Vengono inoltre recuperate e visualizzate informazioni relative ai valori massimi e minimi per l'opzione di configurazione specificata.</span><span class="sxs-lookup"><span data-stu-id="ce19d-142">It also retrieves and displays information about maximum and minimum values for the specified configuration option.</span></span> <span data-ttu-id="ce19d-143">Infine, viene segnalato all'utente se la modifica è stata apportata dinamicamente o se è stata archiviata fino al riavvio dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce19d-143">Finally, the program informs the user if the change has been made dynamically, or if it is stored until the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is restarted.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance replace LocalMachine with the physical server  
cd \sql\LocalMachine  
$svr = Get-Item default  
  
#enumerate its properties  
foreach ($Item in $Svr.Configuration.Properties)   
{  
 $Item.DisplayName  
}  
  
"There are " + $svr.Configuration.Properties.Count.ToString() + " configuration options."  
  
#Display the maximum and minimum values for ShowAdvancedOptions.  
$min = $svr.Configuration.ShowAdvancedOptions.Minimum  
$max = $svr.Configuration.ShowAdvancedOptions.Maximum  
"Minimum and Maximum values are " + $min.ToString() + " and " + $max.ToString() + "."  
  
#Modify the value of ShowAdvancedOptions and run the Alter method.  
$svr.Configuration.ShowAdvancedOptions.ConfigValue = 0  
$svr.Configuration.Alter()  
  
#Display when the change takes place according to the IsDynamic property.  
If ($svr.Configuration.ShowAdvancedOptions.IsDynamic -eq $true)  
 {
   "Configuration option has been updated."  
 }  
Else  
 {  
    "Configuration option will be updated when SQL Server is restarted."  
 }  
```  
