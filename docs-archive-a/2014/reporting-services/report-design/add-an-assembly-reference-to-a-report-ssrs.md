---
title: Aggiungere un riferimento a un assembly in un report (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom assemblies [Reporting Services], referencing
- custom code [Reporting Services]
- adding assembly references
- assemblies [Reporting Services], references
ms.assetid: 0a03939e-48ce-4c30-b227-98533f2e0ccb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23dda0c65589e55849f906c621e42ce70f0d7ab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635428"
---
# <a name="add-an-assembly-reference-to-a-report-ssrs"></a><span data-ttu-id="466a6-102">Aggiungere un riferimento a un assembly in un report (SSRS)</span><span class="sxs-lookup"><span data-stu-id="466a6-102">Add an Assembly Reference to a Report (SSRS)</span></span>
  <span data-ttu-id="466a6-103">Quando si incorpora codice personalizzato contenente riferimenti alle classi [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] che non sono in <xref:System.Math> o <xref:System.Convert>, è necessario fornire un riferimento all'assembly nel report in modo che il componente Elaborazione report possa risolvere i nomi.</span><span class="sxs-lookup"><span data-stu-id="466a6-103">When you embed custom code that contains references to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that are not in <xref:System.Math> or <xref:System.Convert>, you must provide an assembly reference to the report so that the report processor can resolve the names.</span></span> <span data-ttu-id="466a6-104">Per altre informazioni, vedere [Aggiungere codice a un report &#40;SSRS&#41;](add-code-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="466a6-104">For more information, see [Add Code to a Report &#40;SSRS&#41;](add-code-to-a-report-ssrs.md).</span></span>  
  
### <a name="to-add-an-assembly-reference-to-a-report"></a><span data-ttu-id="466a6-105">Per aggiungere un riferimento a un assembly in un report</span><span class="sxs-lookup"><span data-stu-id="466a6-105">To add an assembly reference to a report</span></span>  
  
1.  <span data-ttu-id="466a6-106">Nella visualizzazione **Progettazione** fare clic con il pulsante destro del mouse nell'area di progettazione all'esterno del bordo del report e scegliere **Proprietà report**.</span><span class="sxs-lookup"><span data-stu-id="466a6-106">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="466a6-107">Fare clic su **Riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="466a6-107">Click **References**.</span></span>  
  
3.  <span data-ttu-id="466a6-108">In **Aggiungi o rimuovi assembly**fare clic su **Aggiungi** e quindi fare clic sul pulsante con i puntini di sospensione per passare all'assembly.</span><span class="sxs-lookup"><span data-stu-id="466a6-108">In **Add or remove assemblies**, click **Add** and then click the ellipsis button to browse to the assembly.</span></span>  
  
4.  <span data-ttu-id="466a6-109">In **Aggiungi o rimuovi assembly**fare clic su **Aggiungi** e quindi digitare il nome della classe e specificare un nome di istanza da usare nel report.</span><span class="sxs-lookup"><span data-stu-id="466a6-109">In **Add or remove classes**, click **Add** and then type name of the class and provide an instance name to use within the report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="466a6-110">Specificare il nome di una classe e il nome di un'istanza solo per i membri basati sulle istanze.</span><span class="sxs-lookup"><span data-stu-id="466a6-110">Specify a class and instance name only for instance-based members.</span></span> <span data-ttu-id="466a6-111">Non specificare membri statici nell'elenco **Classi** .</span><span class="sxs-lookup"><span data-stu-id="466a6-111">Do not specify static members in the **Classes** list.</span></span> <span data-ttu-id="466a6-112">Per altre informazioni, vedere [Riferimenti a codice personalizzato e ad assembly in espressioni in Progettazione report &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)sottostante.</span><span class="sxs-lookup"><span data-stu-id="466a6-112">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="466a6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="466a6-113">See Also</span></span>  
 <span data-ttu-id="466a6-114">[Utilizzo di assembly personalizzati con i report](../custom-assemblies/using-custom-assemblies-with-reports.md) </span><span class="sxs-lookup"><span data-stu-id="466a6-114">[Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md) </span></span>  
 [<span data-ttu-id="466a6-115">Finestra di dialogo Proprietà report, Riferimenti</span><span class="sxs-lookup"><span data-stu-id="466a6-115">Report Properties Dialog Box, References</span></span>](../report-properties-dialog-box-references.md)  
  
  
