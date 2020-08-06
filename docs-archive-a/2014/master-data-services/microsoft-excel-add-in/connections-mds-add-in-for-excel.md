---
title: Connessioni (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 2f2b2f9d-7744-460e-83cd-56d34ea70ff0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d4dc41afc6dd59cade9e75475c7cb914d14a8937
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623380"
---
# <a name="connections-mds-add-in-for-excel"></a><span data-ttu-id="a1a41-102">Connessioni (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="a1a41-102">Connections (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="a1a41-103">Per scaricare dati nel [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]è necessario prima creare una connessione.</span><span class="sxs-lookup"><span data-stu-id="a1a41-103">To download data in to the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you must first create a connection.</span></span> <span data-ttu-id="a1a41-104">Una connessione è la modalità con cui un servizio Web [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] individua il database MDS a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a1a41-104">A connection is how the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] web service knows which MDS database to connect to.</span></span>  
  
 <span data-ttu-id="a1a41-105">La stringa di connessione è generalmente l'URL dell'applicazione Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], ad esempio http://contoso/mds.</span><span class="sxs-lookup"><span data-stu-id="a1a41-105">The connection string is usually the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, for example http://contoso/mds.</span></span>  
  
 <span data-ttu-id="a1a41-106">Ogni volta che si avvia Excel, è necessario connettersi a un repository MDS.</span><span class="sxs-lookup"><span data-stu-id="a1a41-106">Each time you start Excel, you must connect to an MDS repository.</span></span> <span data-ttu-id="a1a41-107">L'unica eccezione è quando il foglio di calcolo attivo già contiene i dati gestiti da MDS.</span><span class="sxs-lookup"><span data-stu-id="a1a41-107">The only exception is when the active spreadsheet already contains MDS-managed data.</span></span> <span data-ttu-id="a1a41-108">In questo caso, si stabilisce automaticamente una connessione ogni volta che si aggiornano o pubblicano dati nel foglio.</span><span class="sxs-lookup"><span data-stu-id="a1a41-108">In this case, a connection is automatically made each time you refresh or publish data in the sheet.</span></span>  
  
 <span data-ttu-id="a1a41-109">È possibile creare più connessioni.</span><span class="sxs-lookup"><span data-stu-id="a1a41-109">You can create multiple connections.</span></span> <span data-ttu-id="a1a41-110">La connessione alla quale si è effettuato l'accesso più recentemente è considerata il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a1a41-110">The most recently-accessed connection is considered the default.</span></span>  
  
 <span data-ttu-id="a1a41-111">È possibile connettere più utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a1a41-111">Multiple users can be connected at the same time.</span></span> <span data-ttu-id="a1a41-112">Tuttavia, si possono verificare conflitti quando più utenti tentano di pubblicare gli stessi dati.</span><span class="sxs-lookup"><span data-stu-id="a1a41-112">However, conflicts can arise when multiple users attempt to publish the same data.</span></span> <span data-ttu-id="a1a41-113">Per ulteriori informazioni, vedere la pagina relativa alla [pubblicazione di dati &#40;Componente aggiuntivo MDS per Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="a1a41-113">For more information, see [Publishing Data &#40;MDS Add-in for Excel&#41;](overview-importing-data-from-excel-mds-add-in-for-excel.md).</span></span>  
  
