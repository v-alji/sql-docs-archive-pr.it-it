---
title: Debug di oggetti di database CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- database objects [CLR integration], debugging
- permissions [CLR integration]
- debugging [CLR integration]
- building database objects [CLR integration], debugging
- common language runtime [SQL Server], debugging
ms.assetid: 1332035c-d6ed-424d-8234-46ad21168319
author: rothja
ms.author: jroth
ms.openlocfilehash: 084b2494ec55b502f71154ca1f174a6de6d2ab70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623333"
---
# <a name="debugging-clr-database-objects"></a><span data-ttu-id="d7cb4-102">Debug di oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="d7cb4-102">Debugging CLR Database Objects</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="d7cb4-103">offre il supporto per il debug di oggetti CLR (Common Language Runtime) e [!INCLUDE[tsql](../../../includes/tsql-md.md)] nel database.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-103">provides support for debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="d7cb4-104">Gli aspetti principali del debug in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sono la facilità di installazione e utilizzo e l'integrazione del debugger di SQL Server con il debugger di Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-104">The key aspects of debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are the ease of setup and use, and the integration of the SQL Server debugger with the Microsoft Visual Studio debugger.</span></span> <span data-ttu-id="d7cb4-105">Inoltre, il debug funziona tra linguaggi diversi.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-105">Furthermore, debugging works across languages.</span></span> <span data-ttu-id="d7cb4-106">Gli utenti possono passare senza problemi agli oggetti CLR da [!INCLUDE[tsql](../../../includes/tsql-md.md)] e viceversa.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-106">Users can step seamlessly into CLR objects from [!INCLUDE[tsql](../../../includes/tsql-md.md)], and vice versa.</span></span> <span data-ttu-id="d7cb4-107">Il debugger Transact-SQL in SQL Server Management Studio non può essere utilizzato per eseguire il debug di oggetti di database gestiti, ma è possibile eseguire il debug degli oggetti tramite i debugger disponibili in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-107">The Transact-SQL debugger in SQL Server Management Studio cannot be used to debug managed database objects, but you can debug the objects by using the debuggers in Visual Studio.</span></span> <span data-ttu-id="d7cb4-108">Il debug di oggetti di database gestiti in Visual Studio supporta tutte le caratteristiche di debug comuni, ad esempio l'esecuzione di istruzioni e routine all'interno di routine in esecuzione nel server.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-108">Managed database object debugging in Visual Studio supports all common debugging features, such as "step into" and "step over" statements within routines executing on the server.</span></span> <span data-ttu-id="d7cb4-109">Tramite i debugger è possibile impostare punti di interruzione, controllare lo stack di chiamate, controllare le variabili e modificarne i valori durante il debug.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-109">Debuggers can set breakpoints, inspect the call stack, inspect variables, and modify variable values while debugging.</span></span> <span data-ttu-id="d7cb4-110">Notare che Visual Studio .NET 2003 non può essere utilizzato per la programmazione o il debug dell'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-110">Note that Visual Studio .NET 2003 cannot be used for CLR integration programming or debugging.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="d7cb4-111">viene fornito con .NET Framework preinstallato e non è possibile utilizzare assembly di .NET Framework 2.0 in Visual Studio .NET 2003.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-111">includes the .NET Framework pre-installed, and Visual Studio .NET 2003 cannot use the .NET Framework 2.0 assemblies.</span></span>  
  
 <span data-ttu-id="d7cb4-112">Per altre informazioni sul debug del codice gestito con Visual Studio, vedere l'argomento relativo al[debug del codice gestito](https://go.microsoft.com/fwlink/?LinkId=120377)nella documentazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-112">For more information about debugging managed code using Visual Studio, see the "[Debugging Managed Code](https://go.microsoft.com/fwlink/?LinkId=120377)" topic in the Visual Studio documentation.</span></span>  
  
## <a name="debugging-permissions-and-restrictions"></a><span data-ttu-id="d7cb4-113">Debug di autorizzazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="d7cb4-113">Debugging Permissions and Restrictions</span></span>  
 <span data-ttu-id="d7cb4-114">Il debug è un'operazione con privilegi elevati e pertanto solo i membri del ruolo predefinito del server **sysadmin** possono eseguire questa operazione in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d7cb4-114">Debugging is a highly privileged operation, and therefore only members of the **sysadmin** fixed server role are allowed to do so in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d7cb4-115">Durante il debug vengono applicate le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7cb4-115">The following restrictions apply while debugging:</span></span>  
  
