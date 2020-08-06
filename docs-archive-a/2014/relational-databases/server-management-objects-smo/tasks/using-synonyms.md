---
title: Uso di sinonimi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- synonyms [SMO]
ms.assetid: db0a9022-9549-43e5-b6b3-deb236f05fb8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5e8416dc3daea3b173fae92e5454a8a65c399e53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637720"
---
# <a name="using-synonyms"></a><span data-ttu-id="9eb8a-102">Utilizzo dei sinonimi</span><span class="sxs-lookup"><span data-stu-id="9eb8a-102">Using Synonyms</span></span>
  <span data-ttu-id="9eb8a-103">Per sinonimo si intende un nome alternativo per un oggetto con ambito schema.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-103">A synonym is an alternative name for a schema-scoped object.</span></span> <span data-ttu-id="9eb8a-104">In SMO i sinonimi sono rappresentati dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.Synonym>.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-104">In SMO, synonyms are represented by the <xref:Microsoft.SqlServer.Management.Smo.Synonym> object.</span></span> <span data-ttu-id="9eb8a-105">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Synonym> è un elemento figlio dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-105">The <xref:Microsoft.SqlServer.Management.Smo.Synonym> object is a child of the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span> <span data-ttu-id="9eb8a-106">Ciò significa che i sinonimi sono validi solo all'interno dell'ambito del database nel quale sono definiti.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-106">This means that synonyms are valid only within the scope of the database in which they are defined.</span></span> <span data-ttu-id="9eb8a-107">Il sinonimo può tuttavia fare riferimento a oggetti in un altro database o a un'istanza remota di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9eb8a-107">However, the synonym can refer to objects on another database, or on a remote instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9eb8a-108">L'oggetto a cui viene assegnato un nome alternativo è noto come oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-108">The object that is given an alternative name is known as the base object.</span></span> <span data-ttu-id="9eb8a-109">La proprietà name dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Synonym> è il nome alternativo assegnato all'oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-109">The name property of the <xref:Microsoft.SqlServer.Management.Smo.Synonym> object is the alternative name given to the base object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9eb8a-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="9eb8a-110">Example</span></span>  
 <span data-ttu-id="9eb8a-111">Per l'esempio di codice seguente, è necessario selezionare l'ambiente, il modello e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-111">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="9eb8a-112">Per ulteriori informazioni, vedere la pagina relativa alla [creazione di un progetto Visual Basic SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e alla [creazione di un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="9eb8a-112">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-synonym-in-visual-basic"></a><span data-ttu-id="9eb8a-113">Creazione di un sinonimo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9eb8a-113">Creating a Synonym in Visual Basic</span></span>  
 <span data-ttu-id="9eb8a-114">Nell'esempio di codice viene illustrato come creare un sinonimo o un nome alternativo per un oggetto con ambito schema.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-114">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="9eb8a-115">Le applicazioni client possono utilizzare un singolo riferimento per l'oggetto di base mediante un sinonimo anziché utilizzare un nome costituito da più parti per fare riferimento all'oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-115">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBSynonyms1](SMO How to#SMO_VBSynonyms1)]  -->  
  
## <a name="creating-a-synonym-in-visual-c"></a><span data-ttu-id="9eb8a-116">Creazione di un sinonimo in Visual C#</span><span class="sxs-lookup"><span data-stu-id="9eb8a-116">Creating a Synonym in Visual C#</span></span>  
 <span data-ttu-id="9eb8a-117">Nell'esempio di codice viene illustrato come creare un sinonimo o un nome alternativo per un oggetto con ambito schema.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-117">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="9eb8a-118">Le applicazioni client possono utilizzare un singolo riferimento per l'oggetto di base mediante un sinonimo anziché utilizzare un nome costituito da più parti per fare riferimento all'oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-118">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Synonym object variable by supplying the   
            //parent database, name, and schema arguments in the constructor.   
            //The name is also a synonym of the name of the base object.   
            Synonym syn = new Synonym(db, "Shop", "Sales");  
  
            //Specify the base object, which is the object on which   
            //the synonym is based.   
            syn.BaseDatabase = "AdventureWorks2012";  
            syn.BaseSchema = "Sales";  
            syn.BaseObject = "Store";  
            syn.BaseServer = srv.Name;  
  
            //Create the synonym on the instance of SQL Server.   
            syn.Create();  
        }  
```  
  
## <a name="creating-a-synonym-in-powershell"></a><span data-ttu-id="9eb8a-119">Creazione di un sinonimo in PowerShell</span><span class="sxs-lookup"><span data-stu-id="9eb8a-119">Creating a Synonym in PowerShell</span></span>  
 <span data-ttu-id="9eb8a-120">Nell'esempio di codice viene illustrato come creare un sinonimo o un nome alternativo per un oggetto con ambito schema.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-120">The code example shows how to create a synonym or an alternate name for a schema scoped object.</span></span> <span data-ttu-id="9eb8a-121">Le applicazioni client possono utilizzare un singolo riferimento per l'oggetto di base mediante un sinonimo anziché utilizzare un nome costituito da più parti per fare riferimento all'oggetto di base.</span><span class="sxs-lookup"><span data-stu-id="9eb8a-121">Client applications can use a single reference for the base object via a synonym instead of using a multiple part name to reference the base object.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#And the database object corresponding to Adventureworks  
$db = $srv.Databases["AdventureWorks2012"]  
  
$syn = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Synonym -ArgumentList $db, "Shop", "Sales"  
  
#Specify the base object, which is the object on which the synonym is based.  
$syn.BaseDatabase = "AdventureWorks2012"  
$syn.BaseSchema = "Sales"  
$syn.BaseObject = "Store"  
$syn.BaseServer = $srv.Name  
  
#Create the synonym on the instance of SQL Server.  
$syn.Create()  
```  
  
## <a name="see-also"></a><span data-ttu-id="9eb8a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9eb8a-122">See Also</span></span>  
 [<span data-ttu-id="9eb8a-123">CREATE SYNONYM &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9eb8a-123">CREATE SYNONYM &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-synonym-transact-sql)  
