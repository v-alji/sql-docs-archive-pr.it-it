---
title: Connessione di attività a livello di programmazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- constraints [Integration Services]
ms.assetid: 23668e88-cef4-4009-a9cf-38e607eab7a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5aeeb70ed5741cc7372fdfc63e637fd53d932f91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627349"
---
# <a name="connecting-tasks-programmatically"></a><span data-ttu-id="2248a-102">Connessione di attività a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="2248a-102">Connecting Tasks Programmatically</span></span>
  <span data-ttu-id="2248a-103">Un vincolo di precedenza, rappresentato nel modello a oggetti dalla classe <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, stabilisce l'ordine di esecuzione degli oggetti <xref:Microsoft.SqlServer.Dts.Runtime.Executable> in un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2248a-103">A precedence constraint, represented in the object model by the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> class, establishes the order in which <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects run in a package.</span></span> <span data-ttu-id="2248a-104">Con il vincolo di precedenza, l'esecuzione dei contenitori e delle attività di un pacchetto diventa dipendente dal risultato dell'esecuzione di un'attività o di un contenitore precedente.</span><span class="sxs-lookup"><span data-stu-id="2248a-104">The precedence constraint allows the execution of the containers and tasks in a package to be dependent on the result of the execution of a previous task or container.</span></span> <span data-ttu-id="2248a-105">I vincoli di precedenza vengono stabiliti tra coppie di oggetti <xref:Microsoft.SqlServer.Dts.Runtime.Executable> chiamando il metodo <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A> della raccolta <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints> sull'oggetto contenitore.</span><span class="sxs-lookup"><span data-stu-id="2248a-105">Precedence constraints are established between pairs of <xref:Microsoft.SqlServer.Dts.Runtime.Executable> objects by calling the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints.Add%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraints> collection on the container object.</span></span> <span data-ttu-id="2248a-106">Dopo aver creato un vincolo tra due oggetti eseguibili, impostare la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> per stabilire i criteri per l'esecuzione del secondo eseguibile definito nel vincolo.</span><span class="sxs-lookup"><span data-stu-id="2248a-106">After you create a constraint between two executable objects, you set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property to establish the criteria for executing the second executable defined in the constraint.</span></span>  
  
 <span data-ttu-id="2248a-107">È possibile utilizzare sia un vincolo che un'espressione in un singolo vincolo di precedenza, a seconda del valore specificato per la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A>, come descritto nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="2248a-107">You can use both a constraint and an expression in a single precedence constraint, depending on the value that you specify for the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.EvalOp%2A> property, as described in the following table:</span></span>  
  