-   <span data-ttu-id="d7cb4-116">Il debug di routine CLR è limitato a un'istanza di debugger alla volta.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-116">Debugging CLR routines is restricted to one debugger instance at a time.</span></span> <span data-ttu-id="d7cb4-117">Questa limitazione viene applicata poiché qualsiasi esecuzione di codice CLR si blocca quando viene raggiunto un punto di interruzione e non continua finché il debugger non supera il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-117">This limitation applies because all CLR code execution freezes when a break point is hit and execution does not continue until the debugger advances from the break point.</span></span> <span data-ttu-id="d7cb4-118">Tuttavia, è possibile continuare il debug di [!INCLUDE[tsql](../../../includes/tsql-md.md)] in altre connessioni.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-118">However, you can continue debugging [!INCLUDE[tsql](../../../includes/tsql-md.md)] in other connections.</span></span> <span data-ttu-id="d7cb4-119">Benché il debug di [!INCLUDE[tsql](../../../includes/tsql-md.md)] non blocchi altre esecuzioni nel server, può causare l'attesa di altre connessioni mantenendo un blocco.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-119">Although [!INCLUDE[tsql](../../../includes/tsql-md.md)] debugging does not freeze other executions on the server, it could cause other connections to wait by holding a lock.</span></span>  
  
-   <span data-ttu-id="d7cb4-120">Non è possibile eseguire il debug delle connessioni esistenti, ma solo di quelle nuove, poiché [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] richiede informazioni sul client e sull'ambiente del debugger prima di poter stabilire la connessione.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-120">Existing connections cannot be debugged, only new connections, as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requires information about the client and debugger environment before the connection can be made.</span></span>  
  
 <span data-ttu-id="d7cb4-121">A causa delle restrizioni indicate sopra, si consiglia di eseguire il debug del codice [!INCLUDE[tsql](../../../includes/tsql-md.md)] e di CLR in un server di prova, non in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-121">Due to the above restrictions, we recommend that [!INCLUDE[tsql](../../../includes/tsql-md.md)] and CLR code be debugged on a test server, and not on a production server.</span></span>  
  
