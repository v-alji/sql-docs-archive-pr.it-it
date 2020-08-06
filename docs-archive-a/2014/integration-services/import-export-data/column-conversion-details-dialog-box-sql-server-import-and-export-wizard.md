---
title: Finestra di dialogo Dettagli conversione colonna (Importazione/Esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.issuedetails.f1
ms.assetid: e2d00a39-dfbd-4821-a4d8-a5bd1164ed4d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9207e76191060c56acad37db734827579a83aae0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635155"
---
# <a name="column-conversion-details-dialog-box-sql-server-import-and-export-wizard"></a><span data-ttu-id="f9586-102">Finestra di dialogo Dettagli conversione colonna (Importazione/Esportazione guidata SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f9586-102">Column Conversion Details Dialog Box (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="f9586-103">Utilizzare la finestra di dialogo **Dettagli conversione colonna** per esaminare le informazioni dettagliate sulla conversione di una singola colonna.</span><span class="sxs-lookup"><span data-stu-id="f9586-103">Use the **Column Conversion Details** dialog box to review detailed conversion information about an individual column.</span></span> <span data-ttu-id="f9586-104">Queste informazioni sulla conversione contengono il tipo di dati della colonna nell'origine e nella destinazione e la conversione che verrà eseguita tramite la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="f9586-104">This conversion information contains the column's data type at the source and the destination, and the conversion that the wizard will perform.</span></span> <span data-ttu-id="f9586-105">In questa pagina sono inoltre elencati i file di mapping dei tipi di dati utilizzati dalla procedura guidata per determinare le conversioni dei tipi di dati necessarie.</span><span class="sxs-lookup"><span data-stu-id="f9586-105">This page also lists the data type mapping files that the wizard uses to determine the data type conversions that are required.</span></span> <span data-ttu-id="f9586-106">Tali file di mapping dei tipi di dati vengono installati durante l'installazione di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9586-106">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installs these data type mapping files during setup.</span></span>  
  
 <span data-ttu-id="f9586-107">**Per aprire la finestra di dialogo Dettagli conversione colonna**</span><span class="sxs-lookup"><span data-stu-id="f9586-107">**To open the Column Conversion Details dialog box**</span></span>  
  
1.  <span data-ttu-id="f9586-108">Nella pagina **verifica problemi dei tipi di dati** dell' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] importazione/esportazione guidata selezionare una tabella nell'elenco **tabella** .</span><span class="sxs-lookup"><span data-stu-id="f9586-108">On the **Review Data Type Issues** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, in the **Table** list, select a table.</span></span>  
  
2.  <span data-ttu-id="f9586-109">Nell'elenco **mapping dei tipi di dati** fare doppio clic sulla riga contenente la colonna per la quale si desidera visualizzare i dettagli della conversione.</span><span class="sxs-lookup"><span data-stu-id="f9586-109">In the **Data type mapping** list, double-click the row that contains the column for which you want to view conversion details.</span></span>  
  
 <span data-ttu-id="f9586-110">Per ulteriori informazioni sull' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] importazione/esportazione guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="f9586-110">To learn more about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="f9586-111">Per informazioni sulle opzioni per avviare la procedura guidata e sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="f9586-111">To learn about the options for starting the wizard, and about the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="f9586-112">Lo scopo dell'Importazione/Esportazione guidata [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consiste nel copiare i dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="f9586-112">The purpose of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="f9586-113">La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f9586-113">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="f9586-114">Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database.</span><span class="sxs-lookup"><span data-stu-id="f9586-114">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="f9586-115">Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="f9586-115">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
  
