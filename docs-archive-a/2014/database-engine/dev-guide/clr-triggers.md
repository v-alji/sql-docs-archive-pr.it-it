---
title: Trigger CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- inserted tables
- database objects [CLR integration], triggers
- common language runtime [SQL Server], triggers
- updated columns
- building database objects [CLR integration], triggers
- triggers [CLR integration]
- deleted tables
- EventData property
- SqlTriggerContext class
- transactions [CLR integration]
ms.assetid: 302a4e4a-3172-42b6-9cc0-4a971ab49c1c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 91f12b0d97d2e2065c5bb08d175253c22dffb032
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626243"
---
# <a name="clr-triggers"></a><span data-ttu-id="0f486-102">Trigger CLR</span><span class="sxs-lookup"><span data-stu-id="0f486-102">CLR Triggers</span></span>
  <span data-ttu-id="0f486-103">Grazie all'integrazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con CLR (Common Language Runtime) di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], è possibile utilizzare qualsiasi linguaggio [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] per creare trigger CLR.</span><span class="sxs-lookup"><span data-stu-id="0f486-103">Because of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] common language runtime (CLR), you can use any [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] language to create CLR triggers.</span></span> <span data-ttu-id="0f486-104">In questa sezione vengono fornite informazioni specifiche relative ai trigger implementati utilizzando l'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="0f486-104">This section covers information specific to triggers implemented with CLR integration.</span></span> <span data-ttu-id="0f486-105">Per una descrizione completa dei trigger, vedere [trigger DDL](../../relational-databases/triggers/ddl-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="0f486-105">For a complete discussion of triggers, see [DDL Triggers](../../relational-databases/triggers/ddl-triggers.md).</span></span>  
  
## <a name="what-are-triggers"></a><span data-ttu-id="0f486-106">Definizione dei trigger</span><span class="sxs-lookup"><span data-stu-id="0f486-106">What Are Triggers?</span></span>  
 <span data-ttu-id="0f486-107">Un trigger è un tipo speciale di stored procedure che viene eseguita automaticamente quando viene eseguito un evento del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="0f486-107">A trigger is a special type of stored procedure that automatically runs when a language event executes.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0f486-108">include due tipi generali di trigger: Data Manipulation Language (DML) e Data Definition Language (DDL).</span><span class="sxs-lookup"><span data-stu-id="0f486-108">includes two general types of triggers: data manipulation language (DML) and data definition language (DDL) triggers.</span></span> <span data-ttu-id="0f486-109">I trigger DML possono essere utilizzati quando l'istruzione `INSERT`, `UPDATE` o `DELETE` modifica i dati in una tabella o in una vista specificata.</span><span class="sxs-lookup"><span data-stu-id="0f486-109">DML triggers can be used when `INSERT`, `UPDATE`, or `DELETE` statements modify data in a specified table or view.</span></span> <span data-ttu-id="0f486-110">I trigger DDL attivano stored procedure in risposta a diverse istruzioni DDL, che corrispondono principalmente a istruzioni che iniziano con `CREATE`, `ALTER` e `DROP`.</span><span class="sxs-lookup"><span data-stu-id="0f486-110">DDL triggers fire stored procedures in response to a variety of DDL statements, which are primarily statements that begin with `CREATE`, `ALTER`, and `DROP`.</span></span> <span data-ttu-id="0f486-111">Possono essere utilizzati per attività di amministrazione quali il controllo e la regolazione delle operazioni sul database.</span><span class="sxs-lookup"><span data-stu-id="0f486-111">DDL triggers can be used for administrative tasks, such as auditing and regulating database operations.</span></span>  
  
## <a name="unique-capabilities-of-clr-triggers"></a><span data-ttu-id="0f486-112">Funzionalità univoche dei trigger CLR</span><span class="sxs-lookup"><span data-stu-id="0f486-112">Unique Capabilities of CLR Triggers</span></span>  
 <span data-ttu-id="0f486-113">I trigger scritti in [!INCLUDE[tsql](../../includes/tsql-md.md)] consentono di determinare quali colonne della tabella o della vista di attivazione sono state aggiornate mediante le funzioni `UPDATE(column)` e `COLUMNS_UPDATED()`.</span><span class="sxs-lookup"><span data-stu-id="0f486-113">Triggers written in [!INCLUDE[tsql](../../includes/tsql-md.md)] have the capability of determining which columns from the firing view or table have been updated by using the `UPDATE(column)` and `COLUMNS_UPDATED()` functions.</span></span>  
  
 <span data-ttu-id="0f486-114">Esistono notevoli differenze tra i trigger scritti in un linguaggio CLR e gli altri oggetti di integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="0f486-114">Triggers written in a CLR language differ from other CLR integration objects in several significant ways.</span></span> <span data-ttu-id="0f486-115">I trigger CLR possono:</span><span class="sxs-lookup"><span data-stu-id="0f486-115">CLR triggers can:</span></span>  
  
-   <span data-ttu-id="0f486-116">Fare riferimento ai dati delle tabelle `INSERTED` e `DELETED`</span><span class="sxs-lookup"><span data-stu-id="0f486-116">Reference data in the `INSERTED` and `DELETED` tables</span></span>  
  
-   <span data-ttu-id="0f486-117">Determinare quali colonne sono state modificate in seguito a un'operazione `UPDATE`</span><span class="sxs-lookup"><span data-stu-id="0f486-117">Determine which columns have been modified as a result of an `UPDATE` operation</span></span>  
  
-   <span data-ttu-id="0f486-118">Accedere alle informazioni sugli oggetti di database interessati dall'esecuzione di istruzioni DDL.</span><span class="sxs-lookup"><span data-stu-id="0f486-118">Access information about database objects affected by the execution of DDL statements.</span></span>  
  
 <span data-ttu-id="0f486-119">Queste funzionalità vengono fornite implicitamente nel linguaggio di query o dalla classe `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="0f486-119">These capabilities are provided inherently in the query language, or by the `SqlTriggerContext` class.</span></span> <span data-ttu-id="0f486-120">Per informazioni sui vantaggi dell'integrazione con CLR e sulla scelta tra codice gestito e [!INCLUDE[tsql](../../includes/tsql-md.md)] , vedere [Cenni preliminari sull'integrazione con CLR](../../relational-databases/clr-integration/clr-integration-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0f486-120">For information about the advantages of CLR integration and choosing between managed code and [!INCLUDE[tsql](../../includes/tsql-md.md)], see [Overview of CLR Integration](../../relational-databases/clr-integration/clr-integration-overview.md).</span></span>  
  
## <a name="using-the-sqltriggercontext-class"></a><span data-ttu-id="0f486-121">Utilizzo della classe SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="0f486-121">Using the SqlTriggerContext Class</span></span>  
 <span data-ttu-id="0f486-122">La classe `SqlTriggerContext` non può essere costruita pubblicamente e può essere ottenuta solo accedendo alla proprietà `SqlContext.TriggerContext` all'interno del corpo di un trigger CLR.</span><span class="sxs-lookup"><span data-stu-id="0f486-122">The `SqlTriggerContext` class cannot be publicly constructed and can only be obtained by accessing the `SqlContext.TriggerContext` property within the body of a CLR trigger.</span></span> <span data-ttu-id="0f486-123">È possibile ottenere la classe `SqlTriggerContext` dall'oggetto `SqlContext` attivo chiamando la proprietà `SqlContext.TriggerContext`:</span><span class="sxs-lookup"><span data-stu-id="0f486-123">The `SqlTriggerContext` class can be obtained from the active `SqlContext` by calling the `SqlContext.TriggerContext` property:</span></span>  
  
 `SqlTriggerContext myTriggerContext = SqlContext.TriggerContext;`  
  
 <span data-ttu-id="0f486-124">La classe `SqlTriggerContext` fornisce informazioni sul contesto per il trigger.</span><span class="sxs-lookup"><span data-stu-id="0f486-124">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="0f486-125">Tali informazioni includono il tipo di azione che ha provocato l'attivazione del trigger, le colonne modificate in un'operazione UPDATE e, nel caso di un trigger DDL, una struttura XML `EventData` che descrive l'operazione di attivazione del trigger.</span><span class="sxs-lookup"><span data-stu-id="0f486-125">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a DDL trigger, an XML `EventData` structure which describes the triggering operation.</span></span> <span data-ttu-id="0f486-126">Per ulteriori informazioni, vedere [EVENTDATA &#40;&#41;Transact-SQL ](/sql/t-sql/functions/eventdata-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0f486-126">For more information, see [EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql).</span></span>  
  
### <a name="determining-the-trigger-action"></a><span data-ttu-id="0f486-127">Determinazione dell'azione trigger</span><span class="sxs-lookup"><span data-stu-id="0f486-127">Determining the Trigger Action</span></span>  
 <span data-ttu-id="0f486-128">Dopo aver ottenuto un `SqlTriggerContext`, è possibile utilizzarlo per determinare il tipo di azione che ha causato l'attivazione del trigger.</span><span class="sxs-lookup"><span data-stu-id="0f486-128">Once you have obtained a `SqlTriggerContext`, you can use it to determine the type of action that caused the trigger to fire.</span></span> <span data-ttu-id="0f486-129">Queste informazioni sono disponibili mediante la proprietà `TriggerAction` della classe `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="0f486-129">This information is available through the `TriggerAction` property of the `SqlTriggerContext` class.</span></span>  
  
 <span data-ttu-id="0f486-130">Per i trigger DML, la proprietà `TriggerAction` può essere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f486-130">For DML triggers, the `TriggerAction` property can be one of the following values:</span></span>  
  
-   <span data-ttu-id="0f486-131">TriggerAction.Update (0x1)</span><span class="sxs-lookup"><span data-stu-id="0f486-131">TriggerAction.Update (0x1)</span></span>  
  
-   <span data-ttu-id="0f486-132">TriggerAction.Insert (0x2)</span><span class="sxs-lookup"><span data-stu-id="0f486-132">TriggerAction.Insert (0x2)</span></span>  
  
-   <span data-ttu-id="0f486-133">TriggerAction.Delete (0x3)</span><span class="sxs-lookup"><span data-stu-id="0f486-133">TriggerAction.Delete(0x3)</span></span>  
  
-   <span data-ttu-id="0f486-134">Per i trigger DDL, l'elenco dei valori TriggerAction possibili è molto più lungo.</span><span class="sxs-lookup"><span data-stu-id="0f486-134">For DDL triggers, the list of possible TriggerAction values is considerably longer.</span></span> <span data-ttu-id="0f486-135">Per ulteriori informazioni, vedere "Enumerazione TriggerAction" in .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="0f486-135">Please see "TriggerAction Enumeration" in the .NET Framework SDK for more information.</span></span>  
  
### <a name="using-the-inserted-and-deleted-tables"></a><span data-ttu-id="0f486-136">Utilizzo delle tabelle Inserted e Deleted</span><span class="sxs-lookup"><span data-stu-id="0f486-136">Using the Inserted and Deleted Tables</span></span>  
 <span data-ttu-id="0f486-137">Nelle istruzioni di trigger DML vengono utilizzate due tabelle speciali, ovvero la tabella **inserted** e la tabella **Deleted** .</span><span class="sxs-lookup"><span data-stu-id="0f486-137">Two special tables are used in DML trigger statements: the **inserted** table and the **deleted** table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0f486-138">crea e gestisce queste tabelle automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0f486-138">automatically creates and manages these tables.</span></span> <span data-ttu-id="0f486-139">È possibile utilizzare queste tabelle temporanee per verificare gli effetti di determinate modifiche apportate ai dati e impostare le condizioni per le azioni dei trigger DML. Non è tuttavia possibile modificare direttamente i dati nelle tabelle.</span><span class="sxs-lookup"><span data-stu-id="0f486-139">You can use these temporary tables to test the effects of certain data modifications and to set conditions for DML trigger actions; however, you cannot alter the data in the tables directly.</span></span>  
  
 <span data-ttu-id="0f486-140">I trigger CLR possono accedere alle tabelle **inserted** e **Deleted** tramite il provider in-process CLR.</span><span class="sxs-lookup"><span data-stu-id="0f486-140">CLR triggers can access the **inserted** and **deleted** tables through the CLR in-process provider.</span></span> <span data-ttu-id="0f486-141">A tale scopo è necessario ottenere un oggetto `SqlCommand` dall'oggetto SqlContext.</span><span class="sxs-lookup"><span data-stu-id="0f486-141">This is done by obtaining a `SqlCommand` object from the SqlContext object.</span></span> <span data-ttu-id="0f486-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0f486-142">For example:</span></span>  
  
 <span data-ttu-id="0f486-143">C#</span><span class="sxs-lookup"><span data-stu-id="0f486-143">C#</span></span>  
  
```  
SqlConnection connection = new SqlConnection ("context connection = true");  
connection.Open();  
SqlCommand command = connection.CreateCommand();  
command.CommandText = "SELECT * from " + "inserted";  
```  
  
 <span data-ttu-id="0f486-144">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f486-144">Visual Basic</span></span>  
  
```  
Dim connection As New SqlConnection("context connection=true")  
Dim command As SqlCommand  
connection.Open()  
command = connection.CreateCommand()  
command.CommandText = "SELECT * FROM " + "inserted"  
```  
  
### <a name="determining-updated-columns"></a><span data-ttu-id="0f486-145">Determinazione delle colonne aggiornate</span><span class="sxs-lookup"><span data-stu-id="0f486-145">Determining Updated Columns</span></span>  
 <span data-ttu-id="0f486-146">È possibile determinare il numero di colonne modificate da un'operazione UPDATE tramite la proprietà `ColumnCount` dell'oggetto `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="0f486-146">You can determine the number of columns that were modified by an UPDATE operation by using the `ColumnCount` property of the `SqlTriggerContext` object.</span></span> <span data-ttu-id="0f486-147">Il metodo `IsUpdatedColumn`, che accetta il numero ordinale di colonna come parametro di input, consente di determinare se la colonna è stata aggiornata.</span><span class="sxs-lookup"><span data-stu-id="0f486-147">You can use the `IsUpdatedColumn` method, which takes the column ordinal as an input parameter, to determine whether the column was updated.</span></span> <span data-ttu-id="0f486-148">Il valore `True` indica che la colonna è stata aggiornata.</span><span class="sxs-lookup"><span data-stu-id="0f486-148">A `True` value indicates that the column has been updated.</span></span>  
  
 <span data-ttu-id="0f486-149">Nel frammento di codice seguente, estratto dal trigger EmailAudit riportato più avanti in questo argomento, sono ad esempio elencate tutte le colonne aggiornate:</span><span class="sxs-lookup"><span data-stu-id="0f486-149">For example, this code snippet (from the EmailAudit trigger later in this topic) lists all of the columns updated:</span></span>  
  
 <span data-ttu-id="0f486-150">C#</span><span class="sxs-lookup"><span data-stu-id="0f486-150">C#</span></span>  
  
```  
reader = command.ExecuteReader();  
reader.Read();  
for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
{  
   pipe.Send("Updated column "  
      + reader.GetName(columnNumber) + "? "  
   + triggContext.IsUpdatedColumn(columnNumber).ToString());  
 }  
  
 reader.Close();  
```  
  
 <span data-ttu-id="0f486-151">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f486-151">Visual Basic</span></span>  
  
```  
reader = command.ExecuteReader()  
reader.Read()  
Dim columnNumber As Integer  
  
For columnNumber=0 To triggContext.ColumnCount-1  
  
   pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
   "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
Next  
  
reader.Close()  
```  
  
### <a name="accessing-eventdata-for-clr-ddl-triggers"></a><span data-ttu-id="0f486-152">Accesso a EventData per i trigger CLR DDL</span><span class="sxs-lookup"><span data-stu-id="0f486-152">Accessing EventData for CLR DDL Triggers</span></span>  
 <span data-ttu-id="0f486-153">I trigger DDL, analogamente ai trigger normali, attivano stored procedure in risposta a un evento.</span><span class="sxs-lookup"><span data-stu-id="0f486-153">DDL triggers, like regular triggers, fire stored procedures in response to an event.</span></span> <span data-ttu-id="0f486-154">Diversamente dai trigger DML, tuttavia, questi trigger non vengono attivati in risposta a un'istruzione UPDATE, INSERT o DELETE in una tabella o una vista.</span><span class="sxs-lookup"><span data-stu-id="0f486-154">But unlike DML triggers, they do not fire in response to UPDATE, INSERT, or DELETE statements on a table or view.</span></span> <span data-ttu-id="0f486-155">Tali trigger vengono invece attivati in risposta a diverse istruzioni DDL, che corrispondono principalmente a istruzioni che iniziano con CREATE, ALTER e DROP.</span><span class="sxs-lookup"><span data-stu-id="0f486-155">Instead, they fire in response to a variety of DDL statements, which are primarily statements that begin with CREATE, ALTER, and DROP.</span></span> <span data-ttu-id="0f486-156">I trigger DDL possono essere utilizzati per attività di amministrazione quali il controllo e il monitoraggio delle operazioni sul database e le modifiche di schema.</span><span class="sxs-lookup"><span data-stu-id="0f486-156">DDL triggers can be used for administrative tasks, such as auditing and monitoring of database operations and schema changes.</span></span>  
  
 <span data-ttu-id="0f486-157">Informazioni su un evento che attiva un trigger DDL sono disponibili nella proprietà `EventData` della classe `SqlTriggerContext`.</span><span class="sxs-lookup"><span data-stu-id="0f486-157">Information about an event that fires a DDL trigger is available in the `EventData` property of the `SqlTriggerContext` class.</span></span> <span data-ttu-id="0f486-158">Questa proprietà contiene un valore `xml`.</span><span class="sxs-lookup"><span data-stu-id="0f486-158">This property contains an `xml` value.</span></span> <span data-ttu-id="0f486-159">L'elemento XML Schema include informazioni sugli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f486-159">The xml schema includes information about:</span></span>  
  
-   <span data-ttu-id="0f486-160">Ora dell'evento.</span><span class="sxs-lookup"><span data-stu-id="0f486-160">The time of the event.</span></span>  
  
-   <span data-ttu-id="0f486-161">ID di processo di sistema (SPID) della connessione durante la quale è stato eseguito il trigger.</span><span class="sxs-lookup"><span data-stu-id="0f486-161">The System Process ID (SPID) of the connection during which the trigger executed.</span></span>  
  
-   <span data-ttu-id="0f486-162">Tipo di evento che ha attivato il trigger.</span><span class="sxs-lookup"><span data-stu-id="0f486-162">The type of event that fired the trigger.</span></span>  
  
 <span data-ttu-id="0f486-163">In base al tipo di evento, lo schema include inoltre informazioni aggiuntive quali il database nel quale è stato generato l'evento, l'oggetto per il quale è stato generato l'evento e il comando [!INCLUDE[tsql](../../includes/tsql-md.md)] dell'evento.</span><span class="sxs-lookup"><span data-stu-id="0f486-163">Then, depending on the event type, the schema includes additional information, such as the database in which the event occurred, the object against which the event occurred, and the [!INCLUDE[tsql](../../includes/tsql-md.md)] command of the event.</span></span>  
  
 <span data-ttu-id="0f486-164">Nell'esempio riportato di seguito il trigger DDL restituisce la proprietà `EventData` non elaborata.</span><span class="sxs-lookup"><span data-stu-id="0f486-164">In the following example, the following DDL trigger returns the raw `EventData` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f486-165">L'invio di risultati e messaggi tramite l'oggetto `SqlPipe` è mostrato solo a scopo illustrativo e in genere se ne sconsiglia l'uso nel codice di produzione durante la programmazione dei trigger CLR.</span><span class="sxs-lookup"><span data-stu-id="0f486-165">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code when programming CLR triggers.</span></span> <span data-ttu-id="0f486-166">I dati aggiuntivi restituiti potrebbero essere imprevisti e generare errori nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f486-166">Additional data returned may be unexpected and lead to application errors.</span></span>  
  
 <span data-ttu-id="0f486-167">C#</span><span class="sxs-lookup"><span data-stu-id="0f486-167">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   public static void DropTableTrigger()  
   {  
       SqlTriggerContext triggContext = SqlContext.TriggerContext;             
  
       switch(triggContext.TriggerAction)  
       {  
           case TriggerAction.DropTable:  
           SqlContext.Pipe.Send("Table dropped! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
  
           default:  
           SqlContext.Pipe.Send("Something happened! Here's the EventData:");  
           SqlContext.Pipe.Send(triggContext.EventData.Value);  
           break;  
       }  
   }  
}  
```  
  
 <span data-ttu-id="0f486-168">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f486-168">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    Public Shared Sub DropTableTrigger()  
        Dim triggContext As SqlTriggerContext  
        triggContext = SqlContext.TriggerContext  
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.DropTable  
              SqlContext.Pipe.Send("Table dropped! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
           Case Else  
              SqlContext.Pipe.Send("Something else happened! Here's the EventData:")  
              SqlContext.Pipe.Send(triggContext.EventData.Value)  
  
        End Select  
    End Sub  
End Class     
```  
  
 <span data-ttu-id="0f486-169">L'output di esempio seguente è il valore della proprietà `EventData` restituito dopo un trigger DDL attivato da un evento `CREATE TABLE`</span><span class="sxs-lookup"><span data-stu-id="0f486-169">The following sample output is the `EventData` property value after a DDL trigger fired by a `CREATE TABLE` event:</span></span>  
  
 `<EVENT_INSTANCE><PostTime>2004-04-16T21:17:16.160</PostTime><SPID>58</SPID><EventType>CREATE_TABLE</EventType><ServerName>MACHINENAME</ServerName><LoginName>MYDOMAIN\myname</LoginName><UserName>MYDOMAIN\myname</UserName><DatabaseName>AdventureWorks</DatabaseName><SchemaName>dbo</SchemaName><ObjectName>UserName</ObjectName><ObjectType>TABLE</ObjectType><TSQLCommand><SetOptions ANSI_NULLS="ON" ANSI_NULL_DEFAULT="ON" ANSI_PADDING="ON" QUOTED_IDENTIFIER="ON" ENCRYPTED="FALSE" /><CommandText>create table dbo.UserName  
(  
 UserName varchar(50),  
 RealName varchar(50)  
)  
</CommandText></TSQLCommand></EVENT_INSTANCE>`  
  
 <span data-ttu-id="0f486-170">Oltre alle informazioni accessibili tramite la classe `SqlTriggerContext`, le query possono fare ancora riferimento a `COLUMNS_UPDATED` e alle tabelle Inserted/Deleted all'interno del testo di un comando eseguito in-process.</span><span class="sxs-lookup"><span data-stu-id="0f486-170">In addition to the information accessible through the `SqlTriggerContext` class, queries can still refer to `COLUMNS_UPDATED` and inserted/deleted within the text of a command executed in-process.</span></span>  
  
## <a name="sample-clr-trigger"></a><span data-ttu-id="0f486-171">Trigger CLR di esempio</span><span class="sxs-lookup"><span data-stu-id="0f486-171">Sample CLR Trigger</span></span>  
 <span data-ttu-id="0f486-172">Per questo esempio si consideri lo scenario in cui si lascia l'utente libero di scegliere l'ID desiderato, ma si desidera conoscere gli utenti che hanno immesso in modo specifico un indirizzo di posta elettronica come ID.</span><span class="sxs-lookup"><span data-stu-id="0f486-172">In this example, consider the scenario in which you let the user choose any ID they want, but you want to know the users that specifically entered an e-mail address as an ID.</span></span> <span data-ttu-id="0f486-173">Il trigger seguente consente di rilevare tali informazioni e registrarle nella tabella di controllo.</span><span class="sxs-lookup"><span data-stu-id="0f486-173">The following trigger would detect that information and log it to an audit table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0f486-174">L'invio di risultati e messaggi tramite l'oggetto `SqlPipe` è mostrato solo a scopo illustrativo e in genere se ne sconsiglia l'utilizzo nel codice di produzione.</span><span class="sxs-lookup"><span data-stu-id="0f486-174">Sending results and messages through the `SqlPipe` object is shown here for illustrative purposes only and is generally discouraged for production code.</span></span> <span data-ttu-id="0f486-175">I dati aggiuntivi restituiti potrebbero essere imprevisti e generare errori nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0f486-175">Additional data returned may be unexpected and lead to application errors</span></span>  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Xml;  
using System.Text.RegularExpressions;  
  
public class CLRTriggers  
{  
   [SqlTrigger(Name = @"EmailAudit", Target = "[dbo].[Users]", Event = "FOR INSERT, UPDATE, DELETE")]  
   public static void EmailAudit()  
   {  
      string userName;  
      string realName;  
      SqlCommand command;  
      SqlTriggerContext triggContext = SqlContext.TriggerContext;  
      SqlPipe pipe = SqlContext.Pipe;  
      SqlDataReader reader;  
  
      switch (triggContext.TriggerAction)  
      {  
         case TriggerAction.Insert:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
            reader.Close();  
  
            if (IsValidEMailAddress(userName))  
            {  
               command = new SqlCommand(  
                  @"INSERT [dbo].[UserNameAudit] VALUES ('"  
                  + userName + @"', '" + realName + @"');",  
                  connection);  
               pipe.Send(command.CommandText);  
               command.ExecuteNonQuery();  
               pipe.Send("You inserted: " + userName);  
            }  
         }  
  
         break;  
  
         case TriggerAction.Update:  
         // Retrieve the connection that the trigger is using  
         using (SqlConnection connection  
            = new SqlConnection(@"context connection=true"))  
         {  
            connection.Open();  
            command = new SqlCommand(@"SELECT * FROM INSERTED;",  
               connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
  
            userName = (string)reader[0];  
            realName = (string)reader[1];  
  
            pipe.Send(@"You updated: '" + userName + @"' - '"  
               + realName + @"'");  
  
            for (int columnNumber = 0; columnNumber < triggContext.ColumnCount; columnNumber++)  
            {  
               pipe.Send("Updated column "  
                  + reader.GetName(columnNumber) + "? "  
                  + triggContext.IsUpdatedColumn(columnNumber).ToString());  
            }  
  
            reader.Close();  
         }  
  
         break;  
  
         case TriggerAction.Delete:  
            using (SqlConnection connection  
               = new SqlConnection(@"context connection=true"))  
               {  
                  connection.Open();  
                  command = new SqlCommand(@"SELECT * FROM DELETED;",  
                     connection);  
                  reader = command.ExecuteReader();  
  
                  if (reader.HasRows)  
                  {  
                     pipe.Send(@"You deleted the following rows:");  
                     while (reader.Read())  
                     {  
                        pipe.Send(@"'" + reader.GetString(0)  
                        + @"', '" + reader.GetString(1) + @"'");  
                     }  
  
                     reader.Close();  
  
                     //alternately, to just send a tabular resultset back:  
                     //pipe.ExecuteAndSend(command);  
                  }  
                  else  
                  {  
                     pipe.Send("No rows affected.");  
                  }  
               }  
  
               break;  
            }  
        }  
  
     public static bool IsValidEMailAddress(string email)  
     {  
         return Regex.IsMatch(email, @"^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$");  
     }  
}  
```  
  
 <span data-ttu-id="0f486-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f486-176">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
Imports System.Text.RegularExpressions  
  
'The Partial modifier is only required on one class definition per project.  
Partial Public Class CLRTriggers   
  
    <SqlTrigger(Name:="EmailAudit", Target:="[dbo].[Users]", Event:="FOR INSERT, UPDATE, DELETE")> _  
    Public Shared Sub EmailAudit()  
        Dim userName As String  
        Dim realName As String  
        Dim command As SqlCommand  
        Dim triggContext As SqlTriggerContext  
        Dim pipe As SqlPipe  
        Dim reader As SqlDataReader    
  
        triggContext = SqlContext.TriggerContext      
        pipe = SqlContext.Pipe    
  
        Select Case triggContext.TriggerAction  
           Case TriggerAction.Insert  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 reader.Close()  
  
                 If IsValidEmailAddress(userName) Then  
                     command = New SqlCommand("INSERT [dbo].[UserNameAudit] VALUES ('" & _  
                       userName & "', '" & realName & "');", connection)  
  
                    pipe.Send(command.CommandText)  
                    command.ExecuteNonQuery()  
                    pipe.Send("You inserted: " & userName)  
  
                 End If  
              End Using  
  
           Case TriggerAction.Update  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM INSERTED;", connection)  
  
                 reader = command.ExecuteReader()  
                 reader.Read()  
  
                 userName = CType(reader(0), String)  
                 realName = CType(reader(1), String)  
  
                 pipe.Send("You updated: " & userName & " - " & realName)  
  
                 Dim columnNumber As Integer  
  
                 For columnNumber=0 To triggContext.ColumnCount-1  
  
                    pipe.Send("Updated column " & reader.GetName(columnNumber) & _  
                      "? " & triggContext.IsUpdatedColumn(columnNumber).ToString() )  
  
                 Next  
  
                 reader.Close()  
              End Using  
  
           Case TriggerAction.Delete  
              Using connection As New SqlConnection("context connection=true")  
                 connection.Open()  
                 command = new SqlCommand("SELECT * FROM DELETED;", connection)  
  
                 reader = command.ExecuteReader()  
  
                 If reader.HasRows Then  
                    pipe.Send("You deleted the following rows:")  
  
                    While reader.Read()  
  
                       pipe.Send( reader.GetString(0) & ", " & reader.GetString(1) )  
  
                    End While   
  
                    reader.Close()  
  
                    ' Alternately, just send a tabular resultset back:  
                    ' pipe.ExecuteAndSend(command)  
  
                 Else  
                   pipe.Send("No rows affected.")  
                 End If  
  
              End Using   
        End Select  
    End Sub  
  
    Public Shared Function IsValidEMailAddress(emailAddress As String) As Boolean  
  
       return Regex.IsMatch(emailAddress, "^([\w-]+\.)*?[\w-]+@[\w-]+\.([\w-]+\.)*?[\w]+$")  
    End Function      
End Class  
```  
  
 <span data-ttu-id="0f486-177">Si supponga l'esistenza di due tabelle con le definizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f486-177">Assuming two tables exist with the following definitions:</span></span>  
  
```  
CREATE TABLE Users  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
);  
GO CREATE TABLE UserNameAudit  
(  
    UserName nvarchar(200) NOT NULL,  
    RealName nvarchar(200) NOT NULL  
)  
```  
  
 <span data-ttu-id="0f486-178">L' [!INCLUDE[tsql](../../includes/tsql-md.md)] istruzione che crea il trigger in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è la seguente e presuppone che l'assembly **SQLCLRTest** sia già registrato nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database corrente.</span><span class="sxs-lookup"><span data-stu-id="0f486-178">The [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that creates the trigger in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is as follows, and assumes assembly **SQLCLRTest** is already registered in the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
```  
CREATE TRIGGER EmailAudit  
ON Users  
FOR INSERT, UPDATE, DELETE  
AS  
EXTERNAL NAME SQLCLRTest.CLRTriggers.EmailAudit  
```  
  
## <a name="validating-and-canceling-invalid-transactions"></a><span data-ttu-id="0f486-179">Convalida e annullamento delle transazioni non valide</span><span class="sxs-lookup"><span data-stu-id="0f486-179">Validating and Canceling Invalid Transactions</span></span>  
 <span data-ttu-id="0f486-180">L'utilizzo dei trigger per convalidare e annullare le transazioni INSERT, UPDATE o DELETE non valide o per impedire modifiche allo schema del database è piuttosto comune.</span><span class="sxs-lookup"><span data-stu-id="0f486-180">Using triggers to validate and cancel invalid INSERT, UPDATE, or DELETE transactions or to prevent changes to your database schema is common.</span></span> <span data-ttu-id="0f486-181">A tale scopo è necessario incorporare la logica di convalida nel trigger e quindi eseguire il rollback della transazione corrente se l'azione non soddisfa i criteri di convalida.</span><span class="sxs-lookup"><span data-stu-id="0f486-181">This can be accomplished by incorporating validation logic into your trigger and then rolling back the current transaction if the action does not meet the validation criteria.</span></span>  
  
 <span data-ttu-id="0f486-182">Quando viene chiamato all'interno di un trigger, il metodo `Transaction.Rollback` o un oggetto SqlCommand con il testo del comando "TRANSACTION ROLLBACK" genera un'eccezione con un messaggio di errore ambiguo e deve essere incluso in un blocco try/catch.</span><span class="sxs-lookup"><span data-stu-id="0f486-182">When called within a trigger, the `Transaction.Rollback` method or a SqlCommand with the command text "TRANSACTION ROLLBACK" throws an exception with an ambiguous error message and must be wrapped in a try/catch block.</span></span> <span data-ttu-id="0f486-183">Il messaggio di errore visualizzato è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0f486-183">The error message you see is similar to the following:</span></span>  
  
```  
Msg 6549, Level 16, State 1, Procedure trig_InsertValidator, Line 0  
A .NET Framework error occurred during execution of user defined routine or aggregate 'trig_InsertValidator':   
System.Data.SqlClient.SqlException: Transaction is not allowed to roll back inside a user defined routine, trigger or aggregate because the transaction is not started in that CLR level. Change application logic to enforce strict transaction nesting... User transaction, if any, will be rolled back.  
```  
  
 <span data-ttu-id="0f486-184">Questa eccezione è prevista e il blocco try/catch è necessario per continuare a eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="0f486-184">This exception is expected and the try/catch block is necessary for code execution to continue.</span></span> <span data-ttu-id="0f486-185">Al termine dell'esecuzione del codice del trigger, viene generata un'altra eccezione</span><span class="sxs-lookup"><span data-stu-id="0f486-185">When the trigger code finishes execution, another exception is raised</span></span>  
  
```  
Msg 3991, Level 16, State 1, Procedure trig_InsertValidator, Line 1   
The context transaction which was active before entering user defined routine, trigger or aggregate "trig_InsertValidator" has been ended inside of it, which is not allowed. Change application logic to enforce strict transaction nesting.  
The statement has been terminated.  
```  
  
 <span data-ttu-id="0f486-186">Anche questa eccezione è prevista e per continuare l'esecuzione è necessario un blocco try/catch intorno all'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] che esegue l'azione che attiva il trigger.</span><span class="sxs-lookup"><span data-stu-id="0f486-186">This exception is also expected, and a try/catch block around the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that performs the action that fires the trigger is necessary so that execution can continue.</span></span> <span data-ttu-id="0f486-187">Nonostante le due eccezioni generate, viene eseguito il rollback della transazione e le modifiche non vengono sottoposte a commit nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0f486-187">Despite the two exceptions thrown, the transaction is rolled back and the changes are not committed to the table.</span></span> <span data-ttu-id="0f486-188">Una differenza principale tra i trigger CLR e i trigger [!INCLUDE[tsql](../../includes/tsql-md.md)] sta nel fatto che i trigger [!INCLUDE[tsql](../../includes/tsql-md.md)] possono continuare a eseguire altre operazioni in seguito al rollback della transazione.</span><span class="sxs-lookup"><span data-stu-id="0f486-188">A major difference between CLR triggers and [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers is that [!INCLUDE[tsql](../../includes/tsql-md.md)] triggers can continue to perform more work after the transaction is rolled back.</span></span>  
  
### <a name="example"></a><span data-ttu-id="0f486-189">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f486-189">Example</span></span>  
 <span data-ttu-id="0f486-190">Nel trigger seguente viene eseguita una semplice convalida delle istruzioni INSERT in una tabella.</span><span class="sxs-lookup"><span data-stu-id="0f486-190">The following trigger performs simple validation of INSERT statements on a table.</span></span> <span data-ttu-id="0f486-191">Se il valore intero inserito è uguale a uno, viene eseguito il rollback della transazione e il valore non viene inserito nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0f486-191">If the inserted integer value is equal to one, the transaction is rolled back and the value is not inserted into the table.</span></span> <span data-ttu-id="0f486-192">Tutti gli altri valori interi vengono inseriti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="0f486-192">All other integer values are inserted into the table.</span></span> <span data-ttu-id="0f486-193">Si noti il blocco try/catch intorno al metodo `Transaction.Rollback`.</span><span class="sxs-lookup"><span data-stu-id="0f486-193">Note the try/catch block around the `Transaction.Rollback` method.</span></span> <span data-ttu-id="0f486-194">Lo script [!INCLUDE[tsql](../../includes/tsql-md.md)] crea una tabella di prova, un assembly e una stored procedure gestita.</span><span class="sxs-lookup"><span data-stu-id="0f486-194">The [!INCLUDE[tsql](../../includes/tsql-md.md)] script creates a test table, assembly, and managed stored procedure.</span></span> <span data-ttu-id="0f486-195">Notare che le due istruzioni INSERT vengono inserite in un blocco try/catch in modo da consentire l'intercettazione dell'eccezione generata al termine dell'esecuzione del trigger.</span><span class="sxs-lookup"><span data-stu-id="0f486-195">Note that the two INSERT statements are wrapped in a try/catch block so that the exception thrown when the trigger finishes execution is caught.</span></span>  
  
 <span data-ttu-id="0f486-196">C#</span><span class="sxs-lookup"><span data-stu-id="0f486-196">C#</span></span>  
  
```  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;  
using System.Transactions;  
  
public partial class Triggers  
{  
    // Enter existing table or view for the target and uncomment the attribute line  
    // [Microsoft.SqlServer.Server.SqlTrigger (Name="trig_InsertValidator", Target="Table1", Event="FOR INSERT")]  
    public static void trig_InsertValidator()  
    {  
        using (SqlConnection connection = new SqlConnection(@"context connection=true"))  
        {  
            SqlCommand command;  
            SqlDataReader reader;  
            int value;  
  
            // Open the connection.  
            connection.Open();  
  
            // Get the inserted value.  
            command = new SqlCommand(@"SELECT * FROM INSERTED", connection);  
            reader = command.ExecuteReader();  
            reader.Read();  
            value = (int)reader[0];  
            reader.Close();  
  
            // Rollback the transaction if a value of 1 was inserted.  
            if (1 == value)  
            {  
                try  
                {  
                    // Get the current transaction and roll it back.  
                    Transaction trans = Transaction.Current;  
                    trans.Rollback();                      
                }  
                catch (SqlException ex)  
                {  
                    // Catch the expected exception.                      
                }  
            }  
            else  
            {  
                // Perform other actions here.  
            }  
  
            // Close the connection.  
            connection.Close();              
        }  
    }  
}  
```  
  
 <span data-ttu-id="0f486-197">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f486-197">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Transactions  
  
Partial Public Class Triggers  
' Enter existing table or view for the target and uncomment the attribute line  
' <Microsoft.SqlServer.Server.SqlTrigger(Name:="trig_InsertValidator", Target:="Table1", Event:="FOR INSERT")> _  
Public Shared Sub  trig_InsertValidator ()  
    Using connection As New SqlConnection("context connection=true")  
  
        Dim command As SqlCommand  
        Dim reader As SqlDataReader  
        Dim value As Integer  
  
        ' Open the connection.  
        connection.Open()  
  
        ' Get the inserted value.  
        command = New SqlCommand("SELECT * FROM INSERTED", connection)  
        reader = command.ExecuteReader()  
        reader.Read()  
        value = CType(reader(0), Integer)  
        reader.Close()  
  
        ' Rollback the transaction if a value of 1 was inserted.  
        If value = 1 Then  
  
            Try  
                ' Get the current transaction and roll it back.  
                Dim trans As Transaction  
                trans = Transaction.Current  
                trans.Rollback()  
  
            Catch ex As SqlException  
  
                ' Catch the exception.                      
            End Try  
        Else  
  
            ' Perform other actions here.  
        End If  
  
        ' Close the connection.  
        connection.Close()  
    End Using  
End Sub  
End Class  
```  
  
 <span data-ttu-id="0f486-198">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0f486-198">Transact-SQL</span></span>  
  
```  
-- Create the test table, assembly, and trigger.  
CREATE TABLE Table1(c1 int);  
go  
  
CREATE ASSEMBLY ValidationTriggers from 'E:\programming\ ValidationTriggers.dll';  
go  
  
CREATE TRIGGER trig_InsertValidator  
ON Table1  
FOR INSERT  
AS EXTERNAL NAME ValidationTriggers.Triggers.trig_InsertValidator;  
go  
  
-- Use a Try/Catch block to catch the expected exception  
BEGIN TRY  
   INSERT INTO Table1 VALUES(42)  
   INSERT INTO Table1 VALUES(1)  
END TRY  
BEGIN CATCH  
  SELECT ERROR_NUMBER() AS ErrorNum, ERROR_MESSAGE() AS ErrorMessage  
END CATCH;  
  
-- Clean up.  
DROP TRIGGER trig_InsertValidator;  
DROP ASSEMBLY ValidationTriggers;  
DROP TABLE Table1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f486-199">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f486-199">See Also</span></span>  
 <span data-ttu-id="0f486-200">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0f486-200">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="0f486-201">[Trigger DML](../../relational-databases/triggers/dml-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="0f486-201">[DML Triggers](../../relational-databases/triggers/dml-triggers.md) </span></span>  
 <span data-ttu-id="0f486-202">[Trigger DDL](../../relational-databases/triggers/ddl-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="0f486-202">[DDL Triggers](../../relational-databases/triggers/ddl-triggers.md) </span></span>  
 <span data-ttu-id="0f486-203">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0f486-203">[TRY...CATCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/try-catch-transact-sql) </span></span>  
 <span data-ttu-id="0f486-204">[Compilazione di oggetti di database con Common Language Runtime &#40;integrazione&#41; CLR](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span><span class="sxs-lookup"><span data-stu-id="0f486-204">[Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration](../../relational-databases/clr-integration/database-objects/building-database-objects-with-common-language-runtime-clr-integration.md) </span></span>  
 [<span data-ttu-id="0f486-205">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0f486-205">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
