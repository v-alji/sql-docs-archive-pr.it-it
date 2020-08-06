---
title: Modificare le tabelle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- tabProps
ms.assetid: fed8fada-2abc-45e2-8228-0656f9c599cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8e8058a0c3e8b81814283f055e4c4ac2b08dd2fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624293"
---
# <a name="edit-tables"></a><span data-ttu-id="7c0f1-102">Modificare le tabelle</span><span class="sxs-lookup"><span data-stu-id="7c0f1-102">Edit Tables</span></span>
  <span data-ttu-id="7c0f1-103">Utilizzare la scheda **Tabelle** per apportare modifiche alle tabelle e alle colonne selezionate dal database di origine Oracle.</span><span class="sxs-lookup"><span data-stu-id="7c0f1-103">Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span> <span data-ttu-id="7c0f1-104">Nella scheda sono presenti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c0f1-104">This tab has the following elements:</span></span>  
  
 <span data-ttu-id="7c0f1-105">**Elenco Tabella**</span><span class="sxs-lookup"><span data-stu-id="7c0f1-105">**Table list**</span></span>  
 <span data-ttu-id="7c0f1-106">Nell'elenco tabelle sono presenti tre colonne:</span><span class="sxs-lookup"><span data-stu-id="7c0f1-106">The table list has three columns:</span></span>  
  
-   <span data-ttu-id="7c0f1-107">**Nome tabella Oracle**: nome della tabella, incluso lo schema.</span><span class="sxs-lookup"><span data-stu-id="7c0f1-107">**Oracle Table Name**: The name of the table, including the table schema.</span></span>  
  
-   <span data-ttu-id="7c0f1-108">**Istanza di acquisizione**: nome dell'istanza di acquisizione usato per denominare gli oggetti Change Data Capture specifici dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="7c0f1-108">**Capture Instance**: The name of the capture instance used to name instance-specific change data capture objects.</span></span> <span data-ttu-id="7c0f1-109">L'istanza di acquisizione non può essere NULL.</span><span class="sxs-lookup"><span data-stu-id="7c0f1-109">The capture instance cannot be NULL.</span></span> <span data-ttu-id="7c0f1-110">Se non è specificato, il nome deriva dal nome dello schema di origine più il nome della tabella di origine nel formato `<schema-name>_<table-name>.` Il nome dell'istanza di acquisizione non può superare i 100 caratteri e deve essere univoco nel database.</span><span class="sxs-lookup"><span data-stu-id="7c0f1-110">If not specified, the name is derived from the source schema name plus the source table name in the format `<schema-name>_<table-name>.` The capture instance name cannot exceed 100 characters and must be unique within the database.</span></span> <span data-ttu-id="7c0f1-111">È possibile fare clic in qualsiasi cella di questa colonna per modificare manualmente **capture_instance**.</span><span class="sxs-lookup"><span data-stu-id="7c0f1-111">You can click in any cell in this column to manually edit the **capture_instance**.</span></span>  
  
-   <span data-ttu-id="7c0f1-112">**Ruolo di sicurezza**: nome del ruolo del database utilizzato per ottenere l'accesso ai dati delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="7c0f1-112">**Security Role**: The name of the database role used to gain access to change data.</span></span> <span data-ttu-id="7c0f1-113">È possibile fare clic in qualsiasi cella di questa colonna per modificare manualmente **security_role**.</span><span class="sxs-lookup"><span data-stu-id="7c0f1-113">You can click in any cell in this column to manually edit the **security_role**.</span></span>  
  
 <span data-ttu-id="7c0f1-114">**Aggiungi tabelle**</span><span class="sxs-lookup"><span data-stu-id="7c0f1-114">**Add Tables**</span></span>  
 <span data-ttu-id="7c0f1-115">Fare clic su **Aggiungi tabelle** per aprire la finestra di dialogo Selezione tabelle in cui è possibile [aggiungere tabelle a un'istanza di CDC](add-tables-to-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="7c0f1-115">Click **Add Tables** to open the Table Selection dialog box where you can [Add Tables to a CDC Instance](add-tables-to-a-cdc-instance.md).</span></span> <span data-ttu-id="7c0f1-116">Al primo accesso di questa sessione al database Oracle, è necessario [Connect to Oracle](connect-to-oracle.md).</span><span class="sxs-lookup"><span data-stu-id="7c0f1-116">The first time this session that you access the Oracle database, you must [Connect to Oracle](connect-to-oracle.md).</span></span>  
  
 <span data-ttu-id="7c0f1-117">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="7c0f1-117">**Edit**</span></span>  
 <span data-ttu-id="7c0f1-118">Selezionare una tabella dall'elenco e selezionare **Modifica** per aprire la finestra di dialogo **Proprietà** per tale tabella in cui è possibile [Modificare le proprietà della tabella](edit-the-table-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7c0f1-118">Select a table from the list and select **Edit** to open the **Properties** dialog box for that table where you can [Edit the Table Properties](edit-the-table-properties.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7c0f1-119">Non è possibile modificare il mapping dei tipi per le tabelle che dispongono già di tabelle mirror.</span><span class="sxs-lookup"><span data-stu-id="7c0f1-119">You cannot edit type mapping for tables that already have mirror tables.</span></span> <span data-ttu-id="7c0f1-120">Questa operazione è possibile unicamente per le tabelle nuove.</span><span class="sxs-lookup"><span data-stu-id="7c0f1-120">You can do this for new tables only.</span></span>  
  
 <span data-ttu-id="7c0f1-121">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="7c0f1-121">**Remove**</span></span>  
 <span data-ttu-id="7c0f1-122">Selezionare una tabella dall'elenco e fare clic su **Rimuovi** per rimuovere la tabella dall'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="7c0f1-122">Select a table from the list and click **Remove** to remove the table from the CDC instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c0f1-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c0f1-123">See Also</span></span>  
 <span data-ttu-id="7c0f1-124">[Procedura di modifica delle proprietà dell'istanza di CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7c0f1-124">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="7c0f1-125">Selezionare tabelle e colonne Oracle</span><span class="sxs-lookup"><span data-stu-id="7c0f1-125">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
