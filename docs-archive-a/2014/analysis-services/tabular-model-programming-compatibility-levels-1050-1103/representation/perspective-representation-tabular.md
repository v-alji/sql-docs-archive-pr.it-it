---
title: Rappresentazione della prospettiva (tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 6d2636c4-dae4-448f-a1d4-dbee739e177c
author: minewiskan
ms.author: owend
ms.openlocfilehash: ca8a66d3134748fd524dc0c6b524d944213533e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626932"
---
# <a name="perspective-representation-tabular"></a><span data-ttu-id="5b5db-102">Rappresentazione della prospettiva (tabulare)</span><span class="sxs-lookup"><span data-stu-id="5b5db-102">Perspective Representation (Tabular)</span></span>
  <span data-ttu-id="5b5db-103">Una prospettiva è un meccanismo per semplificare o concentrare il modello in una parte più piccola per l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="5b5db-103">A perspective is a mechanism to simplify or focus the model into a smaller portion of it for the client application.</span></span>  
  
 <span data-ttu-id="5b5db-104">Per una spiegazione dettagliata su come creare e modificare la rappresentazione della prospettiva, vedere [rappresentazione prospettica (tabulare)](perspective-representation-tabular.md) .</span><span class="sxs-lookup"><span data-stu-id="5b5db-104">See [Perspective Representation (Tabular)](perspective-representation-tabular.md) for a detailed explanation on how to create and manipulate the perspective representation.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="5b5db-105">Le prospettive non sono un meccanismo di sicurezza. L'utente può comunque accedere agli oggetti esterni alla prospettiva tramite altre interfacce.</span><span class="sxs-lookup"><span data-stu-id="5b5db-105">Perspectives are not a security mechanism; objects outside the perspective can still be accessed by the user through other interfaces.</span></span>  
  
## <a name="perspective-representation"></a><span data-ttu-id="5b5db-106">Rappresentazione della prospettiva</span><span class="sxs-lookup"><span data-stu-id="5b5db-106">Perspective Representation</span></span>  
 <span data-ttu-id="5b5db-107">In termini di oggetti AMO, una rappresentazione della prospettiva dispone di una relazione di mapping uno-a-uno con <xref:Microsoft.AnalysisServices.Perspective> e non sono richiesti altri oggetti AMO principali.</span><span class="sxs-lookup"><span data-stu-id="5b5db-107">In terms of AMO objects a perspective representation has a one to one mapping relationship with <xref:Microsoft.AnalysisServices.Perspective> and no other main AMO objects are required.</span></span>  
  
### <a name="perspective-in-amo"></a><span data-ttu-id="5b5db-108">Prospettiva in AMO</span><span class="sxs-lookup"><span data-stu-id="5b5db-108">Perspective in AMO</span></span>  
 <span data-ttu-id="5b5db-109">Nel frammento di codice seguente viene mostrato come creare una prospettiva in un modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="5b5db-109">The following code snippet shows how to create a perspective in a Tabular model.</span></span> <span data-ttu-id="5b5db-110">L'elemento principale in questo frammento di codice è perspectiveElements; tale oggetto è una rappresentazione grafica di tutti gli oggetti nel modello tabulare esposti all'utente.</span><span class="sxs-lookup"><span data-stu-id="5b5db-110">The key element in this piece of code is the perspectiveElements; this object is a graphical representation of all the objects in the tabular model that are exposed to the user.</span></span> <span data-ttu-id="5b5db-111">*perspectiveElements* contiene 4 colonne e per questo scenario sono rilevanti solo le colonne 1, 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="5b5db-111">*perspectiveElements* contains 4 columns and for this scenario only columns 1, 2 and 3 are relevant.</span></span> <span data-ttu-id="5b5db-112">La colonna 1 contiene il tipo di elemento visualizzato: elementTypeValue; la colonna 2 contiene il nome completo dell'elemento, che probabilmente dovrà essere analizzato per immettere l'elemento nella prospettiva; la colonna 3 contiene un elemento della casella di controllo: checkedElement che stabilisce se l'elemento fa parte o meno della prospettiva.</span><span class="sxs-lookup"><span data-stu-id="5b5db-112">Column 1 contains the type of element displayed -elementTypeValue-; column 2 contains the complete name of the element --, that probably will need to parsed to enter the element in the perspective; column 3 contains a checkbox item -checkedElement- that tells if the element is part of the perspective or not.</span></span>  
  
```  
  
private void updatePerspective_Click(  
                     AMO.Cube modelCube  
                  ,  DataGridView perspectiveElements  
                  ,  string updatedPerspectiveID  
             )  
{  
    //Update is done by delete first, create new and insert after  
    //if perspective doesn't exist then create first and insert after  
    updatedPerspectiveID = updatedPerspectiveID.Trim();  
    if (modelCube.Perspectives.Contains(updatedPerspectiveID))  
    {  
        modelCube.Perspectives.Remove(updatedPerspectiveID, true);  
        newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
    }  
    AMO.Perspective currentPerspective = modelCube.Perspectives.Add(updatedPerspectiveID, updatedPerspectiveID);  
  
    foreach (DataGridViewRow currentDGVRow in perspectiveElements.Rows)  
    {  
        bool checkedElement = (bool)currentDGVRow.Cells[3].Value;  
        if (checkedElement)  
        {  
            string elementTypeValue = currentDGVRow.Cells[1].Value.ToString();  
            string elementNameValue = currentDGVRow.Cells[2].Value.ToString();  
            switch (elementTypeValue)  
            {  
                case "Column: Attribute":  
                case "Column: Calculated Column":  
                    {  
                        string perspectiveDimensionName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string perspectiveDimensionAttributeName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        AMO.PerspectiveDimension currentPerspectiveDimension;  
                        if (!currentPerspective.Dimensions.Contains(perspectiveDimensionName))  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions.Add(perspectiveDimensionName);  
                        }  
                        else  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions[perspectiveDimensionName];  
                        }  
                        if (!currentPerspectiveDimension.Attributes.Contains(perspectiveDimensionAttributeName))  
                        {  
                            currentPerspectiveDimension.Attributes.Add(perspectiveDimensionAttributeName);  
                        }  
                    }  
                    break;  
                case "Hierarchy":  
                    {  
                        string perspectiveDimensionName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string perspectiveDimensionHierarchyName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        AMO.PerspectiveDimension currentPerspectiveDimension;  
                        if (!currentPerspective.Dimensions.Contains(perspectiveDimensionName))  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions.Add(perspectiveDimensionName);  
                        }  
                        else  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions[perspectiveDimensionName];  
                        }  
                        if (!currentPerspectiveDimension.Hierarchies.Contains(perspectiveDimensionHierarchyName))  
                        {  
                            currentPerspectiveDimension.Hierarchies.Add(perspectiveDimensionHierarchyName);  
                        }  
                    }  
                    break;  
                case "Measure":  
                    {  
                        string perspectiveMeasureGroupName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string measureName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        string perspectiveMeasureName = string.Format("[Measures].[{0}]", measureName);  
                        AMO.PerspectiveCalculation currentPerspectiveCalculation = new AMO.PerspectiveCalculation(perspectiveMeasureName, AMO.PerspectiveCalculationType.Member);  
                        if (!currentPerspective.Calculations.Contains(perspectiveMeasureName))  
                        {  
                            currentPerspective.Calculations.Add(currentPerspectiveCalculation);  
                        }  
                        if (modelCube.MdxScripts["MdxScript"].CalculationProperties.Contains(string.Format("KPIs.[{0}]", measureName)))  
                        {//Current Measure is also a KPI ==> will be added to the KPIs collection of the perspective  
                            AMO.PerspectiveKpi currentPerspectiveKpi = new AMO.PerspectiveKpi(perspectiveMeasureName);  
                            if (!currentPerspective.Kpis.Contains(perspectiveMeasureName))  
                            {  
                                currentPerspective.Kpis.Add(currentPerspectiveKpi);  
                            }  
                        }  
                    }  
                    break;  
                default:  
                    break;  
            }  
        }  
    }  
  
    newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.CreateOrReplace);  
    MessageBox.Show(String.Format("Perpective successfully updated."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
}  
  
```  
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="5b5db-113">Esempio AMO2Tabular</span><span class="sxs-lookup"><span data-stu-id="5b5db-113">AMO2Tabular sample</span></span>  
 <span data-ttu-id="5b5db-114">Per comprendere tuttavia la modalità di utilizzo di AMO (Analysis Management Objects) per la creazione e la modifica delle rappresentazioni della prospettiva, vedere il codice sorgente dell'esempio Da AMO a tabulare.</span><span class="sxs-lookup"><span data-stu-id="5b5db-114">However, to have an understanding on how to use AMO to create and manipulate perspective representations see the source code of the AMO to Tabular sample.</span></span> <span data-ttu-id="5b5db-115">L'esempio è disponibile in Codeplex.</span><span class="sxs-lookup"><span data-stu-id="5b5db-115">The sample is available at Codeplex.</span></span> <span data-ttu-id="5b5db-116">Nota importante sul codice: il codice viene fornito solo come supporto ai concetti logici illustrati in questo argomento e non deve essere utilizzato in un ambiente di produzione né deve essere utilizzato per altro scopo se non quello formativo.</span><span class="sxs-lookup"><span data-stu-id="5b5db-116">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
