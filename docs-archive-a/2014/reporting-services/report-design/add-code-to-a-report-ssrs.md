---
title: Aggiungere codice a un report (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom code [Reporting Services]
- expressions [Reporting Services], code
- adding code
- reports [Reporting Services], code
ms.assetid: 00ef8fc6-99fe-49b2-8a22-7eb475881dc4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c1964e69d00e1a27da29ce8cfb73b7bee1bece7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717519"
---
# <a name="add-code-to-a-report-ssrs"></a><span data-ttu-id="93bb0-102">Aggiungere codice a un report (SSRS)</span><span class="sxs-lookup"><span data-stu-id="93bb0-102">Add Code to a Report (SSRS)</span></span>
  <span data-ttu-id="93bb0-103">In qualsiasi espressione, è possibile chiamare un codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="93bb0-103">In any expression, you can call your own custom code.</span></span> <span data-ttu-id="93bb0-104">Il codice può essere fornito nei due modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="93bb0-104">You can provide code in the following two ways:</span></span>  
  
-   <span data-ttu-id="93bb0-105">Codice scritto in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] direttamente incorporato nel report.</span><span class="sxs-lookup"><span data-stu-id="93bb0-105">Embed code written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] directly in your report.</span></span> <span data-ttu-id="93bb0-106">Se il codice si riferisce a un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] che non è <xref:System.Math> o <xref:System.Convert>, è necessario aggiungere il riferimento al report.</span><span class="sxs-lookup"><span data-stu-id="93bb0-106">If your code refers to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that is not <xref:System.Math> or <xref:System.Convert>, you must add the reference to the report.</span></span> <span data-ttu-id="93bb0-107">Per altre informazioni, vedere [Aggiungere un riferimento a un assembly in un report &#40;SSRS&#41;](add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="93bb0-107">For more information, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](add-an-assembly-reference-to-a-report-ssrs.md).</span></span> <span data-ttu-id="93bb0-108">Per altre informazioni sugli altri riferimenti che è possibile creare a partire dal codice, vedere [Riferimenti a codice personalizzato e ad assembly in espressioni in Progettazione report &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="93bb0-108">For more information about other references you can make from your code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
-   <span data-ttu-id="93bb0-109">Fornire un assembly di codice personalizzato mediante [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93bb0-109">Provide a custom code assembly by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="93bb0-110">L'eventuale assembly personalizzato dovrà essere installato sia nel computer in cui viene creato il report sia nel server di report in cui viene visualizzato il report.</span><span class="sxs-lookup"><span data-stu-id="93bb0-110">If you provide a custom assembly, you must install it on both the computer where you author the report and the report server where you view the report.</span></span> <span data-ttu-id="93bb0-111">Per altre informazioni, vedere [Utilizzo di assembly personalizzati con i report](../custom-assemblies/using-custom-assemblies-with-reports.md).</span><span class="sxs-lookup"><span data-stu-id="93bb0-111">For more information, see [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md).</span></span>  
  
### <a name="to-add-embedded-code-to-a-report"></a><span data-ttu-id="93bb0-112">Per aggiungere codice incorporato a un report</span><span class="sxs-lookup"><span data-stu-id="93bb0-112">To add embedded code to a report</span></span>  
  
1.  <span data-ttu-id="93bb0-113">Nella visualizzazione **Progettazione** fare clic con il pulsante destro del mouse nell'area di progettazione all'esterno del bordo del report e scegliere **Proprietà report**.</span><span class="sxs-lookup"><span data-stu-id="93bb0-113">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="93bb0-114">Fare clic su **Codice**.</span><span class="sxs-lookup"><span data-stu-id="93bb0-114">Click **Code**.</span></span>  
  
3.  <span data-ttu-id="93bb0-115">Digitare il codice in **Codice personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="93bb0-115">In **Custom code**, type the code.</span></span> <span data-ttu-id="93bb0-116">Eventuali errori nel codice genereranno avvisi durante l'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="93bb0-116">Errors in the code produce warnings when the report runs.</span></span> <span data-ttu-id="93bb0-117">L'esempio seguente crea una funzione personalizzata denominata `ChangeWord` che sostituisce la parola "`Bike`" con "`Bicycle`".</span><span class="sxs-lookup"><span data-stu-id="93bb0-117">The following example creates a custom function named `ChangeWord` that replaces the word "`Bike`" with "`Bicycle`".</span></span>  
  
    ```  
    Public Function ChangeWord(ByVal s As String) As String  
       Dim strBuilder As New System.Text.StringBuilder(s)  
       If s.Contains("Bike") Then  
          strBuilder.Replace("Bike", "Bicycle")  
          Return strBuilder.ToString()  
          Else : Return s  
       End If  
    End Function  
    ```  
  
4.  <span data-ttu-id="93bb0-118">Nell'esempio seguente verrà illustrato come passare un campo del set di dati denominato Category a questa funzione in un'espressione:</span><span class="sxs-lookup"><span data-stu-id="93bb0-118">The following example shows how to pass a dataset field named Category to this function in an expression:</span></span>  
  
    ```  
    =Code.ChangeWord(Fields!Category.Value)  
    ```  
  
     <span data-ttu-id="93bb0-119">Se si aggiunge questa espressione a una cella della tabella in cui sono visualizzati i valori della categoria, ogni qualvolta la parola "Bike" è nel campo del set di dati per la riga, nella cella della tabella viene visualizzata invece la parola "Bicycle".</span><span class="sxs-lookup"><span data-stu-id="93bb0-119">If you add this expression to a table cell that displays category values, whenever the word "Bike" is in the dataset field for that row, the table cell value displays the word "Bicycle" instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93bb0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93bb0-120">See Also</span></span>  
 <span data-ttu-id="93bb0-121">[Finestra di dialogo Proprietà report, Codice](../report-properties-dialog-box-code.md) </span><span class="sxs-lookup"><span data-stu-id="93bb0-121">[Report Properties Dialog Box, Code](../report-properties-dialog-box-code.md) </span></span>  
 <span data-ttu-id="93bb0-122">[Esempi di espressioni &#40;Generatore report e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="93bb0-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="93bb0-123">Riferimenti alla raccolta dei parametri &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="93bb0-123">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
