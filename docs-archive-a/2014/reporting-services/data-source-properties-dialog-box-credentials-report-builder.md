---
title: Finestra di dialogo Proprietà origine dati, credenziali (Generatore report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10017"
ms.assetid: 4531f09f-d653-4c05-a120-d7788838bc99
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9e47ba571e2b0adf2738499c1d027a4edde86e3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630342"
---
# <a name="data-source-properties-dialog-box-credentials-report-builder"></a><span data-ttu-id="17b1a-102">Finestra di dialogo Proprietà origine dati, Credenziali (Generatore report)</span><span class="sxs-lookup"><span data-stu-id="17b1a-102">Data Source Properties Dialog Box, Credentials (Report Builder)</span></span>
  <span data-ttu-id="17b1a-103">Selezionare **Credenziali** nella finestra di dialogo **Proprietà origine dati** per visualizzare e modificare le credenziali per la connessione a un'origine dati incorporata nel report.</span><span class="sxs-lookup"><span data-stu-id="17b1a-103">Select **Credentials** on the **Data Source Properties** dialog box to display and modify credentials to connect to an embedded data source in the report.</span></span> <span data-ttu-id="17b1a-104">Le credenziali fornite dall'utente vengono utilizzate per accedere all'origine dati per la visualizzazione in anteprima dei report.</span><span class="sxs-lookup"><span data-stu-id="17b1a-104">The credentials that you provide are used to access the data source for previewing reports.</span></span> <span data-ttu-id="17b1a-105">Per altre informazioni sulle credenziali, vedere [Specificare credenziali in Generatore report](../../2014/reporting-services/specify-credentials-in-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="17b1a-105">For more information about credentials, see [Specify Credentials in Report Builder](../../2014/reporting-services/specify-credentials-in-report-builder.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="17b1a-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="17b1a-106">Options</span></span>  
 <span data-ttu-id="17b1a-107">**Usa autenticazione di Windows (sicurezza integrata)**</span><span class="sxs-lookup"><span data-stu-id="17b1a-107">**Use Windows Authentication (integrated security)**</span></span>  
 <span data-ttu-id="17b1a-108">Selezionare questa opzione per utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="17b1a-108">Select this option to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="17b1a-109">**Usa il nome utente e la password seguenti**</span><span class="sxs-lookup"><span data-stu-id="17b1a-109">**Use this user name and password**</span></span>  
 <span data-ttu-id="17b1a-110">Selezionare questa opzione per specificare nome utente e password specifici.</span><span class="sxs-lookup"><span data-stu-id="17b1a-110">Select this option to provide a specific user name and password.</span></span> <span data-ttu-id="17b1a-111">Per le origini dei dati incorporate, quando si pubblica il progetto del server di report nel server di destinazione, il nome utente e la password vengono salvati come credenziali archiviate per il database.</span><span class="sxs-lookup"><span data-stu-id="17b1a-111">For embedded data sources: when you publish the report server project to the target server, the user name and password are saved as the stored credentials for the database.</span></span> <span data-ttu-id="17b1a-112">Se si desidera utilizzare il nome utente e la password come credenziali di Windows, è possibile modificare le proprietà dell'origine dati condivisa pubblicata nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="17b1a-112">If you want to use the user name and password as Windows credentials, you can change the properties for the published shared data source on the target server.</span></span> <span data-ttu-id="17b1a-113">Per altre informazioni, vedere [Creare, eliminare o modificare un'origine dei dati condivisa &#40;Gestione report&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md) nella documentazione relativa a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] inclusa nella [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [documentazione online di ](https://go.microsoft.com/fwlink/?linkid=121312).</span><span class="sxs-lookup"><span data-stu-id="17b1a-113">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md) in the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  
 <span data-ttu-id="17b1a-114">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="17b1a-114">**User name**</span></span>  
 <span data-ttu-id="17b1a-115">Consente di digitare un nome utente da utilizzare per l'accesso all'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="17b1a-115">Type a user name to log on to the data source.</span></span>  
  
 <span data-ttu-id="17b1a-116">**Password**</span><span class="sxs-lookup"><span data-stu-id="17b1a-116">**Password**</span></span>  
 <span data-ttu-id="17b1a-117">Consente di digitare una password da utilizzare per l'accesso all'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="17b1a-117">Type a password to log on to the data source.</span></span>  
  
 <span data-ttu-id="17b1a-118">**Richiedi credenziali**</span><span class="sxs-lookup"><span data-stu-id="17b1a-118">**Prompt for credentials**</span></span>  
 <span data-ttu-id="17b1a-119">Selezionare questa opzione per richiedere le credenziali durante l'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="17b1a-119">Select this option to prompt for credentials when the report runs.</span></span>  
  
 <span data-ttu-id="17b1a-120">**Immettere una stringa di richiesta**</span><span class="sxs-lookup"><span data-stu-id="17b1a-120">**Enter prompt string**</span></span>  
 <span data-ttu-id="17b1a-121">Digitare una frase con cui chiedere all'utente di specificare le credenziali di accesso per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="17b1a-121">Type a sentence to instruct the user to provide login credentials for the data source.</span></span>  
  
 <span data-ttu-id="17b1a-122">**Nessuna credenziale**</span><span class="sxs-lookup"><span data-stu-id="17b1a-122">**No credentials**</span></span>  
 <span data-ttu-id="17b1a-123">Selezionare questa opzione se non si desidera che vengano specificate credenziali per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="17b1a-123">Select this option to provide no credentials for the data source.</span></span> <span data-ttu-id="17b1a-124">Questa opzione funziona solamente se l'origine dati non accetta le credenziali o se il passaggio di queste ultime avviene in altro modo.</span><span class="sxs-lookup"><span data-stu-id="17b1a-124">This option only works if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
 <span data-ttu-id="17b1a-125">Da alcune estensioni per i dati è necessario configurare l'account di esecuzione automatica nel server di report.</span><span class="sxs-lookup"><span data-stu-id="17b1a-125">From some data extensions, the unattended execution account must be configured on the report server.</span></span>  
  
 <span data-ttu-id="17b1a-126">Per altre informazioni, vedere l'argomento per il tipo di origine dati corrispondente in [Aggiungere dati da origini dati esterne &#40;SSRS&#41;](report-data/add-data-from-external-data-sources-ssrs.md) e [Configurare l'account di esecuzione automatica &#40;Gestione configurazione SSRS&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) nella documentazione relativa a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] inclusa nella [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [documentazione online di ](https://go.microsoft.com/fwlink/?linkid=121312).</span><span class="sxs-lookup"><span data-stu-id="17b1a-126">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](report-data/add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md) in the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] documentation in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [Books Online](https://go.microsoft.com/fwlink/?linkid=121312).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17b1a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17b1a-127">See Also</span></span>  
 <span data-ttu-id="17b1a-128">[Guida Generatore report per finestre di dialogo, riquadri e procedure guidate](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="17b1a-128">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="17b1a-129">[Finestra di dialogo Proprietà origine dati, generale &#40;Generatore report&#41;](../../2014/reporting-services/data-source-properties-dialog-box-general-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="17b1a-129">[Data Source Properties Dialog Box, General &#40;Report Builder&#41;](../../2014/reporting-services/data-source-properties-dialog-box-general-report-builder.md) </span></span>  
 <span data-ttu-id="17b1a-130">[Aggiungere e verificare una connessione dati o un'origine dati &#40;Generatore report e SSRS&#41;](report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="17b1a-130">[Add and Verify a Data Connection or Data Source &#40;Report Builder and SSRS&#41;](report-data/add-and-verify-a-data-connection-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="17b1a-131">Aggiungere dati a un report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="17b1a-131">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
