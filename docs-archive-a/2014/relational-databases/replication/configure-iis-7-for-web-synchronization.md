---
title: Configurare IIS 7 per la sincronizzazione Web | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- IIS 7 server configuration [SQL Server replication]
- Web synchronization, IIS 7 servers
ms.assetid: c201fe2c-0a76-44e5-a233-05e14cd224a6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65b5aa1ea0d314a9675b1c1b90b688d2990e6d24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638385"
---
# <a name="configure-iis-7-for-web-synchronization"></a><span data-ttu-id="e08d7-102">Configurare IIS 7 per la sincronizzazione Web</span><span class="sxs-lookup"><span data-stu-id="e08d7-102">Configure IIS 7 for Web Synchronization</span></span>
  <span data-ttu-id="e08d7-103">Le procedure di questo argomento illustrano il processo di configurazione manuale di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) versione 7 e successive per l'uso con la sincronizzazione Web per la replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="e08d7-103">The procedures in this topic will guide you through the process of manually configuring [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) version 7 and higher for use with Web synchronization for merge replication.</span></span> 
  
 <span data-ttu-id="e08d7-104">La configurazione di IIS 7 è il primo di tre passaggi necessari per abilitare la sincronizzazione Web.</span><span class="sxs-lookup"><span data-stu-id="e08d7-104">Configuring IIS 7 is the first of three steps needed to enable Web synchronization.</span></span>  
  
 <span data-ttu-id="e08d7-105">Per una panoramica del processo di configurazione, vedere [Configurare la sincronizzazione Web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="e08d7-105">For an overview of the entire configuration process, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e08d7-106">Verificare che nell'applicazione venga utilizzato solo [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] o versione successiva e che le versioni precedenti di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] non siano installate sul server IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-106">Make sure that your application uses only [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] or later versions, and that earlier versions of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] are not installed on the IIS server.</span></span> <span data-ttu-id="e08d7-107">Le versioni precedenti di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] possono causare errori, ad esempio: "Formato di messaggio non valido durante la sincronizzazione Web.</span><span class="sxs-lookup"><span data-stu-id="e08d7-107">Earlier versions of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] can cause errors, such as: "The format of a message during Web synchronization was invalid.</span></span> <span data-ttu-id="e08d7-108">Verificare che i componenti di replica siano configurati correttamente nel server Web".</span><span class="sxs-lookup"><span data-stu-id="e08d7-108">Ensure that replication components are properly configured at the Web server."</span></span>  
  
 <span data-ttu-id="e08d7-109">Per utilizzare la sincronizzazione Web, è necessario configurare IIS 7 completando i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="e08d7-109">To use Web synchronization, you must configure IIS 7 by completing the following steps.</span></span> <span data-ttu-id="e08d7-110">Ogni passaggio è descritto in dettaglio in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e08d7-110">Each step is described in detail in this topic.</span></span>  
  
1.  <span data-ttu-id="e08d7-111">Installare e configurare il listener per la replica di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel computer in cui viene eseguito IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-111">Install and configure the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener on the computer that is running IIS.</span></span>  
  
2.  <span data-ttu-id="e08d7-112">Configurare SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="e08d7-112">Configure Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="e08d7-113">L'utilizzo di SSL è obbligatorio per la comunicazione tra IIS e tutti i Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="e08d7-113">SSL is required for communication between IIS and all subscribers.</span></span>  
  
3.  <span data-ttu-id="e08d7-114">Configurare l'autenticazione IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-114">Configure IIS authentication.</span></span>  
  
4.  <span data-ttu-id="e08d7-115">Configurare un account e impostare le autorizzazioni per il listener per la replica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e08d7-115">Configure an account and set permissions for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener.</span></span>  
  
## <a name="installing-the-sql-server-replication-listener"></a><span data-ttu-id="e08d7-116">Installazione del listener per la replica di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e08d7-116">Installing the SQL Server Replication Listener</span></span>  

<span data-ttu-id="e08d7-117">La sincronizzazione Web è supportata in IIS a partire dalla versione 5.0.</span><span class="sxs-lookup"><span data-stu-id="e08d7-117">Web synchronization is supported on IIS, beginning with version 5.0.</span></span> <span data-ttu-id="e08d7-118">La Configurazione guidata sincronizzazione Web di IIS versione 5 e 6 non è disponibile con IIS versione 7.0 e successive.</span><span class="sxs-lookup"><span data-stu-id="e08d7-118">The Configure Web Synchronization Wizard of IIS version 5 and 6, is not available with IIS version 7.0 and higher.</span></span> <span data-ttu-id="e08d7-119">**A partire da SQL Server 2012, per usare il componente di sincronizzazione Web nel server IIS, è necessario installare SQL Server con la replica. Ad esempio, è possibile installare l'edizione gratuita SQL Server Express.**</span><span class="sxs-lookup"><span data-stu-id="e08d7-119">**Beginning with SQL Server 2012, to use the web sync component on IIS server, you should install SQL Server with replication. This can be the free SQL Server Express edition.**</span></span>
  
#### <a name="to-install-and-configure-the-sql-server-replication-listener"></a><span data-ttu-id="e08d7-120">Per installare e configurare Listener per la replica di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e08d7-120">To install and configure the SQL Server Replication Listener</span></span>  
  
1. <span data-ttu-id="e08d7-121">Installare la replica di SQL Server nel computer IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-121">Install SQL Server replication on the IIS computer.</span></span>

2.  <span data-ttu-id="e08d7-122">Creare una nuova directory di file per replisapi.dll nel computer che esegue IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-122">Create a new file directory for replisapi.dll on the computer that is running IIS.</span></span> <span data-ttu-id="e08d7-123">Sebbene sia possibile creare la directory in un percorso qualsiasi, è preferibile crearla nella directory \<*drive*>:\Inetpub.</span><span class="sxs-lookup"><span data-stu-id="e08d7-123">You can create the directory wherever you want, but we recommend that you create the directory under the \<*drive*>:\Inetpub directory.</span></span> <span data-ttu-id="e08d7-124">Ad esempio, creare la directory \<*drive*>:\Inetpub\SQLReplication\\.</span><span class="sxs-lookup"><span data-stu-id="e08d7-124">For example, create the directory \<*drive*>:\Inetpub\SQLReplication\\.</span></span>  
  
3.  <span data-ttu-id="e08d7-125">Copiare replisapi.dll dalla directory [!INCLUDE[ssInstallPathVar](../../includes/ssinstallpathvar-md.md)]com\ alla directory di file creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="e08d7-125">Copy replisapi.dll from the directory [!INCLUDE[ssInstallPathVar](../../includes/ssinstallpathvar-md.md)]com\ to the file directory that you created in step 1.</span></span>  
  
