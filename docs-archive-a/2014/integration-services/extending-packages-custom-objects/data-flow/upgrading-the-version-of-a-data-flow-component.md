---
title: Aggiornamento della versione di un componente del flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- PerformUpgrade method
- custom data flow components [Integration Services], upgrading version
- data flow components [Integration Services], upgrading version
- upgrading data flow components [Integration Services]
ms.assetid: c2a298c6-01b3-4ad1-884d-6108165eb56e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f494793a20f1cdcd108553278b82a44daeea75ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637994"
---
# <a name="upgrading-the-version-of-a-data-flow-component"></a><span data-ttu-id="456c4-102">Aggiornamento della versione di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="456c4-102">Upgrading the Version of a Data Flow Component</span></span>
  <span data-ttu-id="456c4-103">I pacchetti creati con una versione precedente del componente possono contenere metadati non più validi, ad esempio proprietà personalizzate il cui utilizzo è stato modificato nelle versioni più recenti del componente.</span><span class="sxs-lookup"><span data-stu-id="456c4-103">Packages that were created with an older version of your component may contain metadata that is no longer valid, such as custom properties whose usage has been modified in newer versions of the component.</span></span> <span data-ttu-id="456c4-104">È possibile eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> della classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> per aggiornare i metadati salvati in precedenza in pacchetti meno recenti in base alle proprietà correnti del componente.</span><span class="sxs-lookup"><span data-stu-id="456c4-104">You can override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class to update the metadata previously saved in older packages to reflect the current properties of your component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="456c4-105">Quando si ricompila un componente personalizzato per una nuova versione di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], non è necessario modificare il valore della proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> se le proprietà del componente non sono state modificate.</span><span class="sxs-lookup"><span data-stu-id="456c4-105">When you recompile a custom component for a new version of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], you do not have to change the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property if the component's properties have not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="456c4-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="456c4-106">Example</span></span>  
 <span data-ttu-id="456c4-107">L'esempio seguente contiene codice della versione 2.0 di un componente del flusso di dati fittizio.</span><span class="sxs-lookup"><span data-stu-id="456c4-107">The following sample contains code from version 2.0 of a fictitious data flow component.</span></span> <span data-ttu-id="456c4-108">Il nuovo numero di versione è definito nella proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> di <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="456c4-108">The new version number is defined in the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="456c4-109">Il componente include una proprietà che definisce la modalità di gestione dei valori numerici che superano una determinata soglia.</span><span class="sxs-lookup"><span data-stu-id="456c4-109">The component has a property that defines how numeric values that exceed a threshold are to be handled.</span></span> <span data-ttu-id="456c4-110">Nella versione 1.0 del componente fittizio questa proprietà è denominata `RaiseErrorOnInvalidValue` e accetta il valore booleano true o false.</span><span class="sxs-lookup"><span data-stu-id="456c4-110">In version 1.0 of the fictitious component, this property was named `RaiseErrorOnInvalidValue` and accepted a Boolean value of true or false.</span></span> <span data-ttu-id="456c4-111">Nella versione 2.0 del componente fittizio la proprietà è stata rinominata in `InvalidValueHandling` e accetta uno dei quattro valori possibili di un enumeratore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="456c4-111">In version 2.0 of the fictitious component, the property has been renamed to `InvalidValueHandling` and accepts one of four possible values from a custom enumeration.</span></span>  
  
 <span data-ttu-id="456c4-112">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> sottoposto a override nell'esempio effettua le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="456c4-112">The overridden <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the following sample performs the following actions:</span></span>  
  
-   <span data-ttu-id="456c4-113">Ottiene la versione corrente del componente.</span><span class="sxs-lookup"><span data-stu-id="456c4-113">Gets the current version of the component.</span></span>  
  
-   <span data-ttu-id="456c4-114">Ottiene il valore della proprietà personalizzata precedente.</span><span class="sxs-lookup"><span data-stu-id="456c4-114">Gets the value of the old custom property.</span></span>  
  
-   <span data-ttu-id="456c4-115">Rimuove la proprietà precedente dalla raccolta di proprietà personalizzate.</span><span class="sxs-lookup"><span data-stu-id="456c4-115">Removes the old property from the custom property collection.</span></span>  
  
-   <span data-ttu-id="456c4-116">Imposta il valore della nuova proprietà personalizzata in base al valore di quella precedente, se possibile.</span><span class="sxs-lookup"><span data-stu-id="456c4-116">Sets the value of the new custom property based on the value of the old property, if possible.</span></span>  
  
