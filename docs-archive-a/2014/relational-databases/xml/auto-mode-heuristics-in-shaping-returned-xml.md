---
title: Approccio euristico della modalità AUTO per la determinazione della struttura dei valori XML restituiti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, heuristics in shaping returned XML
ms.assetid: 6c5cb6c1-2921-4ba1-8100-0bf8074f9103
author: rothja
ms.author: jroth
ms.openlocfilehash: 7a64cda8989e1e45d4ad869f8883e1c9d65f4b7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623954"
---
# <a name="auto-mode-heuristics-in-shaping-returned-xml"></a><span data-ttu-id="d589b-102">Approccio euristico della modalità AUTO per la determinazione della struttura dei valori XML restituiti</span><span class="sxs-lookup"><span data-stu-id="d589b-102">AUTO Mode Heuristics in Shaping Returned XML</span></span>
  <span data-ttu-id="d589b-103">La modalità AUTO determina la struttura del valore XML restituito in base alla query.</span><span class="sxs-lookup"><span data-stu-id="d589b-103">AUTO mode determines the shape of returned XML based on the query.</span></span> <span data-ttu-id="d589b-104">Per determinare come devono essere nidificati gli elementi, la modalità AUTO, che utilizza un approccio euristico, confronta i valori delle colonne nelle righe adiacenti.</span><span class="sxs-lookup"><span data-stu-id="d589b-104">In determining how elements are to be nested, AUTO mode heuristics compare column values in adjacent rows.</span></span> <span data-ttu-id="d589b-105">Vengono confrontate colonne di tutti i tipi, ad eccezione di **ntext**, **text**, **image**e **xml**.</span><span class="sxs-lookup"><span data-stu-id="d589b-105">Columns of all types, except **ntext**, **text**, **image**, and **xml**, are compared.</span></span> <span data-ttu-id="d589b-106">Vengono confrontate le colonne di tipo **(n)varchar(max)** e **varbinary(max)** .</span><span class="sxs-lookup"><span data-stu-id="d589b-106">Columns of type **(n)varchar(max)** and **varbinary(max)** are compared.</span></span>  
  
 <span data-ttu-id="d589b-107">Nell'esempio seguente viene illustrato l'approccio euristico utilizzato dalla modalità AUTO per determinare la struttura del valore XML risultante:</span><span class="sxs-lookup"><span data-stu-id="d589b-107">The following example illustrates the AUTO mode heuristics that determine the shape of the resulting XML:</span></span>  
  
```  
SELECT T1.Id, T2.Id, T1.Name  
FROM   T1, T2  
WHERE ...  
FOR XML AUTO  
ORDER BY T1.Id  
```  
  
 <span data-ttu-id="d589b-108">Per determinare la posizione iniziale dell'elemento <`T1`>, se non è specificata la chiave della tabella T1 vengono confrontati tutti i valori di colonna di T1, ad eccezione di quelli di tipo **ntext**, **text**, **image** e **xml**.</span><span class="sxs-lookup"><span data-stu-id="d589b-108">To determine where a new <`T1`> element starts, all column values of T1, except **ntext**, **text**, **image** and **xml**, are compared if the key on the table T1 is not specified.</span></span> <span data-ttu-id="d589b-109">Supporre quindi che la colonna **Name** sia di tipo **nvarchar(40)** e che l'istruzione SELECT restituisca il set di righe seguente:</span><span class="sxs-lookup"><span data-stu-id="d589b-109">Next, assume that the **Name** column is **nvarchar(40)** and the SELECT statement returns this rowset:</span></span>  
  
```  
T1.Id  T1.Name  T2.Id  
-----------------------  
1       Andrew    2  
1       Andrew    3  
1       Nancy     4  
```  
  
 <span data-ttu-id="d589b-110">Utilizzando un approccio euristico, la modalità AUTO confronta tutti i valori della tabella T1, ovvero le colonne Id e Name.</span><span class="sxs-lookup"><span data-stu-id="d589b-110">The AUTO mode heuristics compare all the values of table T1, the Id and Name columns.</span></span> <span data-ttu-id="d589b-111">Le prime due righe contengono gli stessi valori nelle colonne Id e Name, quindi al risultato viene aggiunto un elemento \<T1> con due elementi figlio \<T2>.</span><span class="sxs-lookup"><span data-stu-id="d589b-111">Because the first two rows have the same values for the Id and Name columns, one \<T1> element having two \<T2> child elements is added in the result.</span></span>  
  
 <span data-ttu-id="d589b-112">Il valore XML restituito è il seguente:</span><span class="sxs-lookup"><span data-stu-id="d589b-112">Following is the XML that is returned:</span></span>  
  
```  
<T1 Id="1" Name="Andrew">  
    <T2 Id="2" />  
    <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
      <T2 Id="4" />  
</T>  
```  
  
 <span data-ttu-id="d589b-113">Si supponga ora che la colonna Name sia di tipo **text** .</span><span class="sxs-lookup"><span data-stu-id="d589b-113">Now assume that the Name column is of **text** type.</span></span> <span data-ttu-id="d589b-114">A causa dell'approccio euristico, la modalità AUTO non confronta valori di questo tipo,</span><span class="sxs-lookup"><span data-stu-id="d589b-114">The AUTO mode heuristics do not compare the values for this type.</span></span> <span data-ttu-id="d589b-115">ma presuppone che siano diversi.</span><span class="sxs-lookup"><span data-stu-id="d589b-115">Instead, it assumes that the values are not the same.</span></span> <span data-ttu-id="d589b-116">Viene pertanto generato il valore XML illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d589b-116">This results in XML generation as shown in the following:</span></span>  
  
```  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="2" />  
</T1>  
<T1 Id="1" Name="Andrew" >  
  <T2 Id="3" />  
</T1>  
<T1 Id="1" Name="Nancy" >  
  <T2 Id="4" />  
</T1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d589b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d589b-117">See Also</span></span>  
 [<span data-ttu-id="d589b-118">Usare la modalità AUTO con FOR XML</span><span class="sxs-lookup"><span data-stu-id="d589b-118">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  
