---
title: Modificare una connessione all'origine dati esistente (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.selexistconn.f1
ms.assetid: 97e63f18-a01d-4c91-a411-e7e6d40a0647
author: minewiskan
ms.author: owend
ms.openlocfilehash: 675a0d1119e25a92231d3e74a79739cb2e96b6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636453"
---
# <a name="edit-an-existing-data-source-connection-ssas-tabular"></a><span data-ttu-id="b229d-102">Modificare una connessione all'origine dati esistente (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="b229d-102">Edit an Existing Data Source Connection (SSAS Tabular)</span></span>
  <span data-ttu-id="b229d-103">In questo argomento viene descritto come modificare le proprietà di una connessione all'origine dati esistente in un modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="b229d-103">This topic describes how to edit the properties of an existing data source connection in a tabular model.</span></span>  
  
 <span data-ttu-id="b229d-104">Dopo aver creato una connessione a un'origine dati esterna, è possibile modificarla in un secondo momento nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b229d-104">After you have created a connection to an external data source, you can later modify that connection in these ways:</span></span>  
  
-   <span data-ttu-id="b229d-105">È possibile modificare le informazioni di connessione, inclusi il file, il feed o il database utilizzato come origine, le rispettive proprietà o le altre opzioni di connessione specifiche del provider.</span><span class="sxs-lookup"><span data-stu-id="b229d-105">You can change the connection information, including the file, feed, or database used as a source, its properties, or other provider-specific connection options.</span></span>  
  
-   <span data-ttu-id="b229d-106">È possibile modificare i mapping di colonne e tabelle e rimuovere i riferimenti alle colonne che non vengono più utilizzate.</span><span class="sxs-lookup"><span data-stu-id="b229d-106">You can change table and column mappings, and remove references to columns that are no longer used.</span></span>  
  
-   <span data-ttu-id="b229d-107">È possibile modificare le tabelle, le viste o le colonne ottenute dall'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="b229d-107">You can change the tables, views, or columns that you get from the external data source.</span></span>  
  
## <a name="modify-a-connection"></a><span data-ttu-id="b229d-108">Modificare una connessione</span><span class="sxs-lookup"><span data-stu-id="b229d-108">Modify a Connection</span></span>  
 <span data-ttu-id="b229d-109">In questa procedura viene descritto come modificare una connessione all'origine dati di un database.</span><span class="sxs-lookup"><span data-stu-id="b229d-109">This procedure describes how to modify a database data source connection.</span></span> <span data-ttu-id="b229d-110">Alcune opzioni per l'utilizzo delle origini dati differiscono in base al tipo di origine dati; tuttavia, si dovrebbe essere in grado di identificare facilmente tali differenze.</span><span class="sxs-lookup"><span data-stu-id="b229d-110">Some options for working with data sources differ depending on the data source type; however, you should be able to easily identify those differences.</span></span>  
  
#### <a name="to-change-the-external-data-source-used-by-a-current-connection"></a><span data-ttu-id="b229d-111">Per modificare l'origine dati esterna utilizzata da una connessione corrente</span><span class="sxs-lookup"><span data-stu-id="b229d-111">To change the external data source used by a current connection</span></span>  
  
1.  <span data-ttu-id="b229d-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]scegliere **Connessioni esistenti** dal menu **Modello**.</span><span class="sxs-lookup"><span data-stu-id="b229d-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="b229d-113">Selezionare la connessione all'origine dati che si desidera modificare, quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b229d-113">Select the data source connection you want to modify, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="b229d-114">Nella finestra di dialogo **Modifica connessione** fare clic su **Sfoglia** per individuare un altro database dello stesso tipo ma con un nome o un percorso diverso.</span><span class="sxs-lookup"><span data-stu-id="b229d-114">In the **Edit Connection** dialog box, click **Browse** to locate another database of the same type but with a different name or location.</span></span>  
  
     <span data-ttu-id="b229d-115">Appena si modifica il file di database, viene visualizzato un messaggio che indica la necessità di salvare e aggiornare le tabelle per visualizzare i nuovi dati.</span><span class="sxs-lookup"><span data-stu-id="b229d-115">As soon as you change the database file, a message appears indicating that you need to save and refresh the tables in order to see the new data.</span></span>  
  
4.  <span data-ttu-id="b229d-116">Fare clic su **Salva**, quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b229d-116">Click **Save**, and then click **Close**.</span></span>  
  
5.  <span data-ttu-id="b229d-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]fare clic su **Modello**, selezionare **Elabora**, quindi scegliere **Elabora tutto**.</span><span class="sxs-lookup"><span data-stu-id="b229d-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model**, click **Process**, and then click **Process All**.</span></span>  
  
     <span data-ttu-id="b229d-118">Le tabelle vengono elaborate nuovamente utilizzando la nuova origine dati ma con le selezioni dei dati originali.</span><span class="sxs-lookup"><span data-stu-id="b229d-118">The tables are re-processed using the new data source, but with the original data selections.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b229d-119">Se nella nuova origine dati sono incluse le tabelle aggiuntive che non erano presenti nell'origine dati originale, è necessario aprire nuovamente la connessione modificata e aggiungere le tabelle.</span><span class="sxs-lookup"><span data-stu-id="b229d-119">If the new data source contains any additional tables that were not present in the original data source, you must re-open the changed connection and add the tables.</span></span>  
  
