---
title: Configurare Reporting Services per l'uso di un nome alternativo del soggetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ce458f9f-4b4f-4a58-aa75-9a90dda1e622
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0312d2d1fff8f854eb2ffb8d0dad2563212ee23b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723588"
---
# <a name="configure-reporting-services-to-use-a-subject-alternative-name"></a><span data-ttu-id="dd15f-102">Configurare Reporting Services per usare un nome alternativo del soggetto</span><span class="sxs-lookup"><span data-stu-id="dd15f-102">Configure Reporting Services to Use a Subject Alternative Name</span></span>
  <span data-ttu-id="dd15f-103">Questo argomento descrive come configurare [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS) in modo da usare un nome alternativo del soggetto (SAN) modificando il file rsreportserver.config e usando lo strumento Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="dd15f-103">This topic explains how to configure [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS) to use a subject alternative name (SAN) by modifying the rsreportserver.config file and using the Netsh.exe tool.</span></span>

||
|-|
|<span data-ttu-id="dd15f-104">**[!INCLUDE[applies](../includes/applies-md.md)]**  Modalità nativa di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd15f-104">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Native mode</span></span>|

 <span data-ttu-id="dd15f-105">Le istruzioni si applicano all'URL Reporting Service nonché all'URL servizio Web.</span><span class="sxs-lookup"><span data-stu-id="dd15f-105">The instructions apply to the Reporting Service URL as well as a Web Service URL.</span></span>

 <span data-ttu-id="dd15f-106">Per usare un nome alternativo del soggetto, è necessario che il certificato SSL sia registrato nel server, firmato e che contenga la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="dd15f-106">To use a SAN, the SSL certificate must be registered on the server, signed, and have the private key.</span></span> <span data-ttu-id="dd15f-107">Non è possibile usare un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="dd15f-107">You cannot use a self-signed certificate</span></span>

 <span data-ttu-id="dd15f-108">Gli URL in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] possono essere configurati per l'uso di un certificato SSL.</span><span class="sxs-lookup"><span data-stu-id="dd15f-108">URLs in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] can be configured to use an SSL certificate.</span></span> <span data-ttu-id="dd15f-109">In genere, un certificato contiene solo un nome del soggetto che consente un solo URL per una sessione SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="dd15f-109">A certificate normally has just a subject name, which allows only one URL for an SSL (Secure Sockets Layer) session.</span></span> <span data-ttu-id="dd15f-110">Il nome alternativo del soggetto è un campo aggiuntivo nel certificato che consente a un servizio SSL di essere in ascolto e valido per molti URL nonché di condividere la porta SSL con altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="dd15f-110">The SAN is an additional field in the certificate that allows an SSL service to listen and be valid for many URLs, and to share the SSL port with other applications.</span></span> <span data-ttu-id="dd15f-111">Il nome alternativo del soggetto è simile al seguente: www.s2.com.</span><span class="sxs-lookup"><span data-stu-id="dd15f-111">The SAN looks something like the following: www.s2.com.</span></span>

 <span data-ttu-id="dd15f-112">Per altre informazioni sulle impostazioni di SSL per [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], vedere [Configurare connessioni SSL in un server di report in modalità nativa](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="dd15f-112">For more information about SSL settings for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Configure SSL Connections on a Native Mode Report Server](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span></span>

### <a name="configure-ssrs-to-use-a-subject-alternative-name-for-web-service-url"></a><span data-ttu-id="dd15f-113">Configurare SSRS per usare un nome alternativo del soggetto per l'URL servizio Web</span><span class="sxs-lookup"><span data-stu-id="dd15f-113">Configure SSRS to use a subject alternative name for Web Service URL</span></span>

1.  <span data-ttu-id="dd15f-114">Avviare Gestione configurazione Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="dd15f-114">Start Reporting Services Configuration Manager.</span></span>

     <span data-ttu-id="dd15f-115">Per altre informazioni, vedere [Gestione configurazione Reporting Services &#40;modalità nativa&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="dd15f-115">For more information, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>

2.  <span data-ttu-id="dd15f-116">Nella pagina **URL servizio Web** selezionare una porta SSL e un certificato SSL.</span><span class="sxs-lookup"><span data-stu-id="dd15f-116">On the **Web Service URL** page, select an SSL port and SSL Certificate.</span></span>

     <span data-ttu-id="dd15f-117">![Gestione configurazione Reporting Services](media/reportingservices-configurationmanager.png "Gestione configurazione Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="dd15f-117">![Reporting Services Configuration Manager](media/reportingservices-configurationmanager.png "Reporting Services Configuration Manager")</span></span>

     <span data-ttu-id="dd15f-118">Gestione configurazione registra il certificato SSL per la porta.</span><span class="sxs-lookup"><span data-stu-id="dd15f-118">The configuration manager registers the SSL certificate for the port.</span></span>

3.  <span data-ttu-id="dd15f-119">Aprire il file rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="dd15f-119">Open the rsreportserver.config file.</span></span>

     <span data-ttu-id="dd15f-120">Per impostazione predefinita, nella modalità nativa di SSRS il file si trova nella cartella seguente.</span><span class="sxs-lookup"><span data-stu-id="dd15f-120">For SSRS Native mode, the file is located by default in the following folder.</span></span>

    ```
    \Program Files\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer
    ```

4.  <span data-ttu-id="dd15f-121">Copiare la sezione URL del servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="dd15f-121">Copy the URL section for the Report Server Web Service application.</span></span>

     <span data-ttu-id="dd15f-122">Di seguito, ad esempio, è riportata la sezione URL originale.</span><span class="sxs-lookup"><span data-stu-id="dd15f-122">For example, the following is the original URL section.</span></span>

    ```
        <URL>
         <UrlString>https://localhost:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

     <span data-ttu-id="dd15f-123">Di seguito è riportata la sezione URL modificata.</span><span class="sxs-lookup"><span data-stu-id="dd15f-123">The following is the modified URL section.</span></span>

    ```
    <URL>
         <UrlString>https://www.s1.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>
        <URL>
         <UrlString>https://www.s2.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

5.  <span data-ttu-id="dd15f-124">Salvare il file rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="dd15f-124">Save the rsreportserver.config file.</span></span>

6.  <span data-ttu-id="dd15f-125">Avviare un prompt dei comandi come amministratore ed eseguire lo strumento Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="dd15f-125">Start a command prompt as an administrator, and run the Netsh.exe tool.</span></span>

    ```
    C:\windows\system32\netsh
    ```

7.  <span data-ttu-id="dd15f-126">Passare al contesto http digitando il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="dd15f-126">Switch to the http context by typing the following.</span></span>

    ```
    Netsh>http
    ```

8.  <span data-ttu-id="dd15f-127">Mostrare gli urlacl esistenti digitando il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="dd15f-127">Show the existing urlacls by typing the following.</span></span>

    ```
    Netsh http>show urlacl
    ```

     <span data-ttu-id="dd15f-128">Verrà visualizzata una voce simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="dd15f-128">An entry such as the following appears.</span></span>

    ```
    Reserved URL            : https:// www.s1.com:443/ReportServer/
        User: NT SERVICE\ReportServer
            Listen: Yes
            Delegate: No
            SDDL: D:(A;;GX;;;S-1-5-80-1234567890-123456789-123456789-123456789-1234567890)
    ```

     <span data-ttu-id="dd15f-129">Un urlacl è un elenco di controllo di accesso discrezionale (DACL, Discretionary Access Control List) per un URL riservato.</span><span class="sxs-lookup"><span data-stu-id="dd15f-129">An urlacl is a DACL (Discretionary Access Control List) for a reserved URL.</span></span>

9. <span data-ttu-id="dd15f-130">Creare una nuova voce per il nome alternativo del soggetto con lo stesso utente e SDDL della voce esistente digitando il testo seguente.</span><span class="sxs-lookup"><span data-stu-id="dd15f-130">Create a new entry for the subject alternative name, with the same user and SDDL as the existing entry, by typing the following.</span></span>

    ```
    netsh http>add urlacl  url=https://www.s2.com:443/ReportServer  
    user="NT Service\ReportServer" sddl=D:(A;;GX;;;S-1-5-80-1234567980-12346579-123456789-123456789-1234567890)

    ```

10. <span data-ttu-id="dd15f-131">Nella pagina **Stato server di report** di Gestione configurazione Reporting Services fare clic su **Arresta** e quindi su **Avvia** per riavviare il server di report.</span><span class="sxs-lookup"><span data-stu-id="dd15f-131">On the **Report Server Status** page of the Reporting Services Configuration Manager, Click **Stop** and then click **Start** to restart the report server.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd15f-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd15f-132">See Also</span></span>
 <span data-ttu-id="dd15f-133">[File di configurazione RSReportServer](report-server/rsreportserver-config-configuration-file.md) [Reporting Services Configuration Manager &#40;modalità nativa&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [modificare un file di configurazione](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) Reporting Services &#40;RSreportserver.config&#41;[configurare gli URL del server di report &#40;SSRS](install-windows/configure-report-server-urls-ssrs-configuration-manager.md) Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dd15f-133">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)</span></span>


