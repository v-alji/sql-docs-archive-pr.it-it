---
title: Panoramica degli attributi personalizzati dell'integrazione con CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- custom attributes [CLR integration]
- attributes [CLR integration]
- common language runtime [SQL Server], attributes
- database objects [CLR integration], custom attributes
- building database objects [CLR integration], custom attributes
ms.assetid: ecf5c097-0972-48e2-a9c0-b695b7dd2820
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: aa0bf94ee27fd89a6aa690e0ff2f8e3295648946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624335"
---
# <a name="overview-of-clr-integration-custom-attributes"></a><span data-ttu-id="aa374-102">Panoramica degli attributi personalizzati dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="aa374-102">Overview of CLR Integration Custom Attributes</span></span>
  <span data-ttu-id="aa374-103">Common Language Runtime (CLR) di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] consente l'utilizzo di parole chiave descrittive, chiamate attributi.</span><span class="sxs-lookup"><span data-stu-id="aa374-103">The common language runtime (CLR) of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] allows the use of descriptive keywords, called attributes.</span></span> <span data-ttu-id="aa374-104">Questi attributi forniscono informazioni aggiuntive per molti elementi quali metodi e classi.</span><span class="sxs-lookup"><span data-stu-id="aa374-104">These attributes provide additional information for many elements, such as methods and classes.</span></span> <span data-ttu-id="aa374-105">Gli attributi vengono salvati nell'assembly con i metadati dell'oggetto e possono essere utilizzati per descrivere il codice ad altri strumenti di sviluppo o per influire sul comportamento in fase di esecuzione in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa374-105">The attributes are saved in the assembly with the metadata of the object, and can be used to describe your code to other development tools or to affect runtime behavior inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="aa374-106">Quando si registra una routine CLR con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deriva un set di proprietà sulla routine.</span><span class="sxs-lookup"><span data-stu-id="aa374-106">When you register a CLR routine with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives a set of properties about the routine.</span></span> <span data-ttu-id="aa374-107">Queste proprietà della routine determinano le funzionalità della routine, incluso se la routine può essere indicizzata.</span><span class="sxs-lookup"><span data-stu-id="aa374-107">These routine properties determine the capabilities of the routine, including whether the routine can be indexed.</span></span> <span data-ttu-id="aa374-108">Impostando ad esempio la proprietà `DataAccess` su `DataAccessKind.Read` sarà possibile accedere ai dati dalle tabelle utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in una funzione CLR.</span><span class="sxs-lookup"><span data-stu-id="aa374-108">For example, setting the `DataAccess` property to `DataAccessKind.Read` lets you access data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user tables inside a CLR function.</span></span> <span data-ttu-id="aa374-109">Nell'esempio seguente viene illustrato un caso semplice in cui la `DataAccess` proprietà è impostata in modo da facilitare l'accesso ai dati da una tabella utente **Tabella1**.</span><span class="sxs-lookup"><span data-stu-id="aa374-109">The following example shows a simple case in which the `DataAccess` property is set to facilitate data access from a user table **table1**.</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
  
public partial class UserDefinedFunctions  
{  
    [SqlFunction(DataAccess = DataAccessKind.Read)]  
    public static string func1()  
    {  
        // Open a connection and create a command  
        SqlConnection conn = new SqlConnection("context connection = true");  
        conn.Open();  
        SqlCommand cmd = conn.CreateCommand();  
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10";  
        // where table1 is a user table  
        // Execute this command   
        SqlDataReader rd = cmd.ExecuteReader();  
        // Set string ret_val to str_val returned from the query  
        string ret_val = rd.GetValue(0).ToString();  
        rd.Close();  
        return ret_val;  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Public partial Class UserDefinedFunctions  
    <SqlFunction(DataAccess = DataAccessKind.Read)> _   
    Public Shared Function func1() As String  
        ' Open a connection and create a command  
        Dim conn As SqlConnection = New SqlConnection("context connection = true")   
        conn.Open()  
        Dim cmd As SqlCommand =  conn.CreateCommand()   
        cmd.CommandText = "SELECT str_val FROM table1 WHERE int_val = 10"  
        ' where table1 is a user table  
        ' Execute this command   
        Dim rd As SqlDataReader =  cmd.ExecuteReader()   
        ' Set string ret_val to str_val returned from the query  
        Dim ret_val As String =  rd.GetValue(0).ToString()   
        rd.Close()  
        Return ret_val  
    End Function  
End Class  
```  
  
 <span data-ttu-id="aa374-110">Per le routine [!INCLUDE[tsql](../../includes/tsql-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deriva le proprietà della routine direttamente dalla definizione di routine.</span><span class="sxs-lookup"><span data-stu-id="aa374-110">For [!INCLUDE[tsql](../../includes/tsql-md.md)] routines, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] derives routine properties directly from the routine definition.</span></span> <span data-ttu-id="aa374-111">Per le routine CLR, il server non analizza il corpo della routine per derivare queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="aa374-111">For CLR routines, the server does not analyze the body of the routine to derive these properties.</span></span> <span data-ttu-id="aa374-112">È possibile invece utilizzare gli attributi personalizzati per classi e membri della classe implementati in un linguaggio di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa374-112">Instead, you can use custom attributes for classes and class members implemented in a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language.</span></span>  
  
 <span data-ttu-id="aa374-113">Gli attributi personalizzati necessari per routine CLR, tipi definiti dall'utente e aggregazioni vengono definiti nello spazio dei nomi `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="aa374-113">The custom attributes needed for CLR routines, user-defined types, and aggregates are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa374-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa374-114">See Also</span></span>  
 [<span data-ttu-id="aa374-115">Attributi personalizzati per routine CLR</span><span class="sxs-lookup"><span data-stu-id="aa374-115">Custom Attributes for CLR Routines</span></span>](../../relational-databases/clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md)  
  
  
