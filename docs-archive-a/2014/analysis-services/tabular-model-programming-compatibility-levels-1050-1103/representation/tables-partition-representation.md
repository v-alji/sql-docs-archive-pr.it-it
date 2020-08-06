---
title: Rappresentazione di una partizione (tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: b606cd63-755c-4ac0-b19b-95b5363afbdf
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6a29f273a584f3e60c6cf6458751965158cf8704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723116"
---
# <a name="partition-representation-tabular"></a><span data-ttu-id="6f7b5-102">Rappresentazione di una partizione (tabulare)</span><span class="sxs-lookup"><span data-stu-id="6f7b5-102">Partition Representation (Tabular)</span></span>
  <span data-ttu-id="6f7b5-103">Per scopi operativi una tabella può essere divisa in diversi subset di righe che, quando vengono combinate formano la tabella. Ognuno di tali subset è una partizione della tabella.</span><span class="sxs-lookup"><span data-stu-id="6f7b5-103">For operational purposes, a table can be divided in different subsets of rows that when combined together form the table; each of those subsets is a partition of the table.</span></span>  
  
## <a name="partition-representation"></a><span data-ttu-id="6f7b5-104">Rappresentazione di una partizione</span><span class="sxs-lookup"><span data-stu-id="6f7b5-104">Partition Representation</span></span>  
 <span data-ttu-id="6f7b5-105">In termini di oggetti AMO, una rappresentazione di partizione dispone di una relazione di mapping uno-a-uno con <xref:Microsoft.AnalysisServices.Partition> e non sono richiesti altri oggetti AMO principali.</span><span class="sxs-lookup"><span data-stu-id="6f7b5-105">In terms of AMO objects a partition representation has a one to one mapping relationship with <xref:Microsoft.AnalysisServices.Partition> and no other main AMO objects are required</span></span>  
  
### <a name="partition-in-amo"></a><span data-ttu-id="6f7b5-106">Partizione in AMO</span><span class="sxs-lookup"><span data-stu-id="6f7b5-106">Partition in AMO</span></span>  
 <span data-ttu-id="6f7b5-107">In caso di utilizzo di AMO per gestire una partizione, è necessario trovare il gruppo di misure che rappresenta la tabella di modelli tabulari e operare iniziando da tale ambito.</span><span class="sxs-lookup"><span data-stu-id="6f7b5-107">When using AMO to manage a partition in a you need to find the measure group that represents the Tabular Model table and work from there.</span></span>  
  
 <span data-ttu-id="6f7b5-108">Nel frammento di codice seguente viene illustrato come aggiungere una partizione a una tabella di modelli tabulari esistente.</span><span class="sxs-lookup"><span data-stu-id="6f7b5-108">The following code snippet shows how to add a partition to an existing tabular model table.</span></span>  
  
```  
  
private void AddPartition(  
                     AMO.Cube modelCube  
                  ,  AMO.DataSource newDatasource  
                  ,  string mgName  
                  ,  string newPartitionName  
                  , string partitionSelectStatement  
                  , Boolean processPartition  
             )  
{  
    mgName = mgName.Trim();  
    newPartitionName = newPartitionName.Trim();  
    partitionSelectStatement = partitionSelectStatement.Trim();  
    //Validate Input  
    if (string.IsNullOrEmpty(newPartitionName) || string.IsNullOrWhiteSpace(newPartitionName))  
    {  
        MessageBox.Show(String.Format("Partition Name cannot be empty or blank"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (modelCube.MeasureGroups[mgName].Partitions.ContainsName(newPartitionName))  
    {  
        MessageBox.Show(String.Format("Partition Name already defined. Duplicated names are not allowed"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (string.IsNullOrEmpty(partitionSelectStatement) || string.IsNullOrWhiteSpace(partitionSelectStatement))  
    {  
        MessageBox.Show(String.Format("Select statement cannot be empty or blank"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    //Input validated  
    string partitionID = newPartitionName; //Using partition name as the ID  
    AMO.Partition currentPartition = new AMO.Partition(partitionID, partitionID);  
    currentPartition.StorageMode = AMO.StorageMode.InMemory;  
    currentPartition.ProcessingMode = AMO.ProcessingMode.Regular;  
    currentPartition.Source = new AMO.QueryBinding(newDatasource.ID, partitionSelectStatement);  
    modelCube.MeasureGroups[mgName].Partitions.Add(currentPartition);  
    try  
    {  
        modelCube.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
        if (processPartition)  
        {  
            modelCube.MeasureGroups[mgName].Partitions[partitionID].Process(AMO.ProcessType.ProcessFull);  
            MessageBox.Show(String.Format("Partition successfully processed."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
        }  
  
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
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="6f7b5-109">Esempio AMO2Tabular</span><span class="sxs-lookup"><span data-stu-id="6f7b5-109">AMO2Tabular sample</span></span>  
 <span data-ttu-id="6f7b5-110">Per comprendere tuttavia la modalità di utilizzo di AMO (Analysis Management Objects) per creare e modificare le rappresentazioni della partizione, vedere il codice sorgente dell'esempio AMO to Tabular.</span><span class="sxs-lookup"><span data-stu-id="6f7b5-110">However, to have an understanding on how to use AMO to create and manipulate partition representations see the source code of the AMO to Tabular sample.</span></span> <span data-ttu-id="6f7b5-111">L'esempio è disponibile in Codeplex.</span><span class="sxs-lookup"><span data-stu-id="6f7b5-111">The sample is available at Codeplex.</span></span> <span data-ttu-id="6f7b5-112">Nota importante sul codice: il codice viene fornito solo come supporto ai concetti logici illustrati in questo argomento e non deve essere utilizzato in un ambiente di produzione né deve essere utilizzato per altro scopo se non quello formativo.</span><span class="sxs-lookup"><span data-stu-id="6f7b5-112">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
