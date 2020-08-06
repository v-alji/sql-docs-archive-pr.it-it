---
title: Extensible Key Management tramite l'insieme di credenziali delle chiavi di Azure (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- EKM, with key vault
- TDE, EKM and key vault
- Extensible Key Management with key vault
- Key Management with key vault
- Transparent Data Encryption, using EKM and key vault
ms.assetid: 3efdc48a-8064-4ea6-a828-3fbf758ef97c
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 0e4bbc4f0c371c927988e6b91fdbf47307ad9d3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726852"
---
# <a name="extensible-key-management-using-azure-key-vault-sql-server"></a><span data-ttu-id="904f9-102">Extensible Key Management tramite l'insieme di credenziali delle chiavi di Azure (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="904f9-102">Extensible Key Management Using Azure Key Vault (SQL Server)</span></span>
  <span data-ttu-id="904f9-103">Il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] connettore per [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault consente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] la crittografia per sfruttare il servizio Azure Key Vault come provider di [gestione delle chiavi estendibile &#40;EKM&#41;](extensible-key-management-ekm.md) per proteggere le chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="904f9-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to leverage the Azure Key Vault service as an [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) provider to protect its encryption keys.</span></span>

 <span data-ttu-id="904f9-104">Contenuto dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="904f9-104">Included in this topic:</span></span>

-   [<span data-ttu-id="904f9-105">Utilizzi di EKM</span><span class="sxs-lookup"><span data-stu-id="904f9-105">Uses of EKM</span></span>](#Uses)

-   [<span data-ttu-id="904f9-106">Passaggio 1: Configurazione dell'insieme di credenziali delle chiavi per l'uso da parte di SQL Server</span><span class="sxs-lookup"><span data-stu-id="904f9-106">Step 1: Setting up the Key Vault for use by SQL Server</span></span>](#Step1)

-   [<span data-ttu-id="904f9-107">Passaggio 2: Installazione di SQL Server Connector</span><span class="sxs-lookup"><span data-stu-id="904f9-107">Step 2: Installing the SQL Server Connector</span></span>](#Step2)

-   [<span data-ttu-id="904f9-108">Passaggio 3: Configurare SQL Server per l'uso di un provider EKM per l'insieme di credenziali delle chiavi</span><span class="sxs-lookup"><span data-stu-id="904f9-108">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>](#Step3)

-   [<span data-ttu-id="904f9-109">Esempio A: Transparent Data Encryption tramite una chiave asimmetrica dell'insieme di credenziali delle chiavi</span><span class="sxs-lookup"><span data-stu-id="904f9-109">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleA)

-   [<span data-ttu-id="904f9-110">Esempio B: Crittografia dei backup tramite una chiave asimmetrica dell'insieme di credenziali delle chiavi</span><span class="sxs-lookup"><span data-stu-id="904f9-110">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleB)

-   [<span data-ttu-id="904f9-111">Esempio C: Crittografia a livello di colonna tramite una chiave asimmetrica dell'insieme di credenziali delle chiavi</span><span class="sxs-lookup"><span data-stu-id="904f9-111">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleC)

##  <a name="uses-of-ekm"></a><a name="Uses"></a><span data-ttu-id="904f9-112">Utilizzi di EKM</span><span class="sxs-lookup"><span data-stu-id="904f9-112">Uses of EKM</span></span>
 <span data-ttu-id="904f9-113">Un'organizzazione può usare la crittografia di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per proteggere i dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="904f9-113">An organization can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to protect sensitive data.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="904f9-114">la crittografia include [Transparent Data Encryption &#40;&#41;](transparent-data-encryption.md)Transparent Data Encryption, [crittografia a livello di colonna](/sql/t-sql/functions/cryptographic-functions-transact-sql) (CLE) e crittografia dei [backup](../../backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="904f9-114">encryption includes [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md), [Column Level Encryption](/sql/t-sql/functions/cryptographic-functions-transact-sql) (CLE), and [Backup Encryption](../../backup-restore/backup-encryption.md).</span></span> <span data-ttu-id="904f9-115">In tutti questi casi, i dati vengono crittografati tramite una chiave DEK simmetrica.</span><span class="sxs-lookup"><span data-stu-id="904f9-115">In all of these cases the data is encrypted using a symmetric data encryption key.</span></span> <span data-ttu-id="904f9-116">Per proteggerla ulteriormente, tale chiave viene crittografata con una gerarchia di chiavi archiviate in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="904f9-116">The symmetric data encryption key is further protected by encrypting it with a hierarchy of keys stored in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="904f9-117">In alternativa, l'architettura del provider EKM consente a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] di proteggere le chiavi DEK tramite una chiave asimmetrica archiviata all'esterno di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in un provider del servizio di crittografia esterno.</span><span class="sxs-lookup"><span data-stu-id="904f9-117">Alternatively, the EKM provider architecture enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to protect the data encryption keys by using an asymmetric key stored outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in an external cryptographic provider.</span></span> <span data-ttu-id="904f9-118">L'utilizzo dell'architettura del provider EKM aggiunge un ulteriore livello di sicurezza consentendo alle organizzazioni di separare la gestione delle chiavi e dei dati.</span><span class="sxs-lookup"><span data-stu-id="904f9-118">Using EKM provider architecture adds an additional layer of security and allows organizations to separate the management of keys and data.</span></span>

 <span data-ttu-id="904f9-119">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector per l'insieme di credenziali delle chiavi di Azure consente a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] di sfruttare il servizio dell'insieme di credenziali delle chiavi scalabile, ad alte prestazioni e a disponibilità elevata come provider EKM per la protezione delle chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="904f9-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for Azure Key Vault lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] leverage the scalable, high performance, and highly available key vault service as an EKM provider for encryption key protection.</span></span> <span data-ttu-id="904f9-120">Il servizio dell'insieme di credenziali delle chiavi può essere usato con le installazioni di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nelle macchine virtuali di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] e per i server locali.</span><span class="sxs-lookup"><span data-stu-id="904f9-120">The key vault service can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installations on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Virtual Machines and for on-premises servers.</span></span> <span data-ttu-id="904f9-121">Il servizio dell'insieme di credenziali delle chiavi consente inoltre di usare i moduli di protezione hardware (HSM) controllati e monitorati rigorosamente per un livello di protezione maggiore per le chiavi di crittografia asimmetriche.</span><span class="sxs-lookup"><span data-stu-id="904f9-121">The key vault service also provides the option to use tightly controlled and monitored Hardware Security Modules (HSMs) for a higher level of protection for asymmetric encryption keys.</span></span> <span data-ttu-id="904f9-122">Per altre informazioni sull'insieme di credenziali delle chiavi, vedere [Insieme di credenziali delle chiavi di Azure](https://go.microsoft.com/fwlink/?LinkId=521401).</span><span class="sxs-lookup"><span data-stu-id="904f9-122">For more information about the key vault, see [Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521401).</span></span>

 <span data-ttu-id="904f9-123">L'immagine seguente illustra il flusso di processo di EKM con l'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-123">The following image summarizes the process flow of EKM using the key vault.</span></span> <span data-ttu-id="904f9-124">I numeri dei passaggi del processo nell'immagine non sono concepiti per corrispondere ai numeri dei passaggi della configurazione riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="904f9-124">The process step numbers in the image are not meant to match the setup step numbers that follow the image.</span></span>

 <span data-ttu-id="904f9-125">![EKM di SQL Server con Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "EKM di SQL Server con Azure Key Vault")</span><span class="sxs-lookup"><span data-stu-id="904f9-125">![SQL Server EKM using the Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "SQL Server EKM using the Azure Key Vault")</span></span>

##  <a name="step-1-set-up-the-key-vault-for-use-by-sql-server"></a><a name="Step1"></a><span data-ttu-id="904f9-126">Passaggio 1: configurare la Key Vault per l'uso da parte di SQL Server</span><span class="sxs-lookup"><span data-stu-id="904f9-126">Step 1: Set up the Key Vault for use by SQL Server</span></span>
 <span data-ttu-id="904f9-127">Completare i passaggi seguenti per configurare un insieme di credenziali delle chiavi da usare con il [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] per la protezione delle chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="904f9-127">Use the following steps to set up a key vault for use with the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] for encryption key protection.</span></span> <span data-ttu-id="904f9-128">È possibile che per l'organizzazione sia già in uso un insieme di credenziali.</span><span class="sxs-lookup"><span data-stu-id="904f9-128">A vault may already be in use for the organization.</span></span> <span data-ttu-id="904f9-129">Se non esiste un insieme di credenziali, l'amministratore di Azure incaricato della gestione delle chiavi di crittografia può creare un insieme di credenziali, generare una chiave asimmetrica nell'insieme di credenziali e quindi autorizzare [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a usare la chiave.</span><span class="sxs-lookup"><span data-stu-id="904f9-129">When a vault does not exist, the Azure Administrator in your organization that is designated to manage encryption keys can create a vault, generate an asymmetric key in the vault, and then authorize [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use the key.</span></span> <span data-ttu-id="904f9-130">Per acquisire familiarità con il servizio dell'insieme di credenziali delle chiavi, consultare [Introduzione all'insieme di credenziali delle chiavi di Azure](https://go.microsoft.com/fwlink/?LinkId=521402)e il riferimento di PowerShell [Cmdlet per l'insieme di credenziali delle chiavi di Azure](https://docs.microsoft.com/powershell/module/azurerm.keyvault) .</span><span class="sxs-lookup"><span data-stu-id="904f9-130">To familiarize yourself with the key vault service review [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402), and the PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="904f9-131">Se sono disponibili più sottoscrizioni di Azure, è necessario usare la sottoscrizione contenente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="904f9-131">If you have multiple Azure subscriptions, you must use the subscription that contains [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

1.  <span data-ttu-id="904f9-132">**Creare un insieme di credenziali:** creare un insieme di credenziali seguendo le istruzioni presenti nella sezione **Creare un insieme di credenziali delle chiavi** dell'articolo [Introduzione all'insieme di credenziali delle chiavi di Azure](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="904f9-132">**Create a vault:** Create a vault by using the instructions in the **Create a key vault** section of [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="904f9-133">Registrare il nome dell'insieme di credenziali.</span><span class="sxs-lookup"><span data-stu-id="904f9-133">Record the name of the vault.</span></span> <span data-ttu-id="904f9-134">Questo argomento usa **ContosoKeyVault** come nome dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-134">This topic uses **ContosoKeyVault** as the key vault name.</span></span>

2.  <span data-ttu-id="904f9-135">**Generare una chiave asimmetrica nell'insieme di credenziali:** la chiave asimmetrica nell'insieme di credenziali delle chiavi viene usata per proteggere le chiavi di crittografia di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="904f9-135">**Generate an asymmetric key in the vault:** The asymmetric key in the key vault is used to protect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption keys.</span></span> <span data-ttu-id="904f9-136">Solo la parte pubblica della chiave asimmetrica lascia sempre l'insieme di credenziali, la parte privata non viene mai esportata dall'insieme di credenziali.</span><span class="sxs-lookup"><span data-stu-id="904f9-136">Only the public portion of the asymmetric key ever leaves the vault, the private portion is never exported by the vault.</span></span> <span data-ttu-id="904f9-137">Tutte le operazioni crittografiche che usano la chiave asimmetrica vengono delegate all'insieme di credenziali delle chiavi di Azure e sono protette dalla sicurezza dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-137">All cryptographic operations using the asymmetric key are delegated to the Azure Key Vault, and are protected by the key vault security.</span></span>

     <span data-ttu-id="904f9-138">Esistono diversi modi per generare una chiave asimmetrica e archiviarla nell'insieme di credenziali.</span><span class="sxs-lookup"><span data-stu-id="904f9-138">There are several ways that you can generate an asymmetric key and store it in the vault.</span></span> <span data-ttu-id="904f9-139">È possibile generare una chiave esternamente e importarla nell'insieme di credenziali come file con estensione pfx</span><span class="sxs-lookup"><span data-stu-id="904f9-139">You can externally generate a key, and import the key into the vault as a .pfx file.</span></span> <span data-ttu-id="904f9-140">oppure creare la chiave direttamente nell'insieme di credenziali mediante le API dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-140">Or create the key directly in the vault by using the key vault APIs.</span></span>

     <span data-ttu-id="904f9-141">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector richiede che le chiavi asimmetriche siano di tipo RSA a 2048 bit e il nome della chiave può usare solo i caratteri "a-z", "A-Z", "0-9" e "-".</span><span class="sxs-lookup"><span data-stu-id="904f9-141">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector requires the asymmetric keys to be 2048-bit RSA, and the key name can only use the characters "a-z", "A-Z", "0-9", and "-".</span></span> <span data-ttu-id="904f9-142">In questo documento il nome della chiave asimmetrica viene definito **ContosoMasterKey**.</span><span class="sxs-lookup"><span data-stu-id="904f9-142">In this document the name of the asymmetric key is referred to as **ContosoMasterKey**.</span></span> <span data-ttu-id="904f9-143">Sostituire questo nome con il nome univoco da usare per la chiave.</span><span class="sxs-lookup"><span data-stu-id="904f9-143">Replace this with the unique name you use for the key.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="904f9-144">L'importazione della chiave asimmetrica è consigliata per gli scenari di produzione in quanto consente all'amministratore di depositare la chiave in un sistema di deposito delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-144">Importing the asymmetric key is highly recommended for production scenarios because it allows the administrator to escrow the key in a key escrow system.</span></span> <span data-ttu-id="904f9-145">Se la chiave asimmetrica viene creata nell'insieme di credenziali, non potrà essere depositata perché la chiave privata non può mai lasciare l'insieme di credenziali.</span><span class="sxs-lookup"><span data-stu-id="904f9-145">If the asymmetric key is created in the vault, it cannot be escrowed because the private key can never leave the vault.</span></span> <span data-ttu-id="904f9-146">È consigliabile depositare le chiavi usate per proteggere i dati critici.</span><span class="sxs-lookup"><span data-stu-id="904f9-146">Keys used to protect critical data should be escrowed.</span></span> <span data-ttu-id="904f9-147">Se si perde una chiave asimmetrica, non sarà più possibile recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="904f9-147">The loss of an asymmetric key will result in permanently unrecoverable data.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="904f9-148">L'insieme di credenziali delle chiavi supporta più versioni della stessa chiave denominata.</span><span class="sxs-lookup"><span data-stu-id="904f9-148">The key vault supports multiple versions of the same named key.</span></span> <span data-ttu-id="904f9-149">È consigliabile non eseguire il controllo delle versioni né il rollback delle chiavi che vengono usate da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector.</span><span class="sxs-lookup"><span data-stu-id="904f9-149">Keys to be used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector should not be versioned or rolled.</span></span> <span data-ttu-id="904f9-150">Se l'amministratore vuole eseguire il rollback della chiave usata per la crittografia di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , sarà necessario creare una nuova chiave con un nome diverso nell'insieme di credenziali e usarla per crittografare la chiave DEK.</span><span class="sxs-lookup"><span data-stu-id="904f9-150">If the administrator wants to roll the key used for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption, a new key with a different name should be created in the vault and used to encrypt the DEK.</span></span>

     <span data-ttu-id="904f9-151">Per altre informazioni su come importare una chiave nell'insieme di credenziali delle chiavi o creare una chiave nell'insieme di credenziali delle chiavi (non consigliato per un ambiente di produzione), vedere la sezione **Aggiungere una chiave o un segreto nell'insieme di credenziali delle chiavi** in [Introduzione all'insieme di credenziali delle chiavi di Azure](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="904f9-151">For more information on how to import a key into the key vault or to create a key in the key vault (not recommended for a production environment), see the **Add a key or secret to the key vault** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

3.  <span data-ttu-id="904f9-152">**Ottenere le entità servizio di Azure Active Directory da usare per SQL Server:** quando l'organizzazione esegue la registrazione per un servizio cloud Microsoft, ottiene un'istanza di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="904f9-152">**Get Azure Active Directory Service Principals to use for SQL Server:** When the organization signs up for a Microsoft cloud service, it gets an Azure Active Directory.</span></span> <span data-ttu-id="904f9-153">Creare le **entità servizio** nell'istanza di Azure Active Directory per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (per l'autenticazione in Azure Active Directory) per l'accesso all'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-153">Create **Service Principals** in the Azure Active Directory for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use (to authenticate itself to Azure Active Directory) while accessing the key vault.</span></span>

    -   <span data-ttu-id="904f9-154">Un' **entità servizio** sarà necessaria per consentire a un amministratore di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] di accedere all'insieme di credenziali per configurare [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in modo da usare la crittografia.</span><span class="sxs-lookup"><span data-stu-id="904f9-154">One **Service Principal** will be needed by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator to access the vault while configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use encryption.</span></span>

    -   <span data-ttu-id="904f9-155">Un'altra **entità servizio** sarà necessaria per consentire al [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] di accedere all'insieme di credenziali per eseguire l'operazione unwrap per le chiavi usate nella crittografia di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="904f9-155">Another **Service Principal** will be needed by the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] to access the vault for unwrapping keys used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

     <span data-ttu-id="904f9-156">Per altre informazioni su come registrare un'applicazione e generare un'entità servizio, vedere la sezione **Registrare un'applicazione con Azure Active Directory** in [Introduzione all'insieme di credenziali delle chiavi di Azure](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="904f9-156">For more information about how to register an application and generate a service principal, see the **Register an Application with Azure Active Directory** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="904f9-157">Il processo di registrazione restituisce un **ID applicazione** (noto anche come **ID CLIENT**) e una **Chiave di autenticazione** (nota anche come **Segreto**) per ogni **entità servizio**di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="904f9-157">The registration process returns an **Application ID** (also known as a **CLIENT ID**) and a **Authentication Key** (also known as a **Secret**) for each Azure Active Directory **Service Principal**.</span></span> <span data-ttu-id="904f9-158">Se utilizzata nell' `CREATE CREDENTIAL` istruzione, il trattino deve essere rimosso dall' **ID client**.</span><span class="sxs-lookup"><span data-stu-id="904f9-158">When used in the `CREATE CREDENTIAL` statement, the hyphen must be removed from the **CLIENT ID**.</span></span> <span data-ttu-id="904f9-159">Registrare questi valori da usare negli script seguenti:</span><span class="sxs-lookup"><span data-stu-id="904f9-159">Record these for use in the scripts below:</span></span>

    -   <span data-ttu-id="904f9-160">**Entità servizio** per un account di accesso **sysadmin** : **CLIENTID_sysadmin_login** e **SECRET_sysadmin_login**</span><span class="sxs-lookup"><span data-stu-id="904f9-160">**Service Principal** for a **sysadmin** login: **CLIENTID_sysadmin_login** and **SECRET_sysadmin_login**</span></span>

    -   <span data-ttu-id="904f9-161">**Entità servizio** per il [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** e **SECRET_DBEngine**.</span><span class="sxs-lookup"><span data-stu-id="904f9-161">**Service Principal** for the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** and **SECRET_DBEngine**.</span></span>

4.  <span data-ttu-id="904f9-162">**Concedere le autorizzazioni per le entità servizio per accedere al Key Vault:** Per le entità **CLIENTID_sysadmin_login** e **CLIENTID_DBEngineService** sono necessarie le **autorizzazioni Get**, **List**, **wrapKey**e **unwrapKey** nell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-162">**Grant Permission for the Service Principals to access the Key Vault:** Both the **CLIENTID_sysadmin_login** and **CLIENTID_DBEngineService Principals** require the **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span> <span data-ttu-id="904f9-163">Se si intende creare chiavi tramite [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , è necessario concedere anche l'autorizzazione **create** nell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-163">If you intend to create keys through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] you also need to grant the **create** permission in key vault.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="904f9-164">Gli utenti devono avere almeno le operazioni **wrapKey** e **unwrapKey** per l'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-164">Users must have at least the **wrapKey** and **unwrapKey** operations for the key vault.</span></span>

     <span data-ttu-id="904f9-165">Per altre informazioni sulla concessione delle autorizzazioni all'insieme di credenziali, vedere la sezione **Autorizzare l'applicazione a usare la chiave o il segreto** in [Introduzione all'insieme di credenziali delle chiavi di Azure](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="904f9-165">For more information about granting permissions to the vault, see the **Authorize the application to use the key or secret** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

     <span data-ttu-id="904f9-166">Collegamenti alla documentazione dell'insieme di credenziali delle chiavi di Azure</span><span class="sxs-lookup"><span data-stu-id="904f9-166">Links to Azure Key Vault documentation</span></span>

    -   [<span data-ttu-id="904f9-167">Cos'è l'insieme di credenziali chiave di Azure?</span><span class="sxs-lookup"><span data-stu-id="904f9-167">What is Azure Key Vault?</span></span>](https://go.microsoft.com/fwlink/?LinkId=521401)

    -   [<span data-ttu-id="904f9-168">Introduzione all'insieme di credenziali delle chiavi di Azure</span><span class="sxs-lookup"><span data-stu-id="904f9-168">Get Started with Azure Key Vault</span></span>](https://go.microsoft.com/fwlink/?LinkId=521402)

    -   <span data-ttu-id="904f9-169">Riferimento di PowerShell [Cmdlet per l'insieme di credenziali delle chiavi di Azure](https://docs.microsoft.com/powershell/module/azurerm.keyvault)</span><span class="sxs-lookup"><span data-stu-id="904f9-169">PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference</span></span>

##  <a name="step-2-install-the-sql-server-connector"></a><a name="Step2"></a><span data-ttu-id="904f9-170">Passaggio 2: installare il Connettore SQL Server</span><span class="sxs-lookup"><span data-stu-id="904f9-170">Step 2: Install the SQL Server Connector</span></span>
 <span data-ttu-id="904f9-171">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector viene scaricato e installato dall'amministratore del computer in cui è in esecuzione [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="904f9-171">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is downloaded and installed by the administrator of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="904f9-172">È possibile scaricare [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector dalla pagina [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=521700).</span><span class="sxs-lookup"><span data-stu-id="904f9-172">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is available as a download from the [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=521700).</span></span>  <span data-ttu-id="904f9-173">Cercare **SQL Server Connector per l'insieme di credenziali delle chiavi di Microsoft Azure**, esaminare i dettagli, i requisiti di sistema e le istruzioni di installazione e scegliere di scaricare il connettore e avviare l'installazione con il pulsante **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="904f9-173">Search for **SQL Server Connector for Microsoft Azure Key Vault**, review the details, system requirements and install instructions and choose to download the connector and start the installation using **Run**.</span></span> <span data-ttu-id="904f9-174">Esaminare la licenza e accettarne le condizioni, quindi continuare.</span><span class="sxs-lookup"><span data-stu-id="904f9-174">Review the license and accept the license and continue.</span></span>

 <span data-ttu-id="904f9-175">Per impostazione predefinita, il connettore viene installato in **C:\Program \Programmi\sql Server Connector per Microsoft Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="904f9-175">By default the connector is installed at **C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault**.</span></span> <span data-ttu-id="904f9-176">Questo percorso può essere modificato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="904f9-176">This location can be changed during setup.</span></span> <span data-ttu-id="904f9-177">Se si modifica il percorso, apportare la modifica negli script riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="904f9-177">(If changed, adjust the scripts below.)</span></span>

 <span data-ttu-id="904f9-178">Dopo aver completato l'installazione, nel computer vengono installati gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="904f9-178">On completing the install, the following are installed on the machine:</span></span>

-   <span data-ttu-id="904f9-179">**Microsoft.AzureKeyVaultService.EKM.dll**: si tratta della DLL del provider di crittografia EKM che deve essere registrata con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante l'istruzione CREATE CRYPTOGRAPHIC PROVIDER.</span><span class="sxs-lookup"><span data-stu-id="904f9-179">**Microsoft.AzureKeyVaultService.EKM.dll**: This is the cryptographic EKM provider DLL that needs to be registered with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the CREATE CRYPTOGRAPHIC PROVIDER statement.</span></span>

-   <span data-ttu-id="904f9-180">**SQL Server Connector per l'insieme di credenziali delle chiavi di Azure**: si tratta di un servizio di Windows che consente al provider di crittografia EKM di comunicare con l'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-180">**Azure Key Vault SQL Server Connector**: This is a Windows service that enables the cryptographic EKM provider to communicate with the key vault.</span></span>

 <span data-ttu-id="904f9-181">L'installazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector consente anche di scaricare facoltativamente gli script di esempio per la crittografia di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="904f9-181">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector installation also allows you to optionally download sample scripts for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

##  <a name="step-3-configure-sql-server-to-use-an-ekm-provider-for-the-key-vault"></a><a name="Step3"></a><span data-ttu-id="904f9-182">Passaggio 3: configurare SQL Server per l'uso di un provider EKM per il Key Vault</span><span class="sxs-lookup"><span data-stu-id="904f9-182">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>

###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="904f9-183">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="904f9-183">Permissions</span></span>
 <span data-ttu-id="904f9-184">Per completare l'intero processo è necessaria l'autorizzazione CONTROL SERVER o l'appartenenza al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="904f9-184">To complete this entire process requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span> <span data-ttu-id="904f9-185">Le azioni specifiche richiedono le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="904f9-185">Specific actions require the following permissions:</span></span>

-   <span data-ttu-id="904f9-186">Per creare un provider di crittografia è necessaria l'autorizzazione CONTROL SERVER o l'appartenenza al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="904f9-186">To create a cryptographic provider, requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span>

-   <span data-ttu-id="904f9-187">Per modificare un'opzione di configurazione ed eseguire l'istruzione RECONFIGURE, è necessario disporre dell'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="904f9-187">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="904f9-188">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="904f9-188">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>

-   <span data-ttu-id="904f9-189">Per creare le credenziali, è necessaria l'autorizzazione ALTER ANY CREDENTIAL.</span><span class="sxs-lookup"><span data-stu-id="904f9-189">To create a credential, requires ALTER ANY CREDENTIAL permission.</span></span>

-   <span data-ttu-id="904f9-190">Per aggiungere le credenziali per un account di accesso, è necessaria l'autorizzazione ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="904f9-190">To add a credential to a login, requires ALTER ANY LOGIN permission.</span></span>

-   <span data-ttu-id="904f9-191">Per creare una chiave asimmetrica, è necessaria l'autorizzazione CREATE ASYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="904f9-191">To create an asymmetric key, requires CREATE ASYMMETRIC KEY permission.</span></span>

###  <a name="to-configure-sql-server-to-use-a-cryptographic-provider"></a><a name="TsqlProcedure"></a><span data-ttu-id="904f9-192">Per configurare SQL Server per l'utilizzo di un provider di crittografia</span><span class="sxs-lookup"><span data-stu-id="904f9-192">To configure SQL Server to use a cryptographic provider</span></span>

1.  <span data-ttu-id="904f9-193">Configurare il [!INCLUDE[ssDE](../../../includes/ssde-md.md)] per usare EKM e registrare (creare) il provider di crittografia con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="904f9-193">Configure the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use EKM, and register (create) the cryptographic provider with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

    ```sql
    -- Enable advanced options.
    USE master;
    GO

    sp_configure 'show advanced options', 1 ;
    GO
    RECONFIGURE ;
    GO
    -- Enable EKM provider
    sp_configure 'EKM provider enabled', 1 ;
    GO
    RECONFIGURE ;
    GO

    -- Create a cryptographic provider, using the SQL Server Connector
    -- which is an EKM provider for the Azure Key Vault. This example uses 
    -- the name AzureKeyVault_EKM_Prov.

    CREATE CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov 
    FROM FILE = 'C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault\Microsoft.AzureKeyVaultService.EKM.dll';
    GO
    ```

2.  <span data-ttu-id="904f9-194">Configurare le credenziali di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per un account di accesso di amministratore di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per usare l'insieme di credenziali delle chiavi in modo da configurare e gestire gli scenari di crittografia di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="904f9-194">Setup a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator login to use the key vault in order to setup and manage [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption scenarios.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="904f9-195">L'argomento **Identity** di richiede il nome dell'insieme di credenziali delle `CREATE CREDENTIAL` chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-195">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="904f9-196">L'argomento **Secret** di `CREATE CREDENTIAL` richiede *\<Client ID>* (senza trattini) e *\<Secret>* da passare insieme senza uno spazio tra di essi.</span><span class="sxs-lookup"><span data-stu-id="904f9-196">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="904f9-197">Nell'esempio seguente l' **ID client** ( `EF5C8E09-4D2A-4A76-9998-D93440D8115D` ) viene rimosso dai trattini e viene immesso come stringa `EF5C8E094D2A4A769998D93440D8115D` e il **segreto** è rappresentato dalla stringa *SECRET_sysadmin_login*.</span><span class="sxs-lookup"><span data-stu-id="904f9-197">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_sysadmin_login*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL sysadmin_ekm_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_sysadmin_login' 
    FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;

    -- Add the credential to the SQL Server administrators domain login 
    ALTER LOGIN [<domain>/<login>]
    ADD CREDENTIAL sysadmin_ekm_cred;
    ```

     <span data-ttu-id="904f9-198">Per un esempio dell'uso delle variabili per gli `CREATE CREDENTIAL` argomenti e della rimozione dei trattini dall'ID client a livello di codice, vedere [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="904f9-198">For an example of using variables for the `CREATE CREDENTIAL` arguments and programmatically removing the hyphens from the Client ID, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>

3.  <span data-ttu-id="904f9-199">Se è stata importata una chiave asimmetrica come descritto in precedenza nella sezione 3 del passaggio 1, aprire la chiave, fornendo il nome della chiave nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="904f9-199">If you imported an asymmetric key as described earlier in step 1, section 3, open the key by providing your key name in the following example.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
    CREATION_DISPOSITION = OPEN_EXISTING;
    ```

     <span data-ttu-id="904f9-200">Sebbene non consigliabile per un ambiente di produzione (perché la chiave non può essere esportata), è possibile creare una chiave asimmetrica direttamente nell'insieme di credenziali da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="904f9-200">Though not recommended for production (because the key cannot be exported), it is possible to create an asymmetric key directly in the vault from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="904f9-201">Se in precedenza non è stata importata alcuna chiave, creare una chiave asimmetrica nell'insieme di credenziali delle chiavi ai fini del test usando lo script seguente.</span><span class="sxs-lookup"><span data-stu-id="904f9-201">If you did not import a key earlier, then create an asymmetric key in the key vault for testing by using the following script.</span></span> <span data-ttu-id="904f9-202">Eseguire lo script, usando un account di accesso di cui è stato effettuato il provisioning con le credenziali **sysadmin_ekm_cred** .</span><span class="sxs-lookup"><span data-stu-id="904f9-202">Execute the script, using a login provisioned with the **sysadmin_ekm_cred** credential.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH ALGORITHM = RSA_2048,
    PROVIDER_KEY_NAME = 'ContosoMasterKey';
    ```

> [!TIP]
>  <span data-ttu-id="904f9-203">Gli utenti che ricevono l'errore **Non è stato possibile esportare la chiave pubblica dal provider. Codice di errore del provider: 2053.**</span><span class="sxs-lookup"><span data-stu-id="904f9-203">Users receiving the error **Cannot export public key from the provider. Provider error code: 2053.**</span></span> <span data-ttu-id="904f9-204">devono verificare le autorizzazioni **get**, **list**, **wrapKey**e **unwrapKey** nell'insieme di credenziali della chiave.</span><span class="sxs-lookup"><span data-stu-id="904f9-204">should check their **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span>

 <span data-ttu-id="904f9-205">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="904f9-205">For more information, see the following:</span></span>

-   [<span data-ttu-id="904f9-206">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="904f9-206">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)

-   [<span data-ttu-id="904f9-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="904f9-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)

-   [<span data-ttu-id="904f9-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="904f9-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)

-   [<span data-ttu-id="904f9-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="904f9-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)

-   [<span data-ttu-id="904f9-210">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="904f9-210">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)

-   [<span data-ttu-id="904f9-211">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="904f9-211">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)

## <a name="examples"></a><span data-ttu-id="904f9-212">Esempi</span><span class="sxs-lookup"><span data-stu-id="904f9-212">Examples</span></span>

###  <a name="example-a-transparent-data-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleA"></a><span data-ttu-id="904f9-213">Esempio A: Transparent Data Encryption usando una chiave asimmetrica della Key Vault</span><span class="sxs-lookup"><span data-stu-id="904f9-213">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="904f9-214">Dopo aver completato i passaggi precedenti, creare le credenziali e un account di accesso e quindi creare una chiave di crittografia del database protetta dalla chiave asimmetrica nell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-214">After completing the steps above, create a credential and a login, create a database encryption key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="904f9-215">Usare la chiave di crittografia del database per crittografare un database con TDE.</span><span class="sxs-lookup"><span data-stu-id="904f9-215">Use the database encryption key to encrypt a database with TDE.</span></span>

 <span data-ttu-id="904f9-216">Per crittografare un database è necessaria l'autorizzazione CONTROL per il database.</span><span class="sxs-lookup"><span data-stu-id="904f9-216">To encrypt a database requires CONTROL permission on the database.</span></span>

##### <a name="to-enable-tde-using-ekm-and-the-key-vault"></a><span data-ttu-id="904f9-217">Per abilitare TDE tramite EKM e l'insieme di credenziali delle chiavi</span><span class="sxs-lookup"><span data-stu-id="904f9-217">To enable TDE using EKM and the Key Vault</span></span>

1.  <span data-ttu-id="904f9-218">Creare le credenziali di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per il [!INCLUDE[ssDE](../../../includes/ssde-md.md)] da usare per l'accesso a EKM con l'insieme di credenziali delle chiavi durante il caricamento del database.</span><span class="sxs-lookup"><span data-stu-id="904f9-218">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use when accessing the key vault EKM during database load.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="904f9-219">L'argomento **Identity** di richiede il nome dell'insieme di credenziali delle `CREATE CREDENTIAL` chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-219">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="904f9-220">L'argomento **Secret** di `CREATE CREDENTIAL` richiede *\<Client ID>* (senza trattini) e *\<Secret>* da passare insieme senza uno spazio tra di essi.</span><span class="sxs-lookup"><span data-stu-id="904f9-220">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="904f9-221">Nell'esempio seguente l' **ID client** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) viene immesso con tutti i trattini rimossi come stringa `EF5C8E094D2A4A769998D93440D8115D` e il **Segreto** è rappresentato dalla stringa *SECRET_DBEngine*.</span><span class="sxs-lookup"><span data-stu-id="904f9-221">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_DBEngine*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL Azure_EKM_TDE_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_DBEngine' 
        FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;
    ```

2.  <span data-ttu-id="904f9-222">Creare un account di accesso di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] che verrà usato dal [!INCLUDE[ssDE](../../../includes/ssde-md.md)] per TDE e aggiungervi le credenziali.</span><span class="sxs-lookup"><span data-stu-id="904f9-222">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login to be used by the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] for TDE, and add the credential to it.</span></span> <span data-ttu-id="904f9-223">Questo esempio usa la chiave asimmetrica CONTOSO_KEY archiviata nell'insieme di credenziali delle chiavi importato o creato in precedenza per il database master, come sopra descritto nella [sezione 3 del passaggio 3](#Step3) .</span><span class="sxs-lookup"><span data-stu-id="904f9-223">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier for the master database, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE master;
    -- Create a SQL Server login associated with the asymmetric key 
    -- for the Database engine to use when it loads a database 
    -- encrypted by TDE.
    CREATE LOGIN TDE_Login 
    FROM ASYMMETRIC KEY CONTOSO_KEY;
    GO 

    -- Alter the TDE Login to add the credential for use by the 
    -- Database Engine to access the key vault
    ALTER LOGIN TDE_Login 
    ADD CREDENTIAL Azure_EKM_TDE_cred ;
    GO
    ```

3.  <span data-ttu-id="904f9-224">Creare la chiave di crittografia del database (DEK) che verrà usata per TDE.</span><span class="sxs-lookup"><span data-stu-id="904f9-224">Create the database encryption key (DEK) that will be used for TDE.</span></span> <span data-ttu-id="904f9-225">La chiave DEK può essere creata usando qualsiasi algoritmo supportato da SQL Server o la lunghezza della chiave.</span><span class="sxs-lookup"><span data-stu-id="904f9-225">The DEK can be created using any SQL Server supported algorithm or key length.</span></span> <span data-ttu-id="904f9-226">La chiave DEK verrà protetta dalla chiave asimmetrica nell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-226">The DEK will be protected by the asymmetric key in the key vault.</span></span>

     <span data-ttu-id="904f9-227">Questo esempio usa la chiave asimmetrica CONTOSO_KEY archiviata nell'insieme di credenziali delle chiavi importato o creato in precedenza, come sopra descritto nella [sezione 3 del passaggio 3](#Step3) .</span><span class="sxs-lookup"><span data-stu-id="904f9-227">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE ContosoDatabase;
    GO

    CREATE DATABASE ENCRYPTION KEY 
    WITH ALGORITHM = AES_128 
    ENCRYPTION BY SERVER ASYMMETRIC KEY CONTOSO_KEY;
    GO

    -- Alter the database to enable transparent data encryption.
    ALTER DATABASE ContosoDatabase 
    SET ENCRYPTION ON ;
    GO
    ```

     <span data-ttu-id="904f9-228">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="904f9-228">For more information, see the following:</span></span>

    -   [<span data-ttu-id="904f9-229">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="904f9-229">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)

    -   [<span data-ttu-id="904f9-230">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="904f9-230">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)

###  <a name="example-b-encrypting-backups-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleB"></a><span data-ttu-id="904f9-231">Esempio B: crittografia dei backup tramite una chiave asimmetrica dalla Key Vault</span><span class="sxs-lookup"><span data-stu-id="904f9-231">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="904f9-232">I backup crittografati sono supportati a partire da [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="904f9-232">Encrypted backups are supported starting with [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].</span></span> <span data-ttu-id="904f9-233">L'esempio seguente crea e ripristina un backup crittografato di una chiave DEK protetta dalla chiave asimmetrica nell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-233">The following example creates and restores a backup encrypted a data encryption key protected by the asymmetric key in the key vault.</span></span>

```sql
USE master;
BACKUP DATABASE [DATABASE_TO_BACKUP]
TO DISK = N'[PATH TO BACKUP FILE]' 
WITH FORMAT, INIT, SKIP, NOREWIND, NOUNLOAD, 
ENCRYPTION(ALGORITHM = AES_256, SERVER ASYMMETRIC KEY = [CONTOSO_KEY]);
GO
```

 <span data-ttu-id="904f9-234">Esempio del codice di ripristino.</span><span class="sxs-lookup"><span data-stu-id="904f9-234">Sample restore code.</span></span>

```sql
RESTORE DATABASE [DATABASE_TO_BACKUP]
FROM DISK = N'[PATH TO BACKUP FILE]' WITH FILE = 1, NOUNLOAD, REPLACE;
GO
```

 <span data-ttu-id="904f9-235">Per ulteriori informazioni sulle opzioni di backup, vedere [backup &#40;&#41;Transact-SQL ](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="904f9-235">For more information about backup options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>

###  <a name="example-c-column-level-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleC"></a><span data-ttu-id="904f9-236">Esempio C: crittografia a livello di colonna tramite una chiave asimmetrica dalla Key Vault</span><span class="sxs-lookup"><span data-stu-id="904f9-236">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="904f9-237">L'esempio seguente crea una chiave simmetrica protetta dalla chiave asimmetrica nell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="904f9-237">The following example creates a symmetric key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="904f9-238">La chiave simmetrica viene quindi usata per crittografare i dati nel database.</span><span class="sxs-lookup"><span data-stu-id="904f9-238">Then the symmetric key is used to encrypt data in the database.</span></span>

 <span data-ttu-id="904f9-239">Questo esempio usa la chiave asimmetrica CONTOSO_KEY archiviata nell'insieme di credenziali delle chiavi importato o creato in precedenza, come sopra descritto nella [sezione 3 del passaggio 3](#Step3) .</span><span class="sxs-lookup"><span data-stu-id="904f9-239">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span> <span data-ttu-id="904f9-240">Per usare questa chiave asimmetrica nel database `ContosoDatabase` , è necessario eseguire nuovamente l'istruzione CREATE ASYMMETRIC KEY in modo da fornire al database `ContosoDatabase` un riferimento alla chiave.</span><span class="sxs-lookup"><span data-stu-id="904f9-240">To use this asymmetric key in the `ContosoDatabase` database, you must execute the CREATE ASYMMETRIC KEY statement again, to provide the `ContosoDatabase` database with a reference to the key.</span></span>

```sql
USE [ContosoDatabase];
GO

-- Create a reference to the key in the key vault
CREATE ASYMMETRIC KEY CONTOSO_KEY 
FROM PROVIDER [AzureKeyVault_EKM_Prov]
WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
CREATION_DISPOSITION = OPEN_EXISTING;

-- Create the data encryption key.
-- The data encryption key can be created using any SQL Server 
-- supported algorithm or key length.
-- The DEK will be protected by the asymmetric key in the key vault

CREATE SYMMETRIC KEY DATA_ENCRYPTION_KEY
    WITH ALGORITHM=AES_256
    ENCRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

DECLARE @DATA VARBINARY(MAX);

--Open the symmetric key for use in this session
OPEN SYMMETRIC KEY DATA_ENCRYPTION_KEY 
DECRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

--Encrypt syntax
SELECT @DATA = ENCRYPTBYKEY(KEY_GUID('DATA_ENCRYPTION_KEY'), CONVERT(VARBINARY,'Plain text data to encrypt'));

-- Decrypt syntax
SELECT CONVERT(VARCHAR, DECRYPTBYKEY(@DATA));

--Close the symmetric key
CLOSE SYMMETRIC KEY DATA_ENCRYPTION_KEY;
```

## <a name="see-also"></a><span data-ttu-id="904f9-241">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="904f9-241">See Also</span></span>
 <span data-ttu-id="904f9-242">[Creazione di un provider di crittografia &#40;Transact-sql&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) [create Credential &#40;transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [creare una chiave asimmetrica &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [creare una chiave simmetrica &#40;transact-sql](/sql/t-sql/statements/create-symmetric-key-transact-sql) [&#41;Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) [abilitare](enable-tde-on-sql-server-using-ekm.md) Transparent Data Encryption con la [crittografia di backup](../../backup-restore/backup-encryption.md) EKM [creare un backup crittografato](../../backup-restore/create-an-encrypted-backup.md)</span><span class="sxs-lookup"><span data-stu-id="904f9-242">[CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-symmetric-key-transact-sql) [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) [Enable TDE Using EKM](enable-tde-on-sql-server-using-ekm.md) [Backup Encryption](../../backup-restore/backup-encryption.md) [Create an Encrypted Backup](../../backup-restore/create-an-encrypted-backup.md)</span></span>
