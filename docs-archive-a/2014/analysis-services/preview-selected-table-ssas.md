---
title: Anteprima tabella selezionata (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.previewselecttable.f1
ms.assetid: b6b34b5a-43b3-4a75-9f3b-b2ad1084b1b6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25eb4d4424223449052ab1f65b41cf270da81fb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725056"
---
# <a name="preview-selected-table-ssas"></a><span data-ttu-id="a89eb-102">Anteprima tabella selezionata (SSAS)</span><span class="sxs-lookup"><span data-stu-id="a89eb-102">Preview Selected Table (SSAS)</span></span>
  <span data-ttu-id="a89eb-103">Questa pagina dell' **Importazione guidata tabella** consente di visualizzare in anteprima i dati nella tabella selezionata, selezionare le colonne da includere nell'importazione dei dati e filtrare i dati nelle colonne selezionate.</span><span class="sxs-lookup"><span data-stu-id="a89eb-103">This page of the **Table Import Wizard** enables you to preview the data in the selected table, to select the columns to include in the data import, and to filter data in the selected columns.</span></span> <span data-ttu-id="a89eb-104">Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.</span><span class="sxs-lookup"><span data-stu-id="a89eb-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="a89eb-105">Non vengono visualizzate tutte le righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="a89eb-105">Not all the rows in the table are displayed.</span></span> <span data-ttu-id="a89eb-106">Tuttavia, i filtri impostati verranno applicati a tutti i dati presenti nella tabella durante l'importazione.</span><span class="sxs-lookup"><span data-stu-id="a89eb-106">However, the filters that you set will be applied to all of the data in the table during import.</span></span>  
  
 <span data-ttu-id="a89eb-107">Per origini dati in cui viene utilizzata l'autenticazione di Windows, le credenziali dell'utente corrente vengono utilizzate per recuperare i dati visualizzati nella finestra di dialogo Visualizza anteprima e applica filtro.</span><span class="sxs-lookup"><span data-stu-id="a89eb-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the data displayed in the Preview and Filter dialog.</span></span> <span data-ttu-id="a89eb-108">Per altre origini dati, vengono utilizzate le credenziali fornite nella stringa di connessione per il recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="a89eb-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
 <span data-ttu-id="a89eb-109">L'aspetto dei dati in questa pagina non garantisce che l'importazione verrà completata.</span><span class="sxs-lookup"><span data-stu-id="a89eb-109">The appearance of data on this page does not guarantee import will succeed.</span></span> <span data-ttu-id="a89eb-110">Se il nome utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal database selezionato, l'importazione non verrà completata.</span><span class="sxs-lookup"><span data-stu-id="a89eb-110">If the user name specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a89eb-111">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a89eb-111">UI element list</span></span>  
 <span data-ttu-id="a89eb-112">**Casella di controllo nell'intestazione di colonna**</span><span class="sxs-lookup"><span data-stu-id="a89eb-112">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="a89eb-113">Selezionare la casella di controllo per includere la colonna nell'importazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="a89eb-113">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="a89eb-114">Deselezionare la casella di controllo per rimuovere la colonna dall'importazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="a89eb-114">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="a89eb-115">**Pulsante freccia in giù nell'intestazione di colonna**</span><span class="sxs-lookup"><span data-stu-id="a89eb-115">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="a89eb-116">Consente di filtrare i dati nella colonna.</span><span class="sxs-lookup"><span data-stu-id="a89eb-116">Filter data in the column.</span></span>  
  
 <span data-ttu-id="a89eb-117">**Cancella filtri di riga**</span><span class="sxs-lookup"><span data-stu-id="a89eb-117">**Clear Row Filters**</span></span>  
 <span data-ttu-id="a89eb-118">Consente di rimuovere tutti i filtri applicati ai dati nelle colonne.</span><span class="sxs-lookup"><span data-stu-id="a89eb-118">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
