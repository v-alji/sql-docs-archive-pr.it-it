---
title: Rappresentazione dell'indicatore di prestazioni chiave (tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 8d3d949e-5d43-4d2e-9dc8-48d182a7a935
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7cc9ec7e6ccae664a6f608c350483ae9744fb49d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723135"
---
# <a name="key-performance-indicator-representation-tabular"></a><span data-ttu-id="45d9f-102">Rappresentazione dell'indicatore di prestazioni chiave (tabulare)</span><span class="sxs-lookup"><span data-stu-id="45d9f-102">Key Performance Indicator Representation (Tabular)</span></span>
  <span data-ttu-id="45d9f-103">Un indicatore KPI viene utilizzato per misurare le prestazioni di un valore, definito mediante una misura di base, rispetto a un valore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="45d9f-103">A KPI is used to gauge performance of a value, defined by a Base measure, against a Target value</span></span>  
  
## <a name="key-performance-indicator-representation"></a><span data-ttu-id="45d9f-104">Rappresentazione dell'indicatore di prestazioni chiave</span><span class="sxs-lookup"><span data-stu-id="45d9f-104">Key Performance Indicator Representation</span></span>  
 <span data-ttu-id="45d9f-105">Nei modelli a oggetti tabulari un indicatore di prestazioni chiave-KPI è una misura con informazioni aggiuntive che l'applicazione client deve visualizzare graficamente.</span><span class="sxs-lookup"><span data-stu-id="45d9f-105">In tabular object models a key performance indicator -kpi- is a measure with additional information for the client application to display it graphically.</span></span> <span data-ttu-id="45d9f-106">Un indicatore KPI dispone in genere di informazioni su un obiettivo da raggiungere e sullo stato della misura confrontato con l'obiettivo nonché di informazioni per lo strumento client sulla visualizzazione grafica dello stato.</span><span class="sxs-lookup"><span data-stu-id="45d9f-106">A kpi usually has information about a goal to be obtained, the status of the measure compared to a the goal, and information for the client tool on how to display graphically the status.</span></span>  
  
### <a name="key-performance-indicator-in-amo"></a><span data-ttu-id="45d9f-107">Indicatore di prestazioni chiave in AMO</span><span class="sxs-lookup"><span data-stu-id="45d9f-107">Key Performance Indicator in AMO</span></span>  
 <span data-ttu-id="45d9f-108">Se si utilizza AMO per gestire un indicatore di prestazioni chiave (KPI) in un modello tabulare, non vi è corrispondenza di oggetti uno-a-uno per un indicatore KPI in AMO, l'oggetto <xref:Microsoft.AnalysisServices.Kpi> AMO non viene utilizzato per questo scopo; in AMO, per i modelli tabulari, un indicatore KPI è rappresentato il da una serie di oggetti creata in uno degli elementi nella raccolta <xref:Microsoft.AnalysisServices.MdxScript.Commands%2A> e nell'oggetto <xref:Microsoft.AnalysisServices.MdxScript.CalculationProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="45d9f-108">When using AMO to manage a Tabular Model kpi there is no one-to-one object match for a kpi in AMO, the AMO <xref:Microsoft.AnalysisServices.Kpi>object is not used for this purpose; in AMO, for tabular models, a kpi is represented the by a series of objects created in one of the elements in the <xref:Microsoft.AnalysisServices.MdxScript.Commands%2A> collection and in the <xref:Microsoft.AnalysisServices.MdxScript.CalculationProperties%2A>.</span></span>  
  
 <span data-ttu-id="45d9f-109">Nel frammento di codice seguente viene mostrato come creare una di molte possibili definizioni KPI.</span><span class="sxs-lookup"><span data-stu-id="45d9f-109">The following code snippet shows how to create one of many possible kpi definitions.</span></span>  
  
