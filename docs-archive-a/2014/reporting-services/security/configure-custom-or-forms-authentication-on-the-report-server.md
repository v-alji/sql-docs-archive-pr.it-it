---
title: Configurare l'autenticazione personalizzata o basata su form nel server di report | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Forms authentication, configuring
- custom authentication [Reporting Services]
ms.assetid: e8601a8f-e66d-4649-8e4d-a46ca20ec7d0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1447e1e695f0e59dbc07b7e19f4df335a1220a97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625971"
---
# <a name="configure-custom-or-forms-authentication-on-the-report-server"></a><span data-ttu-id="899f7-102">Configurare l'autenticazione personalizzata o basata su form nel server di report</span><span class="sxs-lookup"><span data-stu-id="899f7-102">Configure Custom or Forms Authentication on the Report Server</span></span>
  <span data-ttu-id="899f7-103">Reporting Services offre un'architettura estensibile che consente di inserire moduli di autenticazione basata su form o personalizzata.</span><span class="sxs-lookup"><span data-stu-id="899f7-103">Reporting Services provides an extensible architecture that allows you to plug in custom or forms-based authentication modules.</span></span> <span data-ttu-id="899f7-104">È possibile implementare un'estensione di autenticazione personalizzata, se i requisiti di distribuzione non includono la sicurezza integrata di Windows o l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="899f7-104">You might consider implementing a custom authentication extension if deployment requirements do not include Windows integrated security or Basic authentication.</span></span> <span data-ttu-id="899f7-105">Lo scenario più comune per l'utilizzo dell'autenticazione personalizzata consiste nel supporto dell'accesso Internet o extranet a un'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="899f7-105">The most common scenario for using custom authentication is to support Internet or extranet access to a Web application.</span></span> <span data-ttu-id="899f7-106">La sostituzione dell'estensione di autenticazione di Windows predefinita con un'estensione di autenticazione personalizzata consente un maggiore controllo sulle modalità di concessione dell'accesso al server di report agli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="899f7-106">Replacing the default Windows Authentication extension with a custom authentication extension gives you more control over how external users are granted access to the report server.</span></span>  
  
 <span data-ttu-id="899f7-107">La distribuzione di un'estensione di autenticazione personalizzata richiede sostanzialmente più passaggi, che includono la copia di un assembly e dei file dell'applicazione, la modifica dei file di configurazione e il test.</span><span class="sxs-lookup"><span data-stu-id="899f7-107">In practice, deploying a custom authentication extension requires multiple steps that include copying assemblies and application files, modifying configuration files, and testing.</span></span> <span data-ttu-id="899f7-108">In questo argomento vengono illustrate solo le impostazioni di autenticazione che l'utente specifica nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="899f7-108">This topic focuses on just the authentication settings that you specify in the configuration files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="899f7-109">La creazione di un'estensione di autenticazione personalizzata richiede codice personalizzato ed esperienza in materia di sicurezza di [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="899f7-109">Creating a custom authentication extension requires custom code and expertise in [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] security.</span></span> <span data-ttu-id="899f7-110">Se non si desidera creare un'estensione di autenticazione personalizzata, è possibile utilizzare gruppi e account di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory, ma è necessario ridurre notevolmente l'ambito di distribuzione del server di report.</span><span class="sxs-lookup"><span data-stu-id="899f7-110">If you do not want to create a custom authentication extension, you can use [!INCLUDE[msCoName](../../includes/msconame-md.md)] Active Directory groups and accounts, but you should greatly reduce the scope of a report server deployment.</span></span> <span data-ttu-id="899f7-111">Per altre informazioni sull'autenticazione personalizzata, vedere [Implementazione di un'estensione di sicurezza](../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="899f7-111">For more information about custom authentication, see [Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
 <span data-ttu-id="899f7-112">Se inoltre si desidera utilizzare l'autenticazione basata su form o un'estensione di autenticazione personalizzata in un ambiente [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] integrato con un prodotto SharePoint, è necessario configurare il sito di SharePoint per l'utilizzo del metodo di autenticazione scelto.</span><span class="sxs-lookup"><span data-stu-id="899f7-112">Additionally, if you want to use Forms authentication or a custom authentication extension in a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] environment that is integrated with a SharePoint product, you must configure the SharePoint site to use the authentication method that you choose.</span></span> <span data-ttu-id="899f7-113">Per altre informazioni sulla configurazione dell'autenticazione in SharePoint, vedere [Esempi di autenticazione](https://go.microsoft.com/fwlink/?LinkId=115575) in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Developer Network (MSDN).</span><span class="sxs-lookup"><span data-stu-id="899f7-113">For more information about configuring authentication in SharePoint, see [Authentication Samples](https://go.microsoft.com/fwlink/?LinkId=115575) on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Developer Network (MSDN).</span></span>  
  
### <a name="to-configure-a-report-server-to-use-custom-authentication"></a><span data-ttu-id="899f7-114">Per configurare un server di report per l'utilizzo dell'autenticazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="899f7-114">To configure a report server to use Custom authentication</span></span>  
  
1.  <span data-ttu-id="899f7-115">Aprire RSReportServer.config in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="899f7-115">Open RSReportServer.config in a text editor.</span></span>  
  
2.  <span data-ttu-id="899f7-116">Trovare <`Authentication`>.</span><span class="sxs-lookup"><span data-stu-id="899f7-116">Find <`Authentication`>.</span></span>  
  
3.  <span data-ttu-id="899f7-117">Copiare la struttura XML seguente:</span><span class="sxs-lookup"><span data-stu-id="899f7-117">Copy the following XML structure:</span></span>  
  
    ```  
    <Authentication>  
          <AuthenticationTypes>  
                 <Custom />  
          </AuthenticationTypes>  
          <EnableAuthPersistence>true</EnableAuthPersistence>  
    </Authentication>  
    ```  
  
4.  <span data-ttu-id="899f7-118">Incollarlo sulle voci esistenti per <`Authentication`>.</span><span class="sxs-lookup"><span data-stu-id="899f7-118">Paste it over the existing entries for <`Authentication`>.</span></span>  
  
     <span data-ttu-id="899f7-119">Si noti che non è possibile utilizzare `Custom` con altri tipi di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="899f7-119">Note that you cannot use `Custom` with other authentication types.</span></span>  
  
5.  <span data-ttu-id="899f7-120">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="899f7-120">Save the file.</span></span>  
  
6.  <span data-ttu-id="899f7-121">Aprire il file Web.config per il server di report.</span><span class="sxs-lookup"><span data-stu-id="899f7-121">Open the Web.config file for the report server.</span></span> <span data-ttu-id="899f7-122">Per impostazione predefinita, il percorso di questo file è \Programmi\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="899f7-122">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportServer.</span></span>  
  
7.  <span data-ttu-id="899f7-123">Trovare `authentication mode` e impostarlo su `Forms`.</span><span class="sxs-lookup"><span data-stu-id="899f7-123">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
8.  <span data-ttu-id="899f7-124">Trovare `identity impersonate` e impostarlo su `False`.</span><span class="sxs-lookup"><span data-stu-id="899f7-124">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
9. <span data-ttu-id="899f7-125">Aprire il file Web.config per Gestione report.</span><span class="sxs-lookup"><span data-stu-id="899f7-125">Open the Web.config file for Report Manager.</span></span> <span data-ttu-id="899f7-126">Per impostazione predefinita, il percorso di questo file è \Programmi\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager.</span><span class="sxs-lookup"><span data-stu-id="899f7-126">By default, it is located at \Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\ReportManager.</span></span>  
  
10. <span data-ttu-id="899f7-127">Trovare `authentication mode` e impostarlo su `Forms`.</span><span class="sxs-lookup"><span data-stu-id="899f7-127">Find `authentication mode` and set it `Forms`.</span></span>  
  
    ```  
    <authentication mode = "Forms" />  
    ```  
  
11. <span data-ttu-id="899f7-128">Trovare `identity impersonate` e impostarlo su `False`.</span><span class="sxs-lookup"><span data-stu-id="899f7-128">Find `identity impersonate` and set it to `False`.</span></span>  
  
    ```  
    <identity impersonate = "false" />  
    ```  
  
12. <span data-ttu-id="899f7-129">Aggiungere la struttura dell'elemento `PassThroughCookies` al file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="899f7-129">Add the `PassThroughCookies` element structure to the configuration file.</span></span> <span data-ttu-id="899f7-130">Per altre informazioni, vedere [Configurare Gestione report per il passaggio di cookie di autenticazione personalizzati](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span><span class="sxs-lookup"><span data-stu-id="899f7-130">For more information, see [Configure Report Manager to Pass Custom Authentication Cookies](configure-the-web-portal-to-pass-custom-authentication-cookies.md).</span></span>  
  
13. <span data-ttu-id="899f7-131">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="899f7-131">Save the file.</span></span>  
  
14. <span data-ttu-id="899f7-132">Se è stata configurata una distribuzione con scalabilità orizzontale, ripetere tutti i passaggi precedenti per gli altri server di report presenti nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="899f7-132">If you configured a scale-out deployment, repeat all of the previous steps for other report servers in the deployment.</span></span>  
  
15. <span data-ttu-id="899f7-133">Riavviare il server di report per cancellare qualsiasi sessione attualmente aperta.</span><span class="sxs-lookup"><span data-stu-id="899f7-133">Restart the report server to clear any sessions that are currently open.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="899f7-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="899f7-134">See Also</span></span>  
 <span data-ttu-id="899f7-135">[Implementazione di un'estensione di sicurezza](../extensions/security-extension/implementing-a-security-extension.md) </span><span class="sxs-lookup"><span data-stu-id="899f7-135">[Implementing a Security Extension](../extensions/security-extension/implementing-a-security-extension.md) </span></span>  
 <span data-ttu-id="899f7-136">[Autenticazione con il server di report](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="899f7-136">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="899f7-137">[File di configurazione RSReportServer](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="899f7-137">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="899f7-138">[Configurare l'autenticazione di base nel server di report](configure-basic-authentication-on-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="899f7-138">[Configure Basic Authentication on the Report Server](configure-basic-authentication-on-the-report-server.md) </span></span>  
 [<span data-ttu-id="899f7-139">Configurare l'autenticazione di Windows nel server di report</span><span class="sxs-lookup"><span data-stu-id="899f7-139">Configure Windows Authentication on the Report Server</span></span>](configure-windows-authentication-on-the-report-server.md)  
  
  