|<span data-ttu-id="2248a-108">Valore della proprietà EvalOp</span><span class="sxs-lookup"><span data-stu-id="2248a-108">Value of the EvalOp property</span></span>|<span data-ttu-id="2248a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2248a-109">Description</span></span>|  
|----------------------------------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Constraint>|<span data-ttu-id="2248a-110">Specifica che il risultato dell'esecuzione determina se l'attività o il contenitore vincolato viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="2248a-110">Specifies that the execution outcome determines whether the constrained container or task runs.</span></span> <span data-ttu-id="2248a-111">Impostare la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> di <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> sul valore desiderato dell'enumerazione <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>.</span><span class="sxs-lookup"><span data-stu-id="2248a-111">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> to the desired value from the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> enumeration.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.Expression>|<span data-ttu-id="2248a-112">Specifica che il valore di un'espressione determina se l'attività o il contenitore vincolato viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="2248a-112">Specifies that the value of an expression determines whether the constrained container or task runs.</span></span> <span data-ttu-id="2248a-113">Impostare la proprietà <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> di <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>.</span><span class="sxs-lookup"><span data-stu-id="2248a-113">Set the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionAndConstraint>|<span data-ttu-id="2248a-114">Specifica che, affinché l'attività o il contenitore vincolato venga eseguito, è necessario che il risultato del vincolo si verifichi e che l'espressione restituisca un valore.</span><span class="sxs-lookup"><span data-stu-id="2248a-114">Specifies that the constraint outcome must occur and the expression must evaluate for the constrained container or task to run.</span></span> <span data-ttu-id="2248a-115">Impostare le proprietà <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> di <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> e impostare la relativa proprietà <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="2248a-115">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `true`.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.DTSPrecedenceEvalOp.ExpressionOrConstraint>|<span data-ttu-id="2248a-116">Specifica che, affinché l'attività o il contenitore vincolato venga eseguito, è necessario che il risultato del vincolo si verifichi oppure che l'espressione restituisca un valore.</span><span class="sxs-lookup"><span data-stu-id="2248a-116">Specifies that either the constraint outcome must occur, or the expression must evaluate, for the constrained container or task to run.</span></span> <span data-ttu-id="2248a-117">Impostare le proprietà <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> di <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> e impostare la relativa proprietà <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> su `false`.</span><span class="sxs-lookup"><span data-stu-id="2248a-117">Set both the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Value%2A> and the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.Expression%2A> properties of the <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint>, and set its <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint.LogicalAnd%2A> property to `false`.</span></span>|  
  
 <span data-ttu-id="2248a-118">Nell'esempio di codice seguente è illustrata l'aggiunta di due attività a un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2248a-118">The following code sample demonstrates adding two tasks to a package.</span></span> <span data-ttu-id="2248a-119">Tra le attività viene creato <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> che impedisce l'esecuzione della seconda attività finché non viene completata la prima.</span><span class="sxs-lookup"><span data-stu-id="2248a-119">A <xref:Microsoft.SqlServer.Dts.Runtime.PrecedenceConstraint> is created between them that prevents the second task from running until the first task finishes.</span></span>  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
  
namespace Microsoft.SqlServer.Dts.Samples  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      Package p = new Package();  
  
      // Add a File System task.  
      Executable eFileTask1 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost1 = eFileTask1 as TaskHost;  
  
      // Add a second File System task.  
      Executable eFileTask2 = p.Executables.Add("STOCK:FileSystemTask");  
      TaskHost thFileHost2 = eFileTask2 as TaskHost;  
  
      // Put a precedence constraint between the tasks.  
      // Set the constraint to specify that the second File System task cannot run  
      // until the first File System task finishes.  
      PrecedenceConstraint pcFileTasks =   
        p.PrecedenceConstraints.Add((Executable)thFileHost1, (Executable)thFileHost2);  
      pcFileTasks.Value = DTSExecResult.Completion;  
    }  
  }  
}  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
  
Module Module1  
  
  Sub Main()  
  
    Dim p As Package = New Package()  
    ' Add a File System task.  
    Dim eFileTask1 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost1 As TaskHost = CType(eFileTask1, TaskHost)  
  
    ' Add a second File System task.  
    Dim eFileTask2 As Executable = p.Executables.Add("STOCK:FileSystemTask")  
    Dim thFileHost2 As TaskHost = CType(eFileTask2, TaskHost)  
  
    ' Put a precedence constraint between the tasks.  
    ' Set the constraint to specify that the second File System task cannot run  
    ' until the first File System task finishes.  
    Dim pcFileTasks As PrecedenceConstraint = _  
      p.PrecedenceConstraints.Add(CType(thFileHost1, Executable), CType(thFileHost2, Executable))  
    pcFileTasks.Value = DTSExecResult.Completion  
  
  End Sub  
  
End Module  
```  
  
<span data-ttu-id="2248a-120">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="2248a-120">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2248a-121">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="2248a-121">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2248a-122">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="2248a-122">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2248a-123">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2248a-123">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2248a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2248a-124">See Also</span></span>  
 [<span data-ttu-id="2248a-125">Aggiunta dell'attività Flusso di dati a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="2248a-125">Adding the Data Flow Task Programmatically</span></span>](../building-packages-programmatically/adding-the-data-flow-task-programmatically.md)  
  
  
