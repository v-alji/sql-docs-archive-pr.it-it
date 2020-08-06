---
title: Rappresentazione e credenziali per le connessioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- impersonation [CLR integration]
- security [CLR integration]
- database objects [CLR integration], connections
- connections [CLR integration]
- authentication [CLR integration]
- user impersonation [CLR integration]
- credentials [CLR integration]
- database objects [CLR integration], security
ms.assetid: 293dce7d-1db2-4657-992f-8c583d6e9ebb
author: rothja
ms.author: jroth
ms.openlocfilehash: cdbc52e07f4502adda7301ce7f635c050ed9c3c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629868"
---
# <a name="impersonation-and-credentials-for-connections"></a><span data-ttu-id="2439d-102">Rappresentazione e credenziali per le connessioni</span><span class="sxs-lookup"><span data-stu-id="2439d-102">Impersonation and Credentials for Connections</span></span>
  <span data-ttu-id="2439d-103">Nell'integrazione con Common Language Runtime (CRL) di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'utilizzo dell'autenticazione di Windows è complesso, ma più sicuro rispetto all'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2439d-103">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] common language runtime (CLR) integration, using Windows Authentication is complex, but is more secure than using SQL Server Authentication.</span></span> <span data-ttu-id="2439d-104">Utilizzando l'autenticazione di Windows, è necessario tenere conto di alcune considerazioni.</span><span class="sxs-lookup"><span data-stu-id="2439d-104">When using Windows Authentication, keep in mind the following considerations.</span></span>  
  
 <span data-ttu-id="2439d-105">Per impostazione predefinita, un processo di SQL Server che si connette a Windows acquisisce il contesto di sicurezza dell'account di servizio Windows di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2439d-105">By default, a SQL Server process that connects out to Windows acquires the security context of the SQL Server Windows service account.</span></span> <span data-ttu-id="2439d-106">È tuttavia possibile eseguire il mapping di una funzione CLR a un'identità del proxy, in modo che le connessioni in uscita dispongano di un contesto di sicurezza diverso da quello dell'account di servizio Windows.</span><span class="sxs-lookup"><span data-stu-id="2439d-106">But it is possible to map a CLR function to a proxy identity, so that its outbound connections have a different security context than that of the Windows service account.</span></span>  
  
 <span data-ttu-id="2439d-107">In alcuni casi, può essere necessario rappresentare il chiamante tramite la proprietà `SqlContext.WindowsIdentity` anziché procedere con l'esecuzione come account di servizio.</span><span class="sxs-lookup"><span data-stu-id="2439d-107">In some cases, you may want to impersonate the caller by using the `SqlContext.WindowsIdentity` property instead of running as the service account.</span></span> <span data-ttu-id="2439d-108">L'istanza di `WindowsIdentity` rappresenta l'identità del client che ha richiamato il codice chiamante ed è disponibile solo quando il client ha utilizzato l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="2439d-108">The `WindowsIdentity` instance represents the identity of the client that invoked the calling code, and is only available when the client used Windows Authentication.</span></span> <span data-ttu-id="2439d-109">Dopo avere ottenuto l'istanza di `WindowsIdentity`, è possibile chiamare `Impersonate` per modificare il token di sicurezza del thread e quindi aprire le connessioni ADO.NET per conto del client.</span><span class="sxs-lookup"><span data-stu-id="2439d-109">After you have obtained the `WindowsIdentity` instance, you can call `Impersonate` to change the security token of the thread, and then open ADO.NET connections on behalf of the client.</span></span>  
  
 <span data-ttu-id="2439d-110">Dopo aver chiamato SqlContext. WindowsIdentity. Impersonate, non è possibile accedere ai dati locali e non è possibile accedere ai dati di sistema.</span><span class="sxs-lookup"><span data-stu-id="2439d-110">After you call SQLContext.WindowsIdentity.Impersonate, you cannot access local data and you cannot access system data.</span></span> <span data-ttu-id="2439d-111">Per accedere di nuovo ai dati, è necessario chiamare WindowsImpersonationContext. Undo.</span><span class="sxs-lookup"><span data-stu-id="2439d-111">To access data again, you have to call WindowsImpersonationContext.Undo.</span></span>  
  
 <span data-ttu-id="2439d-112">Nell'esempio seguente viene illustrata la modalità di rappresentazione del chiamante mediante la proprietà `SqlContext.WindowsIdentity`.</span><span class="sxs-lookup"><span data-stu-id="2439d-112">The following example shows how to impersonate the caller by using the `SqlContext.WindowsIdentity` property.</span></span>  
  
 <span data-ttu-id="2439d-113">Visual C#</span><span class="sxs-lookup"><span data-stu-id="2439d-113">Visual C#</span></span>  
  
```  
WindowsIdentity clientId = null;  
WindowsImpersonationContext impersonatedUser = null;  
  
clientId = SqlContext.WindowsIdentity;  
  
// This outer try block is used to protect from   
// exception filter attacks which would prevent  
// the inner finally block from executing and   
// resetting the impersonation.  
try  
{  
   try  
   {  
      impersonatedUser = clientId.Impersonate();  
      if (impersonatedUser != null)  
         return GetFileDetails(directoryPath);  
         else return null;  
   }  
   finally  
   {  
      if (impersonatedUser != null)  
         impersonatedUser.Undo();  
   }  
}  
catch  
{  
   throw;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2439d-114">Per informazioni sulle modifiche del comportamento nella rappresentazione, vedere [modifiche di rilievo apportate alle funzionalità di motore di database in SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="2439d-114">For information about behavior changes in impersonation, see [Breaking Changes to Database Engine Features in SQL Server 2014](../../../database-engine/breaking-changes-to-database-engine-features-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="2439d-115">Inoltre, se è stata ottenuta l'istanza dell'identità di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows, per impostazione predefinita non è possibile propagarla in un altro computer, in quanto la propagazione è limitata dall'infrastruttura di sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="2439d-115">Furthermore, if you obtained the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows identity instance, by default you cannot propagate that instance to another computer; Windows security infrastructure restricts that by default.</span></span> <span data-ttu-id="2439d-116">Esiste tuttavia un meccanismo noto come "delega" che abilita la propagazione delle identità di Windows in più computer attendibili.</span><span class="sxs-lookup"><span data-stu-id="2439d-116">There is, however, a mechanism called "delegation" that enables propagation of Windows identities across multiple trusted computers.</span></span> <span data-ttu-id="2439d-117">Per ulteriori informazioni sulla delega, vedere l'articolo TechNet "[transizione del protocollo Kerberos e delega vincolata](https://go.microsoft.com/fwlink/?LinkId=50419)".</span><span class="sxs-lookup"><span data-stu-id="2439d-117">You can learn more about delegation in the TechNet article, "[Kerberos Protocol Transition and Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=50419)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2439d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2439d-118">See Also</span></span>  
 [<span data-ttu-id="2439d-119">Oggetto SqlContext</span><span class="sxs-lookup"><span data-stu-id="2439d-119">SqlContext Object</span></span>](../../clr-integration-data-access-in-process-ado-net/sqlcontext-object.md)  
  
  
