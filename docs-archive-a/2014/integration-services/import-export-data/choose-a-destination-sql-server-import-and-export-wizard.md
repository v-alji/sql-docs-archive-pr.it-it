---
title: Scelta destinazione (Importazione/Esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.chooseadestination.f1
ms.assetid: 1898be15-3e69-42d3-8ecb-3733c9f6c8e3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4bf9b717ef9de20d84d32c18eb3caa4c54cad87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635156"
---
# <a name="choose-a-destination-sql-server-import-and-export-wizard"></a><span data-ttu-id="2bebd-102">Scelta destinazione (Importazione/Esportazione guidata SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2bebd-102">Choose a Destination (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="2bebd-103">Utilizzare la pagina **scegliere una destinazione** per specificare la destinazione dei dati che si desidera copiare.</span><span class="sxs-lookup"><span data-stu-id="2bebd-103">Use the **Choose a Destination** page to specify the destination of the data that you want to copy.</span></span>  
  
 <span data-ttu-id="2bebd-104">Per ulteriori informazioni su questa procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2bebd-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="2bebd-105">Per informazioni sulle opzioni di avvio della procedura guidata, nonché sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2bebd-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="2bebd-106">Lo scopo dell'Importazione/Esportazione guidata [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consiste nel copiare i dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="2bebd-106">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="2bebd-107">La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2bebd-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="2bebd-108">Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database.</span><span class="sxs-lookup"><span data-stu-id="2bebd-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="2bebd-109">Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="2bebd-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="2bebd-110">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="2bebd-110">Static Options</span></span>  
 <span data-ttu-id="2bebd-111">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="2bebd-111">**Destination**</span></span>  
 <span data-ttu-id="2bebd-112">Consente di scegliere il provider di dati corrispondente al formato di archiviazione dei dati della destinazione.</span><span class="sxs-lookup"><span data-stu-id="2bebd-112">Choose the data provider that matches the data storage format of the destination.</span></span> <span data-ttu-id="2bebd-113">Potrebbero essere disponibili più provider per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="2bebd-113">There may be more than one provider available for your data source.</span></span> <span data-ttu-id="2bebd-114">Ad esempio, con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è possibile utilizzare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client, il .NET Framework provider di dati per SQL Server o il Provider Microsoft OLE DB per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2bebd-114">For example, with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, the .NET Framework Data Provider for SQL Server, or the Microsoft OLE DB Provider for SQL Server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bebd-115">Per salvare i dati in una destinazione ODBC, selezionare Provider di dati .NET Framework per ODBC.</span><span class="sxs-lookup"><span data-stu-id="2bebd-115">To save data to an ODBC destination, select the .NET Framework Data Provider for ODBC.</span></span>  
  
 <span data-ttu-id="2bebd-116">La proprietà **origine dati** presenta un numero variabile di opzioni che variano a seconda dei provider installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2bebd-116">The **Data Source** property has a variable number of options, which change depending on the providers installed on the computer.</span></span> <span data-ttu-id="2bebd-117">Nella tabella seguente vengono illustrate le opzioni relative ad alcune destinazioni comunemente utilizzate.</span><span class="sxs-lookup"><span data-stu-id="2bebd-117">The following tables list the options for some commonly used destinations.</span></span> <span data-ttu-id="2bebd-118">Per altri provider, consultare la documentazione specifica.</span><span class="sxs-lookup"><span data-stu-id="2bebd-118">For other providers, see the provider-specific documentation.</span></span>  
  
## <a name="dynamic-options"></a><span data-ttu-id="2bebd-119">Opzioni dinamiche</span><span class="sxs-lookup"><span data-stu-id="2bebd-119">Dynamic Options</span></span>  
 <span data-ttu-id="2bebd-120">Nelle sezioni seguenti vengono descritte le opzioni disponibili per diverse origini dei dati.</span><span class="sxs-lookup"><span data-stu-id="2bebd-120">The following sections show the options available for several data sources.</span></span> <span data-ttu-id="2bebd-121">Non sono descritte tutte le destinazioni disponibili nell'elenco a discesa Destinazione.</span><span class="sxs-lookup"><span data-stu-id="2bebd-121">Not all the destinations that are available in the Destination drop-down are listed here.</span></span>  
  
### <a name="destination--sql-server-native-client-or-microsoft-ole-db-provider-for-sql-server"></a><span data-ttu-id="2bebd-122">Destinazione = SQL Server Native Client o Provider Microsoft OLE DB per SQL Server</span><span class="sxs-lookup"><span data-stu-id="2bebd-122">Destination = SQL Server Native Client or Microsoft OLE DB Provider for SQL Server</span></span>  
 <span data-ttu-id="2bebd-123">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="2bebd-123">**Server name**</span></span>  
 <span data-ttu-id="2bebd-124">Consente di digitare il nome del server di destinazione dei dati oppure di sceglierne uno nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2bebd-124">Type the name of the server to receive the data, or choose a server from the list.</span></span>  
  
 <span data-ttu-id="2bebd-125">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="2bebd-125">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="2bebd-126">Consente di specificare se il pacchetto deve utilizzare l'autenticazione di Microsoft Windows per l'accesso al database.</span><span class="sxs-lookup"><span data-stu-id="2bebd-126">Specify whether the package should use Microsoft Windows Authentication to log in to the database.</span></span> <span data-ttu-id="2bebd-127">Per una maggiore sicurezza è consigliabile utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="2bebd-127">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="2bebd-128">**Usa autenticazione di SQL Server**</span><span class="sxs-lookup"><span data-stu-id="2bebd-128">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="2bebd-129">Consente di specificare se per l'accesso al database del pacchetto deve essere utilizzata l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bebd-129">Specify whether the package should use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to log in to the database.</span></span> <span data-ttu-id="2bebd-130">Se si usa l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , è necessario specificare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="2bebd-130">If you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="2bebd-131">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="2bebd-131">**User name**</span></span>  
 <span data-ttu-id="2bebd-132">Consente di specificare un nome utente per la connessione al database quando si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bebd-132">Specify a user name for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="2bebd-133">**Password**</span><span class="sxs-lookup"><span data-stu-id="2bebd-133">**Password**</span></span>  
 <span data-ttu-id="2bebd-134">Consente di specificare una password per la connessione al database quando si usa l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bebd-134">Provide the password for the database connection when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="2bebd-135">**Database**</span><span class="sxs-lookup"><span data-stu-id="2bebd-135">**Database**</span></span>  
 <span data-ttu-id="2bebd-136">Consente di selezionare dall'elenco di database nell'istanza specificata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oppure di creare un nuovo database facendo clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2bebd-136">Select from the list of databases on the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or create a new database by clicking **New**.</span></span>  
  
 <span data-ttu-id="2bebd-137">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="2bebd-137">**Refresh**</span></span>  
 <span data-ttu-id="2bebd-138">Consente di ripristinare l'elenco dei database disponibili facendo clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="2bebd-138">Restore the list of available databases by clicking **Refresh**.</span></span>  
  
 <span data-ttu-id="2bebd-139">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="2bebd-139">**New**</span></span>  
 <span data-ttu-id="2bebd-140">Consente di creare un nuovo database di destinazione utilizzando la finestra di dialogo **Crea database** .</span><span class="sxs-lookup"><span data-stu-id="2bebd-140">Create a new destination database by using the **Create Database** dialog box.</span></span>  
  
### <a name="destination--flat-file-destination"></a><span data-ttu-id="2bebd-141">Destinazione = Destinazione file flat</span><span class="sxs-lookup"><span data-stu-id="2bebd-141">Destination = Flat File Destination</span></span>  
 <span data-ttu-id="2bebd-142">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="2bebd-142">**File name**</span></span>  
 <span data-ttu-id="2bebd-143">Consente di specificare il percorso e il nome del file in cui archiviare i dati.</span><span class="sxs-lookup"><span data-stu-id="2bebd-143">Specify the path and file name for the file in which to store the data.</span></span> <span data-ttu-id="2bebd-144">In alternativa, è possibile fare clic su **Sfoglia** per individuare un file.</span><span class="sxs-lookup"><span data-stu-id="2bebd-144">Or, click **Browse** to locate a file.</span></span>  
  
 <span data-ttu-id="2bebd-145">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="2bebd-145">**Browse**</span></span>  
 <span data-ttu-id="2bebd-146">Consente di individuare un file tramite la finestra di dialogo **Apri**.</span><span class="sxs-lookup"><span data-stu-id="2bebd-146">Locate a file by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="2bebd-147">**Impostazioni locali**</span><span class="sxs-lookup"><span data-stu-id="2bebd-147">**Locale**</span></span>  
 <span data-ttu-id="2bebd-148">Consente di specificare l'ID delle impostazioni locali (LCID) che definisce il tipo di ordinamento dei caratteri e i formati di data e ora.</span><span class="sxs-lookup"><span data-stu-id="2bebd-148">Specify the locale ID (LCID) that defines character sort orders and date and time formatting.</span></span>  
  
 <span data-ttu-id="2bebd-149">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="2bebd-149">**Unicode**</span></span>  
 <span data-ttu-id="2bebd-150">Indica se utilizzare il formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="2bebd-150">Indicate whether to use Unicode.</span></span> <span data-ttu-id="2bebd-151">Se si utilizza il formato Unicode, non è necessario specificare una tabella codici.</span><span class="sxs-lookup"><span data-stu-id="2bebd-151">If you use Unicode, you do not have to specify a code page.</span></span>  
  
 <span data-ttu-id="2bebd-152">**Tabella codici**</span><span class="sxs-lookup"><span data-stu-id="2bebd-152">**Code page**</span></span>  
 <span data-ttu-id="2bebd-153">Consente di specificare la tabella codici per la lingua che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2bebd-153">Specify the code page for the language you want to use.</span></span>  
  
 <span data-ttu-id="2bebd-154">**Formato**</span><span class="sxs-lookup"><span data-stu-id="2bebd-154">**Format**</span></span>  
 <span data-ttu-id="2bebd-155">Consente di indicare se utilizzare la formattazione non allineata a destra, a larghezza fissa o delimitata.</span><span class="sxs-lookup"><span data-stu-id="2bebd-155">Indicate whether to use delimited, fixed width, or ragged right formatting.</span></span>  
  
|<span data-ttu-id="2bebd-156">Valore</span><span class="sxs-lookup"><span data-stu-id="2bebd-156">Value</span></span>|<span data-ttu-id="2bebd-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2bebd-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2bebd-158">Delimitato</span><span class="sxs-lookup"><span data-stu-id="2bebd-158">Delimited</span></span>|<span data-ttu-id="2bebd-159">Le colonne sono separate da un delimitatore specificato nella pagina **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="2bebd-159">Columns are separated by a delimiter, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="2bebd-160">File a larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="2bebd-160">Fixed width</span></span>|<span data-ttu-id="2bebd-161">Le colonne hanno una larghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="2bebd-161">Columns have a fixed width.</span></span>|  
|<span data-ttu-id="2bebd-162">Non allineato a destra</span><span class="sxs-lookup"><span data-stu-id="2bebd-162">Ragged right</span></span>|<span data-ttu-id="2bebd-163">I file non allineati a destra sono file in cui ogni colonna ha una larghezza fissa ad eccezione dell'ultima, per la quale viene utilizzato il delimitatore di riga.</span><span class="sxs-lookup"><span data-stu-id="2bebd-163">Ragged right files are files in which every column has a fixed width, except for the last column, which is delimited by the row delimiter.</span></span>|  
  
 <span data-ttu-id="2bebd-164">**Qualificatore di testo**</span><span class="sxs-lookup"><span data-stu-id="2bebd-164">**Text qualifier**</span></span>  
 <span data-ttu-id="2bebd-165">Consente di impostare il qualificatore di testo da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2bebd-165">Type the text qualifier to use.</span></span> <span data-ttu-id="2bebd-166">È possibile, ad esempio, specificare che ogni colonna di testo sia racchiusa tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="2bebd-166">For example, you can specify that each text column be surrounded with quotation marks.</span></span>  
  
 <span data-ttu-id="2bebd-167">**Nomi di colonne nella prima riga di dati**</span><span class="sxs-lookup"><span data-stu-id="2bebd-167">**Column names in first data row**</span></span>  
 <span data-ttu-id="2bebd-168">Consente di indicare se si desidera visualizzare i nomi delle colonne nella prima riga di dati.</span><span class="sxs-lookup"><span data-stu-id="2bebd-168">Indicate whether you want to display column names in the first data row.</span></span>  
  
### <a name="destination--microsoft-excel"></a><span data-ttu-id="2bebd-169">Destinazione = Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="2bebd-169">Destination = Microsoft Excel</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bebd-170">Selezionare **Microsoft Excel** solo se si desidera connettersi a un'origine dati che utilizza Excel 2003 o versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="2bebd-170">Select **Microsoft Excel** only if you want to connect to a data source that uses Excel 2003 or earlier.</span></span> <span data-ttu-id="2bebd-171">Per connettersi a un'origine dati che utilizza Excel 2007, selezionare **Microsoft Office 12,0 accesso motore di database Provider OLE DB**, fare clic su **Proprietà**e quindi nella scheda **tutte** della finestra di dialogo **proprietà di data link** , per **proprietà estese**, immettere `Excel 12.0` .</span><span class="sxs-lookup"><span data-stu-id="2bebd-171">To connect to a data source that uses Excel 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider**, click **Properties**, and then on the **All** tab of the **Data Link Properties** dialog box, for **Extended Properties**, enter `Excel 12.0`.</span></span>  
  
 <span data-ttu-id="2bebd-172">**Percorso file di Excel**</span><span class="sxs-lookup"><span data-stu-id="2bebd-172">**Excel file path**</span></span>  
 <span data-ttu-id="2bebd-173">Specificare il percorso e il nome file per la cartella di lavoro in cui archiviare i dati, ad esempio C:\MyData.xls \\\Sales\Database\Northwind.xls.</span><span class="sxs-lookup"><span data-stu-id="2bebd-173">Specify the path and file name for the workbook in which to store the data (for example, C:\MyData.xls, \\\Sales\Database\Northwind.xls).</span></span> <span data-ttu-id="2bebd-174">In alternativa, è possibile fare clic su **Sfoglia** per individuare una cartella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2bebd-174">Or, click **Browse** to locate a workbook.</span></span>  
  
 <span data-ttu-id="2bebd-175">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="2bebd-175">**Browse**</span></span>  
 <span data-ttu-id="2bebd-176">Individuare una cartella di lavoro di Excel utilizzando la finestra di dialogo **Apri** .</span><span class="sxs-lookup"><span data-stu-id="2bebd-176">Locate an Excel workbook by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="2bebd-177">**Versione di Excel**</span><span class="sxs-lookup"><span data-stu-id="2bebd-177">**Excel version**</span></span>  
 <span data-ttu-id="2bebd-178">Consente di selezionare la versione di Excel utilizzata dalla cartella di lavoro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2bebd-178">Select the version of Excel that is used by the destination workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bebd-179">Quando si esportano dati in una destinazione [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] , nella procedura guidata viene utilizzato il componente Destinazione Excel di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2bebd-179">When you export data to a [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] destination, the wizard uses the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Excel Destination component.</span></span> <span data-ttu-id="2bebd-180">Per informazioni su alcune considerazioni sull'utilizzo e sui problemi noti, vedere [Excel Destination](../data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="2bebd-180">For information on some usage considerations and known issues, see [Excel Destination](../data-flow/excel-destination.md).</span></span>  
  
### <a name="destination--microsoft-access"></a><span data-ttu-id="2bebd-181">Destinazione = Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="2bebd-181">Destination = Microsoft Access</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2bebd-182">Selezionare **Microsoft Access** solo se si desidera connettersi a un database che utilizza Access 2003 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="2bebd-182">Select **Microsoft Access** only if you want to connect to a database that uses Access 2003 or earlier.</span></span> <span data-ttu-id="2bebd-183">Per connettersi a un database che usa Access 2007, selezionare **Microsoft Office 12,0 access motore di database OLE DB provider**.</span><span class="sxs-lookup"><span data-stu-id="2bebd-183">To connect to a database that uses Access 2007, select **Microsoft Office 12.0 Access Database Engine OLE DB Provider**.</span></span>  
  
 <span data-ttu-id="2bebd-184">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="2bebd-184">**File name**</span></span>  
 <span data-ttu-id="2bebd-185">Specificare il percorso e il nome del file di database in cui archiviare i dati, ad esempio C:\MyData.mdb, \\ \Sales\Database\Northwind.mdb.</span><span class="sxs-lookup"><span data-stu-id="2bebd-185">Specify the path and file name for the database file in which to store the data (for example, C:\MyData.mdb, \\\Sales\Database\Northwind.mdb).</span></span> <span data-ttu-id="2bebd-186">In alternativa, è possibile fare clic su **Sfoglia** per individuare un file di database.</span><span class="sxs-lookup"><span data-stu-id="2bebd-186">Or, click **Browse** to locate a database file.</span></span>  
  
 <span data-ttu-id="2bebd-187">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="2bebd-187">**Browse**</span></span>  
 <span data-ttu-id="2bebd-188">Individuare il file di database utilizzando la finestra di dialogo **Apri** .</span><span class="sxs-lookup"><span data-stu-id="2bebd-188">Browse to the database file by using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="2bebd-189">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="2bebd-189">**User name**</span></span>  
 <span data-ttu-id="2bebd-190">Consente di specificare un nome utente valido per la connessione al database quando un file di informazioni sul gruppo di lavoro corrente è associato al database.</span><span class="sxs-lookup"><span data-stu-id="2bebd-190">Specify a valid user name for the database connection when a workgroup information file is associated with the database.</span></span>  
  
 <span data-ttu-id="2bebd-191">**Password**</span><span class="sxs-lookup"><span data-stu-id="2bebd-191">**Password**</span></span>  
 <span data-ttu-id="2bebd-192">Consente di specificare la password dell'utente per la connessione al database quando un file di informazioni sul gruppo di lavoro corrente è associato al database.</span><span class="sxs-lookup"><span data-stu-id="2bebd-192">Provide the user's password for the database connection when a workgroup information file is associated with the database.</span></span> <span data-ttu-id="2bebd-193">Se tuttavia il database è protetto con un'unica password valida per tutti gli utenti, è necessario specificare tale valore nella finestra di dialogo **Proprietà di Data Link** a cui è possibile accedere facendo clic sul pulsante **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="2bebd-193">However, if the database is protected with a single password for all users, you must provide this value in the **Data Link Properties** dialog box, which is accessed from the **Advanced** button.</span></span>  
  
 <span data-ttu-id="2bebd-194">**Funzionalità avanzate**</span><span class="sxs-lookup"><span data-stu-id="2bebd-194">**Advanced**</span></span>  
 <span data-ttu-id="2bebd-195">Consente di specificare le opzioni avanzate, ad esempio la password del database o un file di informazioni sul gruppo di lavoro diverso da quello predefinito, mediante la finestra di dialogo **Proprietà di Data Link**.</span><span class="sxs-lookup"><span data-stu-id="2bebd-195">Specify advanced options, such as the database password or a non-default workgroup information file, by using the **Data Link Properties** dialog box.</span></span> <span data-ttu-id="2bebd-196">Per ulteriori informazioni sulle proprietà del provider OLE DB, vedere la sezione relativa all'accesso ai dati di MSDN Library all'indirizzo [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="2bebd-196">For more information about OLE DB provider properties, search in the Data Access section of the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
  