## <a name="edit-table-and-column-mappings-bindings"></a><span data-ttu-id="b229d-120">Modificare i mapping (associazioni) di tabelle e colonne</span><span class="sxs-lookup"><span data-stu-id="b229d-120">Edit Table and Column Mappings (Bindings)</span></span>  
 <span data-ttu-id="b229d-121">In questa procedura viene descritto come modificare i mapping dopo avere modificato un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="b229d-121">This procedure describes how to edit the mappings after you change a data source.</span></span>  
  
#### <a name="to-edit-column-mappings-when-a-data-source-changes"></a><span data-ttu-id="b229d-122">Per modificare i mapping delle colonne quando viene modificata un'origine dati</span><span class="sxs-lookup"><span data-stu-id="b229d-122">To edit column mappings when a data source changes</span></span>  
  
1.  <span data-ttu-id="b229d-123">In Progettazione modelli selezionare una tabella.</span><span class="sxs-lookup"><span data-stu-id="b229d-123">In the model designer, select a table.</span></span>  
  
2.  <span data-ttu-id="b229d-124">Fare clic sul menu **Tabella** , quindi scegliere **Proprietà tabella**.</span><span class="sxs-lookup"><span data-stu-id="b229d-124">Click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
     <span data-ttu-id="b229d-125">Il nome della tabella selezionata viene visualizzato nella casella **Nome tabella** .</span><span class="sxs-lookup"><span data-stu-id="b229d-125">The name of the selected table is displayed in the **Table Name** box.</span></span> <span data-ttu-id="b229d-126">Nella casella **Nome origine** è presente il nome della tabella dell'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="b229d-126">The **Source Name** box contains the name of the table in the external data source.</span></span> <span data-ttu-id="b229d-127">Se le colonne sono denominate in modo diverso nell'origine e nel modello, è possibile attivare alternativamente i due set di nomi di colonna selezionando le opzioni **Origine** o **Modello**.</span><span class="sxs-lookup"><span data-stu-id="b229d-127">If columns are named differently in the source and in the model, you can toggle between the two sets of column names by selecting the options **Source** or **Model**.</span></span>  
  
3.  <span data-ttu-id="b229d-128">Per modificare la tabella utilizzata come origine dati, per **Nome origine**selezionare una tabella diversa da quella corrente.</span><span class="sxs-lookup"><span data-stu-id="b229d-128">To change the table that is used as a data source, for **Source Name**, select a different table than the current one.</span></span>  
  
4.  <span data-ttu-id="b229d-129">Modificare i mapping delle colonne, se necessario:</span><span class="sxs-lookup"><span data-stu-id="b229d-129">Change column mappings if needed:</span></span>  
  
    1.  <span data-ttu-id="b229d-130">Per aggiungere colonne che sono presenti nell'origine ma non nel modello, selezionare la casella di controllo accanto al nome della colonna.</span><span class="sxs-lookup"><span data-stu-id="b229d-130">To add columns that are present in the source but not in the model, select the checkbox beside the column name.</span></span>  
  
         <span data-ttu-id="b229d-131">I dati effettivi verranno caricati nel modello al successivo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b229d-131">The actual data will be loaded into the model the next time you refresh.</span></span>  
  
    2.  <span data-ttu-id="b229d-132">Se alcune colonne nel modello non sono più disponibili nell'origine dati corrente, viene visualizzato un messaggio nell'area di notifica in cui sono elencate le colonne non valide.</span><span class="sxs-lookup"><span data-stu-id="b229d-132">If some columns in the model are no longer available in the current data source, a message appears in the notification area that lists the invalid columns.</span></span> <span data-ttu-id="b229d-133">Non è necessario eseguire altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="b229d-133">You do not need to do anything else.</span></span>  
  
5.  <span data-ttu-id="b229d-134">Fare clic su **Salva** per applicare le modifiche al modello.</span><span class="sxs-lookup"><span data-stu-id="b229d-134">Click **Save** to apply the changes to your model.</span></span>  
  
     <span data-ttu-id="b229d-135">Quando si salva il set corrente di proprietà della tabella, è possibile che venga visualizzato un messaggio che indica la necessità di elaborare le tabelle.</span><span class="sxs-lookup"><span data-stu-id="b229d-135">When you save the current set of table properties, a message may appear indicating that you need to process the tables.</span></span> <span data-ttu-id="b229d-136">Fare clic su **Elabora** per caricare dati aggiornati nel modello.</span><span class="sxs-lookup"><span data-stu-id="b229d-136">Click **Process** to load updated data into your model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b229d-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b229d-137">See Also</span></span>  
 <span data-ttu-id="b229d-138">[Elaborare dati &#40;SSAS tabulare&#41;](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b229d-138">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="b229d-139">Origini dati supportate &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="b229d-139">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
