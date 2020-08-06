---
title: Caricare dati tramite la destinazione ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 339ec0a8-922e-48c0-97b3-fc5ee34f95e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8bf0b30619c2886df6ddb28858cf98bad858421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715619"
---
# <a name="load-data-by-using-the-odbc-destination"></a><span data-ttu-id="3d8b2-102">Caricare dati tramite la destinazione ODBC</span><span class="sxs-lookup"><span data-stu-id="3d8b2-102">Load Data by Using the ODBC Destination</span></span>
  <span data-ttu-id="3d8b2-103">In questa procedura viene descritto come caricare dati tramite la destinazione ODBC.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-103">This procedure shows how to load data by using the ODBC destination.</span></span> <span data-ttu-id="3d8b2-104">Per aggiungere e configurare una destinazione ODBC, è necessario che il pacchetto includa già almeno un'attività Flusso di dati e un'origine.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-104">To add and configure an ODBC destination, the package must already include at least one Data Flow task and source.</span></span>  
  
### <a name="to-load-data-using-an-odbc-destination"></a><span data-ttu-id="3d8b2-105">Per caricare dati tramite una destinazione ODBC</span><span class="sxs-lookup"><span data-stu-id="3d8b2-105">To load data using an ODBC destination</span></span>  
  
1.  <span data-ttu-id="3d8b2-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]aprire il pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] desiderato.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="3d8b2-107">Fare clic sulla scheda **Flusso di dati** e quindi trascinare la destinazione ODBC dalla **Casella degli strumenti**all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC destination to the design surface.</span></span>  
  
3.  <span data-ttu-id="3d8b2-108">Trascinare un output disponibile di un componente flusso di dati nell'input della destinazione ODBC.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-108">Drag an available output of a data flow component to the input of the ODBC destination.</span></span>  
  
4.  <span data-ttu-id="3d8b2-109">Fare doppio clic sulla destinazione ODBC.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-109">Double-click the ODBC destination.</span></span>  
  
5.  <span data-ttu-id="3d8b2-110">Nella pagina **Gestione connessione** della finestra di dialogo **Editor destinazione ODBC** selezionare una gestione connessione ODBC esistente oppure fare clic su **Nuova** per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-110">In the **ODBC Destination Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
6.  <span data-ttu-id="3d8b2-111">Selezionare il metodo di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-111">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="3d8b2-112">**Nome tabella - Batch**: selezionare questa opzione per configurare la destinazione ODBC per l'utilizzo della modalità batch.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-112">**Table Name - Batch**: Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="3d8b2-113">Quando si seleziona questa opzione, è possibile impostare un valore per **Dimensioni batch**.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-113">When you select this option, you can set the **Batch size**.</span></span>  
  
    -   <span data-ttu-id="3d8b2-114">**Nome tabella - Riga per riga**: selezionare questa opzione per configurare la destinazione ODBC per l'inserimento di una riga per volta nella tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-114">**Table Name - Row by Row**: Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="3d8b2-115">Quando si seleziona questa opzione, i dati vengono caricati una riga per volta nella tabella.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-115">When you select this option, the data is loaded into the table one row at a time.</span></span>  
  
7.  <span data-ttu-id="3d8b2-116">Nel campo **Nome tabella o vista** selezionare una tabella o una vista disponibile del database dall'elenco o digitare un'espressione regolare per identificare la tabella. Questo elenco contiene solo le prime 1000 tabelle.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-116">In the **Name of the table or the view** field, select an available table or view from the database from the list or type in a regular expression to identify the table.This list contains the first 1000 tables only.</span></span> <span data-ttu-id="3d8b2-117">Se il database contiene più di 1000 tabelle, è possibile digitare l'inizio di un nome di tabella o utilizzare il carattere jolly (\*) per immettere qualsiasi parte del nome e visualizzare la tabella o le tabelle che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-117">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
8.  <span data-ttu-id="3d8b2-118">È possibile fare clic su **Anteprima** per visualizzare fino a 200 righe dei dati della tabella selezionata nella destinazione ODBC.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-118">You can click **Preview** to view up to 200 rows of the data from the table selected in the ODBC destination.</span></span>  
  
9. <span data-ttu-id="3d8b2-119">Fare clic su **Mapping** e quindi eseguire il mapping delle colonne nell'elenco **Colonne di input disponibili** alle colonne nell'elenco **Colonne di destinazione disponibili** , trascinando le colonne da un elenco all'altro.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-119">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
10. <span data-ttu-id="3d8b2-120">Per configurare l'output degli errori, fare clic su **Output errori**.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-120">To configure the error output, click **Error Output**.</span></span>  
  
11. <span data-ttu-id="3d8b2-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d8b2-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="3d8b2-122">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="3d8b2-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d8b2-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d8b2-123">See Also</span></span>  
 <span data-ttu-id="3d8b2-124">[Editor destinazione ODBC &#40;pagina Gestione connessione&#41;](../odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="3d8b2-124">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="3d8b2-125">[Editor destinazione ODBC &#40;pagina Mapping&#41;](../odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="3d8b2-125">[ODBC Destination Editor &#40;Mappings Page&#41;](../odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="3d8b2-126">Editor origine ODBC &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="3d8b2-126">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
