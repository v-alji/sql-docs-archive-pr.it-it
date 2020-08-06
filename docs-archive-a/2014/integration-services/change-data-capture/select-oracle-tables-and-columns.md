---
title: Selezionare tabelle e colonne Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selTabCol
ms.assetid: bf73f80e-a954-4c5f-874e-17fdd4082715
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d51e597f1210643b1543ed981045ade7b2fc2b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626834"
---
# <a name="select-oracle-tables-and-columns"></a><span data-ttu-id="4c096-102">Selezionare tabelle e colonne Oracle</span><span class="sxs-lookup"><span data-stu-id="4c096-102">Select Oracle Tables and Columns</span></span>
  <span data-ttu-id="4c096-103">Utilizzare la pagina Seleziona tabelle e colonne Oracle per selezionare le tabelle dal database di origine Oracle in cui vengono acquisite le modifiche.</span><span class="sxs-lookup"><span data-stu-id="4c096-103">Use the Select Oracle Tables and Columns page to select the tables from the Oracle source database where changes are captured.</span></span> <span data-ttu-id="4c096-104">Nella pagina sono presenti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c096-104">This page has the following elements:</span></span>  
  
## <a name="options"></a><span data-ttu-id="4c096-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4c096-105">Options</span></span>  
 <span data-ttu-id="4c096-106">**Elenco Tabella**</span><span class="sxs-lookup"><span data-stu-id="4c096-106">**Table list**</span></span>  
 <span data-ttu-id="4c096-107">Nell'elenco tabelle sono presenti tre colonne:</span><span class="sxs-lookup"><span data-stu-id="4c096-107">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="4c096-108">**Nome tabella Oracle**: nome della tabella, incluso lo schema.</span><span class="sxs-lookup"><span data-stu-id="4c096-108">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="4c096-109">**Istanza di acquisizione**: nome dell'istanza di acquisizione usato per denominare gli oggetti Change Data Capture specifici dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="4c096-109">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="4c096-110">L'istanza di acquisizione non può essere NULL.</span><span class="sxs-lookup"><span data-stu-id="4c096-110">The capture instance cannot be NULL.</span></span>  
  
     <span data-ttu-id="4c096-111">Se non è specificato, il nome deriva dal nome dello schema di origine più il nome della tabella di origine nel formato `<schema-name>_<table-name>`.</span><span class="sxs-lookup"><span data-stu-id="4c096-111">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>`.</span></span> <span data-ttu-id="4c096-112">Il nome dell'istanza di acquisizione non può superare i 100 caratteri e deve essere univoco nel database.</span><span class="sxs-lookup"><span data-stu-id="4c096-112">The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span>  
  
     <span data-ttu-id="4c096-113">È possibile fare clic in qualsiasi cella di questa colonna per modificare manualmente **capture_instance**.</span><span class="sxs-lookup"><span data-stu-id="4c096-113">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="4c096-114">**Ruolo di sicurezza**: nome del ruolo del database utilizzato per controllare l'accesso ai dati delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="4c096-114">**Security Role**: The name of the database gating role used to control access to change data.</span></span>  
  
     <span data-ttu-id="4c096-115">È possibile fare clic in qualsiasi cella di questa colonna per modificare manualmente **security_role**.</span><span class="sxs-lookup"><span data-stu-id="4c096-115">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="4c096-116">**Aggiungi tabelle**</span><span class="sxs-lookup"><span data-stu-id="4c096-116">**Add Tables**</span></span>  
 <span data-ttu-id="4c096-117">Fare clic su **Aggiungi tabelle** per aprire la finestra di dialogo Selezione tabelle in cui è possibile [Selezionare le tabelle Oracle per l'acquisizione delle modifiche](select-oracle-tables-for-capturing-changes.md).</span><span class="sxs-lookup"><span data-stu-id="4c096-117">Click **Add Tables** to open the Table Selection dialog box where you can [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="4c096-118">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="4c096-118">**Edit**</span></span>  
 <span data-ttu-id="4c096-119">Selezionare una tabella dall'elenco e selezionare **Modifica** per aprire la finestra di dialogo **Proprietà** per tale tabella in cui è possibile [Apportare modifiche alle tabelle selezionate per l'acquisizione di modifiche](make-changes-to-the-tables-selected-for-capturing-changes.md).</span><span class="sxs-lookup"><span data-stu-id="4c096-119">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md).</span></span>  
  
 <span data-ttu-id="4c096-120">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="4c096-120">**Remove**</span></span>  
 <span data-ttu-id="4c096-121">Selezionare una tabella dall'elenco e fare clic su **Rimuovi** per rimuovere la tabella dall'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="4c096-121">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
 <span data-ttu-id="4c096-122">Dopo aver [selezionato le tabelle Oracle per l'acquisizione delle modifiche](select-oracle-tables-for-capturing-changes.md) e/o [apportato modifiche alle tabelle selezionate per l'acquisizione di modifiche](make-changes-to-the-tables-selected-for-capturing-changes.md) usando le finestre di dialogo corrette, fare clic su **Avanti** e passare a [Generare ed eseguire lo script di registrazione supplementare](generate-and-run-the-supplemental-logging-script.md).</span><span class="sxs-lookup"><span data-stu-id="4c096-122">After you [Select Oracle Tables for Capturing Changes](select-oracle-tables-for-capturing-changes.md) and/or [Make Changes to the Tables Selected for Capturing Changes](make-changes-to-the-tables-selected-for-capturing-changes.md) using the correct dialog boxes, click **Next** to [Generate and Run the Supplemental Logging Script](generate-and-run-the-supplemental-logging-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c096-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c096-123">See Also</span></span>  
 <span data-ttu-id="4c096-124">[Procedura di creazione dell'istanza del database delle modifiche di SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="4c096-124">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 <span data-ttu-id="4c096-125">[Modificare le tabelle](edit-tables.md) </span><span class="sxs-lookup"><span data-stu-id="4c096-125">[Edit Tables](edit-tables.md) </span></span>  
 <span data-ttu-id="4c096-126">[Aggiungere tabelle a un'istanza di CDC](add-tables-to-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="4c096-126">[Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="4c096-127">Modificare le proprietà delle tabelle</span><span class="sxs-lookup"><span data-stu-id="4c096-127">Edit the Table Properties</span></span>](edit-the-table-properties.md)  
  
  