-   <span data-ttu-id="456c4-117">Imposta i metadati della versione sulla versione corrente del componente.</span><span class="sxs-lookup"><span data-stu-id="456c4-117">Sets the version metadata to the current version of the component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="456c4-118">Il motore flusso di dati passa il proprio numero di versione al metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> nel parametro *pipelineVersion*.</span><span class="sxs-lookup"><span data-stu-id="456c4-118">The data flow engine passes its own version number into the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the *pipelineVersion* parameter.</span></span> <span data-ttu-id="456c4-119">Questo parametro non è utile nella versione 1.0 di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], ma può diventarlo nelle versioni successive.</span><span class="sxs-lookup"><span data-stu-id="456c4-119">This parameter is not useful in version 1.0 of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], but may become useful in subsequent versions.</span></span>  
  
 <span data-ttu-id="456c4-120">Nel codice di esempio vengono utilizzati solo i due valori di enumerazione che possono essere mappati direttamente ai valori booleani precedenti per la proprietà personalizzata.</span><span class="sxs-lookup"><span data-stu-id="456c4-120">The sample code uses only the two enumeration values that map directly to the prior Boolean values for the custom property.</span></span> <span data-ttu-id="456c4-121">Gli utenti possono selezionare gli altri valori di enumerazione disponibili tramite l'interfaccia utente personalizzata del componente, nell'editor avanzato o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="456c4-121">Users can select the other available enumeration values through the component's custom user interface, in the Advanced Editor, or programmatically.</span></span> <span data-ttu-id="456c4-122">Per informazioni sulla visualizzazione di valori di enumerazione per una proprietà personalizzata nell'Editor avanzato, vedere "Creazione di proprietà personalizzate" in [Metodi della fase di progettazione di un componente flusso di dati](design-time-methods-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="456c4-122">For information on displaying enumeration values for a custom property in the Advanced Editor, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(ComponentType:=ComponentType.Transform, CurrentVersion:=2)> _  
Public Class PerformUpgrade  
  Inherits PipelineComponent  
  
  ' Define the set of possible values for the new custom property.  
  Private Enum InvalidValueHandling  
    Ignore  
    FireInformation  
    FireWarning  
    FireError  
  End Enum  
  
  Public Overloads Overrides Sub PerformUpgrade(ByVal pipelineVersion As Integer)  
  
    ' Obtain the current component version from the attribute.  
    Dim componentAttribute As DtsPipelineComponentAttribute = _  
      CType(Attribute.GetCustomAttribute(Me.GetType, _  
      GetType(DtsPipelineComponentAttribute), False), _  
      DtsPipelineComponentAttribute)  
    Dim currentVersion As Integer = componentAttribute.CurrentVersion  
  
    ' If the component version saved in the package is less than  
    '  the current version, Version 2, perform the upgrade.  
    If ComponentMetaData.Version < currentVersion Then  
  
      ' Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
      ' and then remove the property from the custom property collection.  
      Dim oldValue As Boolean = False  
      Try  
        Dim oldProperty As IDTSCustomProperty100 = _  
          ComponentMetaData.CustomPropertyCollection("RaiseErrorOnInvalidValue")  
        oldValue = CType(oldProperty.Value, Boolean)  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue")  
      Catch ex As Exception  
        ' If the old custom property is not available, ignore the error.  
      End Try  
  
      ' Set the value of the new custom property, InvalidValueHandling,  
      '  by using the appropriate enumeration value.  
      Dim newProperty As IDTSCustomProperty100 = _  
        ComponentMetaData.CustomPropertyCollection("InvalidValueHandling")  
      If oldValue = True Then  
        newProperty.Value = InvalidValueHandling.FireError  
      Else  
        newProperty.Value = InvalidValueHandling.Ignore  
      End If  
  
    End If  
  
    ' Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
[DtsPipelineComponent(ComponentType = ComponentType.Transform, CurrentVersion = 2)]  
public class PerformUpgradeCS :  
  PipelineComponent  
  
  // Define the set of possible values for the new custom property.  
{  
  private enum InvalidValueHandling  
  {  
    Ignore,  
    FireInformation,  
    FireWarning,  
    FireError  
  };  
  
  public override void PerformUpgrade(int pipelineVersion)  
  {  
  
    // Obtain the current component version from the attribute.  
    DtsPipelineComponentAttribute componentAttribute =   
      (DtsPipelineComponentAttribute)Attribute.GetCustomAttribute(this.GetType(), typeof(DtsPipelineComponentAttribute), false);  
    int currentVersion = componentAttribute.CurrentVersion;  
  
    // If the component version saved in the package is less than  
    //  the current version, Version 2, perform the upgrade.  
    if (ComponentMetaData.Version < currentVersion)  
  
    // Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
    // and then remove the property from the custom property collection.  
    {  
      bool oldValue = false;  
      try  
      {  
        IDTSCustomProperty100 oldProperty =   
          ComponentMetaData.CustomPropertyCollection["RaiseErrorOnInvalidValue"];  
        oldValue = (bool)oldProperty.Value;  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue");  
      }  
      catch (Exception ex)  
      {  
        // If the old custom property is not available, ignore the error.  
      }  
  
      // Set the value of the new custom property, InvalidValueHandling,  
      //  by using the appropriate enumeration value.  
      IDTSCustomProperty100 newProperty =   
         ComponentMetaData.CustomPropertyCollection["InvalidValueHandling"];  
      if (oldValue == true)  
      {  
        newProperty.Value = InvalidValueHandling.FireError;  
      }  
      else  
      {  
        newProperty.Value = InvalidValueHandling.Ignore;  
      }  
  
    }  
  
    // Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion;  
  
  }  
  
}  
```  
  
<span data-ttu-id="456c4-123">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="456c4-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="456c4-124">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="456c4-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="456c4-125">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="456c4-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="456c4-126">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="456c4-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
