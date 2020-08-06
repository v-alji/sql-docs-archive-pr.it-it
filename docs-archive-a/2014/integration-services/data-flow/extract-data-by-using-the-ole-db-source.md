---
title: Estrarre i dati tramite l'origine OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], OLE DB
- OLE DB source [Integration Services]
ms.assetid: 4ca6eeb5-b60e-4b81-86dd-0674be8ae8d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 352d62cc66e3f17fb10839086e7ee9c5307f1a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726111"
---
# <a name="extract-data-by-using-the-ole-db-source"></a><span data-ttu-id="42f39-102">Estrazione dei dati tramite l'origine OLE DB</span><span class="sxs-lookup"><span data-stu-id="42f39-102">Extract Data by Using the OLE DB Source</span></span>
  <span data-ttu-id="42f39-103">È possibile aggiungere e configurare un'origine OLE DB solo se il pacchetto include già almeno un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="42f39-103">To add and configure an OLE DB source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-ole-db-source"></a><span data-ttu-id="42f39-104">Per estrarre dati tramite un'origine OLE DB</span><span class="sxs-lookup"><span data-stu-id="42f39-104">To extract data using an OLE DB Source</span></span>  
  
1.  <span data-ttu-id="42f39-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="42f39-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="42f39-106">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="42f39-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="42f39-107">Fare clic sulla scheda **Flusso di dati** e quindi dalla **Casella degli strumenti**trascinare l'origine OLE DB sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="42f39-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB source to the design surface.</span></span>  
  
4.  <span data-ttu-id="42f39-108">Fare doppio clic sull'origine OLE DB.</span><span class="sxs-lookup"><span data-stu-id="42f39-108">Double-click the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="42f39-109">Nella pagina **Gestione connessione** della finestra di dialogo **Editor origine OLE DB** selezionare una gestione connessione OLE DB esistente oppure fare clic su **Nuova** per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="42f39-109">In the **OLE DB Source Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="42f39-110">Per altre informazioni, vedere [Gestione connessione OLE DB](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="42f39-110">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
6.  <span data-ttu-id="42f39-111">Selezionare il metodo di accesso ai dati:</span><span class="sxs-lookup"><span data-stu-id="42f39-111">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="42f39-112">**Tabella o vista** Selezionare la tabella o vista del database a cui deve connettersi la gestione connessione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="42f39-112">**Table or view** Select a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="42f39-113">**Variabile nome vista o nome tabella** Selezionare la variabile definita dall'utente che contiene il nome della tabella o vista del database a cui deve connettersi la gestione connessione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="42f39-113">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database to which the OLE DB connection manager connects.</span></span>  
  
    -   <span data-ttu-id="42f39-114">**Comando SQL** Digitare un comando SQL oppure fare clic su **Compila query** per scrivere un comando SQL usando **Generatore query**.</span><span class="sxs-lookup"><span data-stu-id="42f39-114">**SQL command** Type an SQL command or click **Build Query** to write an SQL command using the **Query Builder**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="42f39-115">Il comando può includere parametri.</span><span class="sxs-lookup"><span data-stu-id="42f39-115">The command can include parameters.</span></span> <span data-ttu-id="42f39-116">Per altre informazioni, vedere [Mapping dei parametri di query a variabili in un componente di un flusso di dati](map-query-parameters-to-variables-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="42f39-116">For more information, see [Map Query Parameters to Variables in a Data Flow Component](map-query-parameters-to-variables-in-a-data-flow-component.md).</span></span>  
  
    -   <span data-ttu-id="42f39-117">**Comando SQL da variabile** Selezionare la variabile definita dall'utente che contiene il comando SQL.</span><span class="sxs-lookup"><span data-stu-id="42f39-117">**SQL command from variable** Select the user-defined variable that contains the SQL command.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="42f39-118">La variabile deve essere definita nell'ambito della stessa attività Flusso di dati che contiene l'origine OLE DB, oppure nell'ambito dello stesso pacchetto, e deve avere un tipo di dati string.</span><span class="sxs-lookup"><span data-stu-id="42f39-118">The variables must be defined in the scope of the same Data Flow task that contains the OLE DB source, or in the scope of the same package; additionally, the variable must have a string data type.</span></span>  
  
7.  <span data-ttu-id="42f39-119">Per aggiornare il mapping tra colonne esterne e colonne di output, fare clic su **Colonne** e selezionare colonne diverse nell'elenco **Colonna esterna** .</span><span class="sxs-lookup"><span data-stu-id="42f39-119">To update the mapping between external and output columns, click **Columns** and select different columns in the **External Column** list.</span></span>  
  
8.  <span data-ttu-id="42f39-120">Facoltativamente, aggiornare i nomi delle colonne di output modificando i valori nell'elenco **Colonna di output** .</span><span class="sxs-lookup"><span data-stu-id="42f39-120">Optionally, update the names of output columns by editing values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="42f39-121">Per configurare l'output degli errori, fare clic su **Output errori**.</span><span class="sxs-lookup"><span data-stu-id="42f39-121">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="42f39-122">Per altre informazioni, vedere [Configurazione di un output degli errori in un componente del flusso di dati](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="42f39-122">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="42f39-123">Facendo clic su **Anteprima** è possibile visualizzare fino a 200 righe di dati estratti dall'origine OLE DB.</span><span class="sxs-lookup"><span data-stu-id="42f39-123">You can click **Preview** to view up to 200 rows of the data extracted by the OLE DB source.</span></span>  
  
11. <span data-ttu-id="42f39-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="42f39-124">Click **OK**.</span></span>  
  
12. <span data-ttu-id="42f39-125">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="42f39-125">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f39-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42f39-126">See Also</span></span>  
 <span data-ttu-id="42f39-127">[Origine OLE DB](ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="42f39-127">[OLE DB Source](ole-db-source.md) </span></span>  
 <span data-ttu-id="42f39-128">[Trasformazioni di Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="42f39-128">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="42f39-129">[Percorsi in Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="42f39-129">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="42f39-130">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="42f39-130">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
