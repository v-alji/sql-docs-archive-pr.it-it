---
title: Selezione tabelle e viste (feed di dati) (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviewsdf.f1
ms.assetid: 6c4fafe0-e02e-47d1-b8bc-e70e872690af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 46c317ecf2a87adcde264e8d6d7e822eb833b8b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627426"
---
# <a name="select-tables-and-views-data-feeds-ssas"></a><span data-ttu-id="cd6fd-102">Selezione tabelle e viste (Feed di dati) (SSAS)</span><span class="sxs-lookup"><span data-stu-id="cd6fd-102">Select Tables and Views (Data Feeds) (SSAS)</span></span>
  <span data-ttu-id="cd6fd-103">Questa pagina dell' **Importazione guidata tabella** consente di selezionare le tabelle e le viste da cui importare dati.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="cd6fd-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="cd6fd-105">L'aspetto delle tabelle e delle viste in questa pagina non garantisce che l'importazione verrà completata.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="cd6fd-106">Se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal database selezionato, l'importazione non verrà completata.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="cd6fd-107">Per origini dati in cui viene utilizzata l'autenticazione di Windows, le credenziali dell'utente corrente vengono utilizzate per recuperare le tabelle e le viste nella finestra di dialogo Selezione tabelle e viste.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="cd6fd-108">Per altre origini dati, vengono utilizzate le credenziali fornite nella stringa di connessione per il recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="cd6fd-109">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="cd6fd-109">UI element list</span></span>  
 <span data-ttu-id="cd6fd-110">**URL feed di dati**</span><span class="sxs-lookup"><span data-stu-id="cd6fd-110">**Data feed URL**</span></span>  
 <span data-ttu-id="cd6fd-111">Viene visualizzato l'URL per il feed di dati selezionato.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-111">Displays the URL for the data feed that you selected.</span></span>  
  
 <span data-ttu-id="cd6fd-112">**Tabelle e viste**</span><span class="sxs-lookup"><span data-stu-id="cd6fd-112">**Tables and views**</span></span>  
 <span data-ttu-id="cd6fd-113">Elenca le tabelle e le viste nel feed di dati.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-113">Lists the tables and views in the data feed.</span></span> <span data-ttu-id="cd6fd-114">Selezionare la casella di controllo accanto a ciascuna tabella e visualizzare la tabella che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-114">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="cd6fd-115">**Tabella di origine**</span><span class="sxs-lookup"><span data-stu-id="cd6fd-115">**Source Table**</span></span>  
 <span data-ttu-id="cd6fd-116">Specifica il nome della tabella di origine in base al tipo di origine dati.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-116">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="cd6fd-117">**Nome descrittivo**</span><span class="sxs-lookup"><span data-stu-id="cd6fd-117">**Friendly Name**</span></span>  
 <span data-ttu-id="cd6fd-118">Specifica il nome descrittivo della tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-118">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="cd6fd-119">Per impostazione predefinita, nella colonna viene visualizzato il nome della tabella di origine presente nella colonna **Tabella di origine** .</span><span class="sxs-lookup"><span data-stu-id="cd6fd-119">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span>  
  
 <span data-ttu-id="cd6fd-120">**Dettagli filtro**</span><span class="sxs-lookup"><span data-stu-id="cd6fd-120">**Filter Details**</span></span>  
 <span data-ttu-id="cd6fd-121">Visualizza il filtro per l'importazione dei dati nella finestra di dialogo **Dettagli filtro**, se è stato applicato un filtro ai dati importati.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-121">Displays the data import filter in the **Filter Details** dialog box, when a filter has been applied to the data that is being imported.</span></span> <span data-ttu-id="cd6fd-122">Per altre informazioni, vedere [Dettagli filtro &#40;DAX&#41;](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="cd6fd-122">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="cd6fd-123">**Visualizza anteprima e applica filtro**</span><span class="sxs-lookup"><span data-stu-id="cd6fd-123">**Preview and Filter**</span></span>  
 <span data-ttu-id="cd6fd-124">Visualizza la finestra di dialogo **Anteprima tabella selezionata** usata per applicare un filtro ai dati importati.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-124">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="cd6fd-125">Per altre informazioni, vedere [Anteprima tabella selezionata &#40;SSAS&#41;](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="cd6fd-125">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="cd6fd-126">**Seleziona tabelle correlate**</span><span class="sxs-lookup"><span data-stu-id="cd6fd-126">**Select Related Tables**</span></span>  
 <span data-ttu-id="cd6fd-127">Consente di selezionare le tabelle correlate alle tabelle e alle viste specificate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="cd6fd-127">Select tables that are related to the tables and views that you have selected.</span></span>  
  
  
