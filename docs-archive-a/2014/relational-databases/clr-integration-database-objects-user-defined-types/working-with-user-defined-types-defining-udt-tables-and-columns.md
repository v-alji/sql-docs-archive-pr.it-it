---
title: Definizione di tabelle e colonne UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- user-defined types [CLR integration], columns
- UDTs [CLR integration], columns
- columns [CLR integration]
- user-defined types [CLR integration], tables
- tables [CLR integration]
- UDTs [CLR integration], tables
- UDTs [CLR integration], indexes
- user-defined types [CLR integration], indexes
- indexes [CLR integration]
ms.assetid: aea495f4-ce26-4952-b019-38f012625f3f
author: rothja
ms.author: jroth
ms.openlocfilehash: aa9596629ed8b4877b1793fa0c56956c52989499
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638422"
---
# <a name="defining-udt-tables-and-columns"></a><span data-ttu-id="4603f-102">Definizione di tabelle e colonne con tipi definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="4603f-102">Defining UDT Tables and Columns</span></span>
  <span data-ttu-id="4603f-103">Una volta che l'assembly contenente la definizione del tipo definito dall'utente (UDT) è stato registrato in un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, può essere utilizzato in una definizione di colonna.</span><span class="sxs-lookup"><span data-stu-id="4603f-103">Once the assembly containing the user-defined type (UDT) definition has been registered in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, it can be used in a column definition.</span></span>  
  
## <a name="creating-tables-with-udts"></a><span data-ttu-id="4603f-104">Creazione di tabelle con tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="4603f-104">Creating Tables with UDTs</span></span>  
 <span data-ttu-id="4603f-105">Per la creazione di una colonna con tipo definito dall'utente in una tabella non è necessaria una sintassi speciale.</span><span class="sxs-lookup"><span data-stu-id="4603f-105">There is no special syntax for creating a UDT column in a table.</span></span> <span data-ttu-id="4603f-106">È possibile utilizzare il nome del tipo definito dall'utente in una definizione di colonna come se fosse uno dei tipi di dati intrinseci di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4603f-106">You can use the name of the UDT in a column definition as though it were one of the intrinsic [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="4603f-107">L'istruzione CREATE TABLE seguente [!INCLUDE[tsql](../../includes/tsql-md.md)] Crea una tabella denominata **Points**, con una colonna denominata **ID,** definita come `int` colonna Identity e la chiave primaria per la tabella.</span><span class="sxs-lookup"><span data-stu-id="4603f-107">The following CREATE TABLE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement creates a table named **Points**, with a column named **ID,** which is defined as an `int` identity column and \ the primary key for the table.</span></span> <span data-ttu-id="4603f-108">La seconda colonna è denominata **PointValue**, con tipo di dati **Point**.</span><span class="sxs-lookup"><span data-stu-id="4603f-108">The second column is named **PointValue**, with a data type of **Point**.</span></span> <span data-ttu-id="4603f-109">Il nome dello schema utilizzato in questo esempio è **dbo**.</span><span class="sxs-lookup"><span data-stu-id="4603f-109">The schema name used in this example is **dbo**.</span></span> <span data-ttu-id="4603f-110">Si noti che per specificare un nome di schema è necessario disporre delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="4603f-110">Note that you must have the necessary permissions to specify a schema name.</span></span> <span data-ttu-id="4603f-111">Se si omette il nome dello schema, viene utilizzato lo schema predefinito per l'utente del database.</span><span class="sxs-lookup"><span data-stu-id="4603f-111">If you omit the schema name, the default schema for the database user is used.</span></span>  
  
```  
CREATE TABLE dbo.Points   
(ID int IDENTITY(1,1) PRIMARY KEY, PointValue Point)  
```  
  
## <a name="creating-indexes-on-udt-columns"></a><span data-ttu-id="4603f-112">Creazione di indici in colonne con tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="4603f-112">Creating Indexes on UDT Columns</span></span>  
 <span data-ttu-id="4603f-113">Per indicizzare una colonna con tipo definito dall'utente, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="4603f-113">There are two options for indexing a UDT column:</span></span>  
  
-   <span data-ttu-id="4603f-114">Indicizzare il valore completo.</span><span class="sxs-lookup"><span data-stu-id="4603f-114">Index the full value.</span></span> <span data-ttu-id="4603f-115">In questo caso, se il tipo definito dall'utente ha ordinamento binario, è possibile creare un indice sull'intera colonna con tipo definito dall'utente utilizzando l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE INDEX.</span><span class="sxs-lookup"><span data-stu-id="4603f-115">In this case, if the UDT is binary ordered, you can create an index over the entire UDT column by using the CREATE INDEX [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
-   <span data-ttu-id="4603f-116">Indicizzare espressioni dei tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4603f-116">Index UDT expressions.</span></span> <span data-ttu-id="4603f-117">È possibile creare indici in colonne calcolate persistenti su espressioni dei tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4603f-117">You can create indexes on persisted computed columns over UDT expressions.</span></span> <span data-ttu-id="4603f-118">L'espressione del tipo definito dall'utente può essere un campo, un metodo o una proprietà di un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4603f-118">The UDT expression can be a field, method, or property of a UDT.</span></span> <span data-ttu-id="4603f-119">L'espressione deve essere deterministica e non deve eseguire accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="4603f-119">The expression must be deterministic and must not perform data access.</span></span>  
  
 <span data-ttu-id="4603f-120">Per ulteriori informazioni, vedere [tipi CLR definiti dall'utente](clr-user-defined-types.md) e [CREATE INDEX &#40;&#41;Transact-SQL ](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4603f-120">For more information, see [CLR User-Defined Types](clr-user-defined-types.md) and [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4603f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4603f-121">See Also</span></span>  
 [<span data-ttu-id="4603f-122">Uso di tipi definiti dall'utente in SQL Server</span><span class="sxs-lookup"><span data-stu-id="4603f-122">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
  
  
