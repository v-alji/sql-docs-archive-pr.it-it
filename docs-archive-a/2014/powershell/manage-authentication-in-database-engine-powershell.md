---
title: Gestire l'autenticazione nel motore di database PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: ab9212a6-6628-4f08-a38c-d3156e05ddea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 018a2698a43148af971622f54c8418bf23c2c781
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713227"
---
# <a name="manage-authentication-in-database-engine-powershell"></a><span data-ttu-id="92e13-102">Gestire l'autenticazione in motore di database PowerShell</span><span class="sxs-lookup"><span data-stu-id="92e13-102">Manage Authentication in Database Engine PowerShell</span></span>
  <span data-ttu-id="92e13-103">Per impostazione predefinita, i componenti PowerShell di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilizzano l'autenticazione di Windows in caso di connessione a un'istanza del [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92e13-103">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell components use Windows Authentication when connecting to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="92e13-104">È possibile utilizzare l'autenticazione di SQL Server definendo un'unità virtuale PowerShell o specificando i parametri `-Username` e `-Password` per `Invoke-Sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="92e13-104">You can use SQL Server Authentication by either defining a PowerShell virtual drive, or by specifying the `-Username` and `-Password` parameters for `Invoke-Sqlcmd`.</span></span>  
  
1.  <span data-ttu-id="92e13-105">**Prima di iniziare:**  [Autorizzazioni](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="92e13-105">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
2.  <span data-ttu-id="92e13-106">**Per impostare l'autenticazione usando**  [un'unità virtuale](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span><span class="sxs-lookup"><span data-stu-id="92e13-106">**To set authentication, using:**  [A Virtual Drive](#SQLAuthVirtDrv), [Invoke-Sqlcmd](#SQLAuthInvSqlCmd)</span></span>  
  
##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="92e13-107">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="92e13-107">Permissions</span></span>  
 <span data-ttu-id="92e13-108">Tutte le azioni eseguibili in un'istanza del [!INCLUDE[ssDE](../includes/ssde-md.md)] vengono controllate dalle autorizzazioni concesse alle credenziali di autenticazione utilizzate per connettersi all'istanza.</span><span class="sxs-lookup"><span data-stu-id="92e13-108">All actions you can perform in an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] are controlled by the permissions granted to the authentication credentials used to connect to the instance.</span></span> <span data-ttu-id="92e13-109">Per impostazione predefinita, il provider e i cmdlet di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] utilizzano l'account di Windows in esecuzione per eseguire una connessione con autenticazione di Windows al [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92e13-109">By default, the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider and cmdlets use the Windows account under which it is running to make a Windows Authentication connection to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="92e13-110">Per effettuare una connessione con autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è necessario fornire un ID di accesso per l'autenticazione di SQL Server e una password.</span><span class="sxs-lookup"><span data-stu-id="92e13-110">To make a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication connection you must supply a SQL Server Authentication login ID and password.</span></span> <span data-ttu-id="92e13-111">Quando si utilizza il [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider, è necessario associare le [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] credenziali di accesso a un'unità virtuale e quindi utilizzare il comando di modifica della directory ( `cd` ) per connettersi a tale unità.</span><span class="sxs-lookup"><span data-stu-id="92e13-111">When using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider, you must associate the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login credentials with a virtual drive, and then use the change directory command (`cd`) to connect to that drive.</span></span> <span data-ttu-id="92e13-112">In Windows PowerShell le credenziali di sicurezza possono essere associate solo a unità virtuali.</span><span class="sxs-lookup"><span data-stu-id="92e13-112">In Windows PowerShell, security credentials can only be associated with virtual drives.</span></span>  
  
##  <a name="sql-server-authentication-using-a-virtual-drive"></a><a name="SQLAuthVirtDrv"></a><span data-ttu-id="92e13-113">Autenticazione SQL Server tramite un'unità virtuale</span><span class="sxs-lookup"><span data-stu-id="92e13-113">SQL Server Authentication Using a Virtual Drive</span></span>  
 <span data-ttu-id="92e13-114">**Per creare un'unità virtuale associata a un accesso di autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="92e13-114">**To create a virtual drive associated with a SQL Server Authentication login**</span></span>  
  
1.  <span data-ttu-id="92e13-115">Creare una funzione che:</span><span class="sxs-lookup"><span data-stu-id="92e13-115">Create a function that:</span></span>  
  
    1.  <span data-ttu-id="92e13-116">Disponga di parametri per il nome da assegnare all'unità virtuale, l'ID di accesso e il percorso del provider da associare all'unità virtuale.</span><span class="sxs-lookup"><span data-stu-id="92e13-116">Has parameters for the name to give the virtual drive, the login ID, and the provider path to associate with the virtual drive.</span></span>  
  
    2.  <span data-ttu-id="92e13-117">Utilizzare `read-host` per richiedere l'utente la password.</span><span class="sxs-lookup"><span data-stu-id="92e13-117">Uses `read-host` to prompt the user for the password.</span></span>  
  
    3.  <span data-ttu-id="92e13-118">Utilizzare `new-object` per creare un oggetto delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="92e13-118">Uses `new-object` to create a credentials object.</span></span>  
  
    4.  <span data-ttu-id="92e13-119">Utilizzare `new-psdrive` per creare un'unità virtuale con le credenziali fornite.</span><span class="sxs-lookup"><span data-stu-id="92e13-119">Uses `new-psdrive` to create a virtual drive with the supplied credentials.</span></span>  
  
2.  <span data-ttu-id="92e13-120">Richiamare la funzione per creare un'unità virtuale con le credenziali fornite.</span><span class="sxs-lookup"><span data-stu-id="92e13-120">Invoke the function to create a virtual drive with the supplied credentials.</span></span>  
  
### <a name="example-virtual-drive"></a><span data-ttu-id="92e13-121">Esempio (unità virtuale)</span><span class="sxs-lookup"><span data-stu-id="92e13-121">Example (Virtual Drive)</span></span>  
 <span data-ttu-id="92e13-122">In questo esempio viene creata una funzione denominata **sqldrive** che può essere utilizzata per creare un'unità virtuale associata all'account di accesso con autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e all'istanza specificati.</span><span class="sxs-lookup"><span data-stu-id="92e13-122">This example creates a function named **sqldrive** that you can use to create a virtual drive that is associated with the specified [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login and instance.</span></span>  
  
 <span data-ttu-id="92e13-123">La funzione **sqldrive** richiede di immettere la password per effettuare l'accesso, mascherandola durante la digitazione.</span><span class="sxs-lookup"><span data-stu-id="92e13-123">The **sqldrive** function prompts you to enter the password for your login, masking the password as you type it in.</span></span> <span data-ttu-id="92e13-124">Quindi, ogni volta che si utilizza il comando di modifica della directory ( `cd` ) per connettersi a un percorso utilizzando il nome dell'unità virtuale, tutte le operazioni vengono eseguite utilizzando le credenziali di accesso per l' [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] autenticazione fornite al momento della creazione dell'unità.</span><span class="sxs-lookup"><span data-stu-id="92e13-124">Then, whenever you use the change directory command (`cd`) to connect to a path by using the virtual drive name, all operations are performed by using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication login credentials that you supplied when you created the drive.</span></span>  
  
```powershell
## Create a function that specifies the login and prompts for the password.  
  
function sqldrive  
{  
    param( [string]$name, [string]$login = "MyLogin", [string]$root = "SQLSERVER:\SQL\MyComputer\MyInstance" )  
    $pwd = Read-Host -AsSecureString -Prompt "Password"  
    $cred = New-Object System.Management.Automation.PSCredential -argumentlist $login, $pwd  
    New-PSDrive $name -PSProvider SqlServer -Root $root -Credential $cred -Scope 1  
}  
  
## Use the sqldrive function to create a SQLAuth virtual drive.  
sqldrive SQLAuth  
  
## CD to the virtual drive, which invokes the supplied authentication credentials.  
cd SQLAuth  
```  
  
##  <a name="sql-server-authentication-using-invoke-sqlcmd"></a><a name="SQLAuthInvSqlCmd"></a><span data-ttu-id="92e13-125">Autenticazione SQL Server tramite Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="92e13-125">SQL Server Authentication Using Invoke-Sqlcmd</span></span>  
 <span data-ttu-id="92e13-126">**Per utilizzare Invoke-Sqlcmd con l'autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="92e13-126">**To use Invoke-Sqlcmd with SQL Server Authentication**</span></span>  
  
1.  <span data-ttu-id="92e13-127">Utilizzare il parametro `-Username` per specificare un ID di accesso e il parametro `-Password` per specificare la password associata.</span><span class="sxs-lookup"><span data-stu-id="92e13-127">Use the `-Username` parameter to specify a login ID, and the `-Password` parameter to specify the associated password.</span></span>  
  
### <a name="example-invoke-sqlcmd"></a><span data-ttu-id="92e13-128">Esempio (Invoke-Sqlcmd)</span><span class="sxs-lookup"><span data-stu-id="92e13-128">Example (Invoke-Sqlcmd)</span></span>  
 <span data-ttu-id="92e13-129">In questo esempio viene utilizzato l'host della lettura cmdlet per la richiesta di una password all'utente, quindi viene stabilita la connessione tramite l'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="92e13-129">This example uses the read-host cmdlet to prompt the user for a password, and then connects using SQL Server Authentication.</span></span>  
  
```powershell
## Prompt the user for their password.  
$pwd = Read-Host -AsSecureString -Prompt "Password"  
  
Invoke-Sqlcmd -Query "SELECT GETDATE() AS TimeOfQuery;" -ServerInstance "MyComputer\MyInstance" -Username "MyLogin" -Password $pwd  
```  
  
## <a name="see-also"></a><span data-ttu-id="92e13-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92e13-130">See Also</span></span>  
 <span data-ttu-id="92e13-131">[SQL Server PowerShell](sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="92e13-131">[SQL Server PowerShell](sql-server-powershell.md) </span></span>  
 <span data-ttu-id="92e13-132">[Provider di SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="92e13-132">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="92e13-133">Cmdlet Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="92e13-133">Invoke-Sqlcmd cmdlet</span></span>](../database-engine/invoke-sqlcmd-cmdlet.md)  
