---
title: Rappresentazione della colonna calcolata (tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 190bfa92-2445-404d-86df-7cc94d283add
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1f7a56c01a1c4af7a2e618c6b6a6cb586424e639
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723140"
---
# <a name="calculated-column-representation-tabular"></a><span data-ttu-id="fd2aa-102">Rappresentazione della colonna calcolata (tabulare)</span><span class="sxs-lookup"><span data-stu-id="fd2aa-102">Calculated Column Representation (Tabular)</span></span>
  <span data-ttu-id="fd2aa-103">Una colonna calcolata è un'espressione DAX che crea una nuova colonna in una tabella e i valori ottenuti vengono archiviati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="fd2aa-103">A calculated column is DAX expression that creates a new column in a table and the obtained values are stored in the table.</span></span> <span data-ttu-id="fd2aa-104">L'espressione della colonna calcolata viene valutata ogni volta che la tabella viene elaborata.</span><span class="sxs-lookup"><span data-stu-id="fd2aa-104">The calculated column expression is evaluated every time the table is processed.</span></span>  
  
## <a name="calculated-column-representation"></a><span data-ttu-id="fd2aa-105">Rappresentazione della colonna calcolata</span><span class="sxs-lookup"><span data-stu-id="fd2aa-105">Calculated Column Representation</span></span>  
  
### <a name="calculated-columns-in-amo"></a><span data-ttu-id="fd2aa-106">Colonne calcolate in AMO</span><span class="sxs-lookup"><span data-stu-id="fd2aa-106">Calculated Columns in AMO</span></span>  
 <span data-ttu-id="fd2aa-107">Quando si utilizza AMO per gestire una tabella di modelli tabulari non c'è una corrispondenza dell'oggetto uno-a-uno per una colonna calcolata in AMO.</span><span class="sxs-lookup"><span data-stu-id="fd2aa-107">When using AMO to manage a tabular model table, there is no one-to-one object match for a calculated column in AMO.</span></span> <span data-ttu-id="fd2aa-108">Una colonna calcolata è rappresentata da un attributo in <xref:Microsoft.AnalysisServices.Dimension> e un attributo in <xref:Microsoft.AnalysisServices.MeasureGroup>.</span><span class="sxs-lookup"><span data-stu-id="fd2aa-108">A calculated column is represented by an attribute in <xref:Microsoft.AnalysisServices.Dimension> and an attribute in <xref:Microsoft.AnalysisServices.MeasureGroup>.</span></span>  
  
 <span data-ttu-id="fd2aa-109">Nel frammento di codice seguente viene illustrato come aggiungere una colonna calcolata a un modello tabulare esistente.</span><span class="sxs-lookup"><span data-stu-id="fd2aa-109">The following code snippet shows how to add a calculated column to an existing tabular model.</span></span> <span data-ttu-id="fd2aa-110">Nel codice si presuppone che si disponga di un oggetto di database AMO, newDatabase, e di un oggetto cubo AMO, modelCube.</span><span class="sxs-lookup"><span data-stu-id="fd2aa-110">The code assumes you have an AMO database object, newDatabase, and an AMO cube object, modelCube.</span></span>  
  
```  
  
private void addCalculatedColumn(  
                   AMO.Database newDatabase  
                 , AMO.Cube modelCube  
                 , String ccTableName  
                 , String ccName  
                 , String newCalculatedColumnExpression  
             )  
{  
    if (string.IsNullOrEmpty(ccName) || string.IsNullOrWhiteSpace(ccName))  
    {  
        MessageBox.Show(String.Format("Calculated Column name is not defined."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
    if (string.IsNullOrEmpty(newCalculatedColumnExpression) || string.IsNullOrWhiteSpace(newCalculatedColumnExpression))  
    {  
        MessageBox.Show(String.Format("Calculated Column expression is not defined."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (newDatabase.Dimensions[ccTableName].Attributes.Contains(ccName))  
    {  
        MessageBox.Show(String.Format("Calculated Column name already defined."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
    //Add CC attribute to the Dimension  
    AMO.Dimension dim = newDatabase.Dimensions[ccTableName];  
    AMO.DimensionAttribute currentAttribute = dim.Attributes.Add(ccName, ccName);  
    currentAttribute.Usage = AMO.AttributeUsage.Regular;  
    currentAttribute.KeyUniquenessGuarantee = false;  
  
    currentAttribute.KeyColumns.Add(new AMO.DataItem(ccTableName, ccName, OleDbType.Empty));  
    currentAttribute.KeyColumns[0].Source = new AMO.ExpressionBinding(newCalculatedColumnExpression);  
    currentAttribute.KeyColumns[0].NullProcessing = AMO.NullProcessing.Preserve;  
    currentAttribute.NameColumn = new AMO.DataItem(ccTableName, ccName, System.Data.OleDb.OleDbType.WChar);  
    currentAttribute.NameColumn.Source = new AMO.ExpressionBinding(newCalculatedColumnExpression);  
    currentAttribute.NameColumn.NullProcessing = AMO.NullProcessing.ZeroOrBlank;  
  
    currentAttribute.OrderBy = AMO.OrderBy.Key;  
    AMO.AttributeRelationship currentAttributeRelationship = dim.Attributes["RowNumber"].AttributeRelationships.Add(currentAttribute.ID);  
    currentAttributeRelationship.Cardinality = AMO.Cardinality.Many;  
    currentAttributeRelationship.OverrideBehavior = AMO.OverrideBehavior.None;  
  
    //Add CC as attribute to the MG  
    AMO.MeasureGroup mg = modelCube.MeasureGroups[ccTableName];  
    AMO.DegenerateMeasureGroupDimension currentMGDim = (AMO.DegenerateMeasureGroupDimension)mg.Dimensions[ccTableName];  
    AMO.MeasureGroupAttribute mga = new AMO.MeasureGroupAttribute(ccName);  
  
    mga.KeyColumns.Add(new AMO.DataItem(ccTableName, ccName, OleDbType.Empty));  
    mga.KeyColumns[0].Source = new AMO.ExpressionBinding(newCalculatedColumnExpression);  
  
    currentMGDim.Attributes.Add(mga);  
  
    try  
    {  
        //Update Dimension, CubeDimension and MG in server  
        newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
    }  
    catch (AMO.OperationException amoOpXp)  
    {  
        MessageBox.Show(String.Format("Calculated Column expression contains syntax errors, or references undefined or missspelled elements.\nError message: {0}", amoOpXp.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        return;  
    }  
    catch (AMO.AmoException amoXp)  
    {  
        MessageBox.Show(String.Format("AMO exception accessing the server.\nError message: {0}", amoXp.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        return;  
    }  
    catch (Exception)  
    {  
        throw;  
    }  
}  
  
```  
  
  
