---
title: Modificare i mapping di filtri tabella, colonna o riga (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2124c526-5772-4f84-a019-9dd3e906e8dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: d8a597fb51804ea12caace63f3308b07bffc5899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627411"
---
# <a name="change-table-column-or-row-filter-mappings-ssas-tabular"></a><span data-ttu-id="95a2f-102">Modificare i mapping di filtri tabella, colonna o riga (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="95a2f-102">Change table, column, or row filter mappings (SSAS Tabular)</span></span>
  <span data-ttu-id="95a2f-103">Questo argomento descrive come modificare i mapping di filtri tabella, colonna o riga tramite la finestra di dialogo **Modifica proprietà tabella** di [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="95a2f-103">This topic describes how to change table, column, or row filter mappings by using the **Edit Table Properties** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
 <span data-ttu-id="95a2f-104">Le opzioni disponibili nella finestra di dialogo **Modifica proprietà tabella** sono diverse, a seconda che i dati siano stati originariamente importati selezionando tabelle da un elenco o usando una query SQL.</span><span class="sxs-lookup"><span data-stu-id="95a2f-104">Options in the **Edit Table Properties** dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span> <span data-ttu-id="95a2f-105">Se i dati sono stati originariamente importati selezionandoli da un elenco, nella finestra di dialogo **Modifica proprietà tabella** viene visualizzata la modalità Anteprima tabella.</span><span class="sxs-lookup"><span data-stu-id="95a2f-105">If you originally imported the data by selecting from a list, the **Edit Table Properties** dialog box displays the Table Preview mode.</span></span> <span data-ttu-id="95a2f-106">Questa modalità consente di visualizzare solo un subset limitato alle prime cinquanta righe della tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="95a2f-106">This mode displays only a subset limited to the first fifty rows of the source table.</span></span> <span data-ttu-id="95a2f-107">Se i dati sono stati originariamente importati usando un'istruzione SQL, nella finestra di dialogo **Modifica proprietà tabella** viene visualizzata solo un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="95a2f-107">If you originally imported the data by using a SQL statement, the **Edit Table Properties** dialog box only displays a SQL statement.</span></span> <span data-ttu-id="95a2f-108">Utilizzando un'istruzione di query SQL è possibile recuperare un subset di righe progettando un filtro o modificando manualmente l'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="95a2f-108">Using a SQL query statement, you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="95a2f-109">Se per l'origine si imposta una tabella con colonne diverse rispetto alla tabella corrente, viene visualizzato un messaggio indicante che le colonne sono diverse.</span><span class="sxs-lookup"><span data-stu-id="95a2f-109">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="95a2f-110">Sarà necessario quindi selezionare le colonne che si desidera inserire nella tabella corrente e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="95a2f-110">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="95a2f-111">Selezionando la casella di controllo a sinistra della tabella è possibile sostituire l'intera tabella.</span><span class="sxs-lookup"><span data-stu-id="95a2f-111">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95a2f-112">Se nella tabella è presente più di una partizione, non è possibile utilizzare la finestra di dialogo Modifica proprietà tabella per modificare i mapping del filtro di riga.</span><span class="sxs-lookup"><span data-stu-id="95a2f-112">If your table has more than one partition, you cannot use the Edit Table Properties dialog box to change row filter mappings.</span></span> <span data-ttu-id="95a2f-113">Per modificare i mapping del filtro di riga per le tabelle con più partizioni, utilizzare Gestione partizioni.</span><span class="sxs-lookup"><span data-stu-id="95a2f-113">To change row filter mappings for tables with multiple partitions, use Partition Manager.</span></span> <span data-ttu-id="95a2f-114">Per altre informazioni, vedere [Partizioni &#40;SSAS tabulare&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="95a2f-114">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-change-table-column-or-row-filter-mappings"></a><span data-ttu-id="95a2f-115">Per modificare i mapping dei filtri tabella, colonna o riga</span><span class="sxs-lookup"><span data-stu-id="95a2f-115">To change table, column, or row filter mappings</span></span>  
  
1.  <span data-ttu-id="95a2f-116">In Progettazione modelli fare clic su una tabella e quindi scegliere **Proprietà tabella** dal menu **Tabella**.</span><span class="sxs-lookup"><span data-stu-id="95a2f-116">In the model designer, click the table, then click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="95a2f-117">Nella finestra di dialogo **Modifica proprietà tabella** individuare la colonna in cui sono contenuti i criteri in base ai quali si vuole filtrare e quindi fare clic sulla freccia GIÙ a destra dell'intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="95a2f-117">In the **Edit Table Properties** dialog box, locate the column that contains the criteria you want to filter on, and then click the down arrow at the right of the column heading.</span></span>  
  
3.  <span data-ttu-id="95a2f-118">Nel menu **Filtro automatico** effettuare uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="95a2f-118">In the **AutoFilter** menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="95a2f-119">Nell'elenco di valori delle colonne selezionare o deselezionare uno o più valori da utilizzare come filtri, quindi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="95a2f-119">In the list of column values, select or clear one or more values to filter by, and then click OK.</span></span>  
  
         <span data-ttu-id="95a2f-120">Se il numero di valori è estremamente elevato, singoli elementi potrebbero non essere visualizzati nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="95a2f-120">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="95a2f-121">Verrà invece visualizzato il messaggio, "Troppi elementi da visualizzare".</span><span class="sxs-lookup"><span data-stu-id="95a2f-121">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="95a2f-122">Fare clic su **Filtri per numeri** o su **Filtri per testo** (a seconda del tipo di colonna) e quindi fare clic su uno dei comandi di operatore di confronto (ad esempio Uguale a) o su Filtro personalizzato.</span><span class="sxs-lookup"><span data-stu-id="95a2f-122">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as Equals), or click Custom Filter.</span></span> <span data-ttu-id="95a2f-123">Nella finestra di dialogo **Filtro personalizzato** creare il filtro, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="95a2f-123">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
         <span data-ttu-id="95a2f-124">Se si commette un errore ed è necessario ricominciare, fare clic su **Cancella filtri di riga**.</span><span class="sxs-lookup"><span data-stu-id="95a2f-124">If you make a mistake and need to start over, click **Clear Row Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95a2f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95a2f-125">See Also</span></span>  
 [<span data-ttu-id="95a2f-126">Finestra di dialogo Modifica proprietà tabella &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="95a2f-126">Edit Table Properties Dialog Box &#40;SSAS&#41;</span></span>](../edit-table-properties-dialog-box-ssas.md)  
  
  