4.  <span data-ttu-id="e08d7-126">Registrare replisapi.dll:</span><span class="sxs-lookup"><span data-stu-id="e08d7-126">Register replisapi.dll:</span></span>  
  
    1.  <span data-ttu-id="e08d7-127">Fare clic sul pulsante **Start**e quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-127">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="e08d7-128">Nella casella **Apri** immettere `cmd` , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-128">In the **Open** box, enter `cmd`, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="e08d7-129">Nella directory creata nel passaggio 1 eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e08d7-129">In the directory created in step 1, execute the following command:</span></span>  
  
         `regsvr32 replisapi.dll`  
  
5.  <span data-ttu-id="e08d7-130">Creare un nuovo sito Web per la replica oppure utilizzare un sito esistente.</span><span class="sxs-lookup"><span data-stu-id="e08d7-130">Create a new Web site for replication or use an existing site.</span></span> <span data-ttu-id="e08d7-131">I componenti di replica accederanno al sito Web durante la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="e08d7-131">This Web site will be accessed by replication components during synchronization.</span></span> <span data-ttu-id="e08d7-132">Nelle procedure di questo argomento si presuppone l'utilizzo del sito Web predefinito.</span><span class="sxs-lookup"><span data-stu-id="e08d7-132">Procedures in this topic will assume the Default Web Site.</span></span> <span data-ttu-id="e08d7-133">Per ulteriori informazioni sulla creazione di siti Web, vedere la documentazione di IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-133">For more information about how to create Web sites, see the IIS documentation</span></span>  
  
6.  <span data-ttu-id="e08d7-134">Creare una directory virtuale in IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-134">Create a virtual directory in IIS.</span></span> <span data-ttu-id="e08d7-135">È consigliabile creare la directory virtuale nel sito Web creato nel passaggio 4 ed eseguirne il mapping alla directory creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="e08d7-135">The virtual directory should be created under the Web site that you created in step 4 and map it to the directory created in step 1.</span></span> <span data-ttu-id="e08d7-136">È consigliabile applicare le massime restrizioni nell'assegnazione delle autorizzazioni per questa directory.</span><span class="sxs-lookup"><span data-stu-id="e08d7-136">Be as restrictive as possible when you assign permissions to this directory.</span></span> <span data-ttu-id="e08d7-137">È necessario selezionare almeno autorizzazioni **Lettura** ed **Esecuzione** .</span><span class="sxs-lookup"><span data-stu-id="e08d7-137">You must select at least **Read** and **Execute** permissions.</span></span>  
  
    1.  <span data-ttu-id="e08d7-138">In **Gestione Internet Information Services (IIS)** , nel riquadro **Connessioni** fare clic con il pulsante destro del mouse su **Sito Web predefinito**, quindi selezionare **Aggiungi directory virtuale**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-138">In **Internet Information Services (IIS) Manager**, in the **Connections** pane, right-click **Default Web Site**, and then select **Add Virtual Directory**.</span></span>  
  
    2.  <span data-ttu-id="e08d7-139">In **alias**immettere `SQLReplication` .</span><span class="sxs-lookup"><span data-stu-id="e08d7-139">For **Alias**, enter `SQLReplication`.</span></span>  
  
    3.  <span data-ttu-id="e08d7-140">In **Percorso fisico** immettere **\<drive>:\Inetpub\SQLReplication\\** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-140">For **Physical Path**, enter **\<drive>:\Inetpub\SQLReplication\\**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="e08d7-141">Configurare IIS in modo da consentire l'esecuzione di replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="e08d7-141">Configure IIS to enable replisapi.dll to execute.</span></span>  
  
    1.  <span data-ttu-id="e08d7-142">In **Gestione Internet Information Services (IIS)** fare clic su **Sito Web predefinito**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-142">In **Internet Information Services (IIS) Manager**, click **Default Web Site**.</span></span>  
  
    2.  <span data-ttu-id="e08d7-143">Nel riquadro centrale fare clic su **Mapping gestori**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-143">In the center pane, click **Handler Mappings**.</span></span>  
  
    3.  <span data-ttu-id="e08d7-144">Nel riquadro **Azioni** fare clic su **Aggiungi mapping moduli**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-144">In the **Actions** pane, click **Add Module Mapping**.</span></span>  
  
    4.  <span data-ttu-id="e08d7-145">In percorso **richiesta** immettere `replisapi.dll` .</span><span class="sxs-lookup"><span data-stu-id="e08d7-145">For **Request** Path, enter `replisapi.dll`.</span></span>  
  
    5.  <span data-ttu-id="e08d7-146">Nell'elenco a discesa **Modulo** selezionare **IsapiModule**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-146">From the **Module** drop-down list, select **IsapiModule**.</span></span>  
  
    6.  <span data-ttu-id="e08d7-147">In **Eseguibile** immettere **\<drive>:\Inetpub\SQLReplication\replisapi.dll**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-147">For **Executable**, enter **\<drive>:\Inetpub\SQLReplication\replisapi.dll**.</span></span>  
  
    7.  <span data-ttu-id="e08d7-148">Per **Nome** immettere `Replisapi`.</span><span class="sxs-lookup"><span data-stu-id="e08d7-148">For **Name**, enter `Replisapi`.</span></span>  
  
    8.  <span data-ttu-id="e08d7-149">Fare clic sul pulsante **Restrizioni richieste** , fare clic sulla scheda **Accesso** , quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-149">Click the **Request Restrictions** button, click the **Access** tab, and then click **Execute**.</span></span>  
  
    9. <span data-ttu-id="e08d7-150">Per chiudere la finestra di dialogo **Restrizioni richieste** , fare clic su **OK** , quindi fare nuovamente clic su **OK** per chiudere la finestra di dialogo **Aggiungi mapping moduli** .</span><span class="sxs-lookup"><span data-stu-id="e08d7-150">Click **OK** to close the **Request Restrictions** dialog box, and then click **OK** again to close the **Add Module Mapping** dialog box.</span></span> <span data-ttu-id="e08d7-151">Quando viene richiesto di consentire l'estensione ISAPI, fare clic su **Sì** per aggiungere l'estensione.</span><span class="sxs-lookup"><span data-stu-id="e08d7-151">When you are prompted to allow the ISAPI extension, click **Yes** to add the extension.</span></span>  
  
    10. <span data-ttu-id="e08d7-152">Verificare che Replisapi.dll sia elencato sotto i mapping dei gestori contrassegnati come **Abilitato** .</span><span class="sxs-lookup"><span data-stu-id="e08d7-152">Verify that Replisapi.dll is listed under the **Enabled** handler mappings.</span></span> <span data-ttu-id="e08d7-153">Se si trova nell'elenco **Disabilitato** , fare clic con il pulsante destro del mouse sulla voce Replisapi, quindi scegliere **Modifica autorizzazioni funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-153">If it is in the **Disabled** list, right-click the Replisapi entry and then click **Edit Feature Permissions**.</span></span> <span data-ttu-id="e08d7-154">Selezionare la casella **Esegui** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-154">Check the **Execute** box, and then click **OK**.</span></span>  
  
