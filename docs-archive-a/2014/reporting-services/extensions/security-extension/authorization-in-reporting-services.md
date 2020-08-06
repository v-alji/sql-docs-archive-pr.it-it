---
title: Autorizzazione in Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- authorization [Reporting Services]
ms.assetid: 15fc1c7b-560c-4737-b126-e0d428a1b530
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7420b45175ca0b0a5fc66da4a7939b07b79c75b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629222"
---
# <a name="authorization-in-reporting-services"></a><span data-ttu-id="58a92-102">Autorizzazione in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="58a92-102">Authorization in Reporting Services</span></span>
  <span data-ttu-id="58a92-103">L'autorizzazione è il processo tramite cui viene determinato se a un'identità deve essere concesso il tipo di accesso richiesto a una determinata risorsa nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="58a92-103">Authorization is the process of determining whether an identity should be granted the requested type of access to a given resource in the report server database.</span></span> <span data-ttu-id="58a92-104">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] viene utilizzata un'architettura di autorizzazione basata sui ruoli che consente di concedere a un utente l'accesso a una determinata risorsa in base all'assegnazione di ruolo dell'utente per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58a92-104">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a role-based authorization architecture that grants a user access to a given resource based on the user's role assignment for the application.</span></span> <span data-ttu-id="58a92-105">Le estensioni di sicurezza per [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] contengono un'implementazione di un componente di autorizzazione utilizzata per concedere l'accesso agli utenti dopo l'autenticazione nel server di report.</span><span class="sxs-lookup"><span data-stu-id="58a92-105">Security extensions for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] contain an implementation of an authorization component that is used to grant access to users once they are authenticated on the report server.</span></span> <span data-ttu-id="58a92-106">L'autorizzazione viene richiamata quando un utente tenta di eseguire un'operazione nel sistema o in un elemento del server di report tramite l'API SOAP e l'accesso con URL.</span><span class="sxs-lookup"><span data-stu-id="58a92-106">Authorization is invoked when a user attempts to perform an operation on the system or a report server item through the SOAP API and via URL access.</span></span> <span data-ttu-id="58a92-107">Questa operazione è possibile tramite l'interfaccia dell'estensione di sicurezza **IAuthorizationExtension**.</span><span class="sxs-lookup"><span data-stu-id="58a92-107">This is made possible through the security extension interface **IAuthorizationExtension**.</span></span> <span data-ttu-id="58a92-108">Come dichiarato in precedenza, tutte le estensioni ereditano da **IExtension** l'interfaccia di base per qualsiasi estensione distribuita.</span><span class="sxs-lookup"><span data-stu-id="58a92-108">As stated previously, all extensions inherit from **IExtension** the base interface for any extension that you deploy.</span></span> <span data-ttu-id="58a92-109">**IExtension** e **IAuthorizationExtension** sono membri dello spazio dei nomi **Microsoft. ReportingServices. Interfaces** .</span><span class="sxs-lookup"><span data-stu-id="58a92-109">**IExtension** and **IAuthorizationExtension** are members of the **Microsoft.ReportingServices.Interfaces** namespace.</span></span>

## <a name="checking-access"></a><span data-ttu-id="58a92-110">Controllo dell'accesso</span><span class="sxs-lookup"><span data-stu-id="58a92-110">Checking Access</span></span>
 <span data-ttu-id="58a92-111">Nell'ambito dell'autorizzazione, la chiave per qualsiasi implementazione della sicurezza personalizzata è il controllo dell'accesso, implementato nel metodo <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="58a92-111">In authorization, the key to any custom security implementation is the access check, which is implemented in the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span> <span data-ttu-id="58a92-112"><xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> viene chiamato ogni volta che un utente tenta un'operazione sul server di report.</span><span class="sxs-lookup"><span data-stu-id="58a92-112"><xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> is called each time a user attempts an operation on the report server.</span></span> <span data-ttu-id="58a92-113">Il metodo <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> è sottoposto a overload per ogni tipo di operazione.</span><span class="sxs-lookup"><span data-stu-id="58a92-113">The <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method is overloaded for each operation type.</span></span> <span data-ttu-id="58a92-114">Per le operazioni sulle cartelle, un esempio di controllo dell'accesso potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="58a92-114">For folder operations, an example of an access check might look like the following:</span></span>

