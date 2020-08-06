---
title: Creazione di una gestione connessione personalizzata | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom connection managers [Integration Services], creating
ms.assetid: e83f8e02-ace4-42e0-b979-2f6be1460985
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 857efebbe311e5510e15cae9e78a2b424559ded7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726095"
---
# <a name="creating-a-custom-connection-manager"></a><span data-ttu-id="2a504-102">Creazione di una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="2a504-102">Creating a Custom Connection Manager</span></span>
  <span data-ttu-id="2a504-103">I passaggi che è necessario effettuare per creare una gestione connessione personalizzata sono simili ai passaggi necessari per la creazione di qualsiasi altro oggetto personalizzato per [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="2a504-103">The steps that you must follow to create a custom connection manager are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="2a504-104">Creare una nuova classe che eredita dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="2a504-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="2a504-105">Per una gestione connessione, la classe di base è <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="2a504-105">For a connection manager, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.</span></span>  
  
-   <span data-ttu-id="2a504-106">Applicare alla classe l'attributo che identifica il tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="2a504-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="2a504-107">Per una gestione connessione, l'attributo è <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2a504-107">For a connection manager, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.</span></span>  
  
-   <span data-ttu-id="2a504-108">Eseguire l'override dell'implementazione dei metodi e delle proprietà della classe di base.</span><span class="sxs-lookup"><span data-stu-id="2a504-108">Override the implementation of the methods and properties of the base class.</span></span> <span data-ttu-id="2a504-109">Per una gestione connessione, questi includono la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> e i metodi <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a504-109">For a connection manager, these include the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> property and the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A> methods.</span></span>  
  
-   <span data-ttu-id="2a504-110">Se si desidera, sviluppare un'interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2a504-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="2a504-111">Per una gestione connessione, è richiesta una classe tramite cui venga implementata l'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>.</span><span class="sxs-lookup"><span data-stu-id="2a504-111">For a connection manager, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI> interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2a504-112">La maggior parte delle attività, delle origini e delle destinazioni incluse in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] funziona solo con tipi specifici di gestioni connessioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="2a504-112">Most of the tasks, sources, and destinations that have been built into [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] work only with specific types of built-in connection managers.</span></span> <span data-ttu-id="2a504-113">Questi esempi, pertanto, non possono essere testati con le attività e i componenti predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2a504-113">Therefore, these samples cannot be tested with the built-in tasks and components.</span></span>  
  
## <a name="getting-started-with-a-custom-connection-manager"></a><span data-ttu-id="2a504-114">Introduzione alle gestioni connessioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="2a504-114">Getting Started with a Custom Connection Manager</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="2a504-115">Creazione di progetti e classi</span><span class="sxs-lookup"><span data-stu-id="2a504-115">Creating Projects and Classes</span></span>  
 <span data-ttu-id="2a504-116">Poiché tutte le gestioni connessioni derivano dalla classe di base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, il primo passaggio da completare quando si crea una gestione connessione personalizzata consiste nel creare un progetto di libreria di classi nel linguaggio di programmazione gestito preferito e creare una classe che eredita dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="2a504-116">Because all managed connection managers derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase> base class, the first step when you create a custom connection manager is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="2a504-117">In questa classe derivata si eseguirà l'override dei metodi e delle proprietà della classe di base per implementare la funzionalità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2a504-117">In this derived class, you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="2a504-118">Nella stessa soluzione creare un secondo progetto di libreria di classi per l'interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2a504-118">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="2a504-119">Per semplificare lo sviluppo, si consiglia di utilizzare un assembly distinto per l'interfaccia utente, perché in questo modo è possibile e ridistribuire la gestione connessione o la relativa interfaccia utente in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="2a504-119">A separate assembly for the user interface is recommended for ease of deployment because it lets you update and redeploy the connection manager or its user interface independently.</span></span>  
  
 <span data-ttu-id="2a504-120">Configurare entrambi i progetti per firmare gli assembly che verranno generati durante la compilazione utilizzando un file di chiave con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="2a504-120">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsconnection-attribute"></a><span data-ttu-id="2a504-121">Applicazione dell'attributo DtsConnection</span><span class="sxs-lookup"><span data-stu-id="2a504-121">Applying the DtsConnection Attribute</span></span>  
 <span data-ttu-id="2a504-122">Applicare l'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> alla classe creata per identificarla come gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="2a504-122">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> attribute to the class that you have created to identify it as a connection manager.</span></span> <span data-ttu-id="2a504-123">Questo attributo fornisce informazioni in fase di progettazione, ad esempio il nome, la descrizione e il tipo di connessione della gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="2a504-123">This attribute provides design-time information such as the name, description, and connection type of the connection manager.</span></span> <span data-ttu-id="2a504-124">Le <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> `Description` proprietà e corrispondono al **tipo** e alle `Description` colonne visualizzate nella finestra di dialogo **Aggiungi gestione connessione SSIS** , visualizzata quando si configurano le connessioni per un pacchetto in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a504-124">The <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> and `Description` properties correspond to the **Type** and `Description` columns displayed in the **Add SSIS Connection Manager** dialog box, which is displayed when configuring connections for a package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="2a504-125">Utilizzare la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> per collegare la gestione connessione alla relativa interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2a504-125">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> property to link the connection manager to its custom user interface.</span></span> <span data-ttu-id="2a504-126">Per ottenere il token di chiave pubblica richiesto per questa proprietà, è possibile usare **sn.exe -t** per visualizzare il token di chiave pubblica dal file della coppia di chiavi (con estensione snk) che si intende usare per firmare l'assembly dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="2a504-126">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
<DtsConnection(ConnectionType:="SQLVB", _  
  DisplayName:="SqlConnectionManager (VB)", _  
  Description:="Connection manager for Sql Server", _  
  UITypeName:="SqlConnMgrUIVB.SqlConnMgrUIVB,SqlConnMgrUIVB,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")> _  
Public Class SqlConnMgrVB  
  Inherits ConnectionManagerBase  
  . . .  
End Class  
```  
  
```csharp  
[DtsConnection(ConnectionType = "SQLCS",  
  DisplayName = "SqlConnectionManager (CS)",  
  Description = "Connection manager for Sql Server",  
  UITypeName = "SqlConnMgrUICS.SqlConnMgrUICS,SqlConnMgrUICS,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")]  
public class SqlConnMgrCS :  
ConnectionManagerBase  
{  
  . . .  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-connection-manager"></a><span data-ttu-id="2a504-127">Compilazione, distribuzione e debug di una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="2a504-127">Building, Deploying, and Debugging a Custom Connection Manager</span></span>  
 <span data-ttu-id="2a504-128">I passaggi per la compilazione, la distribuzione e il debug di una gestione connessione personalizzata in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sono simili a quelli richiesti per altri tipi di oggetti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2a504-128">The steps for building, deploying, and debugging a custom connection manager in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are similar to the steps for other types of custom objects.</span></span> <span data-ttu-id="2a504-129">Per altre informazioni, vedere [Compilazione, distribuzione e debug di oggetti personalizzati](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="2a504-129">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="2a504-130">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2a504-130">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2a504-131">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="2a504-131">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2a504-132">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="2a504-132">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2a504-133">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2a504-133">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a504-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a504-134">See Also</span></span>  
 <span data-ttu-id="2a504-135">[Codifica di una gestione connessione personalizzata](coding-a-custom-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="2a504-135">[Coding a Custom Connection Manager](coding-a-custom-connection-manager.md) </span></span>  
 [<span data-ttu-id="2a504-136">Sviluppo di un'interfaccia utente per una gestione connessione personalizzata</span><span class="sxs-lookup"><span data-stu-id="2a504-136">Developing a User Interface for a Custom Connection Manager</span></span>](developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  
