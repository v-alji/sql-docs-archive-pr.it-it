---
title: Finestra di dialogo Proprietà connessione (SSAS-tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.ssmsimbi.ConnectionProperties.F1
ms.assetid: 17bae8ae-2ba0-4978-be70-61c687f59d54
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e4b0360d59f43bc932f68a846f239c4873a5aa9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625702"
---
# <a name="connection-properties-dialog-box-ssas---tabular"></a><span data-ttu-id="fa0c0-102">Finestra di dialogo Proprietà connessione (SSAS - Tabulare)</span><span class="sxs-lookup"><span data-stu-id="fa0c0-102">Connection Properties Dialog Box (SSAS - Tabular)</span></span>
  <span data-ttu-id="fa0c0-103">Utilizzare questa pagina per visualizzare o modificare in SQL Server Management Studio le proprietà di connessione di un'origine dati utilizzata da un database modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-103">Use this page to view or modify in SQL Server Management Studio the connection properties of a data source used by a tabular model database.</span></span>  
  
 <span data-ttu-id="fa0c0-104">In questa finestra di dialogo vengono forniti timestamp e altre informazioni descrittive, nonché proprietà personalizzabili che determinano le caratteristiche della connessione.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-104">This dialog box provides timestamps and other descriptive information, plus customizable properties that determine characteristics of the connection.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa0c0-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fa0c0-105">Options</span></span>  
  
|<span data-ttu-id="fa0c0-106">Termine</span><span class="sxs-lookup"><span data-stu-id="fa0c0-106">Term</span></span>|<span data-ttu-id="fa0c0-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="fa0c0-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="fa0c0-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="fa0c0-108">**Name**</span></span>|<span data-ttu-id="fa0c0-109">Specifica il nome dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-109">Specifies the name of the data source.</span></span>|  
|<span data-ttu-id="fa0c0-110">**ID**</span><span class="sxs-lookup"><span data-stu-id="fa0c0-110">**ID**</span></span>|<span data-ttu-id="fa0c0-111">Visualizza l'identificatore dell'oggetto origine dati.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-111">Displays the identifier of the data source object.</span></span>|  
|<span data-ttu-id="fa0c0-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fa0c0-112">**Description**</span></span>|<span data-ttu-id="fa0c0-113">Visualizza la descrizione dell'oggetto origine dati.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-113">Displays the description of the data source object.</span></span>|  
|<span data-ttu-id="fa0c0-114">**Timestamp creazione**</span><span class="sxs-lookup"><span data-stu-id="fa0c0-114">**Create Timestamp**</span></span>|<span data-ttu-id="fa0c0-115">Consente di visualizzare la data e l'ora di creazione del database.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-115">Displays the date and time the database was created.</span></span>|  
|<span data-ttu-id="fa0c0-116">**Ultimo aggiornamento schema**</span><span class="sxs-lookup"><span data-stu-id="fa0c0-116">**Last Schema Update**</span></span>|<span data-ttu-id="fa0c0-117">Consente di visualizzare la data e l'ora dell'ultimo aggiornamento dei metadati del database.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-117">Displays the date and time the metadata for the database was last updated.</span></span>|  
|<span data-ttu-id="fa0c0-118">**Stringa di connessione**</span><span class="sxs-lookup"><span data-stu-id="fa0c0-118">**Connection String**</span></span>|<span data-ttu-id="fa0c0-119">Visualizza la stringa di connessione utilizzata per stabilire una connessione all'origine dati che fornisce dati al modello.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-119">Displays the connection string used to connect to the data source that provides data to the model.</span></span>|  
|<span data-ttu-id="fa0c0-120">**Numero massimo di connessioni**</span><span class="sxs-lookup"><span data-stu-id="fa0c0-120">**Maximum Number of Connections**</span></span>|<span data-ttu-id="fa0c0-121">Specifica il numero massimo di connessioni client a questo database.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-121">Specifies the maximum number of client connections to this database.</span></span>|  
|<span data-ttu-id="fa0c0-122">**Isolamento**</span><span class="sxs-lookup"><span data-stu-id="fa0c0-122">**Isolation**</span></span>|<span data-ttu-id="fa0c0-123">I valori validi sono ReadCommitted o Snapshot.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-123">Valid values are ReadCommitted or Snapshot.</span></span> <span data-ttu-id="fa0c0-124">Per altre informazioni, vedere [Elemento Isolation &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/isolation-element-assl).</span><span class="sxs-lookup"><span data-stu-id="fa0c0-124">For more information, see [Isolation Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/isolation-element-assl).</span></span>|  
|<span data-ttu-id="fa0c0-125">**Timeout query**</span><span class="sxs-lookup"><span data-stu-id="fa0c0-125">**Query Timeout**</span></span>|<span data-ttu-id="fa0c0-126">Specifica il tempo, in secondi, dopo il quale si verifica il timeout del tentativo di recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-126">Specifies the time, in seconds, after which an attempt to retrieve data is timed out.</span></span>|  
|<span data-ttu-id="fa0c0-127">**Provider gestito**</span><span class="sxs-lookup"><span data-stu-id="fa0c0-127">**Managed Provider**</span></span>|<span data-ttu-id="fa0c0-128">Specifica il nome del provider gestito.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-128">Specifies the name of the managed provider.</span></span> <span data-ttu-id="fa0c0-129">Se la connessione all'origine dati utilizza un provider OLE DB nativo, questo valore è vuoto.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-129">If the data source connection uses a native OLE DB provider, this value is empty.</span></span>|  
|<span data-ttu-id="fa0c0-130">**Impostazioni di rappresentazione**</span><span class="sxs-lookup"><span data-stu-id="fa0c0-130">**Impersonation Info**</span></span>|<span data-ttu-id="fa0c0-131">Viene specificato l'account di rappresentazione utilizzato per le connessioni al database quando vengono elaborati o aggiornati i dati, le query eseguite su un archivio dati relazionale (tramite DirectQuery), le associazioni out-of-line, le partizioni remote e la sincronizzazione del database dalla destinazione all'origine.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-131">Specifies the impersonation account used for database connections when processing or refreshing data, queries that run against a relational data store (via DirectQuery), out-of-line bindings, remote partitions, and database synchronization from target to source.</span></span><br /><br /> <span data-ttu-id="fa0c0-132">I valori validi includono l'account del servizio Analysis Services o un set specifico di credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-132">Valid values include the Analysis Services service account or a specific set of Windows credentials.</span></span> <span data-ttu-id="fa0c0-133">Non specificare **Usa credenziali dell'utente corrente** o **Eredita**.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-133">Do not specify **Use the credentials of the current user** or **Inherit**.</span></span> <span data-ttu-id="fa0c0-134">Tali opzioni per le credenziali non sono supportate per un database modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="fa0c0-134">Those credential options are not supported for a tabular model database.</span></span>|  
  
  
