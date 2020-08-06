---
title: Accesso ai tipi definiti dall'utente in ADO.NET | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- UDTs [CLR integration], ADO.NET
- user-defined types [CLR integration], ADO.NET
ms.assetid: 4b0d876c-8066-490e-8e18-327c0e942b19
author: rothja
ms.author: jroth
ms.openlocfilehash: a94e333ad743ed07dff6b973ebfe227312a1cab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635656"
---
# <a name="accessing-user-defined-types-in-adonet"></a><span data-ttu-id="f858c-102">Accesso ai tipi definiti dall'utente in ADO .NET</span><span class="sxs-lookup"><span data-stu-id="f858c-102">Accessing User-Defined Types in ADO.NET</span></span>
  <span data-ttu-id="f858c-103">I tipi definiti dall'utente (UDT) vengono scritti utilizzando uno dei linguaggi supportati dalla [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework Common Language Runtime (CLR) che producono codice verificabile.</span><span class="sxs-lookup"><span data-stu-id="f858c-103">User-defined types (UDTs) are written using any of the languages supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="f858c-104">[!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# e [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f858c-104">This includes [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic.</span></span> <span data-ttu-id="f858c-105">I tipi definiti dall'utente consentono l'archiviazione di oggetti e strutture di dati personalizzate in un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f858c-105">UDTs allow objects and custom data structures to be stored in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="f858c-106">I dati vengono esposti come membri pubblici di una classe o struttura .NET mentre i comportamenti vengono definiti dai metodi della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="f858c-106">The data is exposed as public members of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span> <span data-ttu-id="f858c-107">Un tipo definito dall'utente (UDT) può essere usato come definizione di colonna di una tabella, come variabile in un batch [!INCLUDE[tsql](../../includes/tsql-md.md)] o come argomento di una funzione [!INCLUDE[tsql](../../includes/tsql-md.md)] o di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f858c-107">A UDT can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
 <span data-ttu-id="f858c-108">In ADO.NET il provider `System.Data.SqlClient` espone i tipi definiti dall'utente nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f858c-108">In ADO.NET, the `System.Data.SqlClient` provider exposes UDTs in the following ways:</span></span>  
  
-   <span data-ttu-id="f858c-109">Mediante `System.Data.SqlClient.SqlDataReader` come oggetto.</span><span class="sxs-lookup"><span data-stu-id="f858c-109">Through the `System.Data.SqlClient.SqlDataReader` as an object.</span></span>  
  
-   <span data-ttu-id="f858c-110">Mediante `SqlDataReader` come byte non elaborati.</span><span class="sxs-lookup"><span data-stu-id="f858c-110">Through the `SqlDataReader` as raw bytes.</span></span>  
  
-   <span data-ttu-id="f858c-111">Come parametro di un oggetto `System.Data.SqlClient.SqlParameter`.</span><span class="sxs-lookup"><span data-stu-id="f858c-111">As a parameter of a `System.Data.SqlClient.SqlParameter` object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f858c-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="f858c-112">In This Section</span></span>  
 [<span data-ttu-id="f858c-113">Recupero di dati UDT</span><span class="sxs-lookup"><span data-stu-id="f858c-113">Retrieving UDT Data</span></span>](accessing-user-defined-types-retrieving-udt-data.md)  
 <span data-ttu-id="f858c-114">Viene illustrato come recuperare i dati dei tipi definiti dall'utente e come specificare i parametri.</span><span class="sxs-lookup"><span data-stu-id="f858c-114">Describes how to retrieve UDT data and how to specify parameters.</span></span>  
  
 [<span data-ttu-id="f858c-115">Aggiornamento di colonne con tipo definito dall'utente con DataAdapter</span><span class="sxs-lookup"><span data-stu-id="f858c-115">Updating UDT Columns with DataAdapters</span></span>](accessing-user-defined-types-updating-udt-columns-with-dataadapters.md)  
 <span data-ttu-id="f858c-116">Viene illustrato come utilizzare i tipi definiti dall'utente in `DataSets` e come aggiornarli utilizzando `DataAdapters`.</span><span class="sxs-lookup"><span data-stu-id="f858c-116">Describes how to work with UDTs in `DataSets` and how to update UDT data using `DataAdapters`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f858c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f858c-117">See Also</span></span>  
 [<span data-ttu-id="f858c-118">Tipi definiti dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="f858c-118">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
  
  