```
// Overload for Folder operations
public bool CheckAccess(
   string userName, 
   IntPtr userToken, 
   byte[] secDesc, 
   FolderOperation requiredOperation)
{
   // If the user is the administrator, allow unrestricted access.
   if (userName == m_adminUserName) 
      return true;

   AceCollection acl = DeserializeAcl(secDesc);
   foreach(AceStruct ace in acl)
   {
         if (userName == ace.PrincipalName)
         {
            foreach(FolderOperation aclOperation in 
               ace.FolderOperations)
            {
               if (aclOperation == requiredOperation)
                     return true;
            }
         }
   }
   return false;
}
```

 <span data-ttu-id="58a92-115">Il server di report chiama il metodo <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> passando il nome dell'utente connesso, un token utente, il descrittore di sicurezza per l'elemento e l'operazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="58a92-115">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method by passing in the name of the logged-on user, a user token, the security descriptor for the item, and the requested operation.</span></span> <span data-ttu-id="58a92-116">A questo punto il descrittore di sicurezza viene controllato per verificare se il nome utente e l'autorizzazione sono appropriati per il completamento della richiesta, quindi viene restituito `true` per indicare che l'accesso è concesso o `false` per indicare che l'accesso è negato.</span><span class="sxs-lookup"><span data-stu-id="58a92-116">Here you would check the security descriptor for the user name and the appropriate permission to complete the request, then return `true` to signify that access is granted or `false` to signify access is denied.</span></span>

## <a name="security-descriptors"></a><span data-ttu-id="58a92-117">Descrittori di sicurezza</span><span class="sxs-lookup"><span data-stu-id="58a92-117">Security Descriptors</span></span>
 <span data-ttu-id="58a92-118">Quando si impostano i criteri di autorizzazione per gli elementi nel database del server di report, un'applicazione client (ad esempio Gestione report) invia le informazioni utente all'estensione di sicurezza insieme ai criteri di sicurezza per l'elemento.</span><span class="sxs-lookup"><span data-stu-id="58a92-118">When setting authorization policies on items in the report server database, a client application (such as Report Manager) submits the user information to the security extension along with a security policy for the item.</span></span> <span data-ttu-id="58a92-119">I criteri di sicurezza e le informazioni utente sono collettivamente denominati descrittore di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="58a92-119">This security policy and user information are known collectively as a security descriptor.</span></span> <span data-ttu-id="58a92-120">Un descrittore di sicurezza contiene le informazioni seguenti per un elemento nel database del server di report:</span><span class="sxs-lookup"><span data-stu-id="58a92-120">A security descriptor contains the following information for an item in the report server database:</span></span>

-   <span data-ttu-id="58a92-121">Gruppo o utente che dispone di un tipo di autorizzazione per l'esecuzione di operazioni sull'elemento.</span><span class="sxs-lookup"><span data-stu-id="58a92-121">The group or user that has some type of permission to perform operations on the item.</span></span>

-   <span data-ttu-id="58a92-122">Tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="58a92-122">The item's type.</span></span>

-   <span data-ttu-id="58a92-123">Elenco di controllo di accesso discrezionale che controlla l'accesso all'elemento.</span><span class="sxs-lookup"><span data-stu-id="58a92-123">A discretionary access control list controlling access to the item.</span></span>

 <span data-ttu-id="58a92-124">I descrittori di sicurezza vengono creati utilizzando i metodi <xref:ReportService2010.ReportingService2010.SetPolicies%2A> e <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A> del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="58a92-124">Security descriptors are created using the Web service <xref:ReportService2010.ReportingService2010.SetPolicies%2A> and <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A> methods.</span></span>

