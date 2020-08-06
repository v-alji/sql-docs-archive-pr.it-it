---
title: Finestra di dialogo Proprietà origine dati condivisa, credenziali | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shareddatasource.credentials.f1
ms.assetid: c08d1a5f-206b-4d53-ab1a-368b651ee5bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8594c6627c033d31937b2aa8691869cdbba213b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716056"
---
# <a name="shared-data-source-properties-dialog-box-credentials"></a><span data-ttu-id="868cb-102">Finestra di dialogo Proprietà origine dati condivisa, Credenziali</span><span class="sxs-lookup"><span data-stu-id="868cb-102">Shared Data Source Properties Dialog Box, Credentials</span></span>
  <span data-ttu-id="868cb-103">Selezionare **Credenziali** nella finestra di dialogo **Proprietà origine dati condivisa** per visualizzare e modificare le credenziali per la connessione a un'origine dati condivisa nel report.</span><span class="sxs-lookup"><span data-stu-id="868cb-103">Select **Credentials** on the **Shared Data Source Properties** dialog box to display and modify credentials to connect to a shared data source in the report.</span></span> <span data-ttu-id="868cb-104">Le credenziali specificate vengono utilizzate per accedere all'origine dati e per memorizzare una copia dei dati nella cache per l'anteprima dei report.</span><span class="sxs-lookup"><span data-stu-id="868cb-104">The credentials that you provide are used to access the data source and to cache a copy of the data for previewing reports.</span></span> <span data-ttu-id="868cb-105">Per altre informazioni sulla modalità di memorizzazione nella cache dei dati di anteprima, vedere [Anteprima dei report](reports/previewing-reports.md).</span><span class="sxs-lookup"><span data-stu-id="868cb-105">For more information about how preview data is cached, see [Previewing Reports](reports/previewing-reports.md).</span></span> <span data-ttu-id="868cb-106">Per altre informazioni sulle credenziali, vedere [Specificare le credenziali e le informazioni sulla connessione per le origini dati del report](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="868cb-106">For more information about credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="868cb-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="868cb-107">Options</span></span>  
 <span data-ttu-id="868cb-108">**Usa autenticazione di Windows (sicurezza integrata)**</span><span class="sxs-lookup"><span data-stu-id="868cb-108">**Use Windows Authentication (integrated security)**</span></span>  
 <span data-ttu-id="868cb-109">Selezionare questa opzione per utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="868cb-109">Select this option to use Windows Authentication.</span></span>  
  
 <span data-ttu-id="868cb-110">**Usa il nome utente e la password seguenti**</span><span class="sxs-lookup"><span data-stu-id="868cb-110">**Use this user name and password**</span></span>  
 <span data-ttu-id="868cb-111">Selezionare questa opzione per specificare nome utente e password specifici.</span><span class="sxs-lookup"><span data-stu-id="868cb-111">Select this option to provide a specific user name and password.</span></span> <span data-ttu-id="868cb-112">Per origini dei dati condivise: quando si pubblica il progetto del server di report sul server di destinazione, il nome utente e la password vengono salvati come credenziali archiviate per il database.</span><span class="sxs-lookup"><span data-stu-id="868cb-112">For shared data sources: when you publish the report server project to the target server, the user name and password are saved as the stored credentials for the database.</span></span> <span data-ttu-id="868cb-113">Se si desidera utilizzare il nome utente e la password come credenziali di Windows, è possibile modificare le proprietà dell'origine dei dati condivisa pubblicata sul server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="868cb-113">If you want to use the user name and password as Windows credentials, you can edit the properties for the published shared data source on the target server.</span></span> <span data-ttu-id="868cb-114">Per altre informazioni, vedere [Creare, eliminare o modificare un'origine dei dati condivisa &#40;Gestione report&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="868cb-114">For more information, see [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../../2014/reporting-services/create-delete-or-modify-a-shared-data-source-report-manager.md).</span></span>  
  
 <span data-ttu-id="868cb-115">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="868cb-115">**User name**</span></span>  
 <span data-ttu-id="868cb-116">Consente di digitare un nome utente da utilizzare per l'accesso all'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="868cb-116">Type a user name to log in to the data source.</span></span>  
  
 <span data-ttu-id="868cb-117">**Password**</span><span class="sxs-lookup"><span data-stu-id="868cb-117">**Password**</span></span>  
 <span data-ttu-id="868cb-118">Consente di digitare una password da utilizzare per l'accesso all'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="868cb-118">Type a password to log in to the data source.</span></span>  
  
 <span data-ttu-id="868cb-119">**Richiedi credenziali**</span><span class="sxs-lookup"><span data-stu-id="868cb-119">**Prompt for credentials**</span></span>  
 <span data-ttu-id="868cb-120">Selezionare questa opzione per richiedere le credenziali durante l'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="868cb-120">Select this option to prompt for credentials when the report is run.</span></span>  
  
 <span data-ttu-id="868cb-121">**Immettere una stringa di richiesta**</span><span class="sxs-lookup"><span data-stu-id="868cb-121">**Enter prompt string**</span></span>  
 <span data-ttu-id="868cb-122">Digitare una frase con cui chiedere all'utente di specificare le credenziali di accesso per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="868cb-122">Type a sentence to instruct the user to provide login credentials for the data source.</span></span>  
  
 <span data-ttu-id="868cb-123">**Nessuna credenziale**</span><span class="sxs-lookup"><span data-stu-id="868cb-123">**No credentials**</span></span>  
 <span data-ttu-id="868cb-124">Selezionare questa opzione se non si desidera che vengano specificate credenziali per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="868cb-124">Select this option to provide no credentials for the data source.</span></span> <span data-ttu-id="868cb-125">Questa opzione funziona solamente se l'origine dati non accetta le credenziali o se il passaggio di queste ultime avviene in altro modo.</span><span class="sxs-lookup"><span data-stu-id="868cb-125">This option only works if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="868cb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="868cb-126">See Also</span></span>  
 <span data-ttu-id="868cb-127">[Connessioni dati, origini dati e stringhe di connessione in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="868cb-127">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="868cb-128">[Specificare le credenziali e le informazioni sulla connessione per le origini dati del report](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="868cb-128">[Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) </span></span>  
 [<span data-ttu-id="868cb-129">Finestra di dialogo Proprietà origine dati condivisa, Generale</span><span class="sxs-lookup"><span data-stu-id="868cb-129">Shared Data Source Properties Dialog Box, General</span></span>](../../2014/reporting-services/shared-data-source-properties-dialog-box-general.md)  
  
  
