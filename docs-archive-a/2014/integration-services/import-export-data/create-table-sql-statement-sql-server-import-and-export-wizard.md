---
title: Istruzione SQL CREATE TABLE (Importazione/Esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.createtablesql.f1
ms.assetid: 0d6f6b3b-d023-4770-a8a9-65b2977c8d05
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d3fc2054711708a27691f2d7219c33749f11b977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635149"
---
# <a name="create-table-sql-statement-sql-server-import-and-export-wizard"></a><span data-ttu-id="19d4d-102">Istruzione SQL CREATE TABLE (Importazione/Esportazione guidata SQL Server)</span><span class="sxs-lookup"><span data-stu-id="19d4d-102">Create Table SQL Statement (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="19d4d-103">Utilizzare la finestra di dialogo **istruzione SQL CREATE TABLE** per visualizzare l'istruzione generata automaticamente o per modificarla ai propri scopi.</span><span class="sxs-lookup"><span data-stu-id="19d4d-103">Use the **Create Table SQL Statement** dialog box to view the statement that was generated automatically, or to modify it for your purposes.</span></span> <span data-ttu-id="19d4d-104">Se si modifica l'istruzione, potrebbe essere necessario apportare le modifiche adeguate al mapping delle colonne, nonché, in seguito, gestire manualmente l'istruzione SQL modificata.</span><span class="sxs-lookup"><span data-stu-id="19d4d-104">If you modify this statement, you may also have to make associated changes to column mapping, and you will have to maintain the edited SQL statement manually thereafter.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="19d4d-105">genera un'istruzione CREATE TABLE predefinita basata sull'origine dati connessa.</span><span class="sxs-lookup"><span data-stu-id="19d4d-105">generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="19d4d-106">Questa istruzione CREATE TABLE predefinita non includerà l'attributo FILESTREAM anche se la tabella di origine include una colonna con l'attributo FILESTREAM dichiarato.</span><span class="sxs-lookup"><span data-stu-id="19d4d-106">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="19d4d-107">Per eseguire un componente [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] con l'attributo FILESTREAM, implementare innanzitutto l'archiviazione di FILESTREAM nel database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="19d4d-107">To run an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="19d4d-108">Aggiungere quindi l'attributo FILESTREAM all'istruzione CREATE TABLE nella finestra di dialogo **Crea tabella** .</span><span class="sxs-lookup"><span data-stu-id="19d4d-108">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="19d4d-109">Per altre informazioni, vedere [Dati BLOB &#40;Binary Large Object&#41; &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="19d4d-109">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="19d4d-110">Per ulteriori informazioni su questa procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="19d4d-110">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="19d4d-111">Per informazioni sulle opzioni di avvio della procedura guidata, nonché sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="19d4d-111">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="19d4d-112">Lo scopo di Importazione/Esportazione guidata SQL Server è la copia di dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="19d4d-112">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="19d4d-113">La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="19d4d-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="19d4d-114">Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database.</span><span class="sxs-lookup"><span data-stu-id="19d4d-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="19d4d-115">Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="19d4d-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="19d4d-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="19d4d-116">Options</span></span>  
 <span data-ttu-id="19d4d-117">**Istruzione SQL**</span><span class="sxs-lookup"><span data-stu-id="19d4d-117">**SQL statement**</span></span>  
 <span data-ttu-id="19d4d-118">Consente di visualizzare l'istruzione SQL generata automaticamente ed eventualmente di modificarla.</span><span class="sxs-lookup"><span data-stu-id="19d4d-118">Displays the auto-generated SQL statement and lets it be edited.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19d4d-119">Se si desidera includere un ritorno a capo nell'istruzione SQL, premere CTRL+INVIO.</span><span class="sxs-lookup"><span data-stu-id="19d4d-119">If you want to include a carriage return in the SQL statement, press CTRL+ENTER.</span></span> <span data-ttu-id="19d4d-120">Premere solo INVIO per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="19d4d-120">If you press only ENTER, the dialog box closes.</span></span>  
  
 <span data-ttu-id="19d4d-121">**AutoGenerate**</span><span class="sxs-lookup"><span data-stu-id="19d4d-121">**Autogenerate**</span></span>  
 <span data-ttu-id="19d4d-122">Il pulsante **Genera automaticamente** consente di ripristinare l'istruzione SQL predefinita, qualora fosse stata modificata.</span><span class="sxs-lookup"><span data-stu-id="19d4d-122">Restore the default SQL statement, if you have modified it, by clicking **Autogenerate**.</span></span>  
  
  
