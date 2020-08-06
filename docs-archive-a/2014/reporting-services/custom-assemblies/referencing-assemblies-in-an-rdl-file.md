---
title: Riferimento agli assembly in un file RDL| Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- RDL [Reporting Services], referencing assemblies
- referencing custom assemblies
- custom assemblies [Reporting Services], referencing
- Report Definition Language, referencing assemblies
- report definition files [Reporting Services]
ms.assetid: 9a48e552-7d47-4243-9be1-894990c506d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 14593717d2319d7d702fd0c414e0c24428006f51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712823"
---
# <a name="referencing-assemblies-in-an-rdl-file"></a><span data-ttu-id="e2efa-102">Impostazione di un riferimento agli assembly in un file RDL</span><span class="sxs-lookup"><span data-stu-id="e2efa-102">Referencing Assemblies in an RDL File</span></span>
  <span data-ttu-id="e2efa-103">Per supportare l'uso di assembly di codice personalizzati nei file di definizione report, nella specifica RDL (Report Definition Language) sono inclusi due elementi RDL, ovvero l'elemento **CodeModules** e l'elemento **Classes**.</span><span class="sxs-lookup"><span data-stu-id="e2efa-103">To support the use of custom code assemblies in report definition files, two Report Definition Language (RDL) elements are included in the RDL specification: the **CodeModules** element and the **Classes** element.</span></span>  
  
 <span data-ttu-id="e2efa-104">L'elemento **CodeModules** consente di fare riferimento agli assembly di codice gestito nelle espressioni di report.</span><span class="sxs-lookup"><span data-stu-id="e2efa-104">The **CodeModules** element enables you to refer to managed code assemblies in report expressions.</span></span> <span data-ttu-id="e2efa-105">**CodeModules** è un elemento di livello principale che contiene il riferimento all'assembly usato nei file di definizione report per chiamare funzioni specializzate.</span><span class="sxs-lookup"><span data-stu-id="e2efa-105">**CodeModules** is a top-level element that contains the reference to the assembly that you use in your report definition files to call specialized functions.</span></span> <span data-ttu-id="e2efa-106">Una voce in una definizione del report che supporta l'utilizzo di un assembly personalizzato può essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e2efa-106">An entry in a report definition that supports the use of a custom assembly might look like the following:</span></span>  
  
```  
<CodeModules>  
   <CodeModule>CurrencyConversion, Version=1.0.1363.31103, Culture=neutral, PublicKeyToken=null</CodeModule>  
</CodeModules>  
```  
  
 <span data-ttu-id="e2efa-107">Anziché chiamare <xref:System.Reflection.Assembly.Load%2A> dal codice personalizzato, registrare gli assembly personalizzati aggiungendo manualmente elementi **CodeModule** al file RDL o usando la scheda **Riferimenti** della finestra di dialogo **Proprietà report**.</span><span class="sxs-lookup"><span data-stu-id="e2efa-107">Instead of calling <xref:System.Reflection.Assembly.Load%2A> from your custom code, register your custom assemblies by either manually adding **CodeModule** elements to your RDL file or by using the **References** tab of the **Report Properties** dialog.</span></span> <span data-ttu-id="e2efa-108">Per altre informazioni, vedere [Riferimenti a codice personalizzato e ad assembly in espressioni in Progettazione report &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)sottostante.</span><span class="sxs-lookup"><span data-stu-id="e2efa-108">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
 <span data-ttu-id="e2efa-109">L'elemento **Classes** supporta l'uso di membri di istanza in una definizione del report.</span><span class="sxs-lookup"><span data-stu-id="e2efa-109">The **Classes** element supports the use of instance members in a report definition.</span></span> <span data-ttu-id="e2efa-110">**Classes** è un elemento di livello principale che contiene un riferimento al nome della classe e un nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="e2efa-110">**Classes** is a top-level element that contains a reference to the class name and an instance name.</span></span> <span data-ttu-id="e2efa-111">Una voce in una definizione del report che supporta l'utilizzo di membri dell'istanza può essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="e2efa-111">An entry in a report definition that supports the use of instance members might look like the following:</span></span>  
  
```  
<Classes>  
   <Class>  
      <ClassName>CurrencyConversion.DollarCurrencyConversion</ClassName>  
      <InstanceName>m_myDollarConversion</InstanceName>  
   </Class>  
</Classes>  
```  
  
 <span data-ttu-id="e2efa-112">Per altre informazioni, vedere [Accesso agli assembly personalizzati tramite espressioni](accessing-custom-assemblies-through-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e2efa-112">For more information, see [Accessing Custom Assemblies Through Expressions](accessing-custom-assemblies-through-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2efa-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2efa-113">See Also</span></span>  
 [<span data-ttu-id="e2efa-114">Utilizzo di assembly personalizzati con i report</span><span class="sxs-lookup"><span data-stu-id="e2efa-114">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
