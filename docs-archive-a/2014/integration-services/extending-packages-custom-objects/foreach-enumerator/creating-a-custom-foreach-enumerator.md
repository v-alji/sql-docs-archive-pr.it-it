---
title: Creazione di un enumeratore Foreach personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom foreach enumerators [Integration Services], creating
ms.assetid: 050e8455-2ed0-4b6d-b3ea-4e80e6c28487
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d99970d466aa53d25a80f0600f1fce7819e94956
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626158"
---
# <a name="creating-a-custom-foreach-enumerator"></a><span data-ttu-id="74518-102">Creazione di un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="74518-102">Creating a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="74518-103">I passaggi per la creazione di un enumeratore Foreach personalizzato sono simili a quelli richiesti per la creazione di qualsiasi altro oggetto personalizzato per [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="74518-103">The steps involved in creating a custom foreach enumerator are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="74518-104">Creare una nuova classe che eredita dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="74518-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="74518-105">Per un enumeratore Foreach, la classe di base è <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="74518-105">For a foreach enumerator, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>.</span></span>  
  
-   <span data-ttu-id="74518-106">Applicare alla classe l'attributo che identifica il tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="74518-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="74518-107">Per un enumeratore Foreach, l'attributo è <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="74518-107">For a foreach enumerator, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.</span></span>  
  
-   <span data-ttu-id="74518-108">Eseguire l'override dell'implementazione dei metodi e delle proprietà della classe di base.</span><span class="sxs-lookup"><span data-stu-id="74518-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="74518-109">Per un enumeratore Foreach, il più importante è il metodo <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="74518-109">For a foreach enumerator, the most important is the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
-   <span data-ttu-id="74518-110">Se si desidera, sviluppare un'interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="74518-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="74518-111">Per un enumeratore Foreach, questa operazione richiede una classe che implementi l'interfaccia <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI>.</span><span class="sxs-lookup"><span data-stu-id="74518-111">For a foreach enumerator, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI> interface.</span></span>  
  
 <span data-ttu-id="74518-112">Un enumeratore personalizzato è ospitato dal contenitore <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>.</span><span class="sxs-lookup"><span data-stu-id="74518-112">A custom enumerator is hosted by the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container.</span></span> <span data-ttu-id="74518-113">In fase di esecuzione il contenitore <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> chiama il metodo <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> dell'enumeratore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="74518-113">At run time, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="74518-114">L'enumeratore personalizzato restituisce un oggetto che implementa l'interfaccia `IEnumerable`, ad esempio `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="74518-114">The custom enumerator returns an object that implements the `IEnumerable` interface, such as an `ArrayList`.</span></span> <span data-ttu-id="74518-115">Tramite l'oggetto <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> viene quindi scorso ogni elemento della raccolta, viene fornito il valore dell'elemento corrente al flusso di controllo tramite una variabile definita dall'utente e viene eseguito il flusso di controllo nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="74518-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates over each element in the collection, provides the value of the current element to the control flow through a user-defined variable, and executes the control flow in the container.</span></span>  
  