## <a name="configuring-iis-authentication"></a><span data-ttu-id="e08d7-155">Configurazione dell'autenticazione IIS</span><span class="sxs-lookup"><span data-stu-id="e08d7-155">Configuring IIS Authentication</span></span>  
 <span data-ttu-id="e08d7-156">Quando i computer Sottoscrittori si connettono a IIS, è necessario che vengano autenticati da IIS per poter accedere a risorse e processi.</span><span class="sxs-lookup"><span data-stu-id="e08d7-156">When subscriber computers connect to IIS, IIS must authenticate the subscribers before they can access resources and processes.</span></span> <span data-ttu-id="e08d7-157">L'autenticazione può essere applicata all'intero sito Web oppure alla directory virtuale creata.</span><span class="sxs-lookup"><span data-stu-id="e08d7-157">Authentication can be applied to the whole Web site or to the virtual directory that you created.</span></span>  
  
 <span data-ttu-id="e08d7-158">È consigliabile utilizzare l'autenticazione di base con SSL.</span><span class="sxs-lookup"><span data-stu-id="e08d7-158">We recommend that you use Basic Authentication with SSL.</span></span> <span data-ttu-id="e08d7-159">SSL è necessario indipendentemente dal tipo di autenticazione utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e08d7-159">SSL is required, regardless of the type of authentication that is used.</span></span>  
  
 <span data-ttu-id="e08d7-160">È consigliabile utilizzare l'autenticazione di base con SSL.</span><span class="sxs-lookup"><span data-stu-id="e08d7-160">We recommend that you use Basic Authentication with SSL.</span></span> <span data-ttu-id="e08d7-161">SSL è necessario indipendentemente dal tipo di autenticazione utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e08d7-161">SSL is required, regardless of the type of authentication that is used.</span></span>  
  
#### <a name="to-configure-iis-authentication"></a><span data-ttu-id="e08d7-162">Per configurare l'autenticazione IIS</span><span class="sxs-lookup"><span data-stu-id="e08d7-162">To Configure IIS Authentication</span></span>  
  
1.  <span data-ttu-id="e08d7-163">In **Gestione Internet Information Services (IIS)** fare clic su **Sito Web predefinito**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-163">In **Internet Information Services (IIS) Manager**, click **Default Web Site**.</span></span>  
  
2.  <span data-ttu-id="e08d7-164">Nel riquadro centrale fare doppio clic su **Autenticazione**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-164">In the middle pane, double-click **Authentication**.</span></span>  
  
3.  <span data-ttu-id="e08d7-165">Fare clic con il pulsante destro del mouse su Autenticazione anonima, quindi scegliere Disabilita.</span><span class="sxs-lookup"><span data-stu-id="e08d7-165">Right-click Anonymous Authentication, and then choose Disable.</span></span>  
  
4.  <span data-ttu-id="e08d7-166">Fare clic con il pulsante destro del mouse su Autenticazione di base, quindi scegliere Abilita.</span><span class="sxs-lookup"><span data-stu-id="e08d7-166">Right-click Basic Authentication, and then choose Enable.</span></span>  
  
## <a name="configuring-secure-sockets-layer"></a><span data-ttu-id="e08d7-167">Configurazione di SSL (Secure Sockets Layer)</span><span class="sxs-lookup"><span data-stu-id="e08d7-167">Configuring Secure Sockets Layer</span></span>  
 <span data-ttu-id="e08d7-168">Per configurare SSL, specificare un certificato che verrà utilizzato dal computer che esegue IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-168">To configure SSL, specify a certificate to be used by the computer running IIS.</span></span> <span data-ttu-id="e08d7-169">La sincronizzazione Web per la replica di tipo merge supporta l'utilizzo di certificati server, ma non di certificati client.</span><span class="sxs-lookup"><span data-stu-id="e08d7-169">Web synchronization for merge replication supports using server certificates, but not client certificates.</span></span> <span data-ttu-id="e08d7-170">Per configurare IIS per la distribuzione, è innanzitutto necessario ottenere un certificato da un'autorità di certificazione.</span><span class="sxs-lookup"><span data-stu-id="e08d7-170">To configure IIS for deployment, you must first obtain a certificate from a certification authority (CA).</span></span> <span data-ttu-id="e08d7-171">Per ulteriori informazioni sui certificati, vedere la documentazione di IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-171">For more information about certificates, see the IIS documentation.</span></span>  
  
 <span data-ttu-id="e08d7-172">Dopo l'installazione del certificato, è necessario associare il certificato al sito Web utilizzato nella sincronizzazione Web.</span><span class="sxs-lookup"><span data-stu-id="e08d7-172">After you install the certificate, you must associate the certificate with the Web site that is used by Web synchronization.</span></span> <span data-ttu-id="e08d7-173">Per lo sviluppo e i test, è possibile specificare un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="e08d7-173">For development and testing, you can specify a self-signed certificate.</span></span> <span data-ttu-id="e08d7-174">Con IIS 7 è possibile creare un certificato e registrarlo nel computer.</span><span class="sxs-lookup"><span data-stu-id="e08d7-174">IIS 7 can create a certificate for you and register it on your computer.</span></span>  
  
 <span data-ttu-id="e08d7-175">La differenza tra la distribuzione per la produzione e le procedure fornite in questo argomento è data dal fatto che nei test di produzione e pre-produzione si utilizza un certificato rilasciato da una CA anziché un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="e08d7-175">The difference between deploying for production and the procedures given here is that in production and pre-production testing, you would use a certificate issued by a CA instead of a self-signed certificate.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e08d7-176">Non è consigliabile utilizzare un certificato autofirmato per un'installazione di produzione.</span><span class="sxs-lookup"><span data-stu-id="e08d7-176">A self-signed certificate is not recommended for a production installation.</span></span> <span data-ttu-id="e08d7-177">I certificati autofirmati non sono sicuri.</span><span class="sxs-lookup"><span data-stu-id="e08d7-177">Self-signed certificates are not secure.</span></span> <span data-ttu-id="e08d7-178">Utilizzare tali certificati solo ai fini di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="e08d7-178">Use self-signed certificates for development and testing only.</span></span>  
  
 <span data-ttu-id="e08d7-179">Per configurare SSL, verranno eseguiti i passaggi riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="e08d7-179">To configure SSL, you will perform the following steps:</span></span>  
  
