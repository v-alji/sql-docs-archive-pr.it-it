---
title: Aggiungere una tabella (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d713c432-db99-4983-acc1-52b0fdd58bd6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80c22c992a89ed2cb3db84809b47a7cd08cb514
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635740"
---
# <a name="add-a-table-ssas-tabular"></a><span data-ttu-id="e62c1-102">Aggiungere una tabella (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="e62c1-102">Add a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="e62c1-103">In questo argomento verrà illustrato come aggiungere una tabella da un'origine dati dalla quale sono stati importati precedentemente i dati nel modello.</span><span class="sxs-lookup"><span data-stu-id="e62c1-103">This topic describes how to add a table from a data source from which you have previously imported data into your model.</span></span> <span data-ttu-id="e62c1-104">Per aggiungere una tabella dalla stessa origine dati, è possibile utilizzare la connessione all'origine dati esistente.</span><span class="sxs-lookup"><span data-stu-id="e62c1-104">To add a table from the same data source, you can use the existing data source connection.</span></span> <span data-ttu-id="e62c1-105">È consigliabile utilizzare sempre una sola connessione in caso di importazione di un qualsiasi numero di tabelle da un'unica origine dati.</span><span class="sxs-lookup"><span data-stu-id="e62c1-105">It is recommended you always use a single connection when importing any number of tables from a single data source.</span></span>  
  
### <a name="to-add-a-table-from-an-existing-data-source"></a><span data-ttu-id="e62c1-106">Per aggiungere una tabella da un'origine dati esistente</span><span class="sxs-lookup"><span data-stu-id="e62c1-106">To add a table from an existing data source</span></span>  
  
1.  <span data-ttu-id="e62c1-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]scegliere **Connessioni esistenti** dal menu **Modello**.</span><span class="sxs-lookup"><span data-stu-id="e62c1-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="e62c1-108">Nella pagina **Connessioni esistenti** selezionare la connessione all'origine dati contenente la tabella da aggiungere, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="e62c1-108">On the **Existing Connections** page, select the connection to the data source that has the table you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="e62c1-109">Nella pagina **Selezione tabelle e viste** selezionare la tabella dall'origine dati che si desidera aggiungere al modello.</span><span class="sxs-lookup"><span data-stu-id="e62c1-109">On the **Select Tables and Views** page, select the table from the data source you want to add to your model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e62c1-110">Nella pagina **Selezione tabelle e viste** non verranno mostrate le tabelle importate in precedenza come selezionate.</span><span class="sxs-lookup"><span data-stu-id="e62c1-110">The **Select Tables and Views** page will not show tables that were previously imported as checked.</span></span>  <span data-ttu-id="e62c1-111">Se si seleziona una tabella che è stata precedentemente importata tramite questa connessione e a cui non è stato assegnato un nome descrittivo diverso, verrà accodato 1 al nome utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e62c1-111">If you select a table that was previously imported using this connection, and you did not give the table a different friendly name, a 1 will be appended to the friendly name.</span></span> <span data-ttu-id="e62c1-112">Non è necessario selezionare di nuovo tutte le tabelle importate precedentemente tramite questa connessione.</span><span class="sxs-lookup"><span data-stu-id="e62c1-112">You do not need to re-select any tables that were previously imported by using this connection.</span></span>  
  
4.  <span data-ttu-id="e62c1-113">Se necessario, usare **Visualizza anteprima e applica filtro** per selezionare solo determinate colonne o per applicare filtri ai dati da importare.</span><span class="sxs-lookup"><span data-stu-id="e62c1-113">If necessary, use **Preview & Filter** to select only certain columns or apply filters to the data to be imported.</span></span>  
  
5.  <span data-ttu-id="e62c1-114">Fare clic su **Fine** per importare la nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="e62c1-114">Click **Finish** to import the new table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e62c1-115">Se si importano più tabelle contemporaneamente da una sola origine dati, tutte le relazioni tra tali tabelle nell'origine saranno create automaticamente nel modello.</span><span class="sxs-lookup"><span data-stu-id="e62c1-115">When importing multiple tables at the same time from a single data source, any relationships between those tables at the source will automatically be created in the model.</span></span> <span data-ttu-id="e62c1-116">In caso di aggiunta di una tabella in un secondo momento, potrebbe essere tuttavia necessario creare manualmente le relazioni nel modello tra le tabelle appena aggiunte e quelle importate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e62c1-116">When adding a table later; however, you may need to manually create relationships in the model between newly added tables and the tables that were previously imported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e62c1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e62c1-117">See Also</span></span>  
 <span data-ttu-id="e62c1-118">[Importare dati &#40;SSAS tabulare&#41;](../import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="e62c1-118">[Import Data &#40;SSAS Tabular&#41;](../import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="e62c1-119">Eliminare una tabella &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="e62c1-119">Delete a Table &#40;SSAS Tabular&#41;</span></span>](delete-a-table-ssas-tabular.md)  
  
  
