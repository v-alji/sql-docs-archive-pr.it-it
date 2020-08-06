---
title: Caricare dati tramite la destinazione OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- loading data
- OLE DB destination [Integration Services]
- destinations [Integration Services], OLE DB
ms.assetid: 78899498-725e-4300-a7af-f983f4ea384b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43e8d1123ae91d9e68c00fbe3e05c490383afe0c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715615"
---
# <a name="load-data-by-using-the-ole-db-destination"></a><span data-ttu-id="4800f-102">Caricamento dei dati tramite la destinazione OLE DB</span><span class="sxs-lookup"><span data-stu-id="4800f-102">Load Data by Using the OLE DB Destination</span></span>
  <span data-ttu-id="4800f-103">È possibile aggiungere e configurare una destinazione OLE DB solo se il pacchetto include già almeno un'attività Flusso di dati e un'origine.</span><span class="sxs-lookup"><span data-stu-id="4800f-103">To add and configure an OLE DB destination, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-load-data-using-an-ole-db-destination"></a><span data-ttu-id="4800f-104">Per caricare dati tramite una destinazione OLE DB</span><span class="sxs-lookup"><span data-stu-id="4800f-104">To load data using an OLE DB destination</span></span>  
  
1.  <span data-ttu-id="4800f-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="4800f-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="4800f-106">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="4800f-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4800f-107">Fare clic sulla scheda **Flusso di dati** e quindi, dalla **Casella degli strumenti**, trascinare la destinazione OLE DB sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4800f-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB destination to the design surface.</span></span>  
  
4.  <span data-ttu-id="4800f-108">Connettere la destinazione OLE DB al flusso di dati trascinando un connettore da un'origine dati o una trasformazione precedente alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="4800f-108">Connect the OLE DB destination to the data flow by dragging a connector from a data source or a previous transformation to the destination.</span></span>  
  
5.  <span data-ttu-id="4800f-109">Fare doppio clic sulla destinazione OLE DB.</span><span class="sxs-lookup"><span data-stu-id="4800f-109">Double-click the OLE DB destination.</span></span>  
  
6.  <span data-ttu-id="4800f-110">Nella pagina **Gestione connessione** della finestra di dialogo **Editor destinazione OLE DB** selezionare una gestione connessione OLE DB esistente oppure fare clic su **Nuova** per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="4800f-110">In the **OLE DB Destination Editor** dialog box, on the **Connection Manager** page, select an existing OLE DB connection manager or click **New** to create a new connection manager.</span></span> <span data-ttu-id="4800f-111">Per altre informazioni, vedere [Gestione connessione OLE DB](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4800f-111">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="4800f-112">Selezionare il metodo di accesso ai dati:</span><span class="sxs-lookup"><span data-stu-id="4800f-112">Select the data access method:</span></span>  
  
    -   <span data-ttu-id="4800f-113">**Tabella o vista** Selezionare una tabella o una vista nel database che contiene i dati.</span><span class="sxs-lookup"><span data-stu-id="4800f-113">**Table or view** Select a table or view in the database that contains the data.</span></span>  
  
    -   <span data-ttu-id="4800f-114">**Tabella o vista - Caricamento rapido** Selezionare una tabella o una vista nel database che contiene i dati e quindi impostare le opzioni relative al caricamento rapido: **Mantieni valori Identity**, **Mantieni valori Null**, **Blocco di tabella**, **Verifica vincoli**, **Righe per batch**o **Dimensioni massime commit inserimento**.</span><span class="sxs-lookup"><span data-stu-id="4800f-114">**Table or view - fast load** Select a table or view in the database that contains the data, and then set the fast-load options: **Keep identity**, **Keep null**, **Table lock**, **Check constraint**, **Rows per batch**, or **Maximum insert commit size**.</span></span>  
  
    -   <span data-ttu-id="4800f-115">**Variabile nome vista o nome tabella** Selezionare una variabile definita dall'utente contenente il nome di una tabella o vista del database.</span><span class="sxs-lookup"><span data-stu-id="4800f-115">**Table name or view name variable** Select the user-defined variable that contains the name of a table or view in the database.</span></span>  
  
    -   <span data-ttu-id="4800f-116">**Variabile nome vista o nome tabella - Caricamento rapido** Selezionare la variabile definita dall'utente contenente il nome di una tabella o vista del database che contiene i dati e quindi impostare le opzioni relative al caricamento rapido.</span><span class="sxs-lookup"><span data-stu-id="4800f-116">**Table name or view name variable fast load** Select the user-defined variable that contains the name of a table or view in the database that contains the data, and then set the fast-load options.</span></span>  
  
    -   <span data-ttu-id="4800f-117">**Comando SQL** Digitare un comando SQL oppure fare clic su **Compila query** per scrivere un comando SQL utilizzando **Generatore query**.</span><span class="sxs-lookup"><span data-stu-id="4800f-117">**SQL command** Type an SQL command or click **Build Query** to write an SQL command by using the **Query Builder**.</span></span>  
  
8.  <span data-ttu-id="4800f-118">Fare clic su **Mapping** e quindi eseguire il mapping delle colonne nell'elenco **Colonne di input disponibili** alle colonne nell'elenco **Colonne di destinazione disponibili** , trascinando le colonne da un elenco all'altro.</span><span class="sxs-lookup"><span data-stu-id="4800f-118">Click **Mappings** and then map columns from the **Available Input Columns** list to columns in the **Available Destination Columns** list by dragging columns from one list to another.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4800f-119">La destinazione OLE DB esegue automaticamente il mapping delle colonne con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="4800f-119">The OLE DB destination automatically maps same-named columns.</span></span>  
  
9. <span data-ttu-id="4800f-120">Per configurare l'output degli errori, fare clic su **Output errori**.</span><span class="sxs-lookup"><span data-stu-id="4800f-120">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="4800f-121">Per altre informazioni, vedere [Configurazione di un output degli errori in un componente del flusso di dati](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="4800f-121">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="4800f-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4800f-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="4800f-123">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="4800f-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4800f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4800f-124">See Also</span></span>  
 <span data-ttu-id="4800f-125">[Destinazione OLE DB](ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="4800f-125">[OLE DB Destination](ole-db-destination.md) </span></span>  
 <span data-ttu-id="4800f-126">[Trasformazioni di Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="4800f-126">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="4800f-127">[Percorsi in Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="4800f-127">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="4800f-128">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="4800f-128">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