1.  <span data-ttu-id="e08d7-180">Configurare il sito Web per richiedere SSL e ignorare i certificati client.</span><span class="sxs-lookup"><span data-stu-id="e08d7-180">Configure the Web site to require SSL and ignore client certificates.</span></span>  
  
2.  <span data-ttu-id="e08d7-181">Ottenere un certificato da una CA o creare un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="e08d7-181">Obtain a certificate from a CA or create a self-signed certificate.</span></span>  
  
3.  <span data-ttu-id="e08d7-182">Associare il certificato al sito Web per la replica.</span><span class="sxs-lookup"><span data-stu-id="e08d7-182">Bind the certificate to the replication Web site.</span></span>  
  
#### <a name="to-require-ssl-security-for-a-web-site"></a><span data-ttu-id="e08d7-183">Per richiedere la sicurezza SSL per un sito Web</span><span class="sxs-lookup"><span data-stu-id="e08d7-183">To require SSL security for a Web site</span></span>  
  
1.  <span data-ttu-id="e08d7-184">In **Gestione Internet Information Services (IIS)** espandere il nodo del server locale, quindi fare clic su **Sito Web predefinito** o sul sito di sincronizzazione Web se è diverso dal sito Web predefinito.</span><span class="sxs-lookup"><span data-stu-id="e08d7-184">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click the **Default Web Site** (or your Web synchronization site if it is different from the default Web site).</span></span>  
  
2.  <span data-ttu-id="e08d7-185">Nel riquadro centrale fare doppio clic su **Impostazioni SSL**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-185">In the middle pane, double-click **SSL Settings**.</span></span>  
  
3.  <span data-ttu-id="e08d7-186">Selezionare l'opzione **Richiedi SSL** .</span><span class="sxs-lookup"><span data-stu-id="e08d7-186">Check the **Require SSL** option.</span></span> <span data-ttu-id="e08d7-187">In **Certificati client**verificare che il pulsante **Ignora** sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="e08d7-187">Under **Client certificates**, verify that the **Ignore** button is selected.</span></span>  
  
#### <a name="to-create-a-self-signed-certificate-for-testing"></a><span data-ttu-id="e08d7-188">Per creare un certificato autofirmato per i test</span><span class="sxs-lookup"><span data-stu-id="e08d7-188">To create a self-signed certificate for testing</span></span>  
  
1.  <span data-ttu-id="e08d7-189">In **Gestione Internet Information Services (IIS)** fare clic sul nodo del server locale, quindi fare doppio clic su **Certificati server**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-189">In **Internet Information Services (IIS) Manager**, click the local server node, and then in the center pane, double-click on **Server Certificates**.</span></span>  
  
2.  <span data-ttu-id="e08d7-190">Nel riquadro **Azioni** fare clic su **Crea certificato autofirmato**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-190">In the **Actions** pane, click **Create Self-Signed Certificate**.</span></span>  
  
3.  <span data-ttu-id="e08d7-191">Nella finestra di dialogo **Crea certificato autofirmato** immettere un nome per il certificato, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-191">In the **Create Self-Signed Certificate** dialog box, enter a name for the certificate, and then click **OK**.</span></span>  
  
###### <a name="to-bind-a-certificate-to-a-web-site"></a><span data-ttu-id="e08d7-192">Per associare un certificato a un sito Web</span><span class="sxs-lookup"><span data-stu-id="e08d7-192">To bind a certificate to a Web site</span></span>  
  
1.  <span data-ttu-id="e08d7-193">Nel riquadro **Connessioni** fare clic su **Sito Web predefinito** o sul sito di sincronizzazione Web se è diverso dal sito Web predefinito.</span><span class="sxs-lookup"><span data-stu-id="e08d7-193">In the **Connections** pane, click the **Default Web Site** (or your Web synchronization site, if it is different from the default Web site).</span></span>  
  
2.  <span data-ttu-id="e08d7-194">Nel riquadro **Azioni** fare clic su **Binding**, quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-194">In the **Actions** pane, click **Bindings**, and then click **Add**.</span></span> <span data-ttu-id="e08d7-195">Verrà visualizzata la finestra di dialogo **Aggiungi binding sito** .</span><span class="sxs-lookup"><span data-stu-id="e08d7-195">The **Add Site Binding** dialog box will appear.</span></span>  
  
3.  <span data-ttu-id="e08d7-196">Nell'elenco a discesa **Tipo** selezionare **https**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-196">From the **Type** drop-down list, select **https**.</span></span> <span data-ttu-id="e08d7-197">Mantenere le impostazioni predefinite per **Indirizzo IP** e **Porta**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-197">Leave the default settings for **IP address** and **Port**.</span></span>  
  
4.  <span data-ttu-id="e08d7-198">Nell'elenco a discesa **Certificato SSL** selezionare il certificato creato in "Per creare un certificato autofirmato per i test", fare clic su **OK**, quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-198">From the **SSL certificate** drop-down list, select the certificate created in "To create a self-signed certificate for testing," click **OK**, and then click **Close**.</span></span>  
  
###### <a name="to-test-the-certificate"></a><span data-ttu-id="e08d7-199">Per testare il certificato</span><span class="sxs-lookup"><span data-stu-id="e08d7-199">To test the certificate</span></span>  
  
1.  <span data-ttu-id="e08d7-200">In **Gestione Internet Information Services (IIS)** fare clic su **Sito Web predefinito.**</span><span class="sxs-lookup"><span data-stu-id="e08d7-200">In **Internet Information Services (IIS) Manager**, click **Default Web Site.**</span></span>  
  
2.  <span data-ttu-id="e08d7-201">Nel riquadro **Azioni** fare clic su **Sfoglia \*:443 (https)** .</span><span class="sxs-lookup"><span data-stu-id="e08d7-201">From the **Actions** pane, click **Browse \*:443(https)**.</span></span>  
  
3.  <span data-ttu-id="e08d7-202">Verrà aperto Internet Explorer e verrà visualizzato il messaggio "Si è verificato un problema con il certificato di sicurezza del sito Web".</span><span class="sxs-lookup"><span data-stu-id="e08d7-202">Internet Explorer will open and display a message that "There is a problem with this website's security certificate."</span></span> <span data-ttu-id="e08d7-203">Questo avviso suggerisce che il certificato associato non è stato rilasciato da una CA riconosciuta e potrebbe non essere attendibile.</span><span class="sxs-lookup"><span data-stu-id="e08d7-203">This warning tells you that the associated certificate was not issued by a recognized CA and might not be trustworthy.</span></span> <span data-ttu-id="e08d7-204">Si tratta di un avviso previsto, pertanto fare clic su **Continuare con il sito Web (scelta non consigliata)** .</span><span class="sxs-lookup"><span data-stu-id="e08d7-204">This is an expected warning, so click **Continue to this website (not recommended)**.</span></span>  
  
