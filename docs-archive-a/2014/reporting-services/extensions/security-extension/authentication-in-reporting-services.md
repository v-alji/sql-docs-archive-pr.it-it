---
title: Autenticazione in Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], authentication
- forms-based authentication [Reporting Services]
- authentication [Reporting Services]
- custom authentication [Reporting Services]
ms.assetid: 103ce1f9-31d8-44bb-b540-2752e4dcf60b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59e97ba6ef849d8b4bfddfd6953c85826e351d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629231"
---
# <a name="authentication-in-reporting-services"></a><span data-ttu-id="41a56-102">Autenticazione in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41a56-102">Authentication in Reporting Services</span></span>
  <span data-ttu-id="41a56-103">L'autenticazione è il processo di determinazione del diritto di un utente a un'identità.</span><span class="sxs-lookup"><span data-stu-id="41a56-103">Authentication is the process of establishing a user's right to an identity.</span></span> <span data-ttu-id="41a56-104">Per autenticare un utente sono disponibili numerose tecniche.</span><span class="sxs-lookup"><span data-stu-id="41a56-104">There are many techniques that you can use to authenticate a user.</span></span> <span data-ttu-id="41a56-105">La più comune consiste nell'utilizzo di password.</span><span class="sxs-lookup"><span data-stu-id="41a56-105">The most common way is to use passwords.</span></span> <span data-ttu-id="41a56-106">Quando si implementa l'autenticazione basata su form, ad esempio, si sceglie un'implementazione che richiede le credenziali agli utenti (generalmente tramite un'interfaccia in cui vengono richiesti un nome di accesso e una password), quindi si convalidano gli utenti in base a un archivio dati, ad esempio una tabella di database o un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="41a56-106">When you implement Forms Authentication, for example, you want an implementation that queries users for credentials (usually by some interface that requests a login name and password) and then validates users against a data store, such as a database table or configuration file.</span></span> <span data-ttu-id="41a56-107">Se non è possibile convalidare le credenziali, il processo di autenticazione non riesce e all'utente viene assegnata un'identità anonima.</span><span class="sxs-lookup"><span data-stu-id="41a56-107">If the credentials can't be validated, the authentication process fails and the user will assume an anonymous identity.</span></span>  
  
## <a name="custom-authentication-in-reporting-services"></a><span data-ttu-id="41a56-108">Autenticazione personalizzata in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="41a56-108">Custom Authentication in Reporting Services</span></span>  
 <span data-ttu-id="41a56-109">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] l'autenticazione degli utenti viene gestita dal sistema operativo Windows tramite la sicurezza integrata o tramite operazioni esplicite di ricezione e convalida delle credenziali utente.</span><span class="sxs-lookup"><span data-stu-id="41a56-109">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], the Windows operating system handles the authentication of users either through integrated security or through the explicit reception and validation of user credentials.</span></span> <span data-ttu-id="41a56-110">L'autenticazione personalizzata può essere sviluppata in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] per supportare schemi di autenticazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="41a56-110">Custom authentication can be developed in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to support additional authentication schemes.</span></span> <span data-ttu-id="41a56-111">Ciò è possibile tramite l'interfaccia dell'estensione di sicurezza <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>.</span><span class="sxs-lookup"><span data-stu-id="41a56-111">This is made possible through the security extension interface <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>.</span></span> <span data-ttu-id="41a56-112">Tutte le estensioni ereditano dall'interfaccia di base <xref:Microsoft.ReportingServices.Interfaces.IExtension> per qualsiasi estensione distribuita e utilizzata dal server di report.</span><span class="sxs-lookup"><span data-stu-id="41a56-112">All extensions inherit from the <xref:Microsoft.ReportingServices.Interfaces.IExtension> base interface for any extension deployed and used by the report server.</span></span> <span data-ttu-id="41a56-113"><xref:Microsoft.ReportingServices.Interfaces.IExtension> e <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension> sono membri dello spazio dei nomi <xref:Microsoft.ReportingServices.Interfaces>.</span><span class="sxs-lookup"><span data-stu-id="41a56-113"><xref:Microsoft.ReportingServices.Interfaces.IExtension>, as well as <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>, are members of the <xref:Microsoft.ReportingServices.Interfaces> namespace.</span></span>  
  
 <span data-ttu-id="41a56-114">La principale modalità di autenticazione in un server di report in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] è costituita dal metodo <xref:ReportService2010.ReportingService2010.LogonUser%2A>.</span><span class="sxs-lookup"><span data-stu-id="41a56-114">The primary way to authenticate against a report server in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span> <span data-ttu-id="41a56-115">Questo membro del servizio Web Reporting Services può essere utilizzato per passare le credenziali utente a un server di report per la convalida.</span><span class="sxs-lookup"><span data-stu-id="41a56-115">This member of the Reporting Services Web service can be used to pass user credentials to a report server for validation.</span></span> <span data-ttu-id="41a56-116">L'estensione di sicurezza sottostante implementa **IAuthenticationExtension. LogonUser** che contiene il codice di autenticazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="41a56-116">Your underlying security extension implements **IAuthenticationExtension.LogonUser** which contains your custom authentication code.</span></span> <span data-ttu-id="41a56-117">Nell'esempio di autenticazione basata su form, **LogonUser**, che esegue un controllo di autenticazione in base alle credenziali fornite e a un archivio utente personalizzato in un database.</span><span class="sxs-lookup"><span data-stu-id="41a56-117">In the Forms Authentication sample, **LogonUser**, which performs an authentication check against the supplied credentials and a custom user store in a database.</span></span> <span data-ttu-id="41a56-118">Un esempio di implementazione di **LogonUser** è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="41a56-118">An example of an implementation of **LogonUser** looks like this:</span></span>  
  
