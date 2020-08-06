---
title: Uso di Posta elettronica database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- e-mail [SMO]
- Database Mail [SMO]
- mail [SMO]
ms.assetid: 7605390f-b485-48cc-8d97-e364a066067b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 86ceec7417638f53427ed5a62101f2fdb6d7440a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716167"
---
# <a name="using-database-mail"></a><span data-ttu-id="4e607-102">Utilizzo di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="4e607-102">Using Database Mail</span></span>
  <span data-ttu-id="4e607-103">In SMO il sottosistema Posta elettronica database è rappresentato dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> a cui fa riferimento la proprietà <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A>.</span><span class="sxs-lookup"><span data-stu-id="4e607-103">In SMO, the Database Mail subsystem is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object that is referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property.</span></span> <span data-ttu-id="4e607-104">Tramite l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> SMO, è possibile configurare il sottosistema Posta elettronica database e gestire profili e account di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4e607-104">By using the SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object, you can configure the Database Mail subsystem and manage profiles and mail accounts.</span></span> <span data-ttu-id="4e607-105">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> SMO appartiene all'oggetto `Server`, di conseguenza l'ambito degli account di posta elettronica è a livello del server.</span><span class="sxs-lookup"><span data-stu-id="4e607-105">The SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object belongs to the `Server` object, meaning that scope of the mail accounts is at the server level.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4e607-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="4e607-106">Examples</span></span>  
 <span data-ttu-id="4e607-107">Per usare qualsiasi esempio di codice fornito, è necessario scegliere l'ambiente di programmazione, il modello di programmazione e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4e607-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="4e607-108">Per ulteriori informazioni, vedere [creare un Visual Basic progetto SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [creare un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="4e607-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
 <span data-ttu-id="4e607-109">Per i programmi che utilizzano [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] posta elettronica database, è necessario includere l' `Imports` istruzione per qualificare lo spazio dei nomi della posta.</span><span class="sxs-lookup"><span data-stu-id="4e607-109">For programs that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Database Mail, you must include the `Imports` statement to qualify the Mail namespace.</span></span> <span data-ttu-id="4e607-110">Inserire l'istruzione dopo le altre istruzioni `Imports`, ma prima di qualsiasi dichiarazione nell'applicazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4e607-110">Insert the statement after the other `Imports` statements, before any declarations in the application, such as:</span></span>  
  
 `Imports Microsoft.SqlServer.Management.Smo`  
  
 `Imports Microsoft.SqlServer.Management.Common`  
  
 `Imports Microsoft.SqlServer.Management.Smo.Mail`  
  
## <a name="creating-a-database-mail-account-by-using-visual-basic"></a><span data-ttu-id="4e607-111">Creazione di un account di Posta elettronica database tramite Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4e607-111">Creating a Database Mail Account by Using Visual Basic</span></span>  
 <span data-ttu-id="4e607-112">In questo esempio di codice viene illustrato come creare un account di posta elettronica in SMO.</span><span class="sxs-lookup"><span data-stu-id="4e607-112">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="4e607-113">Il sistema Posta elettronica database è rappresentato dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> e la proprietà <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> fa riferimento ad esso.</span><span class="sxs-lookup"><span data-stu-id="4e607-113">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="4e607-114">È possibile utilizzare SMO per configurare Posta elettronica database a livello di codice, ma non per inviare o gestire i messaggi di posta elettronica ricevuti.</span><span class="sxs-lookup"><span data-stu-id="4e607-114">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>  
  
 <span data-ttu-id="4e607-115">VB.NET</span><span class="sxs-lookup"><span data-stu-id="4e607-115">VB.NET</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMail1](SMO How to#SMO_VBMail1)]  -->  
  
## <a name="creating-a-database-mail-account-by-using-visual-c"></a><span data-ttu-id="4e607-116">Creazione di un account di Posta elettronica database tramite Visual C#</span><span class="sxs-lookup"><span data-stu-id="4e607-116">Creating a Database Mail Account by Using Visual C#</span></span>  
 <span data-ttu-id="4e607-117">In questo esempio di codice viene illustrato come creare un account di posta elettronica in SMO.</span><span class="sxs-lookup"><span data-stu-id="4e607-117">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="4e607-118">Il sistema Posta elettronica database è rappresentato dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> e la proprietà <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> fa riferimento ad esso.</span><span class="sxs-lookup"><span data-stu-id="4e607-118">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="4e607-119">È possibile utilizzare SMO per configurare Posta elettronica database a livello di codice, ma non per inviare o gestire i messaggi di posta elettronica ricevuti.</span><span class="sxs-lookup"><span data-stu-id="4e607-119">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>  
  
```csharp  
{  
         //Connect to the local, default instance of SQL Server.  
         Server srv = default(Server);   
           srv = new Server();   
           //Define the Database Mail service with a SqlMail object variable   
           //and reference it using the Server Mail property.   
           SqlMail sm;   
           sm = srv.Mail;   
           //Define and create a mail account by supplying the Database Mail  
           //service, name, description, display name, and email address  
           //arguments in the constructor.   
           MailAccount a = default(MailAccount);   
           a = new MailAccount(sm, "AdventureWorks2012 Administrator", "AdventureWorks2012 Automated Mailer", "Mail account for administrative e-mail.", "dba@Adventure-Works.com");   
           a.Create();    
}  
```  
  
## <a name="creating-a-database-mail-account-by-using-powershell"></a><span data-ttu-id="4e607-120">Creazione di un account di Posta elettronica database tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e607-120">Creating a Database Mail Account by Using PowerShell</span></span>  
 <span data-ttu-id="4e607-121">In questo esempio di codice viene illustrato come creare un account di posta elettronica in SMO.</span><span class="sxs-lookup"><span data-stu-id="4e607-121">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="4e607-122">Il sistema Posta elettronica database è rappresentato dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> e la proprietà <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> fa riferimento ad esso.</span><span class="sxs-lookup"><span data-stu-id="4e607-122">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="4e607-123">È possibile utilizzare SMO per configurare Posta elettronica database a livello di codice, ma non per inviare o gestire i messaggi di posta elettronica ricevuti.</span><span class="sxs-lookup"><span data-stu-id="4e607-123">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>
  
```powershell  
#Connect to the local, default instance of SQL Server.  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Define the Database Mail; reference it using the Server Mail property.  
$sm = $srv.Mail  
  
#Define and create a mail account by supplying the Database Mail service,  
#name, description, display name, and email address arguments in the constructor.  
$a = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Mail.MailAccount -ArgumentList $sm, `  
"Adventure Works Administrator", "Adventure Works Automated Mailer",`  
 "Mail account for administrative e-mail.", "dba@Adventure-Works.com"  
$a.Create()  
```  
