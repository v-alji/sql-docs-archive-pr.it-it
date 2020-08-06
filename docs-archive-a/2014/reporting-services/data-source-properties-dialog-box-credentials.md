---
title: Finestra di dialogo Proprietà origine dati, credenziali | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.datasourceproperties.credentials.f1
- "10100"
ms.assetid: 14c3eeb6-d37b-4fda-967b-43afcdb48119
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 491da16e6cd38db54c4d27bd8497ca7fdfaae5b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629252"
---
# <a name="data-source-properties-dialog-box-credentials"></a><span data-ttu-id="13869-102">Finestra di dialogo Proprietà origine dati, Credenziali</span><span class="sxs-lookup"><span data-stu-id="13869-102">Data Source Properties Dialog Box, Credentials</span></span>
  <span data-ttu-id="13869-103">Selezionare **Credenziali** nella finestra di dialogo **Proprietà origine dati** per visualizzare e modificare le credenziali per la connessione a un'origine dati nel report.</span><span class="sxs-lookup"><span data-stu-id="13869-103">Select **Credentials** on the **Data Source Properties** dialog box to display and modify credentials to connect to a data source in the report.</span></span> <span data-ttu-id="13869-104">Le credenziali specificate vengono utilizzate per accedere all'origine dati e per memorizzare una copia dei dati nella cache per l'anteprima dei report.</span><span class="sxs-lookup"><span data-stu-id="13869-104">The credentials that you provide are used to access the data source and to cache a copy of the data for previewing reports.</span></span> <span data-ttu-id="13869-105">Per altre informazioni sulla modalità di memorizzazione nella cache dei dati di anteprima, vedere [Anteprima dei report](reports/previewing-reports.md).</span><span class="sxs-lookup"><span data-stu-id="13869-105">For more information about how preview data is cached, see [Previewing Reports](reports/previewing-reports.md).</span></span> <span data-ttu-id="13869-106">Per altre informazioni sulle credenziali, vedere [Specificare le credenziali e le informazioni sulla connessione per le origini dati del report](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="13869-106">For more information about credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="13869-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="13869-107">Options</span></span>  
 <span data-ttu-id="13869-108">**Usa autenticazione di Windows (sicurezza integrata)**</span><span class="sxs-lookup"><span data-stu-id="13869-108">**Use Windows Authentication (integrated security)**</span></span>  
 <span data-ttu-id="13869-109">Selezionare questa opzione per utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="13869-109">Select this option to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="13869-110">**Usa il nome utente e la password seguenti**</span><span class="sxs-lookup"><span data-stu-id="13869-110">**Use this user name and password**</span></span>  
 <span data-ttu-id="13869-111">Selezionare questa opzione per specificare nome utente e password specifici.</span><span class="sxs-lookup"><span data-stu-id="13869-111">Select this option to provide a specific user name and password.</span></span> <span data-ttu-id="13869-112">Per origini dei dati condivise: quando si pubblica il progetto del server di report sul server di destinazione, il nome utente e la password vengono salvati come credenziali archiviate per il database.</span><span class="sxs-lookup"><span data-stu-id="13869-112">For shared data sources: when you publish the report server project to the target server, the user name and password are saved as the stored credentials for the database.</span></span> <span data-ttu-id="13869-113">Se si desidera utilizzare il nome utente e la password come credenziali di Windows, è possibile modificare le proprietà dell'origine dei dati condivisa pubblicata sul server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="13869-113">If you want to use the user name and password as Windows credentials, you can edit the properties for the published shared data source on the target server.</span></span> <span data-ttu-id="13869-114">Per altre informazioni, vedere [Creare, eliminare o modificare un'origine dei dati condivisa &#40;Gestione report&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="13869-114">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span></span>  
  
 <span data-ttu-id="13869-115">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="13869-115">**User name**</span></span>  
 <span data-ttu-id="13869-116">Consente di digitare un nome utente da utilizzare per l'accesso all'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="13869-116">Type a user name to log in to the data source.</span></span>  
  
 <span data-ttu-id="13869-117">**Password**</span><span class="sxs-lookup"><span data-stu-id="13869-117">**Password**</span></span>  
 <span data-ttu-id="13869-118">Consente di digitare una password da utilizzare per l'accesso all'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="13869-118">Type a password to log in to the data source.</span></span>  
  
 <span data-ttu-id="13869-119">**Richiedi credenziali**</span><span class="sxs-lookup"><span data-stu-id="13869-119">**Prompt for credentials**</span></span>  
 <span data-ttu-id="13869-120">Selezionare questa opzione per richiedere le credenziali durante l'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="13869-120">Select this option to prompt for credentials when the report is run.</span></span>  
  
 <span data-ttu-id="13869-121">**Immettere una stringa di richiesta**</span><span class="sxs-lookup"><span data-stu-id="13869-121">**Enter prompt string**</span></span>  
 <span data-ttu-id="13869-122">Digitare una frase con cui chiedere all'utente di specificare le credenziali di accesso per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="13869-122">Type a sentence to instruct the user to provide login credentials for the data source.</span></span>  
  
 <span data-ttu-id="13869-123">**Nessuna credenziale**</span><span class="sxs-lookup"><span data-stu-id="13869-123">**No credentials**</span></span>  
 <span data-ttu-id="13869-124">Selezionare questa opzione se non si desidera che vengano specificate credenziali per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="13869-124">Select this option to provide no credentials for the data source.</span></span> <span data-ttu-id="13869-125">Questa opzione funziona solamente se l'origine dati non accetta le credenziali o se il passaggio di queste ultime avviene in altro modo.</span><span class="sxs-lookup"><span data-stu-id="13869-125">This option only works if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13869-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13869-126">See Also</span></span>  
 <span data-ttu-id="13869-127">[Finestra di dialogo Proprietà origine dati, generale](../../2014/reporting-services/data-source-properties-dialog-box-general.md) </span><span class="sxs-lookup"><span data-stu-id="13869-127">[Data Source Properties Dialog Box, General](../../2014/reporting-services/data-source-properties-dialog-box-general.md) </span></span>  
 <span data-ttu-id="13869-128">[Specificare le credenziali e le informazioni sulla connessione per le origini dati del report](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="13869-128">[Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span></span>  
 [<span data-ttu-id="13869-129">Connessioni dati, origini dati e stringhe di connessione in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="13869-129">Data Connections, Data Sources, and Connection Strings in Reporting Services</span></span>](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md)  
  
  
