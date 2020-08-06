---
title: Oggetto SqlContext | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- Windows identity [CLR integration]
- SqlContext object
- context [CLR integration]
ms.assetid: 67437853-8a55-44d9-9337-90689ebba730
author: rothja
ms.author: jroth
ms.openlocfilehash: 10f036e274925f7b28b79f619f8e24b3e8804140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718269"
---
# <a name="sqlcontext-object"></a><span data-ttu-id="904c4-102">Oggetto SqlContext</span><span class="sxs-lookup"><span data-stu-id="904c4-102">SqlContext Object</span></span>
  <span data-ttu-id="904c4-103">È possibile richiamare il codice gestito nel server quando si chiama una routine o una funzione, quando si chiama un metodo su un tipo CLR definito dall'utente o quando l'azione genera un trigger definito in uno dei linguaggi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="904c4-103">You invoke managed code in the server when you call a procedure or function, when you call a method on a common language runtime (CLR) user-defined type, or when your action fires a trigger defined in any of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework languages.</span></span> <span data-ttu-id="904c4-104">Dal momento che l'esecuzione di questo codice viene richiesta come parte di una connessione utente, è necessario l'accesso al contesto del chiamante dal codice in esecuzione sul server.</span><span class="sxs-lookup"><span data-stu-id="904c4-104">Because execution of this code is requested as part of a user connection, access to the context of the caller from the code running in the server is required.</span></span> <span data-ttu-id="904c4-105">Determinate operazioni di accesso ai dati potrebbero inoltre essere valide solo se eseguite nel contesto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="904c4-105">In addition, certain data access operations may only be valid if run under the context of the caller.</span></span> <span data-ttu-id="904c4-106">L'accesso alle pseudotabelle inserite ed eliminate utilizzate nelle operazioni del trigger, ad esempio, è valido solo nel contesto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="904c4-106">For example, access to inserted and deleted pseudo-tables used in trigger operations is only valid under the context of the caller.</span></span>  
  
 <span data-ttu-id="904c4-107">Il contesto del chiamante può essere un'astrazione in un oggetto `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="904c4-107">The context of the caller is abstracted in a `SqlContext` object.</span></span> <span data-ttu-id="904c4-108">Per ulteriori informazioni sulle proprietà e sui metodi `SqlTriggerContext`, vedere la documentazione di riferimento della classe `Microsoft.SqlServer.Server.SqlTriggerContext` in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="904c4-108">For more information about the `SqlTriggerContext` methods and properties, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
 <span data-ttu-id="904c4-109">`SqlContext` fornisce l'accesso ai componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="904c4-109">`SqlContext` provides access to the following components:</span></span>  
  
-   <span data-ttu-id="904c4-110">`SqlPipe`: l'oggetto `SqlPipe` rappresenta la "pipe" tramite la quale i risultati vengono propagati al client.</span><span class="sxs-lookup"><span data-stu-id="904c4-110">`SqlPipe`: The `SqlPipe` object represents the "pipe" through which results flow to the client.</span></span> <span data-ttu-id="904c4-111">Per ulteriori informazioni sull' `SqlPipe` oggetto, vedere [SqlPipe Object](sqlpipe-object.md).</span><span class="sxs-lookup"><span data-stu-id="904c4-111">For more information about the `SqlPipe` object, see [SqlPipe Object](sqlpipe-object.md).</span></span>  
  
-   <span data-ttu-id="904c4-112">`SqlTriggerContext`: l'oggetto `SqlTriggerContext` può essere recuperato solo dall'interno un trigger CLR.</span><span class="sxs-lookup"><span data-stu-id="904c4-112">`SqlTriggerContext`: The `SqlTriggerContext` object can only be retrieved from within a CLR trigger.</span></span> <span data-ttu-id="904c4-113">Fornisce informazioni sull'operazione che ha attivato il trigger e una mappa delle colonne che sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="904c4-113">It provides information about the operation that caused the trigger to fire and a map of the columns that were updated.</span></span> <span data-ttu-id="904c4-114">Per ulteriori informazioni sull' `SqlTriggerContext` oggetto, vedere [oggetto SqlTriggerContext](sqltriggercontext-object.md).</span><span class="sxs-lookup"><span data-stu-id="904c4-114">For more information about the `SqlTriggerContext` object, see [SqlTriggerContext Object](sqltriggercontext-object.md).</span></span>  
  
