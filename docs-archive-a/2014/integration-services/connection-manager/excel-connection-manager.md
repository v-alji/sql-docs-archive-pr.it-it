---
title: Gestione connessione Excel | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- files [Integration Services], connections
- connections [Integration Services], Excel
- Excel [Integration Services]
- connection managers [Integration Services], Excel
ms.assetid: 667419f2-74fb-4b50-b963-9197d1368cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7561361c6d4ab7e22282b25367906aa4b75e5bc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627945"
---
# <a name="excel-connection-manager"></a><span data-ttu-id="20dca-102">Gestione connessione Excel</span><span class="sxs-lookup"><span data-stu-id="20dca-102">Excel Connection Manager</span></span>
  <span data-ttu-id="20dca-103">Una gestione connessione Excel consente la connessione di un pacchetto a un file di cartella di lavoro di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel esistente.</span><span class="sxs-lookup"><span data-stu-id="20dca-103">An Excel connection manager enables a package to connect to an existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbook file.</span></span> <span data-ttu-id="20dca-104">L'origine Excel e la destinazione Excel che [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includono utilizzano la gestione connessione Excel.</span><span class="sxs-lookup"><span data-stu-id="20dca-104">The Excel source and the Excel destination that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] include use the Excel connection manager.</span></span>  
  
 <span data-ttu-id="20dca-105">Quando si aggiunge una gestione connessione Excel a un pacchetto, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea una gestione connessione che in fase di esecuzione verrà risolta in una connessione Excel, imposta le proprietà della gestione connessione e quindi la aggiunge alla raccolta `Connections` del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="20dca-105">When you add an Excel connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that is resolved as an Excel connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="20dca-106">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `EXCEL`.</span><span class="sxs-lookup"><span data-stu-id="20dca-106">The `ConnectionManagerType` property of the connection manager is set to `EXCEL`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20dca-107">Non è possibile connettersi a un file di Excel protetto da password.</span><span class="sxs-lookup"><span data-stu-id="20dca-107">You cannot connect to a password-protected Excel file.</span></span>  
  
## <a name="configuration-of-the-excel-connection-manager"></a><span data-ttu-id="20dca-108">Configurazione della gestione connessione Excel</span><span class="sxs-lookup"><span data-stu-id="20dca-108">Configuration of the Excel Connection Manager</span></span>  
 <span data-ttu-id="20dca-109">Per configurare la gestione connessione Excel, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="20dca-109">You can configure the Excel connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="20dca-110">Specificare il percorso del file della cartella di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="20dca-110">Specify the path of the Excel workbook file.</span></span>  
  
-   <span data-ttu-id="20dca-111">Specificare la versione di Excel utilizzata per creare il file.</span><span class="sxs-lookup"><span data-stu-id="20dca-111">Specify the version of Excel that was used to create the file.</span></span>  
  
-   <span data-ttu-id="20dca-112">Indicare se la prima riga di dati a cui si accede nei fogli di lavoro o negli intervalli selezionati contiene i nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="20dca-112">Indicate whether the first row of accessed data in the selected worksheets or ranges contains column names.</span></span>  
  
 <span data-ttu-id="20dca-113">Se la gestione connessione Excel viene utilizzata da un'origine Excel, i nomi delle colonne saranno inclusi nei dati estratti.</span><span class="sxs-lookup"><span data-stu-id="20dca-113">If the Excel connection manager is used by an Excel source, the column names are included with the extracted data.</span></span> <span data-ttu-id="20dca-114">Se viene utilizzata da una destinazione Excel, i nomi delle colonne saranno inclusi nei dati scritti.</span><span class="sxs-lookup"><span data-stu-id="20dca-114">If it is used by an Excel destination, the column names are included in the written data.</span></span>  
  
 <span data-ttu-id="20dca-115">La gestione connessione Excel utilizza il provider OLE DB [!INCLUDE[msCoName](../../includes/msconame-md.md)] per Jet 4.0 e il relativo driver ISAM (Indexed Sequential Access Method, metodo di accesso sequenziale indicizzato) di Excel di supporto per stabilire la connessione con le origini dei dati Excel e quindi leggere e scrivere informazioni.</span><span class="sxs-lookup"><span data-stu-id="20dca-115">The Excel connection manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span> <span data-ttu-id="20dca-116">Per ulteriori informazioni sul comportamento di questo provider e driver se utilizzato con origini Excel e destinazioni Excel, vedere [Excel source](../data-flow/excel-source.md) ed Excel [Destination](../data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="20dca-116">For more information about the behavior of this provider and driver when used with Excel sources and Excel destinations, see [Excel Source](../data-flow/excel-source.md) and [Excel Destination](../data-flow/excel-destination.md).</span></span>  
  
 <span data-ttu-id="20dca-117">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="20dca-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="20dca-118">Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vedere [Editor gestione connessione Excel](../excel-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="20dca-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Excel Connection Manager Editor](../excel-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="20dca-119">Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere l'articolo relativo a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="20dca-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
 <span data-ttu-id="20dca-120">Per informazioni sul ciclo tramite un gruppo di file Excel, vedere [Esecuzione di un ciclo su file e tabelle di Excel utilizzando un contenitore Ciclo Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="20dca-120">For information about looping through a group of Excel files, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="20dca-121">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="20dca-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="20dca-122">Esecuzione di un ciclo su file e tabelle di Excel usando un contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="20dca-122">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="20dca-123">Caricare dati da o in Excel con SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="20dca-123">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)
  
  