```  
public bool LogonUser(string userName, string password, string authority)  
{  
   return AuthenticationUtilities.VerifyPassword(userName, password);  
}  
  
```  
  
 <span data-ttu-id="41a56-119">La funzione di esempio seguente viene utilizzata per verificare le credenziali fornite:</span><span class="sxs-lookup"><span data-stu-id="41a56-119">The following sample function is used to verify the supplied credentials:</span></span>  
  
```  
  
internal static bool VerifyPassword(string suppliedUserName,  
   string suppliedPassword)  
{   
   bool passwordMatch = false;  
   // Get the salt and pwd from the database based on the user name.  
   // See "How To: Use DPAPI (Machine Store) from ASP.NET," "How To:  
   // Use DPAPI (User Store) from Enterprise Services," and "How To:  
   // Create a DPAPI Library" for more information about how to use  
   // DPAPI to securely store connection strings.  
   SqlConnection conn = new SqlConnection(  
      "Server=localhost;" +   
      "Integrated Security=SSPI;" +  
      "database=UserAccounts");  
   SqlCommand cmd = new SqlCommand("LookupUser", conn);  
   cmd.CommandType = CommandType.StoredProcedure;  
  
   SqlParameter sqlParam = cmd.Parameters.Add("@userName",  
       SqlDbType.VarChar,  
       255);  
   sqlParam.Value = suppliedUserName;  
   try  
   {  
      conn.Open();  
      SqlDataReader reader = cmd.ExecuteReader();  
      reader.Read(); // Advance to the one and only row  
      // Return output parameters from returned data stream  
      string dbPasswordHash = reader.GetString(0);  
      string salt = reader.GetString(1);  
      reader.Close();  
      // Now take the salt and the password entered by the user  
      // and concatenate them together.  
      string passwordAndSalt = String.Concat(suppliedPassword, salt);  
      // Now hash them  
      string hashedPasswordAndSalt =  
         FormsAuthentication.HashPasswordForStoringInConfigFile(  
         passwordAndSalt,  
         "SHA1");  
      // Now verify them. Returns true if they are equal.  
      passwordMatch = hashedPasswordAndSalt.Equals(dbPasswordHash);  
   }  
   catch (Exception ex)  
   {  
       throw new Exception("Exception verifying password. " +  
          ex.Message);  
   }  
   finally  
   {  
       conn.Close();  
   }  
   return passwordMatch;  
}  
```  
  