## <a name="connect-automatically-and-load-frequently-used-data"></a><span data-ttu-id="a1a41-114">Connettersi automaticamente e caricare i dati utilizzati frequentemente</span><span class="sxs-lookup"><span data-stu-id="a1a41-114">Connect Automatically and Load Frequently-Used Data</span></span>  
 <span data-ttu-id="a1a41-115">Se si desidera connettersi sempre allo stesso server e caricare lo stesso set di dati, è possibile creare file di query collegamento che contengano la connessione e filtrino le informazioni.</span><span class="sxs-lookup"><span data-stu-id="a1a41-115">If you want to always connect to the same server and load the same set of data, you can create shortcut query files, which contain connection and filter information.</span></span> <span data-ttu-id="a1a41-116">Per altre informazioni sui file di query, vedere [File di query collegamento &#40;componente aggiuntivo MDS per Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="a1a41-116">For more information about query files, see [Shortcut Query Files &#40;MDS Add-in for Excel&#41;](shortcut-query-files-mds-add-in-for-excel.md).</span></span>  
  
## <a name="data-quality-services"></a><span data-ttu-id="a1a41-117">Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="a1a41-117">Data Quality Services</span></span>  
 <span data-ttu-id="a1a41-118">Il [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] dispone della funzionalità Data Quality Services per consentire la corrispondenza dei dati prima di pubblicarli nel repository MDS.</span><span class="sxs-lookup"><span data-stu-id="a1a41-118">The [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] has Data Quality Services functionality to help you match data before publishing it to the MDS repository.</span></span> <span data-ttu-id="a1a41-119">Quando si stabilisce una connessione, se un database DQS è installato sulla stessa istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] come database MDS, sarà possibile visualizzare i pulsanti DQS sulla barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="a1a41-119">When you make a connection, if a DQS database is installed on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the MDS database, you will be able to view DQS buttons on the ribbon.</span></span> <span data-ttu-id="a1a41-120">Se il database DQS_Main non esiste nell'istanza, questi pulsanti non sono visualizzati e la funzionalità Data Quality non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a1a41-120">If the DQS_Main database does not exist on the instance, these buttons are not displayed and data quality functionality is not available.</span></span>  
  
## <a name="troubleshooting-connections"></a><span data-ttu-id="a1a41-121">Risoluzione dei problemi relativi alle connessioni</span><span class="sxs-lookup"><span data-stu-id="a1a41-121">Troubleshooting Connections</span></span>  
 <span data-ttu-id="a1a41-122">Quando ci si connette a MDS, se si verificano problemi, vedere [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) per suggerimenti sulla risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="a1a41-122">When you connect to MDS, if you encounter any issues see [https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx](https://social.technet.microsoft.com/wiki/contents/articles/4520.aspx) for troubleshooting tips.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a1a41-123">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="a1a41-123">Related Tasks</span></span>  
  
|<span data-ttu-id="a1a41-124">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="a1a41-124">Task Description</span></span>|<span data-ttu-id="a1a41-125">Argomento</span><span class="sxs-lookup"><span data-stu-id="a1a41-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="a1a41-126">Creare una connessione a un database [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1a41-126">Create a connection to a [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] database.</span></span>|[<span data-ttu-id="a1a41-127">Connettersi a un repository MDS &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a1a41-127">Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;</span></span>](connect-to-an-mds-repository-mds-add-in-for-excel.md)|  
|<span data-ttu-id="a1a41-128">Caricare dati MDS in Excel.</span><span class="sxs-lookup"><span data-stu-id="a1a41-128">Load MDS data into Excel.</span></span>|[<span data-ttu-id="a1a41-129">Caricare i dati da MDS in Excel</span><span class="sxs-lookup"><span data-stu-id="a1a41-129">Load Data from MDS into Excel</span></span>](export-data-to-excel-from-master-data-services.md)|  
|<span data-ttu-id="a1a41-130">Filtrare i dati MDS prima di caricarli in Excel.</span><span class="sxs-lookup"><span data-stu-id="a1a41-130">Filter MDS data before you load it into Excel.</span></span>|[<span data-ttu-id="a1a41-131">Filtrare i dati prima di caricare &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a1a41-131">Filter Data before Loading &#40;MDS Add-in for Excel&#41;</span></span>](filter-data-before-exporting-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="a1a41-132">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="a1a41-132">Related Content</span></span>  
  
-   [<span data-ttu-id="a1a41-133">Caricamento dei dati &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a1a41-133">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="a1a41-134">File di query collegamento &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a1a41-134">Shortcut Query Files &#40;MDS Add-in for Excel&#41;</span></span>](shortcut-query-files-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="a1a41-135">Componente aggiuntivo Master Data Services per Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="a1a41-135">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
  
