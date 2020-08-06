---
title: Selezione tabelle e viste (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviews.f1
ms.assetid: 5e8121cc-03f0-4168-98cf-63c5c032bb0b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 891da51478670122f5dbce8fdd7be55c98c898c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723155"
---
# <a name="select-tables-and-views-ssas"></a><span data-ttu-id="1758b-102">Selezione tabelle e viste (SSAS)</span><span class="sxs-lookup"><span data-stu-id="1758b-102">Select Tables and Views (SSAS)</span></span>
  <span data-ttu-id="1758b-103">Questa pagina dell' **Importazione guidata tabella** consente di selezionare le tabelle e le viste da cui importare dati.</span><span class="sxs-lookup"><span data-stu-id="1758b-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="1758b-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="1758b-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="1758b-105">L'aspetto delle tabelle e delle viste in questa pagina non garantisce che l'importazione verrà completata.</span><span class="sxs-lookup"><span data-stu-id="1758b-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="1758b-106">Se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal database selezionato, l'importazione non verrà completata.</span><span class="sxs-lookup"><span data-stu-id="1758b-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="1758b-107">Per origini dati in cui viene utilizzata l'autenticazione di Windows, le credenziali dell'utente corrente vengono utilizzate per recuperare le tabelle e le viste nella finestra di dialogo Selezione tabelle e viste.</span><span class="sxs-lookup"><span data-stu-id="1758b-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="1758b-108">Per altre origini dati, vengono utilizzate le credenziali fornite nella stringa di connessione per il recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="1758b-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="1758b-109">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="1758b-109">UI element list</span></span>  
 <span data-ttu-id="1758b-110">**Server**</span><span class="sxs-lookup"><span data-stu-id="1758b-110">**Server**</span></span>  
 <span data-ttu-id="1758b-111">Viene visualizzato il server al quale si è connessi.</span><span class="sxs-lookup"><span data-stu-id="1758b-111">Displays the server that you are connected to.</span></span>  
  
 <span data-ttu-id="1758b-112">**Database**</span><span class="sxs-lookup"><span data-stu-id="1758b-112">**Database**</span></span>  
 <span data-ttu-id="1758b-113">Visualizza il database selezionato.</span><span class="sxs-lookup"><span data-stu-id="1758b-113">Displays the database that you selected.</span></span>  
  
 <span data-ttu-id="1758b-114">**Tabelle e viste**</span><span class="sxs-lookup"><span data-stu-id="1758b-114">**Tables and Views**</span></span>  
 <span data-ttu-id="1758b-115">Elenca le tabelle e le viste presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="1758b-115">Lists the tables and views in the database.</span></span> <span data-ttu-id="1758b-116">Selezionare la casella di controllo accanto a ciascuna tabella e visualizzare la tabella che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="1758b-116">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="1758b-117">**Tabella di origine**</span><span class="sxs-lookup"><span data-stu-id="1758b-117">**Source Table**</span></span>  
 <span data-ttu-id="1758b-118">Specifica il nome della tabella di origine in base al tipo di origine dati.</span><span class="sxs-lookup"><span data-stu-id="1758b-118">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="1758b-119">**Schema**</span><span class="sxs-lookup"><span data-stu-id="1758b-119">**Schema**</span></span>  
 <span data-ttu-id="1758b-120">Specifica lo schema in cui è contenuta la tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="1758b-120">Specifies the schema in which the source table is contained.</span></span> <span data-ttu-id="1758b-121">A seconda del tipo di database, un schema funziona come un contenitore per altri oggetti, ad esempio tabelle, nonché indicare la proprietà di tali oggetti.</span><span class="sxs-lookup"><span data-stu-id="1758b-121">Depending on the type of database, a schema functions as a container for other objects, such as tables, and can also indicate ownership of those objects.</span></span>  
  
 <span data-ttu-id="1758b-122">**Nome descrittivo**</span><span class="sxs-lookup"><span data-stu-id="1758b-122">**Friendly Name**</span></span>  
 <span data-ttu-id="1758b-123">Specifica il nome descrittivo della tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="1758b-123">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="1758b-124">Per impostazione predefinita, nella colonna viene visualizzato il nome della tabella di origine presente nella colonna **Tabella di origine** .</span><span class="sxs-lookup"><span data-stu-id="1758b-124">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span> <span data-ttu-id="1758b-125">Modificare il nome se si desidera utilizzare un nome diverso da quello utilizzato nel database di origine.</span><span class="sxs-lookup"><span data-stu-id="1758b-125">Change the name if you want to use a different name than the name used in the source database.</span></span>  
  
 <span data-ttu-id="1758b-126">**Dettagli filtro**</span><span class="sxs-lookup"><span data-stu-id="1758b-126">**Filter Details**</span></span>  
 <span data-ttu-id="1758b-127">Se è stato applicato un filtro ai dati importati, consente di visualizzare il filtro per l'importazione dei dati nella finestra di dialogo **Dettagli filtro**.</span><span class="sxs-lookup"><span data-stu-id="1758b-127">When a filter has been applied to the data that is being imported, displays the data import filter in the **Filter Details** dialog box.</span></span> <span data-ttu-id="1758b-128">Per altre informazioni, vedere [Dettagli filtro &#40;DAX&#41;](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="1758b-128">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="1758b-129">**Visualizza anteprima e applica filtro**</span><span class="sxs-lookup"><span data-stu-id="1758b-129">**Preview and Filter**</span></span>  
 <span data-ttu-id="1758b-130">Visualizza la finestra di dialogo **Anteprima tabella selezionata** usata per applicare un filtro ai dati importati.</span><span class="sxs-lookup"><span data-stu-id="1758b-130">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="1758b-131">Per altre informazioni, vedere [Anteprima tabella selezionata &#40;SSAS&#41;](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="1758b-131">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="1758b-132">**Seleziona tabelle correlate**</span><span class="sxs-lookup"><span data-stu-id="1758b-132">**Select Related Tables**</span></span>  
 <span data-ttu-id="1758b-133">Consente di selezionare per l'importazione le tabelle e le viste correlate alle tabelle e alle viste già selezionate.</span><span class="sxs-lookup"><span data-stu-id="1758b-133">Selects for import those tables and views that are related to the tables and views that you have already selected.</span></span>  
  
  
