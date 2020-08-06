---
title: Esplorazione dei dati in una vista origine dati (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exploring data [Analysis Services]
- data source views [Analysis Services], exploring data
- viewing source data
ms.assetid: 2c922c35-fbcb-45b2-96b1-c7a846d8b419
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adf9edecd807158ba1d0de3287cccd6fa8dd787
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638118"
---
# <a name="explore-data-in-a-data-source-view-analysis-services"></a><span data-ttu-id="5f095-102">Esplorare dati in una vista origine dati (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="5f095-102">Explore Data in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="5f095-103">La finestra di dialogo **Esplora dati** in Progettazione vista origine dati di [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] consente di esplorare i dati di una tabella, una vista o una query denominata in una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="5f095-103">You can use the **Explore Data** dialog box in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to browse data for a table, view, or named query in a data source view (DSV).</span></span> <span data-ttu-id="5f095-104">Quando si esplorano i dati in Progettazione vista origine dati, è possibile visualizzare il contenuto di ogni colonna di dati in una tabella, una vista o una query denominata selezionata.</span><span class="sxs-lookup"><span data-stu-id="5f095-104">When you explore the data in Data Source View Designer, you can view the contents of each column of data in a selected table, view, or named query.</span></span> <span data-ttu-id="5f095-105">La visualizzazione del contenuto effettivo consente di determinare se sono necessarie tutte le colonne, se sono necessari calcoli denominati per incrementare la fruibilità e la facilità di utilizzo per gli utenti e se le query denominate o i calcoli denominati esistenti restituiscono i valori previsti.</span><span class="sxs-lookup"><span data-stu-id="5f095-105">Viewing the actual contents assists you in determining whether all columns are needed, if named calculations are required to increase user friendliness and usability, and whether existing named calculations or named queries return the anticipated values.</span></span>  
  
 <span data-ttu-id="5f095-106">Per visualizzare i dati, è necessario disporre di una connessione attiva alle origini dati per l'oggetto selezionato nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="5f095-106">To view data, you must have an active connection to the data source or sources for the selected object in the DSV.</span></span> <span data-ttu-id="5f095-107">Nella query vengono inviati anche i calcoli denominati contenuti in una tabella.</span><span class="sxs-lookup"><span data-stu-id="5f095-107">Any named calculations in a table are also sent in the query.</span></span>  
  
 <span data-ttu-id="5f095-108">I dati restituiti in un formato tabulare che è possibile ordinare e copiare.</span><span class="sxs-lookup"><span data-stu-id="5f095-108">The data returned in a tabular format that you can sort and copy.</span></span> <span data-ttu-id="5f095-109">Fare clic sull'intestazione di colonna per riordinare le righe in base alla colonna.</span><span class="sxs-lookup"><span data-stu-id="5f095-109">Click on the column headers to re-sort the rows by that column.</span></span> <span data-ttu-id="5f095-110">È anche possibile evidenziare i dati nella griglia e premere CTRL-C per copiare la selezione negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="5f095-110">You can also highlight data in the grid and press Ctrl-C to copy the selection to the clipboard.</span></span>  
  
 <span data-ttu-id="5f095-111">È inoltre possibile controllare il metodo di campionamento e il conteggio campione.</span><span class="sxs-lookup"><span data-stu-id="5f095-111">You can also control the sample method and the sample count.</span></span> <span data-ttu-id="5f095-112">Per impostazione predefinita, vengono restituite le prime 5000 righe.</span><span class="sxs-lookup"><span data-stu-id="5f095-112">By default, the top 5000 rows are returned.</span></span>  
  
## <a name="to-browse-data-or-change-sampling-options"></a><span data-ttu-id="5f095-113">Per esplorare i dati o modificare le opzioni di campionamento</span><span class="sxs-lookup"><span data-stu-id="5f095-113">To browse data or change sampling options</span></span>  
  
1.  <span data-ttu-id="5f095-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto o connettersi al database contenente la vista origine dati in cui si desidera esplorare i dati.</span><span class="sxs-lookup"><span data-stu-id="5f095-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to browse data.</span></span>  
  
2.  <span data-ttu-id="5f095-115">In Esplora soluzioni espandere la cartella **Viste origine dati** e quindi fare doppio clic sulla vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="5f095-115">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="5f095-116">Fare clic con il pulsante destro del mouse sulla tabella, sulla vista o sulla query denominata contenente i dati che si desidera visualizzare, quindi scegliere **Esplora dati**.</span><span class="sxs-lookup"><span data-stu-id="5f095-116">Right-click the table, view, or named query that contains the data you want to view, and then click **Explore Data**.</span></span>  
  
     <span data-ttu-id="5f095-117">L'origine dati sottostante la tabella, la vista o la query denominata nella vista origine dati è una query e i risultati vengono visualizzati nella scheda **Esplora \<object name> tabella** .</span><span class="sxs-lookup"><span data-stu-id="5f095-117">The data source underlying the table, view, or named query in the data source view are queries, and the results appear in the **Explore \<object name> Table** tab.</span></span>  
  
4.  <span data-ttu-id="5f095-118">Sulla barra degli strumenti **Esplora \<object name> tabella** fare clic sull'icona **Opzioni di campionamento** .</span><span class="sxs-lookup"><span data-stu-id="5f095-118">On the **Explore \<object name> Table** toolbar, click the **Sampling options** icon.</span></span>  
  
     <span data-ttu-id="5f095-119">Verrà visualizzata la finestra di dialogo **Opzioni di esplorazione dati** .</span><span class="sxs-lookup"><span data-stu-id="5f095-119">The **Data Exploration Options** dialog box opens.</span></span> <span data-ttu-id="5f095-120">In tale finestra di dialogo è possibile specificare il metodo di campionamento (un numero di record inferiore o superiore alla dimensione di campionamento predefinita pari a 5000 righe) o il conteggio campione.</span><span class="sxs-lookup"><span data-stu-id="5f095-120">In this dialog box you can specify the sampling method (fewer or more records than the default sampling size of 5000 rows), or sample count.</span></span>  
  
5.  <span data-ttu-id="5f095-121">Fare clic su **OK** o **Annulla** , a seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="5f095-121">Click **OK** or **Cancel** as appropriate.</span></span>  
  
6.  <span data-ttu-id="5f095-122">Per ricampionare i dati, fare clic su **Ricampiona dati** sulla barra degli strumenti della \*\* \<object name> tabella Esplora\*\* .</span><span class="sxs-lookup"><span data-stu-id="5f095-122">To resample the data, click **Resample Data** on the **Explore \<object name> Table** toolbar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f095-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f095-123">See Also</span></span>  
 [<span data-ttu-id="5f095-124">Viste origine dati in modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="5f095-124">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
