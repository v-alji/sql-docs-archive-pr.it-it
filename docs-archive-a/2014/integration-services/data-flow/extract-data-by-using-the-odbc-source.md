---
title: Estrarre dati tramite l'origine ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 10f25703-49a2-4d45-abab-6b4da2a57ba5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c05efe2b0479047280fc093ee555e037c77d82e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726112"
---
# <a name="extract-data-by-using-the-odbc-source"></a><span data-ttu-id="874f1-102">Estrarre dati tramite l'origine ODBC</span><span class="sxs-lookup"><span data-stu-id="874f1-102">Extract Data by Using the ODBC Source</span></span>
  <span data-ttu-id="874f1-103">In questa procedura viene descritto come estrarre dati utilizzando un'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="874f1-103">This procedure describes how to extract data by using an ODBC source.</span></span> <span data-ttu-id="874f1-104">Per aggiungere e configurare un'origine ODBC, è necessario che il pacchetto includa già almeno un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="874f1-104">To add and configure an ODBC source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-odbc-source"></a><span data-ttu-id="874f1-105">Per estrarre dati tramite un'origine ODBC</span><span class="sxs-lookup"><span data-stu-id="874f1-105">To extract data using an ODBC source</span></span>  
  
1.  <span data-ttu-id="874f1-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]aprire il pacchetto di [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] desiderato.</span><span class="sxs-lookup"><span data-stu-id="874f1-106">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="874f1-107">Fare clic sulla scheda **Flusso di dati** e quindi trascinare l'origine ODBC dalla **Casella degli strumenti**all'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="874f1-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the ODBC source to the design surface.</span></span>  
  
3.  <span data-ttu-id="874f1-108">Fare doppio clic sull'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="874f1-108">Double-click the ODBC source.</span></span>  
  
4.  <span data-ttu-id="874f1-109">Nella pagina **Gestione connessione** della finestra di dialogo **Editor origine ODBC** selezionare una gestione connessione ODBC esistente oppure fare clic su **Nuova** per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="874f1-109">In the **ODBC Source Editor** dialog box, on the **Connection Manager** page, select an existing ODBC connection manager or click **New** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="874f1-110">Selezionare il metodo di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="874f1-110">Select the data access method.</span></span>  
  
    -   <span data-ttu-id="874f1-111">**Nome tabella**: selezionare una tabella o una vista nel database o digitare un'espressione regolare per identificare la tabella a cui è connessa la gestione connessione ODBC.</span><span class="sxs-lookup"><span data-stu-id="874f1-111">**Table Name**: Select a table or view in the database or type a regular expression to identify the table to which the ODBC connection manager connects.</span></span>  
  
         <span data-ttu-id="874f1-112">Questo elenco contiene solo le prime 1000 tabelle.</span><span class="sxs-lookup"><span data-stu-id="874f1-112">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="874f1-113">Se il database contiene più di 1000 tabelle, è possibile digitare l'inizio di un nome di tabella o utilizzare il carattere jolly (\*) per immettere qualsiasi parte del nome e visualizzare la tabella o le tabelle che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="874f1-113">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>  
  
    -   <span data-ttu-id="874f1-114">**Comando SQL**: digitare un comando SQL o fare clic su **Sfoglia** per caricare la query SQL da un file di testo.</span><span class="sxs-lookup"><span data-stu-id="874f1-114">**SQL Command**: Type an SQL Command or click **Browse** to load the SQL query from a text file.</span></span>  
  
6.  <span data-ttu-id="874f1-115">È possibile fare clic su **Anteprima** per visualizzare fino a 200 righe dei dati estratti dall'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="874f1-115">You can click **Preview** to view up to 200 rows of the data extracted by the ODBC source.</span></span>  
  
7.  <span data-ttu-id="874f1-116">Per aggiornare il mapping tra colonne esterne e colonne di output, fare clic su **Colonne** e selezionare colonne diverse nell'elenco **Colonna esterna** .</span><span class="sxs-lookup"><span data-stu-id="874f1-116">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="874f1-117">Se necessario, aggiornare i nomi delle colonne di output modificando i valori nell'elenco **Colonna di output** .</span><span class="sxs-lookup"><span data-stu-id="874f1-117">If necessary, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="874f1-118">Per configurare l'output degli errori, fare clic su **Output errori**.</span><span class="sxs-lookup"><span data-stu-id="874f1-118">To configure the error output, click **Error Output**.</span></span>  
  
10. <span data-ttu-id="874f1-119">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="874f1-119">Click **OK**.</span></span>  
  
11. <span data-ttu-id="874f1-120">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="874f1-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="874f1-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="874f1-121">See Also</span></span>  
 <span data-ttu-id="874f1-122">[Editor origine ODBC &#40;pagina Gestione connessione&#41;](../odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="874f1-122">[ODBC Source Editor &#40;Connection Manager Page&#41;](../odbc-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="874f1-123">[Editor origine ODBC &#40;pagina Colonne&#41;](../odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="874f1-123">[ODBC Source Editor &#40;Columns Page&#41;](../odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="874f1-124">Editor origine ODBC &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="874f1-124">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
  
