---
title: Utilizzo di variabili e parametri (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [MDX]
- queries [MDX], variables
- queries [MDX], parameters
- variables [MDX]
ms.assetid: a4754d16-d9c4-49f6-9be0-392180b912e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd01cf78ea5e3284aa51cad7dc848176a5dc9298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721888"
---
# <a name="using-variables-and-parameters-mdx"></a><span data-ttu-id="a1355-102">Utilizzo di variabili e parametri (MDX)</span><span class="sxs-lookup"><span data-stu-id="a1355-102">Using Variables and Parameters (MDX)</span></span>
  <span data-ttu-id="a1355-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] è possibile parametrizzare un'istruzione MDX (Multidimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="a1355-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], you can parameterize a Multidimensional Expressions (MDX) statement.</span></span> <span data-ttu-id="a1355-104">Un'istruzione parametrizzata consente di creare istruzioni generiche che possono essere personalizzate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a1355-104">A parameterized statement lets you create generic statements that can be customized at runtime.</span></span>  
  
 <span data-ttu-id="a1355-105">Durante la creazione di un'istruzione parametrizzata, il nome del parametro viene identificato aggiungendovi come prefisso il simbolo chiocciola (@).</span><span class="sxs-lookup"><span data-stu-id="a1355-105">In creating a parameterized statement, you identify the parameter name by prefixing the name with the at sign (@).</span></span> <span data-ttu-id="a1355-106">Ad esempio, @Year sarebbe un nome di parametro valido</span><span class="sxs-lookup"><span data-stu-id="a1355-106">For example, @Year would be a valid parameter name</span></span>  
  
 <span data-ttu-id="a1355-107">MDX supporta i parametri solo per valori letterali o scalari.</span><span class="sxs-lookup"><span data-stu-id="a1355-107">MDX supports only parameters for literal or scalar values.</span></span> <span data-ttu-id="a1355-108">Per creare un parametro che faccia riferimento a un membro, a un set o a una tupla, è possibile usare una funzione quale [StrToMember](/sql/mdx/strtomember-mdx) o [StrToSet](/sql/mdx/strtoset-mdx).</span><span class="sxs-lookup"><span data-stu-id="a1355-108">To create a parameter that references a member, set, or tuple, you would have to use a function such as [StrToMember](/sql/mdx/strtomember-mdx) or [StrToSet](/sql/mdx/strtoset-mdx).</span></span>  
  
 <span data-ttu-id="a1355-109">Nell'esempio seguente XML for Analysis (XMLA) il parametro conterrà @CountryName il paese per il quale vengono recuperati i dati del cliente:</span><span class="sxs-lookup"><span data-stu-id="a1355-109">In the following XML for Analysis (XMLA) example, the @CountryName parameter will contain the country for which customer data is retrieved:</span></span>  
  
```  
<Envelope xmlns="http://schemas.xmlsoap.org/soap/envelope/">  
  <Body>  
    <Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
      <Command>  
        <Statement>  
select [Measures].members on 0,   
       Filter(Customer.[Customer Geography].Country.members,   
              Customer.[Customer Geography].CurrentMember.Name =  
              @CountryName) on 1  
from [Adventure Works]  
</Statement>  
      </Command>  
      <Properties />  
      <Parameters>  
        <Parameter>  
          <Name>CountryName</Name>  
          <Value>'United Kingdom'</Value>  
        </Parameter>  
      </Parameters>  
    </Execute>  
  </Body>  
</Envelope>  
```  
  
 <span data-ttu-id="a1355-110">Per utilizzare questa funzionalità con OLE DB, è necessario utilizzare l'interfaccia `ICommandWithParameters`.</span><span class="sxs-lookup"><span data-stu-id="a1355-110">To use this functionality with OLE DB, you would use the `ICommandWithParameters` interface.</span></span> <span data-ttu-id="a1355-111">Per usare questa funzionalità con ADOMD.Net, è necessario usare l'interfaccia **AdomdCommand.Parameters** .</span><span class="sxs-lookup"><span data-stu-id="a1355-111">To use this functionality with ADOMD.Net, you would use the **AdomdCommand.Parameters** collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1355-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1355-112">See Also</span></span>  
 [<span data-ttu-id="a1355-113">Nozioni fondamentali sullo scripting MDX &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a1355-113">MDX Scripting Fundamentals &#40;Analysis Services&#41;</span></span>](mdx-scripting-fundamentals-analysis-services.md)  
  
  