4.  <span data-ttu-id="e08d7-205">Se viene visualizzata la richiesta **Connetti a localhost**, immettere un nome utente e una password per continuare.</span><span class="sxs-lookup"><span data-stu-id="e08d7-205">If you are prompted to **Connect to localhost**, enter a user name and password to proceed.</span></span> <span data-ttu-id="e08d7-206">Dovrebbe venire visualizzata la pagina predefinita del sito Web.</span><span class="sxs-lookup"><span data-stu-id="e08d7-206">You should see the default page for the Web site.</span></span>  
  
## <a name="setting-permissions-for-the-sql-server-replication-listener"></a><span data-ttu-id="e08d7-207">Impostazione delle autorizzazioni per Listener per la replica di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e08d7-207">Setting Permissions for the SQL Server Replication Listener</span></span>  
 <span data-ttu-id="e08d7-208">Quando un computer Sottoscrittore si connette al computer che esegue IIS, viene autenticato mediante il tipo di autenticazione specificato durante la configurazione di IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-208">When a subscriber computer connects to the computer running IIS, the subscriber is authenticated by using the type of authentication specified when you configured IIS.</span></span> <span data-ttu-id="e08d7-209">Dopo l'autenticazione del Sottoscrittore, in IIS viene controllato se il Sottoscrittore è autorizzato a richiamare la replica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e08d7-209">After IIS authenticates the subscriber, IIS checks whether the subscriber is authorized to invoke [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span> <span data-ttu-id="e08d7-210">Per controllare gli utenti autorizzati a richiamare le replica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è necessario impostare le autorizzazioni per replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="e08d7-210">You control the users that can invoke [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication by setting permissions for replisapi.dll.</span></span> <span data-ttu-id="e08d7-211">La corretta configurazione delle autorizzazioni è fondamentale per impedire l'accesso non autorizzato alla replica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e08d7-211">Properly configuring permissions is necessary to prevent unauthorized access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span>  
  
 <span data-ttu-id="e08d7-212">Per configurare le autorizzazioni minime per l'account utilizzato per l'esecuzione di Listener per la replica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , completare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e08d7-212">To configure the minimum permissions for the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener runs, complete the following procedure.</span></span> <span data-ttu-id="e08d7-213">I passaggi della procedura seguente sono validi per [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Server 2008 con IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="e08d7-213">The steps in the following procedure apply to [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Server 2008 running IIS 7.0.</span></span>  
  
 <span data-ttu-id="e08d7-214">Oltre a eseguire la procedura seguente, assicurarsi che gli account di accesso necessari siano inclusi nell'elenco di accesso alla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="e08d7-214">In addition to performing the following steps, make sure that the required logins are in the publication access list (PAL).</span></span> <span data-ttu-id="e08d7-215">Per altre informazioni sull'elenco di acceso alla pubblicazione, vedere [Proteggere il server di pubblicazione](security/secure-the-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="e08d7-215">For more information about the PAL, see [Secure the Publisher](security/secure-the-publisher.md).</span></span>  
  
 <span data-ttu-id="e08d7-216">**Importante** L'account creato in questa sezione è quello che verrà utilizzato per la connessione al server di pubblicazione e al database di distribuzione durante la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="e08d7-216">**Important** The account created in this section is the account that will connect to the Publisher and Distributor during synchronization.</span></span> <span data-ttu-id="e08d7-217">È necessario aggiungere questo account come account di accesso SQL nel server di distribuzione e di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="e08d7-217">This account must be added as a SQL Login account on the distribution and publication server.</span></span>  
  
 <span data-ttu-id="e08d7-218">L'account utilizzato per il listener per la replica di SQL Server deve disporre di autorizzazioni come descritto nell'argomento Sicurezza dell'agente di merge, nella sezione "Connettersi al server di pubblicazione o al database di distribuzione".</span><span class="sxs-lookup"><span data-stu-id="e08d7-218">The account used for the SQL Server Replication Listener must have permissions as described in the Merge Agent Security topic, in the "Connect to the Publisher or Distributor" section.</span></span>  
  
 <span data-ttu-id="e08d7-219">In breve è necessario che l'account:</span><span class="sxs-lookup"><span data-stu-id="e08d7-219">In summary, the account must:</span></span>  
  
-   <span data-ttu-id="e08d7-220">sia membro dell'elenco di accesso alla pubblicazione;</span><span class="sxs-lookup"><span data-stu-id="e08d7-220">Be a member of the Publication Access List (PAL).</span></span>  
  
-   <span data-ttu-id="e08d7-221">sia sottoposto a mapping a un account di accesso associato a un utente nel database di pubblicazione;</span><span class="sxs-lookup"><span data-stu-id="e08d7-221">Be mapped to a login associated with a user in the publication database.</span></span>  
  
-   <span data-ttu-id="e08d7-222">sia sottoposto a mapping a un account di accesso associato a un utente nel database di distribuzione;</span><span class="sxs-lookup"><span data-stu-id="e08d7-222">Be mapped to a login associated with a user in the distribution database.</span></span>  
  
-   <span data-ttu-id="e08d7-223">disponga delle autorizzazioni di lettura per la condivisione snapshot.</span><span class="sxs-lookup"><span data-stu-id="e08d7-223">Have Read permissions on the snapshot share.</span></span>  
  
#### <a name="to-configure-the-account-and-permissions"></a><span data-ttu-id="e08d7-224">Per configurare l'account e le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e08d7-224">To configure the account and permissions</span></span>  
  
1.  <span data-ttu-id="e08d7-225">Creare un account locale nel computer che esegue IIS:</span><span class="sxs-lookup"><span data-stu-id="e08d7-225">Create a local account on the computer running IIS:</span></span>  
  
    1.  <span data-ttu-id="e08d7-226">Aprire **Gestione server**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-226">Open **Server Manager**.</span></span> <span data-ttu-id="e08d7-227">Dal menu Start fare clic con il pulsante destro del mouse su **Computer**e scegliere **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-227">From the Start menu, right-click **Computer**, and then click **Manage**.</span></span>  
  
    2.  <span data-ttu-id="e08d7-228">In **Gestione server**espandere **Configurazione**, quindi **Utenti e gruppi locali**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-228">In **Server Manager**, expand **Configuration**, and then expand **Local Users and Groups**.</span></span>  
  
    3.  <span data-ttu-id="e08d7-229">Fare clic con il pulsante destro del mouse su **Utenti**e quindi scegliere **Nuovo utente**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-229">Right-click **Users**, and then click **New User**.</span></span>  
  
    4.  <span data-ttu-id="e08d7-230">Immettere un nome utente e una password complessa.</span><span class="sxs-lookup"><span data-stu-id="e08d7-230">Enter a user name and a strong password.</span></span> <span data-ttu-id="e08d7-231">Deselezionare **Cambiamento obbligatorio password all'accesso successivo**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-231">Clear **User must change password at next logon**.</span></span>  
  
    5.  <span data-ttu-id="e08d7-232">Fare clic su **Crea**e quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-232">Click **Create**, and then click **Close**.</span></span>  
  
2.  <span data-ttu-id="e08d7-233">Aggiungere l'account al gruppo IIS_IUSRS:</span><span class="sxs-lookup"><span data-stu-id="e08d7-233">Add the account to the IIS_IUSRS group:</span></span>  
  
    1.  <span data-ttu-id="e08d7-234">In **Gestione server**espandere **Configurazione**e **Utenti e gruppi locali**, quindi fare clic su **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-234">In **Server Manager**, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>  
  
    2.  <span data-ttu-id="e08d7-235">Fare clic con il pulsante destro del mouse su **IIS_IUSRS**, quindi fare clic su **Aggiungi al gruppo**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-235">Right-click **IIS_IUSRS**, and then click **Add to Group**.</span></span>  
  
    3.  <span data-ttu-id="e08d7-236">Nella finestra di dialogo **Proprietà - IIS_IUSRS** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-236">In the **IIS_IUSRS Properties** dialog box, click **Add**.</span></span>  
  
    4.  <span data-ttu-id="e08d7-237">Nella finestra di dialogo **Seleziona Utenti** aggiungere l'account creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="e08d7-237">In the **Select Users, Computers, or Groups** dialog box, add the account created in step 1.</span></span>  
  
    5.  <span data-ttu-id="e08d7-238">Assicurarsi che nel campo **Da questo percorso** sia visualizzato il nome del computer locale (non di un dominio).</span><span class="sxs-lookup"><span data-stu-id="e08d7-238">Verify that **From this location** displays the name of the local computer (not a domain).</span></span> <span data-ttu-id="e08d7-239">Se in questo campo non è visualizzato il nome del computer locale, fare clic su **Percorsi**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-239">If this field does not display the local computer name, click **Locations**.</span></span> <span data-ttu-id="e08d7-240">Nella finestra di dialogo **Percorsi** selezionare il computer locale e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-240">In the **Locations** dialog box, select the local computer, and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="e08d7-241">Nelle finestre di dialogo **Seleziona utenti** e **Proprietà - IIS_IUSRS** fare clic su**OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-241">In the **Select Users** dialog box and the **IIS_IUSRS Properties** dialog box, click**OK**.</span></span>  
  
3.  <span data-ttu-id="e08d7-242">Concedere all'account le autorizzazioni minime per la cartella contenente replisapi.dll:</span><span class="sxs-lookup"><span data-stu-id="e08d7-242">Grant minimum account permissions on the folder that contains replisapi.dll:</span></span>  
  
    1.  <span data-ttu-id="e08d7-243">In Windows Explorer fare clic con il pulsante destro del mouse sulla cartella creata per replisapi.dll, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-243">In Windows Explorer, right-click the folder that you created for replisapi.dll, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="e08d7-244">Nella scheda **Sicurezza** fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-244">On the **Security** tab, click **Edit**.</span></span>  
  
    3.  <span data-ttu-id="e08d7-245">Nella finestra di dialogo **Autorizzazioni per \<foldername>** fare clic su **Aggiungi** per aggiungere l'account creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="e08d7-245">In the **Permissions for \<foldername>** dialog box, click **Add** to add the account that you created in step 1.</span></span>  
  
    4.  <span data-ttu-id="e08d7-246">Assicurarsi che nel campo **Da questo percorso** sia visualizzato il nome del computer locale (non di un dominio).</span><span class="sxs-lookup"><span data-stu-id="e08d7-246">Verify that **From this location** displays the name of the local computer (not a domain).</span></span> <span data-ttu-id="e08d7-247">Se in questo campo non è visualizzato il nome del computer locale, fare clic su **Percorsi**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-247">If this field does not display the local computer name, click **Locations**.</span></span> <span data-ttu-id="e08d7-248">Nella finestra di dialogo **Percorsi** selezionare il computer locale e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-248">In the **Locations** dialog box, select the local computer, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="e08d7-249">Verificare che all'account siano concesse soltanto le autorizzazioni **Lettura**, **Lettura ed esecuzione** e **Visualizzazione contenuto cartella**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-249">Verify that the account is granted only **Read**, **Read & Execute**, and **List Folder Contents** permissions.</span></span>  
  
    6.  <span data-ttu-id="e08d7-250">Selezionare gli utenti o i gruppi che non necessitano dell'accesso alla directory, quindi fare clic su **Rimuovi**e su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-250">Select any users or groups that do not require access to the directory, click **Remove**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="e08d7-251">Creare un pool di applicazioni in **Gestione Internet Information Services (IIS)** :</span><span class="sxs-lookup"><span data-stu-id="e08d7-251">Create an application pool in **Internet Information Services (IIS) Manager**:</span></span>  
  
    1.  <span data-ttu-id="e08d7-252">In **Gestione Internet Information Services (IIS)** , nel riquadro **Connessioni** espandere il nodo del server locale.</span><span class="sxs-lookup"><span data-stu-id="e08d7-252">In **Internet Information Services (IIS) Manager**, in the **Connections** pane, expand the local server node.</span></span>  
  
    2.  <span data-ttu-id="e08d7-253">Fare clic con il pulsante destro del mouse su **Pool di applicazioni**, quindi scegliere **Aggiungi pool di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-253">Right-click **Application Pools**, and then click **Add Application Pool**.</span></span>  
  
    3.  <span data-ttu-id="e08d7-254">Immettere un nome per il pool di applicazioni, mantenere i valori predefiniti per i campi rimanenti, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-254">Enter a name for the application pool, leave the default values for the remaining fields, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e08d7-255">Se si prevede di utilizzare più di due client di sincronizzazione simultanei, è necessario creare un Web garden.</span><span class="sxs-lookup"><span data-stu-id="e08d7-255">If you anticipate having more than two concurrent synchronization clients, you might want to create a web garden.</span></span> <span data-ttu-id="e08d7-256">Per altre informazioni, vedere "Creazione di un Web garden" in [Configurare la sincronizzazione Web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="e08d7-256">For more information, see "Creating a Web Garden" in [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
5.  <span data-ttu-id="e08d7-257">Associare l'account al pool di applicazioni:</span><span class="sxs-lookup"><span data-stu-id="e08d7-257">Associate the account with the application pool:</span></span>  
  
    1.  <span data-ttu-id="e08d7-258">In **Gestione Internet Information Services (IIS)** espandere il nodo del server locale, quindi fare clic su **Pool di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-258">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click on **Application Pools**.</span></span>  
  
    2.  <span data-ttu-id="e08d7-259">Fare clic con il pulsante destro del mouse sul pool di applicazioni creato, quindi scegliere **Impostazioni predefinite pool di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-259">Right-click the application pool that you created, and then click **Set Application Pool Defaults**.</span></span>  
  
    3.  <span data-ttu-id="e08d7-260">Nella finestra di dialogo **Impostazioni predefinite pool di applicazioni** passare alla sezione **Modello di processo** , quindi fare clic sul campo **Identità** .</span><span class="sxs-lookup"><span data-stu-id="e08d7-260">In the **Application Pool Defaults** dialog box, scroll down to the **Process Model** section, and then click the **Identity** field.</span></span>  
  
    4.  <span data-ttu-id="e08d7-261">Fare clic sul pulsante con i puntini di sospensione sul lato destro della riga **Identità** .</span><span class="sxs-lookup"><span data-stu-id="e08d7-261">Click the ellipsis button on the right side of the **Identity** row.</span></span>  
  
    5.  <span data-ttu-id="e08d7-262">Fare clic sul pulsante di opzione **Account personalizzato** , quindi su **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-262">Click the **Custom Account** radio button, and then click **Set**.</span></span>  
  
    6.  <span data-ttu-id="e08d7-263">Nei campi **Nome utente** e **Password** immettere l'account e la password creati nel passaggio 1, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-263">In the **User name** and **Password** fields, enter the account and password that were created in step 1, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="e08d7-264">Fare clic su **OK** per chiudere la finestra di dialogo **Identità pool di applicazioni** , quindi fare nuovamente clic su **OK** per chiudere la finestra di dialogo **Impostazioni predefinite pool di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-264">Click **OK** to close the **Application Pool Identity** dialog box, and then click **OK** again to close the **Application Pool Defaults**dialog box.</span></span>  
  
6.  <span data-ttu-id="e08d7-265">Associare il pool di applicazioni al sito Web per la replica:</span><span class="sxs-lookup"><span data-stu-id="e08d7-265">Associate the application pool with the replication Web site:</span></span>  
  
    1.  <span data-ttu-id="e08d7-266">In **Gestione Internet Information Services (IIS)** espandere il nodo del server locale, quindi fare clic su **Sito Web predefinito** o sul sito di sincronizzazione Web se è diverso dal sito Web predefinito.</span><span class="sxs-lookup"><span data-stu-id="e08d7-266">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click on the **Default Web Site** (or your Web synchronization site if it is different from the default Web site).</span></span>  
  
    2.  <span data-ttu-id="e08d7-267">Nel riquadro **Azioni** , in **Gestione sito Web**fare clic su **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-267">In the **Actions** pane, under **Manage Web Site**, click **Advanced Settings**.</span></span>  
  
    3.  <span data-ttu-id="e08d7-268">Nella finestra di dialogo **Impostazioni avanzate** fare clic sul pulsante con i puntini di sospensione a destra di **Pool di applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-268">In the **Advanced Settings** dialog box, click on the ellipsis button to the right of **Application Pool**.</span></span>  
  
    4.  <span data-ttu-id="e08d7-269">Nell'elenco a discesa **Pool di applicazioni** selezionare il pool di applicazioni creato nel passaggio 4, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-269">From the **Application pool** drop-down list, select the application pool you created in step 4, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="e08d7-270">Fare nuovamente clic su **OK** per chiudere Impostazioni avanzate.</span><span class="sxs-lookup"><span data-stu-id="e08d7-270">Click **OK** again to close Advanced Settings.</span></span>  
  
## <a name="testing-the-connection-to-replisapidll"></a><span data-ttu-id="e08d7-271">Test della connessione a replisapi.dll</span><span class="sxs-lookup"><span data-stu-id="e08d7-271">Testing the Connection to replisapi.dll</span></span>  
 <span data-ttu-id="e08d7-272">Eseguire la sincronizzazione Web in modalità diagnostica per testare la connessione al computer che esegue IIS e verificare la corretta installazione del certificato SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="e08d7-272">Run Web synchronization in diagnostic mode to test the connection to the computer running IIS and to make sure that the Secure Sockets Layer (SSL) certificate is properly installed.</span></span> <span data-ttu-id="e08d7-273">Per eseguire la sincronizzazione Web in modalità diagnostica, è necessario disporre dei privilegi di amministratore sul computer che esegue IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-273">To run Web synchronization in diagnostic mode, you must be an administrator on the computer running IIS.</span></span>  
  
#### <a name="to-test-the-connection-to-replisapidll"></a><span data-ttu-id="e08d7-274">Per testare la connessione a replisapi.dll</span><span class="sxs-lookup"><span data-stu-id="e08d7-274">To test the connection to replisapi.dll</span></span>  
  
1.  <span data-ttu-id="e08d7-275">Assicurarsi che le impostazioni per la rete LAN (Local Area Network) nel Sottoscrittore siano corrette:</span><span class="sxs-lookup"><span data-stu-id="e08d7-275">Make sure that local area network (LAN) settings at the Subscriber are correct:</span></span>  
  
    1.  <span data-ttu-id="e08d7-276">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer fare clic su **Opzioni Internet** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-276">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, on the **Tools** menu, click **Internet Options**.</span></span>  
  
    2.  <span data-ttu-id="e08d7-277">Nella scheda **Connessioni** fare clic su **Impostazioni LAN**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-277">On the **Connections** tab, click **LAN Settings**.</span></span>  
  
    3.  <span data-ttu-id="e08d7-278">Se nella rete LAN non viene utilizzato un server proxy, deselezionare **Rileva automaticamente impostazioni** e **Utilizza un server proxy server per le connessioni LAN**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-278">If a proxy server is not used on the LAN, clear **Automatically Detect Settings** and **Use a proxy server for your LAN**.</span></span>  
  
    4.  <span data-ttu-id="e08d7-279">Se viene utilizzato un server proxy, selezionare **Utilizza un server proxy per le connessioni LAN** e **Ignora server proxy per indirizzi locali**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-279">If a proxy server is used, click **Use a proxy server for your LAN** and **Bypass proxy server for local addresses**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="e08d7-280">Nel Sottoscrittore, in Internet Explorer, connettersi al server in modalità diagnostica aggiungendo `?diag` alla fine dell'indirizzo di replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="e08d7-280">At the Subscriber, in Internet Explorer, connect to the server in diagnostic mode by appending `?diag` to the address for the replisapi.dll.</span></span> <span data-ttu-id="e08d7-281">Ad esempio: `https://server.domain.com/directory/replisapi.dll?diag`.</span><span class="sxs-lookup"><span data-stu-id="e08d7-281">For example: `https://server.domain.com/directory/replisapi.dll?diag`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e08d7-282">Nell'esempio precedente sostituire **server.dominio.com** con il nome esatto di **Rilasciato a** elencato nella sezione **Certificati del server** in Gestione IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-282">In the example above, **server.domain.com** should be replaced with the exact **Issued To** name listed under the **Server Certificates** section in IIS Manager.</span></span>  
  
3.  <span data-ttu-id="e08d7-283">Se il certificato specificato per IIS non viene riconosciuto dal sistema operativo Windows, viene visualizzata la finestra di dialogo **Avviso di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="e08d7-283">If the certificate that you specified for IIS is not recognized by the Windows operating system, the **Security Alert** dialog box appears.</span></span> <span data-ttu-id="e08d7-284">Questo avviso può essere visualizzato perché il certificato è un certificato di prova o è stato emesso da un'autorità di certificazione non riconosciuta da Windows.</span><span class="sxs-lookup"><span data-stu-id="e08d7-284">This alert might occur because the certificate is a test certificate or the certificate was issued by a certification authority (CA) that Windows does not recognize.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e08d7-285">Se questa finestra di dialogo non viene visualizzata, verificare che il certificato per il server a cui si accede sia stato aggiunto all'archivio certificati nel Sottoscrittore come certificato attendibile.</span><span class="sxs-lookup"><span data-stu-id="e08d7-285">If this dialog box does not appear, make sure that the certificate for the server that you are accessing has been added to the certificate store at the Subscriber as a trusted certificate.</span></span> <span data-ttu-id="e08d7-286">Per ulteriori informazioni sull'esportazione dei certificati, vedere la documentazione di IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-286">For more information about exporting certificates, see the IIS documentation.</span></span>  
  
    1.  <span data-ttu-id="e08d7-287">Nella finestra di dialogo **Avviso di sicurezza** fare clic su **Visualizza certificato**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-287">In the **Security Alert** dialog box, click **View Certificate**.</span></span>  
  
    2.  <span data-ttu-id="e08d7-288">Nella scheda **Generale** della finestra di dialogo **Certificato** fare clic su **Installa certificato**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-288">In the **Certificate** dialog box, on the **General** tab, click **Install Certificate**.</span></span>  
  
    3.  <span data-ttu-id="e08d7-289">Completare l'Importazione guidata certificati, accettando le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="e08d7-289">Complete the Certificate Import Wizard, accepting the defaults.</span></span>  
  
    4.  <span data-ttu-id="e08d7-290">Nella finestra di dialogo **Avviso di sicurezza** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-290">In the **Security Warning** dialog box, click **Yes**.</span></span>  
  
    5.  <span data-ttu-id="e08d7-291">Nella finestra di dialogo di conferma dell'Importazione guidata certificati fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-291">In the Certificate Import Wizard confirmation dialog box, click **OK**.</span></span>  
  
    6.  <span data-ttu-id="e08d7-292">Chiudere la finestra di dialogo **Certificato** .</span><span class="sxs-lookup"><span data-stu-id="e08d7-292">Close the **Certificate** dialog box.</span></span>  
  
    7.  <span data-ttu-id="e08d7-293">Nella finestra di dialogo **Avviso di sicurezza** fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-293">In the **Security Alert** dialog box, click **Yes**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e08d7-294">I certificati vengono installati per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e08d7-294">Certificates are installed for users.</span></span> <span data-ttu-id="e08d7-295">Questo processo deve pertanto essere eseguito per ogni utente che eseguirà la sincronizzazione con IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-295">This process must be performed for each user that will synchronize with IIS.</span></span>  
  
4.  <span data-ttu-id="e08d7-296">Nella finestra di dialogo **Connetti a \<ServerName>** specificare l'account di accesso e la password che verranno utilizzati dall'agente di merge per la connessione a IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-296">In the **Connect to \<ServerName>** dialog box, specify the login and password that the Merge Agent will use to connect to IIS.</span></span> <span data-ttu-id="e08d7-297">Queste credenziali verranno inoltre specificate nella Creazione guidata nuova sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="e08d7-297">These credentials will also be specified in the New Subscription Wizard.</span></span>  
  
5.  <span data-ttu-id="e08d7-298">Nella finestra di Internet Explorer denominata **Informazioni diagnostica SQL Websync**, verificare che il valore contenuto in ogni colonna **Stato** della pagina sia **SUCCESS**.</span><span class="sxs-lookup"><span data-stu-id="e08d7-298">In the Internet Explorer window called **SQL Websync diagnostic information**, verify that the value in each **Status** column on the page is **SUCCESS**.</span></span>  
  
6.  <span data-ttu-id="e08d7-299">Assicurarsi che il certificato sia installato correttamente nel Sottoscrittore:</span><span class="sxs-lookup"><span data-stu-id="e08d7-299">Make sure that the certificate is installed correctly on the Subscriber:</span></span>  
  
    1.  <span data-ttu-id="e08d7-300">Chiudere e riaprire Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e08d7-300">Close and then reopen Internet Explorer.</span></span>  
  
    2.  <span data-ttu-id="e08d7-301">Connettersi al server in modalità diagnostica.</span><span class="sxs-lookup"><span data-stu-id="e08d7-301">Connect to the server in diagnostic mode.</span></span> <span data-ttu-id="e08d7-302">Se il certificato è stato installato correttamente, la finestra di dialogo **Avviso di sicurezza** non verrà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="e08d7-302">If the certificate is installed properly, the **Security Alert** dialog box will not appear.</span></span> <span data-ttu-id="e08d7-303">Se la finestra di dialogo viene visualizzata, i tentativi dell'agente di merge di connettersi al computer che esegue IIS avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e08d7-303">If the dialog box appears, the Merge Agent will fail when it tries to connect to the computer that is running IIS.</span></span> <span data-ttu-id="e08d7-304">È necessario verificare che il certificato per il server a cui si accede sia stato aggiunto all'archivio certificati del Sottoscrittore come certificato attendibile.</span><span class="sxs-lookup"><span data-stu-id="e08d7-304">You must make sure that the certificate for the server that you are accessing has been added to the certificate store at the Subscriber as a trusted certificate.</span></span> <span data-ttu-id="e08d7-305">Per ulteriori informazioni sull'esportazione dei certificati, vedere la documentazione di IIS.</span><span class="sxs-lookup"><span data-stu-id="e08d7-305">For more information about exporting certificates, see the IIS documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e08d7-306">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e08d7-306">See Also</span></span>  
 <span data-ttu-id="e08d7-307">[Sincronizzazione Web per la replica di tipo merge](web-synchronization-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="e08d7-307">[Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="e08d7-308">Configurare la sincronizzazione Web</span><span class="sxs-lookup"><span data-stu-id="e08d7-308">Configure Web Synchronization</span></span>](configure-web-synchronization.md)  
  
  