-   <span data-ttu-id="904c4-115">`IsAvailable`: la proprietà `IsAvailable` viene utilizzata per stabilire la disponibilità del contesto.</span><span class="sxs-lookup"><span data-stu-id="904c4-115">`IsAvailable`: The `IsAvailable` property is used to determine context availability.</span></span>  
  
-   <span data-ttu-id="904c4-116">`WindowsIdentity`: la proprietà `WindowsIdentity` viene utilizzata per recuperare l'identità di Windows del chiamante.</span><span class="sxs-lookup"><span data-stu-id="904c4-116">`WindowsIdentity`: The `WindowsIdentity` property is used to retrieve the Windows identity of the caller.</span></span>  
  
## <a name="determining-context-availability"></a><span data-ttu-id="904c4-117">Determinazione della disponibilità del contesto</span><span class="sxs-lookup"><span data-stu-id="904c4-117">Determining Context Availability</span></span>  
 <span data-ttu-id="904c4-118">Eseguire una query sulla classe `SqlContext` per vedere se il codice attualmente in esecuzione viene eseguito in-process.</span><span class="sxs-lookup"><span data-stu-id="904c4-118">Query the `SqlContext` class to see if the currently executing code is running in-process.</span></span> <span data-ttu-id="904c4-119">A tale scopo, verificare la proprietà `IsAvailable` dell'oggetto `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="904c4-119">To do this, check the `IsAvailable` property of the `SqlContext` object.</span></span> <span data-ttu-id="904c4-120">La proprietà `IsAvailable` è di sola lettura e restituisce `True` se il codice chiamante viene eseguito all'interno di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e se è possibile accedere ad altri membri di `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="904c4-120">The `IsAvailable` property is read-only, and returns `True` if the calling code is running inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and if other `SqlContext` members can be accessed.</span></span> <span data-ttu-id="904c4-121">Se la proprietà `IsAvailable` restituisce `False`, tutti gli altri membri di `SqlContext` generano un'eccezione `InvalidOperationException` se vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="904c4-121">If the `IsAvailable` property returns `False`, all the other `SqlContext` members throw an `InvalidOperationException`, if used.</span></span> <span data-ttu-id="904c4-122">Se `IsAvailable` restituisce `False`, qualsiasi tentativo di aprire un oggetto connessione in cui "context connection=true" nella stringa di connessione non riesce.</span><span class="sxs-lookup"><span data-stu-id="904c4-122">If `IsAvailable` returns `False`, any attempt to open a connection object that has "context connection=true" in the connection string fails.</span></span>  
  
## <a name="retrieving-windows-identity"></a><span data-ttu-id="904c4-123">Recupero dell'identità di Windows</span><span class="sxs-lookup"><span data-stu-id="904c4-123">Retrieving Windows Identity</span></span>  
 <span data-ttu-id="904c4-124">Il codice CLR in esecuzione all'interno di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene sempre richiamato nel contesto dell'account del processo.</span><span class="sxs-lookup"><span data-stu-id="904c4-124">CLR code executing inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is always invoked in the context of the process account.</span></span> <span data-ttu-id="904c4-125">Se il codice deve eseguire determinate azioni utilizzando l'identità dell'utente chiamante, anziché l'identità di processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è necessario ottenere un token di rappresentazione mediante la proprietà `WindowsIdentity` dell'oggetto `SqlContext`.</span><span class="sxs-lookup"><span data-stu-id="904c4-125">If the code should perform certain actions using the identity of the calling user, instead of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process identity, then an impersonation token should be obtained through the `WindowsIdentity` property of the `SqlContext` object.</span></span> <span data-ttu-id="904c4-126">La proprietà `WindowsIdentity` restituisce un'istanza di `WindowsIdentity` che rappresenta l'identità di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows del chiamante oppure Null se il client è stato autenticato con l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="904c4-126">The `WindowsIdentity` property returns a `WindowsIdentity` instance representing the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows identity of the caller, or null if the client was authenticated using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="904c4-127">Solo gli assembly contrassegnati con le autorizzazioni `EXTERNAL_ACCESS` o `UNSAFE` possono accedere a questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="904c4-127">Only assemblies marked with `EXTERNAL_ACCESS` or `UNSAFE` permissions can access this property.</span></span>  
  
 <span data-ttu-id="904c4-128">Dopo avere ottenuto l'oggetto `WindowsIdentity`, i chiamanti possono rappresentare l'account del client ed eseguirne le azioni.</span><span class="sxs-lookup"><span data-stu-id="904c4-128">After obtaining the `WindowsIdentity` object, callers can impersonate the client account and perform actions on their behalf.</span></span>  
  
 <span data-ttu-id="904c4-129">L'identità del chiamante è disponibile solo tramite `SqlContext.WindowsIdentity` se il client che ha iniziato l'esecuzione della stored procedure o della funzione ha eseguito la connessione al server utilizzando l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="904c4-129">The identity of the caller is only available through `SqlContext.WindowsIdentity` if the client that initiated execution of the stored-procedure or function connected to the server using Windows Authentication.</span></span> <span data-ttu-id="904c4-130">Se invece è stata utilizzata l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], questa proprietà è Null e il codice non è in grado di rappresentare il chiamante.</span><span class="sxs-lookup"><span data-stu-id="904c4-130">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication was used instead, this property is null and the code is unable to impersonate the caller.</span></span>  
  
### <a name="example"></a><span data-ttu-id="904c4-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="904c4-131">Example</span></span>  
 <span data-ttu-id="904c4-132">Nell'esempio riportato di seguito viene illustrato come ottenere l'identità di Windows del client chiamante e rappresentare il client.</span><span class="sxs-lookup"><span data-stu-id="904c4-132">The following example shows how to get the Windows identity of the calling client and impersonate the client.</span></span>  
  
 <span data-ttu-id="904c4-133">C#</span><span class="sxs-lookup"><span data-stu-id="904c4-133">C#</span></span>  
  
```  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void WindowsIDTestProc()  
{  
    WindowsIdentity clientId = null;  
    WindowsImpersonationContext impersonatedUser = null;  
  
    // Get the client ID.  
    clientId = SqlContext.WindowsIdentity;  
  
    // This outer try block is used to thwart exception filter   
    // attacks which would prevent the inner finally   
    // block from executing and resetting the impersonation.  
    try  
    {  
        try  
        {  
            impersonatedUser = clientId.Impersonate();  
            if (impersonatedUser != null)  
            {  
                // Perform some action using impersonation.  
            }  
        }  
        finally  
        {  
            // Undo impersonation.  
            if (impersonatedUser != null)  
                impersonatedUser.Undo();  
        }  
    }  
    catch  
    {  
        throw;  
    }  
}  
```  
  
 <span data-ttu-id="904c4-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="904c4-134">Visual Basic</span></span>  
  
```  
<Microsoft.SqlServer.Server.SqlProcedure()> _  
Public Shared Sub  WindowsIDTestProcVB ()  
    Dim clientId As WindowsIdentity  
    Dim impersonatedUser As WindowsImpersonationContext  
  
    ' Get the client ID.  
    clientId = SqlContext.WindowsIdentity  
  
    ' This outer try block is used to thwart exception filter   
    ' attacks which would prevent the inner finally   
    ' block from executing and resetting the impersonation.  
  
    Try  
        Try  
  
            impersonatedUser = clientId.Impersonate()  
  
            If impersonatedUser IsNot Nothing Then  
                ' Perform some action using impersonation.  
            End If  
  
        Finally  
            ' Undo impersonation.  
            If impersonatedUser IsNot Nothing Then  
                impersonatedUser.Undo()  
            End If  
        End Try  
  
    Catch e As Exception  
  
        Throw e  
  
    End Try  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="904c4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="904c4-135">See Also</span></span>  
 <span data-ttu-id="904c4-136">[SqlPipe (oggetto)](sqlpipe-object.md) </span><span class="sxs-lookup"><span data-stu-id="904c4-136">[SqlPipe Object](sqlpipe-object.md) </span></span>  
 <span data-ttu-id="904c4-137">[Oggetto SqlTriggerContext](sqltriggercontext-object.md) </span><span class="sxs-lookup"><span data-stu-id="904c4-137">[SqlTriggerContext Object](sqltriggercontext-object.md) </span></span>  
 <span data-ttu-id="904c4-138">[Trigger CLR](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="904c4-138">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="904c4-139">Estensioni specifiche in-process di SQL Server ad ADO.NET</span><span class="sxs-lookup"><span data-stu-id="904c4-139">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](sql-server-in-process-specific-extensions-to-ado-net.md)  
  
  
