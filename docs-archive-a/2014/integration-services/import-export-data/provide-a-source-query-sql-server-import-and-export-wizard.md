---
title: Impostazione query di origine (Importazione/Esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.providesourcequery.f1
ms.assetid: c8cbd07e-b9c3-422f-94b8-d6fc8cf31cf5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b21100f51c279e9ba764c8f82565af9d6e391ef3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635135"
---
# <a name="provide-a-source-query-sql-server-import-and-export-wizard"></a><span data-ttu-id="83f61-102">Impostazione query di origine (Importazione/Esportazione guidata SQL Server)</span><span class="sxs-lookup"><span data-stu-id="83f61-102">Provide a Source Query (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="83f61-103">Utilizzare la pagina **specificare una query di origine** per digitare l'istruzione SQL che genererà i dati da copiare dall'origine dati alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="83f61-103">Use the **Provide a Source Query** page to type the SQL statement that will generate the data to copy from the data source to the destination.</span></span>  
  
 <span data-ttu-id="83f61-104">Per ulteriori informazioni su questa procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="83f61-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="83f61-105">Per informazioni sulle opzioni di avvio della procedura guidata, nonché sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="83f61-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="83f61-106">Lo scopo di Importazione/Esportazione guidata SQL Server è la copia di dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="83f61-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="83f61-107">La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83f61-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="83f61-108">Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database.</span><span class="sxs-lookup"><span data-stu-id="83f61-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="83f61-109">Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="83f61-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="83f61-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="83f61-110">Options</span></span>  
 <span data-ttu-id="83f61-111">**Istruzione SQL**</span><span class="sxs-lookup"><span data-stu-id="83f61-111">**SQL statement**</span></span>  
 <span data-ttu-id="83f61-112">Consente di immettere un'istruzione di query per il recupero delle righe di dati selezionate dal database di origine.</span><span class="sxs-lookup"><span data-stu-id="83f61-112">Type a query statement to retrieve selected rows of data from the source database.</span></span> <span data-ttu-id="83f61-113">Ad esempio, l'istruzione di query seguente recupera i valori di **SalesPersonID**, **SalesQuota**e **SalesYTD** dal database AdventureWorks per i venditori la cui percentuale di Commissione è superiore al 1,5%.</span><span class="sxs-lookup"><span data-stu-id="83f61-113">For example, the following query statement retrieves the **SalesPersonID**, **SalesQuota**, and **SalesYTD** from the AdventureWorks database for sales persons whose commission percentage is more than 1.5 percent.</span></span>  
  
```  
SELECT SalesPersonID, SalesQuota, SalesYTD  
FROM Sales.SalesPerson  
WHERE CommissionPct > 0.015  
```  
  
 <span data-ttu-id="83f61-114">**Parse**.</span><span class="sxs-lookup"><span data-stu-id="83f61-114">**Parse**</span></span>  
 <span data-ttu-id="83f61-115">Controlla la sintassi dell'istruzione SQL nella casella di testo **Istruzione SQL**.</span><span class="sxs-lookup"><span data-stu-id="83f61-115">Checks the syntax of the SQL statement in the **SQL statement** text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83f61-116">Se il tempo necessario per il controllo della sintassi dell'istruzione supera il valore di timeout di 30 secondi, l'analisi si arresta e viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="83f61-116">If the time that is required to check the syntax of the statement exceeds the time-out value of 30 seconds, parsing stops and generates an error.</span></span> <span data-ttu-id="83f61-117">Non sarà possibile andare oltre questa pagina della procedura guidata fino a quando l'analisi non avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="83f61-117">You will not be able to move past this page of the wizard until parsing succeeds.</span></span> <span data-ttu-id="83f61-118">Una soluzione possibile consiste nel creare una vista di database basata sulla query ed eseguire la query sulla vista dalla procedura guidata, anziché immettere direttamente il testo della query.</span><span class="sxs-lookup"><span data-stu-id="83f61-118">One solution is to create a database view based on the query, and to query the view from the wizard, instead of entering the query text directly.</span></span>  
  
 <span data-ttu-id="83f61-119">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="83f61-119">**Browse**</span></span>  
 <span data-ttu-id="83f61-120">Consente di selezionare un file contenente un'istruzione SQL tramite la finestra di dialogo **Apri** .</span><span class="sxs-lookup"><span data-stu-id="83f61-120">Select a file containing a SQL statement by using the **Open** dialog box.</span></span> <span data-ttu-id="83f61-121">La selezione di un file copia il testo dal file nella casella di testo **istruzione query** .</span><span class="sxs-lookup"><span data-stu-id="83f61-121">Selecting a file copies the text from the file into the **Query statement** text box.</span></span>  
  
  