## <a name="getting-started-with-a-custom-foreach-enumerator"></a><span data-ttu-id="74518-116">Introduzione a un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="74518-116">Getting Started with a Custom ForEach Enumerator</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="74518-117">Creazione di progetti e classi</span><span class="sxs-lookup"><span data-stu-id="74518-117">Creating Projects and Classes</span></span>  
 <span data-ttu-id="74518-118">Poiché tutti gli enumeratori Foreach gestiti derivano dalla classe di base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, il primo passaggio da completare quando si crea un enumeratore Foreach personalizzato consiste nel creare un progetto di libreria di classi nel linguaggio di programmazione gestito preferito e creare una classe che eredita dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="74518-118">Because all managed foreach enumerators derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, the first step when you create a custom foreach enumerator is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="74518-119">In questa classe derivata si eseguirà l'override dei metodi e delle proprietà della classe di base per implementare la funzionalità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="74518-119">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="74518-120">Nella stessa soluzione creare un secondo progetto di libreria di classi per l'interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="74518-120">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="74518-121">Per semplificare lo sviluppo, si consiglia di utilizzare un assembly distinto per l'interfaccia utente, perché in questo modo è possibile e ridistribuire l'enumeratore Foreach o la relativa interfaccia utente in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="74518-121">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the foreach enumerator or its user interface independently.</span></span>  
  
 <span data-ttu-id="74518-122">Configurare entrambi i progetti per firmare gli assembly che verranno generati durante la compilazione utilizzando un file di chiave con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="74518-122">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsforeachenumerator-attribute"></a><span data-ttu-id="74518-123">Applicazione dell'attributo DtsForEachEnumerator</span><span class="sxs-lookup"><span data-stu-id="74518-123">Applying the DtsForEachEnumerator Attribute</span></span>  
 <span data-ttu-id="74518-124">Applicare l'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> alla classe creata per identificarla come enumeratore Foreach.</span><span class="sxs-lookup"><span data-stu-id="74518-124">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class that you have created to identify it as a foreach enumerator.</span></span> <span data-ttu-id="74518-125">Questo attributo fornisce informazioni in fase di progettazione, ad esempio il nome e la descrizione dell'enumeratore Foreach.</span><span class="sxs-lookup"><span data-stu-id="74518-125">This attribute provides design-time information such as the name and description of the foreach enumerator.</span></span> <span data-ttu-id="74518-126">La `Name` proprietà viene visualizzata nell'elenco a discesa degli enumeratori disponibili nella scheda **raccolta** della finestra di dialogo **Editor ciclo foreach** .</span><span class="sxs-lookup"><span data-stu-id="74518-126">The `Name` property appears in the dropdown list of available enumerators on the **Collection** tab of the **Foreach Loop Editor** dialog box.</span></span>  
  
 <span data-ttu-id="74518-127">Utilizzare la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> per collegare l'enumeratore Foreach alla relativa interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="74518-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> property to link the foreach enumerator to its custom user interface.</span></span> <span data-ttu-id="74518-128">Per ottenere il token di chiave pubblica richiesto per questa proprietà, è possibile usare **sn.exe -t** per visualizzare il token di chiave pubblica dal file della coppia di chiavi (con estensione snk) che si intende usare per firmare l'assembly dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="74518-128">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Namespace Microsoft.Samples.SqlServer.Dts  
    <DtsForEachEnumerator(DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")> _   
    Public Class MyEnumerator  
     Inherits ForEachEnumerator  
        'Insert code here.  
    End Class  
End Namespace  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsForEachEnumerator( DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")]  
    public class MyEnumerator : ForEachEnumerator  
    {  
        //Insert code here.  
    }  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-enumerator"></a><span data-ttu-id="74518-129">Compilazione, distribuzione e debug di un enumeratore personalizzato</span><span class="sxs-lookup"><span data-stu-id="74518-129">Building, Deploying, and Debugging a Custom Enumerator</span></span>  
 <span data-ttu-id="74518-130">I passaggi per la compilazione, la distribuzione e il debug di un enumeratore Foreach personalizzato in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sono molto simili a quelli richiesti per altri tipi di oggetti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="74518-130">The steps for building, deploying, and debugging a custom foreach enumerator in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are very similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="74518-131">Per altre informazioni, vedere [Compilazione, distribuzione e debug di oggetti personalizzati](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="74518-131">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="74518-132">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="74518-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="74518-133">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="74518-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="74518-134">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="74518-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="74518-135">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="74518-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74518-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74518-136">See Also</span></span>  
 <span data-ttu-id="74518-137">[Codifica di un enumeratore Foreach personalizzato](coding-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="74518-137">[Coding a Custom Foreach Enumerator](coding-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="74518-138">Sviluppo di un'interfaccia utente per un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="74518-138">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