```  
  
private void addStaticKPI(object sender, EventArgs e)  
{  
    double KPIGoal = 0, status1ThresholdValue = 0, status2ThresholdValue = 0  
        , redAreaValue = 0, yellowAreaValue = 0, greenAreaValue = 0;  
    string clientStatusGraphicImageName = "Three Circles Colored";  
  
    //Verify input requirements  
    //Goal values  
    if (staticTargetKPI.Checked)  
    {//Static KPI Goal selected  
        if (string.IsNullOrEmpty(staticTargetKPIGoal.Text)  
            || string.IsNullOrWhiteSpace(staticTargetKPIGoal.Text)  
            || !double.TryParse(staticTargetKPIGoal.Text, out KPIGoal))  
        {  
            MessageBox.Show(String.Format("Static Goal is not defined or is not a valid number."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
            return;  
        }  
    }  
    else  
    {//Measure KPI Goal selected  
        if (!TargetMeasureForKPISelected)  
        {  
            MessageBox.Show(String.Format("Measure Goal is not selected."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
            return;  
        }  
    }  
  
    //Status  
    if (string.IsNullOrEmpty(firstStatusThresholdValue.Text)  
        || string.IsNullOrWhiteSpace(firstStatusThresholdValue.Text)  
        || !double.TryParse(firstStatusThresholdValue.Text, out status1ThresholdValue)  
        || string.IsNullOrEmpty(secondStatusThresholdValue.Text)  
        || string.IsNullOrWhiteSpace(secondStatusThresholdValue.Text)  
        || !double.TryParse(secondStatusThresholdValue.Text, out status2ThresholdValue))  
    {  
        MessageBox.Show(String.Format("Status Threshold are not defined or they are not a valid number."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    if (string.IsNullOrEmpty(statusValueRedArea.Text)  
        || string.IsNullOrWhiteSpace(statusValueRedArea.Text)  
        || !double.TryParse(statusValueRedArea.Text, out redAreaValue)  
        || string.IsNullOrEmpty(statusValueYellowArea.Text)  
        || string.IsNullOrWhiteSpace(statusValueYellowArea.Text)  
        || !double.TryParse(statusValueYellowArea.Text, out yellowAreaValue)  
        || string.IsNullOrEmpty(statusValueGreenArea.Text)  
        || string.IsNullOrWhiteSpace(statusValueGreenArea.Text)  
        || !double.TryParse(statusValueGreenArea.Text, out greenAreaValue))  
    {  
        MessageBox.Show(String.Format("Status Area values are not defined or they are not a valid number."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    //Set working variables  
    string kpiTableName = ((DataRowView)MeasuresInModelList.CheckedItems[0])[0].ToString();  
    string kpiMeasureName = ((DataRowView)MeasuresInModelList.CheckedItems[0])[1].ToString();  
  
    //Verify if KPI is already defined  
    if (modelCube.MdxScripts["MdxScript"].CalculationProperties.Contains(string.Format("KPIs.[{0}]", kpiMeasureName)))  
    {  
        //ToDo: Verify with the user if wants to update KPI or exit  
        //If user wants to update then remove KPI from mdxScripts and continue with the creating the KPI  
        //  
        // Until the code to remove KPI is finished we'll have to exit with a message of no duplicated KPIs are allowed  
        MessageBox.Show(String.Format("Another KPI exists for the same measeure."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
        return;  
    }  
  
    StringBuilder kpiCommand = new StringBuilder();  
  
    AMO.MdxScript mdxScript = modelCube.MdxScripts["MdxScript"];  
    kpiCommand.Append(mdxScript.Commands[1].Text);  
  
    string goalExpression;  
    if (staticTargetKPI.Checked)  
    {//Static KPI Goal selected  
        goalExpression = KPIGoal.ToString();  
    }  
    else  
    {//Measure KPI Goal selected  
        string measureGoalMeasureName = ((DataRowView)KpiTargetMeasures.CheckedItems[0])[1].ToString();  
        goalExpression = string.Format("[Measures].[{0}]", measureGoalMeasureName);  
    }  
  
    kpiCommand.AppendLine(string.Format("CREATE MEMBER CURRENTCUBE.Measures.[_{1} Goal] AS '{2}', ASSOCIATED_MEASURE_GROUP = '{0}';"  
            , kpiTableName, kpiMeasureName, goalExpression));  
  
    string statusExpression;  
    if (staticTargetKPI.Checked)  
    {//Static KPI Goal selected  
        statusExpression = string.Format("KpiValue(\"{0}\")", kpiMeasureName).Trim();  
    }  
    else  
    {//Measure KPI Goal selected  
        string measureGoalMeasureName = ((DataRowView)KpiTargetMeasures.CheckedItems[0])[1].ToString().Trim();  
  
        string M = string.Format("[Measures].[{0}]", kpiMeasureName);  
        string T = string.Format("[Measures].[{0}]", measureGoalMeasureName);  
  
        if (KpiRelationDifference.Checked)  
        {  
            statusExpression = string.Format("{1} - {0}", M, T);  
        }  
        else  
        {  
            if (KpiRelationRatioMT.Checked)  
            {  
                statusExpression = string.Format("{0} / {1}", M, T);  
            }  
            else  
            {  
                statusExpression = string.Format("{1} / {0}", M, T);  
            }  
        }  
    }  
    kpiCommand.AppendLine(string.Format("CREATE MEMBER CURRENTCUBE.Measures.[_{1} Status] "  
                                              + " AS 'Case When IsEmpty({9}) Then Null "  
                                                       + " When ({9}) {2} {3} Then {4} "  
                                                       + " When ({9}) {5} {6} Then {7} "  
                                                       + " Else {8} End'"  
                                              + ", ASSOCIATED_MEASURE_GROUP = '{0}';"  
        , kpiTableName, kpiMeasureName // 0, 1  
        , statusThreshold1ComparisonOperator.Text, status1ThresholdValue, redAreaValue // 2, 3, 4  
        , statusThreshold2ComparisonOperator.Text, status2ThresholdValue, yellowAreaValue, greenAreaValue // 5, 6, 7, 8  
        , statusExpression // 9  
        ));  
  
    kpiCommand.AppendLine(string.Format("CREATE MEMBER CURRENTCUBE.Measures.[_{1} Trend] AS '0', ASSOCIATED_MEASURE_GROUP = '{0}';"  
        , kpiTableName, kpiMeasureName));  
  
    kpiCommand.AppendLine(string.Format("CREATE KPI CURRENTCUBE.[{1}] AS Measures.[{1}]"  
                                               + ", ASSOCIATED_MEASURE_GROUP = '{0}'"  
                                               + ", GOAL = Measures.[_{1} Goal]"  
                                               + ", STATUS = Measures.[_{1} Status]"  
                                               + ", TREND = Measures.[_{1} Trend]"  
                                               + ", STATUS_GRAPHIC = '{2}'"  
                                               + ", TREND_GRAPHIC = '{2}';"  
        , kpiTableName, kpiMeasureName, clientStatusGraphicImageName));  
  
    {//Adding Calculation Reference for the Measure itself  
        if (!mdxScript.CalculationProperties.Contains(kpiMeasureName))  
        {  
            AMO.CalculationProperty cp = new AMO.CalculationProperty(kpiMeasureName, AMO.CalculationType.Member);  
            cp.FormatString = ""; // ToDo: Get formatting attributes for the member  
            cp.Visible = true;  
            mdxScript.CalculationProperties.Add(cp);  
        }  
    }  
    {//Adding Calculation Reference for the Goal measure  
        AMO.CalculationProperty cp = new AMO.CalculationProperty(string.Format("Measures.[_{0} Goal]", kpiMeasureName), AMO.CalculationType.Member);  
        cp.FormatString = ""; // ToDo: Get formatting attributes for the member  
        cp.Visible = false;  
        mdxScript.CalculationProperties.Add(cp);  
    }  
  
    {//Adding Calculation Reference for the Status measure  
        AMO.CalculationProperty cp = new AMO.CalculationProperty(string.Format("Measures.[_{0} Status]", kpiMeasureName), AMO.CalculationType.Member);  
        cp.FormatString = ""; // ToDo: Get formatting attributes for the member  
        cp.Visible = false;  
        mdxScript.CalculationProperties.Add(cp);  
    }  
  
    {//Adding Calculation Reference for the Status measure  
        AMO.CalculationProperty cp = new AMO.CalculationProperty(string.Format("Measures.[_{0} Trend]", kpiMeasureName), AMO.CalculationType.Member);  
        cp.FormatString = ""; // ToDo: Get formatting attributes for the member  
        cp.Visible = false;  
        mdxScript.CalculationProperties.Add(cp);  
    }  
  
    {//Adding Calculation Reference for the KPI  
        AMO.CalculationProperty cp = new AMO.CalculationProperty(string.Format("KPIs.[{0}]", kpiMeasureName), AMO.CalculationType.Member);  
        cp.FormatString = ""; // ToDo: Get formatting attributes for the member  
        cp.Visible = true;  
        mdxScript.CalculationProperties.Add(cp);  
    }  
    try  
    {                  
        newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
        MessageBox.Show(String.Format("KPI successfully defined."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
    }  
    catch (AMO.OperationException amoOperationException)  
    {  
        //ToDo: remove anything left in mdxScript up to the point where the exception was thrown  
        MessageBox.Show(String.Format("Error creating KPI for Measure '{0}'[{1}]\nError message: {2}", kpiTableName, kpiMeasureName, amoOperationException.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
    }  
  
}  
  
```  
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="45d9f-110">Esempio AMO2Tabular</span><span class="sxs-lookup"><span data-stu-id="45d9f-110">AMO2Tabular sample</span></span>  
 <span data-ttu-id="45d9f-111">Per comprendere la modalità di utilizzo di AMO per la creazione e la gestione delle rappresentazioni dell'indicatore di prestazioni di chiave, vedere il codice sorgente dell'esempio Da AMO a tabulare. In particolare effettuare un controllo nel seguente file di origine: AddKPIs.cs.</span><span class="sxs-lookup"><span data-stu-id="45d9f-111">To have an understanding on how to use AMO to create and manipulate Key Performance Indicator representations see the source code of the AMO to Tabular sample; specifically check in the following source file: AddKPIs.cs.</span></span> <span data-ttu-id="45d9f-112">L'esempio è disponibile in Codeplex.</span><span class="sxs-lookup"><span data-stu-id="45d9f-112">The sample is available at Codeplex.</span></span> <span data-ttu-id="45d9f-113">Nota importante sul codice: il codice viene fornito solo come supporto ai concetti logici illustrati in questo argomento e non deve essere utilizzato in un ambiente di produzione né deve essere utilizzato per altro scopo se non quello formativo.</span><span class="sxs-lookup"><span data-stu-id="45d9f-113">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
