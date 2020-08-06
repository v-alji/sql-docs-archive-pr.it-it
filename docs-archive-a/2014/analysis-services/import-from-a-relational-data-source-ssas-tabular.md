---
title: Importare da un'origine dati relazionale (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 043201cc-fbef-4ed0-bde8-dc5e3a3e8bea
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93bb9ba9ba8d40262e4e90e840dcd15ac6826df3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636933"
---
# <a name="import-from-a-relational-data-source-ssas-tabular"></a><span data-ttu-id="c5edd-102">Importare da un'origine dati relazionale (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="c5edd-102">Import from a Relational Data Source (SSAS Tabular)</span></span>
  <span data-ttu-id="c5edd-103">Tramite Importazione guidata tabella è possibile importare dati da un'ampia gamma di database relazionali.</span><span class="sxs-lookup"><span data-stu-id="c5edd-103">You can import data from a variety of relational databases by using the Table Import Wizard.</span></span> <span data-ttu-id="c5edd-104">La procedura guidata è disponibile in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], dal menu **Modello** .</span><span class="sxs-lookup"><span data-stu-id="c5edd-104">The wizard is available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Model** menu.</span></span> <span data-ttu-id="c5edd-105">Per connettersi a un'origine dati, è necessario che nel computer sia installato il provider appropriato.</span><span class="sxs-lookup"><span data-stu-id="c5edd-105">To connect to a data source, you must have the appropriate provider installed on your computer.</span></span> <span data-ttu-id="c5edd-106">Per altre informazioni su origini dati e provider supportati, vedere [Origini dati supportate &#40;SSAS tabulare&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c5edd-106">For more information about supported data sources and providers, see [Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="c5edd-107">L'Importazione guidata tabella supporta l'importazione di dati dalle origini dati seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5edd-107">The Table Import Wizard supports importing data from the following data sources:</span></span>  
  
 <span data-ttu-id="c5edd-108">**Database relazionali**</span><span class="sxs-lookup"><span data-stu-id="c5edd-108">**Relational Databases**</span></span>  
  
-   <span data-ttu-id="c5edd-109">Database di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="c5edd-109">Microsoft SQL Server database</span></span>  
  
-   <span data-ttu-id="c5edd-110">Microsoft SQL Azure</span><span class="sxs-lookup"><span data-stu-id="c5edd-110">Microsoft SQL Azure</span></span>  
  
-   <span data-ttu-id="c5edd-111">Database di Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="c5edd-111">Microsoft Access database</span></span>  
  
-   <span data-ttu-id="c5edd-112">Microsoft SQL Server Parallel Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="c5edd-112">Microsoft SQL Server Parallel Data Warehouse</span></span>  
  
-   <span data-ttu-id="c5edd-113">Oracle</span><span class="sxs-lookup"><span data-stu-id="c5edd-113">Oracle</span></span>  
  
-   <span data-ttu-id="c5edd-114">Teradata</span><span class="sxs-lookup"><span data-stu-id="c5edd-114">Teradata</span></span>  
  
-   <span data-ttu-id="c5edd-115">Sybase</span><span class="sxs-lookup"><span data-stu-id="c5edd-115">Sybase</span></span>  
  
-   <span data-ttu-id="c5edd-116">Informix</span><span class="sxs-lookup"><span data-stu-id="c5edd-116">Informix</span></span>  
  
-   <span data-ttu-id="c5edd-117">IBM DB2</span><span class="sxs-lookup"><span data-stu-id="c5edd-117">IBM DB2</span></span>  
  
-   <span data-ttu-id="c5edd-118">OLE DB/ODBC</span><span class="sxs-lookup"><span data-stu-id="c5edd-118">OLE DB/ODBC</span></span>  
  
 <span data-ttu-id="c5edd-119">**Origini multidimensionali**</span><span class="sxs-lookup"><span data-stu-id="c5edd-119">**Multidimensional Sources**</span></span>  
  
-   <span data-ttu-id="c5edd-120">Cubo di Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c5edd-120">Microsoft SQL Server Analysis Services cube</span></span>  
  
 <span data-ttu-id="c5edd-121">L'Importazione guidata tabella non supporta l'importazione di dati da una cartella di lavoro di [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] come origine dati.</span><span class="sxs-lookup"><span data-stu-id="c5edd-121">The Table Import Wizard does not support importing data from a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] Workbook as a data source.</span></span>  
  
### <a name="to-import-data-from-a-database"></a><span data-ttu-id="c5edd-122">Per importare dati da un database</span><span class="sxs-lookup"><span data-stu-id="c5edd-122">To import data from a database</span></span>  
  
1.  <span data-ttu-id="c5edd-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]fare clic sul menu **Modello** , quindi selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="c5edd-123">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
2.  <span data-ttu-id="c5edd-124">Nella pagina **Connessione a un'origine dati** selezionare il tipo di database a cui connettersi, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c5edd-124">On the **Connect to a Data Source** page, select the type of database to connect to, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="c5edd-125">Seguire i passaggi nell'Importazione guidata tabella.</span><span class="sxs-lookup"><span data-stu-id="c5edd-125">Follow the steps in the Table Import Wizard.</span></span> <span data-ttu-id="c5edd-126">Nelle pagine successive, sarà possibile selezionare tabelle e viste specifiche o applicare filtri tramite la pagina **Selezione tabelle e viste** oppure creando una query SQL nella pagina **Specifica di una query SQL** .</span><span class="sxs-lookup"><span data-stu-id="c5edd-126">On subsequent pages, you will be able to select specific tables and views or apply filters by using the **Select Tables and Views** page or by creating a SQL query on **Specify a SQL Query** page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5edd-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5edd-127">See Also</span></span>  
 <span data-ttu-id="c5edd-128">[Importare dati &#40;SSAS tabulare&#41;](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c5edd-128">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="c5edd-129">Origini dati supportate &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="c5edd-129">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