## <a name="authentication-flow"></a><span data-ttu-id="41a56-120">Flusso di autenticazione</span><span class="sxs-lookup"><span data-stu-id="41a56-120">Authentication Flow</span></span>  
 <span data-ttu-id="41a56-121">Il servizio Web Reporting Services fornisce estensioni di autenticazione personalizzate per l'abilitazione dell'autenticazione basata su form da parte di Gestione report e del server di report.</span><span class="sxs-lookup"><span data-stu-id="41a56-121">The Reporting Services Web service provides custom authentication extensions to enable Forms Authentication by Report Manager and the report server.</span></span>  
  
 <span data-ttu-id="41a56-122">Il metodo <xref:ReportService2010.ReportingService2010.LogonUser%2A> del servizio Web Reporting Services viene utilizzato per inviare le credenziali al server di report per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="41a56-122">The <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of the Reporting Services Web service is used to submit credentials to the report server for authentication.</span></span> <span data-ttu-id="41a56-123">Il servizio Web utilizza le intestazioni HTTP per passare un ticket di autenticazione (noto come "cookie") dal server al client per le richieste di accesso convalidate.</span><span class="sxs-lookup"><span data-stu-id="41a56-123">The Web service uses HTTP headers to pass an authentication ticket (known as a "cookie") from the server to the client for validated logon requests.</span></span>  
  
 <span data-ttu-id="41a56-124">Nell'illustrazione seguente è rappresentato il metodo di autenticazione degli utenti per il servizio Web quando l'applicazione viene distribuita con un server di report configurato per l'utilizzo di un'estensione di autenticazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="41a56-124">The following illustration depicts the method of authenticating users to the Web service when your application is deployed with a report server configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="41a56-125">![Flusso di autenticazione di sicurezza per Reporting Services](../../media/rosettasecurityextensionauthenticationflow.gif "Flusso di autenticazione di sicurezza per Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="41a56-125">![Reporting Services security authentication flow](../../media/rosettasecurityextensionauthenticationflow.gif "Reporting Services security authentication flow")</span></span>  
  
 <span data-ttu-id="41a56-126">Come illustrato nella figura 2, il processo di autenticazione è il seguente:</span><span class="sxs-lookup"><span data-stu-id="41a56-126">As shown in Figure 2, the authentication process is as follows:</span></span>  
  
1.  <span data-ttu-id="41a56-127">Un'applicazione client chiama il metodo <xref:ReportService2010.ReportingService2010.LogonUser%2A> del servizio Web per autenticare un utente.</span><span class="sxs-lookup"><span data-stu-id="41a56-127">A client application calls the Web service <xref:ReportService2010.ReportingService2010.LogonUser%2A> method to authenticate a user.</span></span>  
  
2.  <span data-ttu-id="41a56-128">Il servizio Web effettua una chiamata al <xref:ReportService2010.ReportingService2010.LogonUser%2A> metodo dell'estensione di sicurezza, in particolare, la classe che implementa **IAuthenticationExtension**.</span><span class="sxs-lookup"><span data-stu-id="41a56-128">The Web service makes a call to the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of your security extension, specifically, the class that implements **IAuthenticationExtension**.</span></span>  
  
3.  <span data-ttu-id="41a56-129">L'implementazione di <xref:ReportService2010.ReportingService2010.LogonUser%2A> convalida il nome utente e la password nell'archivio utente o nell'autorità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="41a56-129">Your implementation of <xref:ReportService2010.ReportingService2010.LogonUser%2A> validates the user name and password in the user store or security authority.</span></span>  
  
4.  <span data-ttu-id="41a56-130">Dopo la corretta esecuzione dell'autenticazione, il servizio Web crea un cookie e lo gestisce per la sessione.</span><span class="sxs-lookup"><span data-stu-id="41a56-130">Upon successful authentication, the Web service creates a cookie and manages it for the session.</span></span>  
  
5.  <span data-ttu-id="41a56-131">Il servizio Web restituisce il ticket di autenticazione all'applicazione chiamante nell'intestazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="41a56-131">The Web service returns the authentication ticket to the calling application on the HTTP header.</span></span>  
  
 <span data-ttu-id="41a56-132">Quando un utente viene correttamente autenticato dal servizio Web tramite l'estensione di sicurezza, viene generato un cookie utilizzato per le richieste successive.</span><span class="sxs-lookup"><span data-stu-id="41a56-132">When the Web service successfully authenticates a user through the security extension, it generates a cookie that is used for subsequent requests.</span></span> <span data-ttu-id="41a56-133">Il cookie non può essere reso persistente nell'autorità di sicurezza personalizzata perché il server di report non possiede l'autorità di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="41a56-133">The cookie may not persist within the custom security authority because the report server does not own the security authority.</span></span> <span data-ttu-id="41a56-134">Il cookie viene restituito dal metodo del servizio Web <xref:ReportService2010.ReportingService2010.LogonUser%2A> e viene utilizzato nelle successive chiamate al metodo del servizio Web e nell'accesso con URL.</span><span class="sxs-lookup"><span data-stu-id="41a56-134">The cookie is returned from the <xref:ReportService2010.ReportingService2010.LogonUser%2A> Web service method and is used in subsequent Web service method calls and in URL access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41a56-135">Per evitare di compromettere il cookie durante la trasmissione, i cookie di autenticazione restituiti da <xref:ReportService2010.ReportingService2010.LogonUser%2A> devono essere trasmessi in modo protetto utilizzando la crittografia SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="41a56-135">In order to avoid compromising the cookie during transmission, authentication cookies returned from <xref:ReportService2010.ReportingService2010.LogonUser%2A> should be transmitted securely using Secure Sockets Layer (SSL) encryption.</span></span>  
  
 <span data-ttu-id="41a56-136">Se si accede al server di report tramite accesso con URL quando un'estensione di sicurezza personalizzata è installata, Internet Information Services (IIS) e [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] gestiscono automaticamente la trasmissione del ticket di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="41a56-136">If you access the report server through URL access when a custom security extension is installed, Internet Information Services (IIS) and [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] automatically manage the transmission of the authentication ticket.</span></span> <span data-ttu-id="41a56-137">Se si accede al server di report tramite l'API SOAP, l'implementazione della classe proxy deve includere supporto aggiuntivo per la gestione del ticket di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="41a56-137">If you are accessing the report server through the SOAP API, your implementation of the proxy class must include additional support for managing the authentication ticket.</span></span> <span data-ttu-id="41a56-138">Per ulteriori informazioni sull'utilizzo dell'API SOAP e sulla gestione del ticket di autenticazione, vedere "Utilizzo del servizio Web con la sicurezza personalizzata".</span><span class="sxs-lookup"><span data-stu-id="41a56-138">For more information about using the SOAP API and managing the authentication ticket, see "Using the Web Service with Custom Security."</span></span>  
  
## <a name="forms-authentication"></a><span data-ttu-id="41a56-139">Autenticazione basata su form</span><span class="sxs-lookup"><span data-stu-id="41a56-139">Forms Authentication</span></span>  
 <span data-ttu-id="41a56-140">L'autenticazione basata su form è un tipo di autenticazione di [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] con la quale un utente non autenticato viene indirizzato a un form HTML.</span><span class="sxs-lookup"><span data-stu-id="41a56-140">Forms Authentication is a type of [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in which an unauthenticated user is directed to an HTML form.</span></span> <span data-ttu-id="41a56-141">Dopo che l'utente ha fornito le credenziali, il sistema produce un cookie contenente un ticket di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="41a56-141">Once the user provides credentials, the system issues a cookie containing an authentication ticket.</span></span> <span data-ttu-id="41a56-142">In occasione delle richieste successive, il sistema controlla innanzitutto il cookie per verificare se l'utente è già stato autenticato dal server di report.</span><span class="sxs-lookup"><span data-stu-id="41a56-142">On later requests, the system first checks the cookie to see if the user was already authenticated by the report server.</span></span>  
  
 <span data-ttu-id="41a56-143">È possibile estendere [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] per supportare l'autenticazione basata su form utilizzando le interfacce di estendibilità della sicurezza disponibili tramite l'API di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="41a56-143">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] can be extended to support Forms Authentication using the security extensibility interfaces available through the Reporting Services API.</span></span> <span data-ttu-id="41a56-144">Se si estende [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] per l'utilizzo dell'autenticazione basata su form, utilizzare SSL (Secure Sockets Layer) per tutte le comunicazioni con il server di report per impedire a utenti malintenzionati di accedere al cookie di un altro utente.</span><span class="sxs-lookup"><span data-stu-id="41a56-144">If you extend [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to use Forms Authentication, use Secure Sockets Layer (SSL) for all communications with the report server to prevent malicious users from gaining access to another user's cookie.</span></span> <span data-ttu-id="41a56-145">SSL consente ai client e a un server di report di autenticarsi a vicenda per garantire che il contenuto delle comunicazioni tra i due computer non possa essere letto da nessun altro computer.</span><span class="sxs-lookup"><span data-stu-id="41a56-145">SSL enables clients and a report server to authenticate each other and to ensure that no other computers can read the contents of communications between the two computers.</span></span> <span data-ttu-id="41a56-146">Tutti i dati inviati da un client tramite una connessione SSL vengono crittografati in modo che gli utenti malintenzionati non possano intercettare le password o i dati inviati a un server di report.</span><span class="sxs-lookup"><span data-stu-id="41a56-146">All data sent from a client through an SSL connection is encrypted so that malicious users cannot intercept passwords or data sent to a report server.</span></span>  
  
 <span data-ttu-id="41a56-147">L'autenticazione basata su form viene in genere implementata per supportare account e autenticazione per piattaforme diverse da Windows.</span><span class="sxs-lookup"><span data-stu-id="41a56-147">Forms Authentication is generally implemented to support accounts and authentication for platforms other than Windows.</span></span> <span data-ttu-id="41a56-148">Quando un utente richiede l'accesso a un server di report, viene visualizzata un'interfaccia grafica e le credenziali fornite vengono inviate a un'autorità di sicurezza per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="41a56-148">A graphical interface is presented to a user who requests access to a report server, and the supplied credentials are submitted to a security authority for authentication.</span></span>  
  
 <span data-ttu-id="41a56-149">L'autenticazione basata su form richiede la presenza di una persona per l'immissione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="41a56-149">Forms Authentication requires that a person is present to enter credentials.</span></span> <span data-ttu-id="41a56-150">Per le applicazioni automatiche che comunicano direttamente con il servizio Web Reporting Services, l'autenticazione basata su form deve essere utilizzata in combinazione con uno schema di autenticazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="41a56-150">For unattended applications that communicate directly with the Reporting Services Web service, Forms Authentication must be combined with a custom authentication scheme.</span></span>  
  
 <span data-ttu-id="41a56-151">L'autenticazione basata su form è adatta per [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a56-151">Forms Authentication is appropriate for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] when:</span></span>  
  
-   <span data-ttu-id="41a56-152">Quando è necessario archiviare e autenticare utenti che non dispongono di account di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="41a56-152">You need to store and authenticate users that do not have [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows accounts, and</span></span>  
  
-   <span data-ttu-id="41a56-153">Quando è necessario fornire un modulo di interfaccia utente personalizzato come pagina di accesso tra pagine diverse in un sito Web.</span><span class="sxs-lookup"><span data-stu-id="41a56-153">You need to provide your own user interface form as a logon page between different pages on a Web site.</span></span>  
  
 <span data-ttu-id="41a56-154">Quando si scrive un'estensione di sicurezza personalizzata che supporta l'autenticazione basata su form, prendere in considerazione gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="41a56-154">Consider the following when writing a custom security extension that supports Forms Authentication:</span></span>  
  
-   <span data-ttu-id="41a56-155">Se si utilizza l'autenticazione basata su form, l'accesso anonimo deve essere abilitato nella directory virtuale del server di report in Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="41a56-155">If you use Forms Authentication, anonymous access must be enabled on the report server virtual directory in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="41a56-156">L'autenticazione di [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] deve essere impostata su Forms.</span><span class="sxs-lookup"><span data-stu-id="41a56-156">[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication must be set to Forms.</span></span> <span data-ttu-id="41a56-157">È possibile configurare l'autenticazione di [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] nel file Web.config per il server di report.</span><span class="sxs-lookup"><span data-stu-id="41a56-157">You configure [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in the Web.config file for the report server.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="41a56-158">consente di autenticare e autorizzare gli utenti con l'autenticazione di Windows o con l'autenticazione personalizzata, ma non con entrambe.</span><span class="sxs-lookup"><span data-stu-id="41a56-158">can authenticate and authorize users with either Windows Authentication or custom authentication, but not both.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="41a56-159">non supporta l'utilizzo simultaneo di più estensioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="41a56-159">does not support simultaneous use of multiple security extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a56-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41a56-160">See Also</span></span>  
 [<span data-ttu-id="41a56-161">Implementazione di un'estensione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="41a56-161">Implementing a Security Extension</span></span>](../security-extension/implementing-a-security-extension.md)  
  
  