### <a name="authorization-flow"></a><span data-ttu-id="58a92-125">Flusso di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="58a92-125">Authorization Flow</span></span>
 <span data-ttu-id="58a92-126">L'autorizzazione in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] viene controllata dall'estensione di sicurezza attualmente configurata per l'esecuzione nel server.</span><span class="sxs-lookup"><span data-stu-id="58a92-126">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] authorization is controlled by the security extension currently configured to run on the server.</span></span> <span data-ttu-id="58a92-127">L'autorizzazione è basata sul ruolo ed è limitata alle autorizzazioni e alle operazioni fornite dall'architettura di sicurezza di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58a92-127">Authorization is role-based and limited to the permissions and operations supplied by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security architecture.</span></span> <span data-ttu-id="58a92-128">Nel diagramma seguente è illustrato il processo di autorizzazione degli utenti per l'utilizzo degli elementi nel database del server di report:</span><span class="sxs-lookup"><span data-stu-id="58a92-128">The following diagram depicts the process of authorizing users to operate on items in the report server database:</span></span>

 <span data-ttu-id="58a92-129">![Flusso delle autorizzazioni di sicurezza per Reporting Services](../../media/rosettasecurityextensionauthorizationflow.gif "Flusso delle autorizzazioni di sicurezza per Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="58a92-129">![Reporting Services security authorization flow](../../media/rosettasecurityextensionauthorizationflow.gif "Reporting Services security authorization flow")</span></span>

 <span data-ttu-id="58a92-130">Come illustrato in questo diagramma, per l'autorizzazione viene applicata la sequenza seguente:</span><span class="sxs-lookup"><span data-stu-id="58a92-130">As shown in this diagram, authorization follows this sequence:</span></span>

1.  <span data-ttu-id="58a92-131">Dopo l'autenticazione, le applicazioni client inviano le richieste al server di report tramite i metodi del servizio Web Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="58a92-131">Once authenticated, client applications make requests to the report server through the Reporting Services Web service methods.</span></span> <span data-ttu-id="58a92-132">Un ticket di autenticazione viene passato al server di report sotto forma di cookie nell'intestazione HTTP di ogni richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="58a92-132">An authentication ticket is passed to the report server in the form of a cookie in the HTTP header of each Web request.</span></span>

2.  <span data-ttu-id="58a92-133">Il cookie viene convalidato prima di qualsiasi controllo dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="58a92-133">The cookie is validated prior to any access check.</span></span>

3.  <span data-ttu-id="58a92-134">Dopo la convalida del cookie, il server di report chiama <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> e all'utente viene fornita un'identità.</span><span class="sxs-lookup"><span data-stu-id="58a92-134">Once the cookie is validated, the report server calls <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> and the user is given an identity.</span></span>

4.  <span data-ttu-id="58a92-135">L'utente tenta di eseguire un'operazione tramite il servizio Web Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="58a92-135">The user attempts an operation through the Reporting Services Web service.</span></span>

5.  <span data-ttu-id="58a92-136">Il server di report chiama il metodo <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="58a92-136">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span>

6.  <span data-ttu-id="58a92-137">Il descrittore di sicurezza viene recuperato e passato a un'implementazione dell'estensione di sicurezza personalizzata di <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="58a92-137">The security descriptor is retrieved and passed to a custom security extension implementation of <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span></span> <span data-ttu-id="58a92-138">A questo punto, l'utente, il gruppo o il computer viene confrontato con il descrittore di sicurezza dell'elemento a cui viene eseguito l'accesso e viene autorizzato a eseguire l'operazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="58a92-138">At this point, the user, group, or computer is compared to the security descriptor of the item being accessed and is authorized to perform the requested operation.</span></span>

7.  <span data-ttu-id="58a92-139">Se l'utente è autorizzato, il servizio Web esegue l'operazione e restituisce una risposta all'applicazione chiamante.</span><span class="sxs-lookup"><span data-stu-id="58a92-139">If the user is authorized, the Web service performs the operation and returns a response to the calling application.</span></span>


