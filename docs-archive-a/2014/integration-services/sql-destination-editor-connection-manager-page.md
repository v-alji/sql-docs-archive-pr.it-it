---
title: Editor destinazione SQL (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.connection.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 423e1654-54af-47c6-ab6f-98670534557d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f3a552968cb297de337e1f0c406b444d95dc5a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627300"
---
# <a name="sql-destination-editor-connection-manager-page"></a><span data-ttu-id="d2921-102">Editor destinazione SQL Server (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="d2921-102">SQL Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="d2921-103">Usare la pagina **Gestione connessione** della finestra di dialogo **Editor destinazione SQL** per specificare le informazioni sull'origine dei dati e visualizzare un'anteprima dei risultati.</span><span class="sxs-lookup"><span data-stu-id="d2921-103">Use the **Connection Manager** page of the **SQL Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="d2921-104">La [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destinazione carica i dati in tabelle o viste di un [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span><span class="sxs-lookup"><span data-stu-id="d2921-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destination loads data into tables or views in a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="d2921-105">Per ulteriori informazioni sulla destinazione SQL Server, vedere [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="d2921-105">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d2921-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d2921-106">Options</span></span>  
 <span data-ttu-id="d2921-107">**Gestione connessione OLE DB**</span><span class="sxs-lookup"><span data-stu-id="d2921-107">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="d2921-108">Selezionare una connessione esistente nell'elenco oppure fare clic su **Nuova**per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="d2921-108">Select an existing connection from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="d2921-109">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="d2921-109">**New**</span></span>  
 <span data-ttu-id="d2921-110">Consente di creare una nuova connessione usando la finestra di dialogo **Configura gestione connessione OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="d2921-110">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="d2921-111">**Tabella o vista**</span><span class="sxs-lookup"><span data-stu-id="d2921-111">**Use a table or view**</span></span>  
 <span data-ttu-id="d2921-112">Consente di selezionare una tabella o vista esistente nell'elenco oppure di creare una nuova connessione facendo clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="d2921-112">Select an existing table or view from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="d2921-113">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="d2921-113">**New**</span></span>  
 <span data-ttu-id="d2921-114">Consente di creare una nuova tabella usando la finestra di dialogo **Crea tabella** .</span><span class="sxs-lookup"><span data-stu-id="d2921-114">Create a new table by using the **Create Table** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2921-115">Quando si fa clic su **Nuova**, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] genera un'istruzione CREATE TABLE predefinita basata sull'origine dati connessa.</span><span class="sxs-lookup"><span data-stu-id="d2921-115">When you click **New**, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="d2921-116">Questa istruzione CREATE TABLE predefinita non includerà l'attributo FILESTREAM anche se la tabella di origine include una colonna con l'attributo FILESTREAM dichiarato.</span><span class="sxs-lookup"><span data-stu-id="d2921-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="d2921-117">Per eseguire un componente [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] con l'attributo FILESTREAM, implementare innanzitutto l'archiviazione di FILESTREAM nel database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d2921-117">To run an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="d2921-118">Aggiungere quindi l'attributo FILESTREAM all'istruzione CREATE TABLE nella finestra di dialogo **Crea tabella** .</span><span class="sxs-lookup"><span data-stu-id="d2921-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="d2921-119">Per altre informazioni, vedere [Dati BLOB &#40;Binary Large Object&#41; &#40;SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d2921-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="d2921-120">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="d2921-120">**Preview**</span></span>  
 <span data-ttu-id="d2921-121">Consente di visualizzare in anteprima i risultati nella finestra di dialogo **Anteprima risultati query** .</span><span class="sxs-lookup"><span data-stu-id="d2921-121">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="d2921-122">L'anteprima supporta la visualizzazione di un massimo di 200 righe.</span><span class="sxs-lookup"><span data-stu-id="d2921-122">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2921-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2921-123">See Also</span></span>  
 <span data-ttu-id="d2921-124">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d2921-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d2921-125">[Editor destinazione SQL &#40;pagina mapping&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="d2921-125">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="d2921-126">[Editor destinazione SQL &#40;pagina avanzate&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="d2921-126">[SQL Destination Editor &#40;Advanced Page&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="d2921-127">Caricamento bulk dei dati tramite la destinazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="d2921-127">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
