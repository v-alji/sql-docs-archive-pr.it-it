---
title: Accesso ai file utilizzati dai pacchetti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- packages [Integration Services], security
- configuration files [Integration Services]
- checkpoint files
- Integration Services packages, security
- logs [Integration Services], security
- files [Integration Services], security
- SQL Server Integration Services packages, security
ms.assetid: 2e3ddea9-5289-4289-a70e-11c018f34977
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8db9511c91c9f229b7002f5b16cf077910a4ccf0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625534"
---
# <a name="access-to-files-used-by-packages"></a><span data-ttu-id="35858-102">Accesso ai file utilizzati dai pacchetti</span><span class="sxs-lookup"><span data-stu-id="35858-102">Access to Files Used by Packages</span></span>
  <span data-ttu-id="35858-103">Il livello di protezione del pacchetto non protegge i file archiviati al di fuori del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="35858-103">The package protection level does not protect files that are stored outside the package.</span></span> <span data-ttu-id="35858-104">ovvero i file seguenti:</span><span class="sxs-lookup"><span data-stu-id="35858-104">These files include the following:</span></span>  
  
-   <span data-ttu-id="35858-105">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="35858-105">Configuration files</span></span>  
  
-   <span data-ttu-id="35858-106">file del checkpoint</span><span class="sxs-lookup"><span data-stu-id="35858-106">Checkpoint files</span></span>  
  
-   <span data-ttu-id="35858-107">File di log</span><span class="sxs-lookup"><span data-stu-id="35858-107">Log files</span></span>  
  
 <span data-ttu-id="35858-108">Questi file devono essere protetti separatamente, soprattutto se includono informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="35858-108">These files must be protected separately, especially if they include sensitive information.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="35858-109">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="35858-109">Configuration Files</span></span>  
 <span data-ttu-id="35858-110">Se un file di configurazione contiene dati riservati, come informazioni su account di accesso e password, è consigliabile salvare tale configurazione in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]oppure usare un elenco di controllo di accesso (ACL) per limitare l'accesso al percorso o alla cartella in cui sono archiviati i file e consentire l'accesso solo a determinati account.</span><span class="sxs-lookup"><span data-stu-id="35858-110">If you have sensitive information in a configuration, such as login and password information, you should consider saving the configuration to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], or use an access control list (ACL) to restrict access to the location or folder where you store the files and allow access only to certain accounts.</span></span> <span data-ttu-id="35858-111">L'accesso viene in genere concesso agli account autorizzati all'esecuzione dei pacchetti e agli account utilizzati per la gestione e la risoluzione dei problemi dei pacchetti, che possono comportare la revisione dei contenuti dei file di configurazione, del checkpoint e di log.</span><span class="sxs-lookup"><span data-stu-id="35858-111">Typically, you would grant access to the accounts that you permit to run packages, and to the accounts that manage and troubleshoot packages, which may include reviewing the contents of configuration, checkpoint, and log files.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="35858-112">dispone di un'archiviazione più sicura perché la protezione viene garantita ai livelli del server e del database.</span><span class="sxs-lookup"><span data-stu-id="35858-112">provides the more secure storage because it offers protection at the server and database levels.</span></span> <span data-ttu-id="35858-113">Per salvare le configurazioni in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], è necessario usare il tipo di configurazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ,</span><span class="sxs-lookup"><span data-stu-id="35858-113">To save configurations to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration type.</span></span> <span data-ttu-id="35858-114">mentre per salvarle nel file system è necessario utilizzare il tipo di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="35858-114">To save to the file system, you use the XML configuration type.</span></span>  
  
 <span data-ttu-id="35858-115">Per altre informazioni, vedere [Configurazioni di pacchetto](../../2014/integration-services/package-configurations.md), [Creazione di configurazioni dei pacchetti](../../2014/integration-services/create-package-configurations.md)e [Considerazioni sulla sicurezza per un'installazione SQL Server](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="35858-115">For more information, see [Package Configurations](../../2014/integration-services/package-configurations.md), [Create Package Configurations](../../2014/integration-services/create-package-configurations.md), and [Security Considerations for a SQL Server Installation](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md).</span></span>  
  
## <a name="checkpoint-files"></a><span data-ttu-id="35858-116">file del checkpoint</span><span class="sxs-lookup"><span data-stu-id="35858-116">Checkpoint Files</span></span>  
 <span data-ttu-id="35858-117">In modo analogo, è consigliabile utilizzare un elenco di controllo di accesso del sistema operativo per la sicurezza del percorso o della cartella se il file del checkpoint utilizzato dal pacchetto contiene informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="35858-117">Similarly, if the checkpoint file that the package uses includes sensitive information, you should use an access control list (ACL) to secure the location or folder where you store the file.</span></span> <span data-ttu-id="35858-118">Nei file del checkpoint vengono salvate informazioni aggiornate sullo stato del pacchetto e sui valori correnti delle variabili.</span><span class="sxs-lookup"><span data-stu-id="35858-118">Checkpoint files save current state information on the progress of the package as well as the current values of variables.</span></span> <span data-ttu-id="35858-119">Il pacchetto potrebbe includere, ad esempio, una variabile personalizzata per la memorizzazione di un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="35858-119">For example, the package may include a custom variable that contains a telephone number.</span></span> <span data-ttu-id="35858-120">Per ulteriori informazioni, vedere [Restart Packages by Using Checkpoints](packages/restart-packages-by-using-checkpoints.md).</span><span class="sxs-lookup"><span data-stu-id="35858-120">For more information, see [Restart Packages by Using Checkpoints](packages/restart-packages-by-using-checkpoints.md).</span></span>  
  
## <a name="log-files"></a><span data-ttu-id="35858-121">File di log</span><span class="sxs-lookup"><span data-stu-id="35858-121">Log Files</span></span>  
 <span data-ttu-id="35858-122">Anche le voci di log scritte nel file system dovrebbero essere protette tramite un elenco di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="35858-122">Log entries that are written to the file system should also be secured using an access control list (ACL).</span></span> <span data-ttu-id="35858-123">È inoltre possibile archiviare le voci di log nelle tabelle di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e proteggerle con gli strumenti di sicurezza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="35858-123">Log entries can also be stored in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables and protected by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] security.</span></span> <span data-ttu-id="35858-124">Le voci di log possono infatti includere informazioni riservate. Se ad esempio il pacchetto contiene un'attività Esegui SQL che genera un'istruzione SQL che fa riferimento a un numero di telefono, la voce di log per l'istruzione SQL conterrà tale numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="35858-124">Log entries may include sensitive information, For example, if the package contains an Execute SQL task that constructs an SQL statement that refers to a telephone number, the log entry for the SQL statement includes the telephone number.</span></span> <span data-ttu-id="35858-125">L'istruzione SQL potrebbe inoltre esporre informazioni private sui nomi di tabelle e colonne nei database.</span><span class="sxs-lookup"><span data-stu-id="35858-125">The SQL statement may also reveal private information about table and column names in databases.</span></span> <span data-ttu-id="35858-126">Per altre informazioni, vedere [registrazione di Integration Services &#40;SSIS&#41;](performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="35858-126">For more information, see [Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md).</span></span>  
  
  
