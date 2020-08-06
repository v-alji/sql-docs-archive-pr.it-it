---
title: Registrare un nome dell'entità servizio (SPN) per un server di report | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dda91d4f-77cc-4898-ad03-810ece5f8e74
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 502170f16aad66757e8f44419ccbac3017072449
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637642"
---
# <a name="register-a-service-principal-name-spn-for-a-report-server"></a><span data-ttu-id="3fd28-102">Registrare un nome dell'entità servizio (SPN) per un server di report</span><span class="sxs-lookup"><span data-stu-id="3fd28-102">Register a Service Principal Name (SPN) for a Report Server</span></span>
  <span data-ttu-id="3fd28-103">Se si distribuisce [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in una rete che utilizza il protocollo Kerberos per l'autenticazione reciproca, è necessario creare un nome dell'entità servizio (SPN) per il server di report se questo è configurato per l'esecuzione come account utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="3fd28-103">If you are deploying [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in a network that uses the Kerberos protocol for mutual authentication, you must create a Service Principal Name (SPN) for the Report Server service if you configure it to run as a domain user account.</span></span>  
  
## <a name="about-spns"></a><span data-ttu-id="3fd28-104">Informazioni sugli SPN</span><span class="sxs-lookup"><span data-stu-id="3fd28-104">About SPNs</span></span>  
 <span data-ttu-id="3fd28-105">Un SPN è un identificatore univoco per un servizio in una rete che utilizza l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="3fd28-105">An SPN is a unique identifier for a service on a network that uses Kerberos authentication.</span></span> <span data-ttu-id="3fd28-106">Un SPN è costituito da una classe del servizio, un nome host e una porta.</span><span class="sxs-lookup"><span data-stu-id="3fd28-106">It consists of a service class, a host name, and a port.</span></span> <span data-ttu-id="3fd28-107">In una rete che utilizza l'autenticazione Kerberos un SPN per il server deve essere registrato con un account computer predefinito, ad esempio NetworkService o LocalSystem, o un account utente.</span><span class="sxs-lookup"><span data-stu-id="3fd28-107">On a network that uses Kerberos authentication, an SPN for the server must be registered under either a built-in computer account (such as NetworkService or LocalSystem) or user account.</span></span> <span data-ttu-id="3fd28-108">Gli SPN vengono registrati automaticamente per gli account predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3fd28-108">SPNs are registered for built-in accounts automatically.</span></span> <span data-ttu-id="3fd28-109">Quando, tuttavia, si esegue un servizio utilizzando un account utente di dominio, è necessario registrare manualmente l'SPN per l'account che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="3fd28-109">However, when you run a service under a domain user account, you must manually register the SPN for the account you want to use.</span></span>  
  
 <span data-ttu-id="3fd28-110">Per creare un SPN, è possibile usare l'utilità della riga di comando **SetSPN** .</span><span class="sxs-lookup"><span data-stu-id="3fd28-110">To create an SPN, you can use the **SetSPN** command line utility.</span></span> <span data-ttu-id="3fd28-111">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3fd28-111">For more information, see the following:</span></span>  
  
-   <span data-ttu-id="3fd28-112">[SetSPN](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) ( https://technet.microsoft.com/library/cc731241(WS.10).aspx) .</span><span class="sxs-lookup"><span data-stu-id="3fd28-112">[Setspn](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) (https://technet.microsoft.com/library/cc731241(WS.10).aspx).</span></span>  
  
-   <span data-ttu-id="3fd28-113">[Sintassi SetSPN dei nomi dell'entità servizio (SPN) (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) ( https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3fd28-113">[Service Principal Names (SPNs) SetSPN Syntax (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) (https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx).</span></span>  
  
 <span data-ttu-id="3fd28-114">Per eseguire l'utilità nel controller di dominio, è necessario essere un amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="3fd28-114">You must be a domain administrator to run the utility on the domain controller.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fd28-115">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fd28-115">Syntax</span></span>  
 <span data-ttu-id="3fd28-116">La sintassi del comando per l'utilizzo dell'utilità SetSPN per la creazione di un SPN per il server di report è analoga alla seguente:</span><span class="sxs-lookup"><span data-stu-id="3fd28-116">The command syntax for using SetSPN utility to create an SPN for the report server resembles the following:</span></span>  
  
```  
Setspn -s http/<computername>.<domainname>:<port> <domain-user-account>  
```  
  
 <span data-ttu-id="3fd28-117">**SetSPN** è disponibile in Windows Server.</span><span class="sxs-lookup"><span data-stu-id="3fd28-117">**SetSPN** is available with Windows Server.</span></span> <span data-ttu-id="3fd28-118">L'argomento `-s` aggiunge un nome SPN dopo avere verificato che non sono presenti duplicati.</span><span class="sxs-lookup"><span data-stu-id="3fd28-118">The `-s` argument adds a SPN after validating no duplicate exists.</span></span> <span data-ttu-id="3fd28-119">**NOTA:** -s è disponibile in Windows Server a partire da Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="3fd28-119">**NOTE:-s** is available in Windows Server starting with Windows Server 2008.</span></span>  
  
 <span data-ttu-id="3fd28-120">`HTTP` è la classe del servizio.</span><span class="sxs-lookup"><span data-stu-id="3fd28-120">`HTTP` is the service class.</span></span> <span data-ttu-id="3fd28-121">Il servizio Web ReportServer viene eseguito in HTTP.SYS.</span><span class="sxs-lookup"><span data-stu-id="3fd28-121">The Report Server Web service runs in HTTP.SYS.</span></span> <span data-ttu-id="3fd28-122">Una conseguenza della creazione di un SPN per HTTP è che a tutte le applicazioni Web presenti nello stesso computer ed eseguite in HTTP.SYS, incluse le applicazioni ospitate in IIS, verranno concessi ticket basati sull'account utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="3fd28-122">A by-product of creating an SPN for HTTP is that all Web applications on the same computer that run in HTTP.SYS (including applications hosted in IIS) will be granted tickets based on the domain user account.</span></span> <span data-ttu-id="3fd28-123">Se tali servizi vengono eseguiti con un account diverso, le richieste di autenticazione avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3fd28-123">If those services run under a different account, the authentication requests will fail.</span></span> <span data-ttu-id="3fd28-124">Per evitare questo problema, assicurarsi di configurare tutte le applicazioni HTTP per l'esecuzione con lo stesso account oppure creare intestazioni host per ogni applicazione e quindi SPN distinti per ciascuna intestazione host.</span><span class="sxs-lookup"><span data-stu-id="3fd28-124">To avoid this problem, be sure to configure all HTTP applications to run under the same account, or consider creating host headers for each application and then creating separate SPNs for each host header.</span></span> <span data-ttu-id="3fd28-125">Quando si configurano le intestazioni host, è necessario apportare le modifiche DNS indipendentemente dalla configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3fd28-125">When you configure host headers, DNS changes are required regardless of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration.</span></span>  
  
 <span data-ttu-id="3fd28-126">I valori specificati per \<*computername*> , \<*domainname*> e \<*port*> identificano l'indirizzo di rete univoco del computer che ospita il server di report.</span><span class="sxs-lookup"><span data-stu-id="3fd28-126">The values that you specify for \<*computername*>, \<*domainname*>, and \<*port*> identify the unique network address of the computer that hosts the report server.</span></span> <span data-ttu-id="3fd28-127">Può trattarsi di un nome host locale o di un nome di dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="3fd28-127">This can be a local host name or a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="3fd28-128">Se è presente un solo dominio e si usa la porta 80, è possibile omettere \<*domainname*> e \<*port*> dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3fd28-128">If you only have one domain and are using port 80, you can omit \<*domainname*> and \<*port*> from your command line.</span></span> <span data-ttu-id="3fd28-129">\<*domain-user-account*>account utente con cui viene eseguito il servizio del server di report e per il quale è necessario registrare il nome SPN.</span><span class="sxs-lookup"><span data-stu-id="3fd28-129">\<*domain-user-account*> is the user account under which the Report Server service runs and for which the SPN must be registered.</span></span>  
  
## <a name="register-an-spn-for-domain-user-account"></a><span data-ttu-id="3fd28-130">Registrare un SPN per l'account utente di dominio</span><span class="sxs-lookup"><span data-stu-id="3fd28-130">Register an SPN for Domain User Account</span></span>  
  
#### <a name="to-register-an-spn-for-a-report-server-service-running-as-a-domain-user"></a><span data-ttu-id="3fd28-131">Per registrare un SPN per un servizio del server di report eseguito come utente di dominio</span><span class="sxs-lookup"><span data-stu-id="3fd28-131">To register an SPN for a Report Server service running as a domain user</span></span>  
  
1.  <span data-ttu-id="3fd28-132">Installare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e configurare il servizio del server di report per l'esecuzione come account utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="3fd28-132">Install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and configure the Report Server service to run as a domain user account.</span></span> <span data-ttu-id="3fd28-133">Si noti che gli utenti non saranno in grado di connettersi al server di report fino a quando non vengono completati i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="3fd28-133">Note that users will not be able to connect to the report server until you complete the following steps.</span></span>  
  
2.  <span data-ttu-id="3fd28-134">Accedere al controller di dominio come amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="3fd28-134">Log on to the domain controller as domain administrator.</span></span>  
  
3.  <span data-ttu-id="3fd28-135">Aprire una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="3fd28-135">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="3fd28-136">Copiare il comando seguente, sostituendo i valori segnaposto con quelli effettivi, validi per la rete in uso:</span><span class="sxs-lookup"><span data-stu-id="3fd28-136">Copy the following command, replacing placeholder values with actual values that are valid for your network:</span></span>  
  
    ```  
    Setspn -s http/<computer-name>.<domain-name>:<port> <domain-user-account>  
    ```  
  
     <span data-ttu-id="3fd28-137">Ad esempio: `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span><span class="sxs-lookup"><span data-stu-id="3fd28-137">For example: `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span></span>  
  
5.  <span data-ttu-id="3fd28-138">Eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="3fd28-138">Run the command.</span></span>  
  
6.  <span data-ttu-id="3fd28-139">Aprire il file **RsReportServer.config** e individuare la sezione `<AuthenticationTypes>`.</span><span class="sxs-lookup"><span data-stu-id="3fd28-139">Open the **RsReportServer.config** file and locate the `<AuthenticationTypes>` section.</span></span>  
  
7.  <span data-ttu-id="3fd28-140">Aggiungere `<RSWindowsNegotiate/>` come prima voce in questa sezione per abilitare NTLM.</span><span class="sxs-lookup"><span data-stu-id="3fd28-140">Add `<RSWindowsNegotiate/>` as the first entry in this section to enable NTLM.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd28-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fd28-141">See Also</span></span>  
 <span data-ttu-id="3fd28-142">[Configurare un account di servizio &#40;Configuration Manager SSRS&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="3fd28-142">[Configure a Service Account &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="3fd28-143">[Configurare l'account del servizio del server di report &#40;Gestione configurazione SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="3fd28-143">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="3fd28-144">Gestire un server di report in modalità nativa di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="3fd28-144">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
