---
title: Creazione, modifica e rimozione di regole | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- rules [SMO]
ms.assetid: 16981459-524e-4b39-a899-4370eaf763cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7742a9cb718bdde4f268d5226c45eba475f44ddd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635467"
---
# <a name="creating-altering-and-removing-rules"></a><span data-ttu-id="62def-102">Creazione, modifica e rimozione di regole</span><span class="sxs-lookup"><span data-stu-id="62def-102">Creating, Altering, and Removing Rules</span></span>
  <span data-ttu-id="62def-103">In SMO le regole sono rappresentate dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.Rule>.</span><span class="sxs-lookup"><span data-stu-id="62def-103">In SMO, rules are represented by the <xref:Microsoft.SqlServer.Management.Smo.Rule> object.</span></span> <span data-ttu-id="62def-104">La regola è definita dalla proprietà <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A>, ovvero una stringa di testo contenente un'espressione della condizione che utilizza operatori o predicati, ad esempio IN, LIKE o BETWEEN.</span><span class="sxs-lookup"><span data-stu-id="62def-104">The rule is defined by the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property, which is a text string that contains a condition expression that uses operators or predicates, such as IN, LIKE, or BETWEEN.</span></span> <span data-ttu-id="62def-105">Una regola non può fare riferimento a colonne o ad altri oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="62def-105">A rule cannot reference columns or other database objects.</span></span> <span data-ttu-id="62def-106">È possibile includere funzioni predefinite che non fanno riferimento a oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="62def-106">Built-in functions that do not reference database objects can be included.</span></span>  
  
 <span data-ttu-id="62def-107">La definizione nella proprietà <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> deve contenere una variabile che fa riferimento al valore di dati immesso.</span><span class="sxs-lookup"><span data-stu-id="62def-107">The definition in the <xref:Microsoft.SqlServer.Management.Smo.DefaultRuleBase.TextBody%2A> property must contain a variable that refers to the data value entered.</span></span> <span data-ttu-id="62def-108">È possibile utilizzare qualsiasi nome o simbolo per rappresentare il valore durante la creazione della regola, ma il primo carattere deve essere il \@ simbolo.</span><span class="sxs-lookup"><span data-stu-id="62def-108">Any name or symbol can be used to represent the value when creating the rule, but the first character must be the \@ symbol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62def-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="62def-109">Example</span></span>  
 <span data-ttu-id="62def-110">Per usare qualsiasi esempio di codice fornito, è necessario scegliere l'ambiente di programmazione, il modello di programmazione e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62def-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="62def-111">Per ulteriori informazioni, vedere [creare un Visual Basic progetto SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [creare un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="62def-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-basic"></a><span data-ttu-id="62def-112">Creazione, modifica e rimozione di una regola in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62def-112">Creating, Altering, and Removing a Rule in Visual Basic</span></span>  
 <span data-ttu-id="62def-113">In questo esempio di codice viene illustrato come creare una regola, collegarla a una colonna, modificare le proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Rule>, scollegarla dalla colonna e infine eliminarla.</span><span class="sxs-lookup"><span data-stu-id="62def-113">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="62def-114">L'istruzione `Dim` per l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Rule> viene specificata con il percorso completo dell'assembly per evitare ambiguità con un oggetto <xref:Microsoft.SqlServer.Management.Smo.Rule> nell'assembly System.Data.</span><span class="sxs-lookup"><span data-stu-id="62def-114">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBRules1](SMO How to#SMO_VBRules1)]  -->  
  
## <a name="creating-altering-and-removing-a-rule-in-visual-c"></a><span data-ttu-id="62def-115">Creazione, modifica e rimozione di una regola in Visual C#</span><span class="sxs-lookup"><span data-stu-id="62def-115">Creating, Altering, and Removing a Rule in Visual C#</span></span>  
 <span data-ttu-id="62def-116">In questo esempio di codice viene illustrato come creare una regola, collegarla a una colonna, modificare le proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Rule>, scollegarla dalla colonna e infine eliminarla.</span><span class="sxs-lookup"><span data-stu-id="62def-116">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="62def-117">L'istruzione `Dim` per l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Rule> viene specificata con il percorso completo dell'assembly per evitare ambiguità con un oggetto <xref:Microsoft.SqlServer.Management.Smo.Rule> nell'assembly System.Data.</span><span class="sxs-lookup"><span data-stu-id="62def-117">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv;  
            srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db;  
            db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Rule object variable by supplying the parent database, name and schema in the constructor.   
            //Note that the full namespace must be given for the Rule type to differentiate it from other Rule types.   
            Microsoft.SqlServer.Management.Smo.Rule ru;  
            ru = new Rule(db, "TestRule", "Production");  
            //Set the TextHeader and TextBody properties to define the rule.   
            ru.TextHeader = "CREATE RULE [Production].[TestRule] AS";  
            ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())";  
            //Create the rule on the instance of SQL Server.   
            ru.Create();  
            //Bind the rule to a column in the Product table by supplying the table, schema, and   
            //column as arguments in the BindToColumn method.   
            ru.BindToColumn("Product", "SellEndDate", "Production");  
            //Unbind from the column before removing the rule from the database.   
            ru.UnbindFromColumn("Product", "SellEndDate", "Production");  
            ru.Drop();  
  
        }  
```  
  
## <a name="creating-altering-and-removing-a-rule-in-powershell"></a><span data-ttu-id="62def-118">Creazione, modifica e rimozione di una regola in PowerShell</span><span class="sxs-lookup"><span data-stu-id="62def-118">Creating, Altering, and Removing a Rule in PowerShell</span></span>  
 <span data-ttu-id="62def-119">In questo esempio di codice viene illustrato come creare una regola, collegarla a una colonna, modificare le proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Rule>, scollegarla dalla colonna e infine eliminarla.</span><span class="sxs-lookup"><span data-stu-id="62def-119">This code sample shows how to create a rule, attach it to a column, modify properties of the <xref:Microsoft.SqlServer.Management.Smo.Rule> object, detach it from the column, and then drop it.</span></span>  
  
 <span data-ttu-id="62def-120">L'istruzione `Dim` per l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Rule> viene specificata con il percorso completo dell'assembly per evitare ambiguità con un oggetto <xref:Microsoft.SqlServer.Management.Smo.Rule> nell'assembly System.Data.</span><span class="sxs-lookup"><span data-stu-id="62def-120">The `Dim` statement for the <xref:Microsoft.SqlServer.Management.Smo.Rule> object is specified with the full assembly path to avoid ambiguity with a <xref:Microsoft.SqlServer.Management.Smo.Rule> object in the System.Data assembly.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a Rule object variable by supplying the parent database, name and schema in the constructor.
$ru = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Rule -argumentlist $db, "TestRule", "Production"  
  
#Set the TextHeader and TextBody properties to define the rule.
$ru.TextHeader = "CREATE RULE [Production].[TestRule] AS"  
$ru.TextBody = "@value BETWEEN GETDATE() AND DATEADD(year,4,GETDATE())"  
  
#Create the rule on the instance of SQL Server.
$ru.Create()  
  
# Bind the rule to a column in the Product table by supplying the table, schema, and column as arguments in the BindToColumn method.
$ru.BindToColumn("Product", "SellEndDate", "Production")  
  
#Unbind from the column before removing the rule from the database.
$ru.UnbindFromColumn("Product", "SellEndDate", "Production")  
$ru.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="62def-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62def-121">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Rule>  