## <a name="overview-of-debugging-managed-database-objects"></a><span data-ttu-id="d7cb4-122">Cenni preliminari sul debug di oggetti di database gestiti</span><span class="sxs-lookup"><span data-stu-id="d7cb4-122">Overview of Debugging Managed Database Objects</span></span>  
 <span data-ttu-id="d7cb4-123">Il debug in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] si basa su un modello per connessione.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-123">Debugging in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] follows a per-connection model.</span></span> <span data-ttu-id="d7cb4-124">Un debugger può rilevare le attività ed eseguirne il debug solo nella connessione client a cui è connesso.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-124">A debugger can detect and debug activities only to the client connection to which it is attached.</span></span> <span data-ttu-id="d7cb4-125">Poiché la funzionalità del debugger non è limitata dal tipo di connessione, è possibile eseguire il debug sia di connessioni del flusso TDS sia di connessioni HTTP.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-125">Because the functionality of the debugger is not limited by the type of connection, both tabular data stream (TDS) and HTTP connections can be debugged.</span></span> <span data-ttu-id="d7cb4-126">Tuttavia, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] non consente il debug delle connessioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-126">However, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not allow debugging existing connections.</span></span> <span data-ttu-id="d7cb4-127">Il debug supporta tutte le caratteristiche di debug comuni all'interno di routine in esecuzione nel server.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-127">Debugging supports all common debugging features within routines executing on the server.</span></span> <span data-ttu-id="d7cb4-128">L'interazione tra un debugger e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] viene effettuata tramite Component Object Model (COM).</span><span class="sxs-lookup"><span data-stu-id="d7cb4-128">The interaction between a debugger and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] happens through distributed Component Object Model (COM).</span></span>  
  
 <span data-ttu-id="d7cb4-129">Per ulteriori informazioni e scenari relativi al debug di stored procedure, funzioni, trigger, tipi definiti dall'utente e aggregati gestiti, vedere l'argomento "[SQL Server debug del database di integrazione CLR](https://go.microsoft.com/fwlink/?LinkId=120378)" nella documentazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-129">For more information and scenarios about debugging managed stored procedures, functions, triggers, user-defined types, and aggregates, see the "[SQL Server CLR Integration Database Debugging](https://go.microsoft.com/fwlink/?LinkId=120378)" topic in the Visual Studio documentation.</span></span>  
  
 <span data-ttu-id="d7cb4-130">È necessario abilitare il protocollo di rete TCP/IP nell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per utilizzare Visual Studio per lo sviluppo e il debug remoti.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-130">The TCP/IP network protocol must be enabled on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in order to use Visual Studio for remote development, debugging, and development.</span></span> <span data-ttu-id="d7cb4-131">Per ulteriori informazioni sull'abilitazione del protocollo TCP/IP nel server, vedere [configure client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="d7cb4-131">For more information about enabling TCP/IP protocol on the server, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
  
#### <a name="to-debug-a-managed-database-object"></a><span data-ttu-id="d7cb4-132">Per eseguire il debug di un oggetto di database gestito</span><span class="sxs-lookup"><span data-stu-id="d7cb4-132">To debug a managed database object</span></span>  
  
1.  <span data-ttu-id="d7cb4-133">Aprire Microsoft Visual Studio, creare un nuovo progetto [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e stabilire una connessione a un database in un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7cb4-133">Open Microsoft Visual Studio, create a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] project, and establish a connection to a database on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="d7cb4-134">Creare un nuovo tipo.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-134">Create a new type.</span></span> <span data-ttu-id="d7cb4-135">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto, scegliere **Aggiungi** e **nuovo elemento...** Dalla finestra **Aggiungi nuovo elemento** selezionare **stored procedure**, **funzione definita dall'utente**, **tipo definito dall'utente**, **trigger**, **aggregazione**o **classe**.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-135">In **Solution Explorer**, right-click the project, select **Add** and **New Item...** From the **Add New Item** window, select **Stored Procedure**, **User-Defined Function**, **User-Defined Type**, **Trigger**, **Aggregate**, or **Class**.</span></span> <span data-ttu-id="d7cb4-136">Specificare un nome per il file di origine del nuovo tipo e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-136">Specify a name for the source file of the new type and click **Add**.</span></span>  
  
3.  <span data-ttu-id="d7cb4-137">Aggiungere il codice per il nuovo tipo nell'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-137">Add code for the new type to the text editor.</span></span> <span data-ttu-id="d7cb4-138">Per un codice di esempio relativo a un esempio di stored procedure, vedere la sezione più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-138">For sample code for an example stored procedure, see the section later in this topic.</span></span>  
  
4.  <span data-ttu-id="d7cb4-139">Aggiungere uno script di test per il tipo.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-139">Add a script that tests the type.</span></span> <span data-ttu-id="d7cb4-140">In **Esplora soluzioni**espandere la directory **script** e fare doppio clic su **test. SQL** per aprire il file di origine dello script di test predefinito.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-140">In **Solution Explorer**, expand the **TestScripts** directory double-click **Test.sql** to open the default test script source file.</span></span> <span data-ttu-id="d7cb4-141">Aggiungere nell'editor di testo uno script di test che richiama il codice di cui eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-141">Add the test script, one that invokes the code to be debugged, to the text editor.</span></span> <span data-ttu-id="d7cb4-142">Di seguito viene fornito uno script di esempio.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-142">See below for a sample script.</span></span>  
  
5.  <span data-ttu-id="d7cb4-143">Inserire uno o più punti di interruzione nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-143">Place one or more breakpoints in the source code.</span></span> <span data-ttu-id="d7cb4-144">Fare clic con il pulsante destro del mouse su una riga di codice nell'editor di testo, all'interno della funzione o della routine di cui si vuole eseguire il debug **e selezionare punto di interruzione e** Inserisci punto di **interruzione**.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-144">Right-click on a line of code in the text editor, within the function or routine you want to debug, and select **Breakpoint** and **Insert Breakpoint**.</span></span> <span data-ttu-id="d7cb4-145">Il punto di interruzione viene aggiunto e la riga di codice viene evidenziata in rosso.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-145">The breakpoint is added, highlighting the line of code in red.</span></span>  
  
6.  <span data-ttu-id="d7cb4-146">Scegliere **Avvia debug** dal menu **debug** per compilare, distribuire e testare il progetto.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-146">In the **Debug** menu, select **Start Debugging** to compile, deploy, and test the project.</span></span> <span data-ttu-id="d7cb4-147">Verrà eseguito lo script di test in Test.sql e verrà richiamato l'oggetto di database gestito.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-147">The test script in Test.sql will be run and the managed database object will be invoked.</span></span>  
  
7.  <span data-ttu-id="d7cb4-148">Quando la freccia gialla che indica il puntatore all'istruzione viene visualizzata in corrispondenza del punto di interruzione, l'esecuzione del codice viene sospesa ed è possibile avviare il debug dell'oggetto di database gestito.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-148">When the yellow arrow designating the instruction pointer appears at the breakpoint code execution pauses and you can begin debugging your managed database object.</span></span> <span data-ttu-id="d7cb4-149">È possibile eseguire un' **istruzione/** routine dal menu **debug** per far avanzare il puntatore all'istruzione alla riga di codice successiva.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-149">You can **Step Over** from the **Debug** menu to advance the instruction pointer to the next line of code.</span></span> <span data-ttu-id="d7cb4-150">La finestra **variabili locali** viene utilizzata per osservare lo stato degli oggetti attualmente evidenziati dal puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-150">The **Locals** window is used to observe the state of the objects currently highlighted by the instruction pointer.</span></span> <span data-ttu-id="d7cb4-151">Le variabili possono essere aggiunte alla finestra **espressioni di controllo** .</span><span class="sxs-lookup"><span data-stu-id="d7cb4-151">Variables can be added to the **Watch** window.</span></span> <span data-ttu-id="d7cb4-152">È possibile osservare lo stato delle variabili controllate durante l'intera sessione di debug, non solo quando la variabile si trova nella riga di codice attualmente evidenziata dal puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-152">The state of watched variables can be observed throughout the entire debugging session, not only when the variable is in the line of code currently highlighted by instruction pointer.</span></span> <span data-ttu-id="d7cb4-153">Scegliere Continua dal menu Debug per fare avanzare il puntatore all'istruzione al successivo punto di interruzione o per completare l'esecuzione della routine se non sono presenti altri punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-153">Select Continue from the Debug menu to advance the instruction pointer to the next breakpoint or to complete execution of the routine if there are no more breakpoints.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d7cb4-154">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7cb4-154">Example</span></span>  
 <span data-ttu-id="d7cb4-155">Nell'esempio seguente viene restituita al chiamante la versione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7cb4-155">The following example returns the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] version to the caller.</span></span>  
  
 <span data-ttu-id="d7cb4-156">C#</span><span class="sxs-lookup"><span data-stu-id="d7cb4-156">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Server;   
  
public class StoredProcedures   
{  
   [Microsoft.SqlServer.Server.SqlProcedure]  
   public static void GetVersion()  
   {  
   using(SqlConnection connection = new SqlConnection("context connection=true"))   
   {  
      connection.Open();  
      SqlCommand command = new SqlCommand("select @@version",  
                                           connection);  
      SqlContext.Pipe.ExecuteAndSend(command);  
      }  
   }  
}  
```  
  
 <span data-ttu-id="d7cb4-157">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7cb4-157">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlClient  
  
Partial Public Class StoredProcedures   
    <Microsoft.SqlServer.Server.SqlProcedure> _  
    Public Shared Sub GetVersion()  
        Using connection As New SqlConnection("context connection=true")  
            connection.Open()  
            Dim command As New SqlCommand("SELECT @@VERSION", connection)  
            SqlContext.Pipe.ExecuteAndSend(command)  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="d7cb4-158">Di seguito viene fornito uno script di test che richiama la stored procedure GetVersion definita sopra.</span><span class="sxs-lookup"><span data-stu-id="d7cb4-158">The following is a test script that invokes the GetVersion stored procedure defined above.</span></span>  
  
```  
EXEC GetVersion  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7cb4-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7cb4-159">See Also</span></span>  
 [<span data-ttu-id="d7cb4-160">Concetti relativi alla programmazione dell'integrazione con CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="d7cb4-160">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
