---
title: Corrispondenza nomi (creazione guidata vista origine dati) (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.namematchingcriteria.f1
ms.assetid: 7f811e02-0fe6-45c9-a7b7-29c61032d96b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50cc46db7f582e0aea1570dadc956336ef8be074
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629049"
---
# <a name="name-matching-data-source-view-wizard-analysis-services"></a><span data-ttu-id="f19c8-102">Corrispondenza nomi (Configurazione guidata vista origine dati) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="f19c8-102">Name Matching (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="f19c8-103">Utilizzare la pagina **Corrispondenza nomi** per selezionare il criterio da utilizzare per il rilevamento delle possibili relazioni esistenti tra le tabelle selezionate per la vista origine dati e le altre tabelle dello schema.</span><span class="sxs-lookup"><span data-stu-id="f19c8-103">Use the **Name Matching** page to select the criterion to use for detecting possible relationships between the tables that you select for the data source view and the other tables in the schema.</span></span> <span data-ttu-id="f19c8-104">Se non esistono relazioni fisiche di chiave esterna tra le tabelle, questo criterio consente all'utente di identificare e aggiungere tabelle correlate alla vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="f19c8-104">If no physical foreign key relationships exist between the tables, this criterion helps you identify and add related tables to the data source view.</span></span> <span data-ttu-id="f19c8-105">Anche le relazioni logiche identificate mediante la corrispondenza dei nomi vengono aggiunte alla vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="f19c8-105">The logical relationships that are identified by name matching are also added to the data source view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f19c8-106">Questa pagina viene visualizzata solo se si seleziona un'origine dei dati che dispone di più tabelle ma non di relazioni di chiave esterna tra una delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="f19c8-106">This page appears only if you select a data source that has multiple tables but no foreign key relationships between any one of the tables.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f19c8-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f19c8-107">Options</span></span>  
 <span data-ttu-id="f19c8-108">**Crea relazioni logiche individuando le corrispondenze tra le colonne**</span><span class="sxs-lookup"><span data-stu-id="f19c8-108">**Create logical relationships by matching columns**</span></span>  
 <span data-ttu-id="f19c8-109">Selezionare questa opzione per utilizzare un criterio di corrispondenza dei nomi che consenta di rilevare le possibili dipendenze e relazioni logiche esistenti tra le tabelle che si desidera includere nella vista origine dati e le altre tabelle dello schema.</span><span class="sxs-lookup"><span data-stu-id="f19c8-109">Select to use a name-matching criterion to detect possible logical dependencies and relationships between the tables that you select to include in the data source view and the other tables in the schema.</span></span> <span data-ttu-id="f19c8-110">Se questa casella di controllo viene deselezionata, non viene utilizzato alcun criterio di corrispondenza dei nomi per identificare le relazioni logiche esistenti tra le tabelle dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="f19c8-110">If you clear this check box, no name-matching criterion is used to identify logical relationships between tables in the data source.</span></span>  
  
 <span data-ttu-id="f19c8-111">**Corrispondenze chiavi esterne**</span><span class="sxs-lookup"><span data-stu-id="f19c8-111">**Foreign key matches**</span></span>  
 <span data-ttu-id="f19c8-112">Consente di selezionare il criterio da utilizzare per la creazione di relazioni logiche tra le tabelle e le viste dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="f19c8-112">Select the criterion to use for creating logical relationships between tables and views in the data source.</span></span> <span data-ttu-id="f19c8-113">I caratteri non alfanumerici contenuti nelle stringhe di corrispondenza vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="f19c8-113">Non-alphanumeric characters are ignored in matching strings.</span></span> <span data-ttu-id="f19c8-114">Ad esempio, le stringhe "Customer ID", "Customer_ID" e "CustomerID" corrispondono.</span><span class="sxs-lookup"><span data-stu-id="f19c8-114">For example, "Customer ID", "Customer_ID", "CustomerID" all match.</span></span> <span data-ttu-id="f19c8-115">Selezionare una delle opzioni riportate nella tabella seguente per creare relazioni in base alle condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="f19c8-115">Select one of the options in the following table to create relationships under the specified conditions.</span></span>  
  
|<span data-ttu-id="f19c8-116">Select</span><span class="sxs-lookup"><span data-stu-id="f19c8-116">Select</span></span>|<span data-ttu-id="f19c8-117">Per creare</span><span class="sxs-lookup"><span data-stu-id="f19c8-117">To create</span></span>|  
|------------|---------------|  
|<span data-ttu-id="f19c8-118">**Stesso nome della chiave primaria**</span><span class="sxs-lookup"><span data-stu-id="f19c8-118">**Same name as primary key**</span></span>|<span data-ttu-id="f19c8-119">Una relazione logica a qualsiasi tabella che dispone di un nome di colonna che corrisponde alla colonna chiave primaria nella tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="f19c8-119">A logical relationship to any table with a column name that matches the name of the primary key column in a selected table.</span></span>|  
|<span data-ttu-id="f19c8-120">**Stesso nome della tabella di destinazione**</span><span class="sxs-lookup"><span data-stu-id="f19c8-120">**Same name as destination table name**</span></span>|<span data-ttu-id="f19c8-121">Una relazione logica a qualsiasi tabella che dispone di un nome di colonna che corrisponde al nome di una tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="f19c8-121">A logical relationship to any table with a column name that matches the name of a selected table.</span></span>|  
|<span data-ttu-id="f19c8-122">**Nome tabella di destinazione + nome chiave primaria**</span><span class="sxs-lookup"><span data-stu-id="f19c8-122">**Destination table name + primary key name**</span></span>|<span data-ttu-id="f19c8-123">Una relazione logica a qualsiasi tabella in cui un nome di colonna corrisponde al nome della tabella selezionata concatenato al nome della colonna chiave primaria per la tabella selezionata,in base a tale ordine.</span><span class="sxs-lookup"><span data-stu-id="f19c8-123">A logical relationship to any table in which a column name matches the selected table name concatenated with the name of the primary key column for the selected table, in that order.</span></span> <span data-ttu-id="f19c8-124">I caratteri non alfanumerici inclusi nella concatenazione vengono ignorati. Ad esempio, le stringhe "Product ID", "Product_ID" e "ProductID" corrispondono.</span><span class="sxs-lookup"><span data-stu-id="f19c8-124">Non-alphanumeric characters within the concatenation are ignored (for example, "Product ID", "Product_ID" and "ProductID" all match).</span></span>|  
  
 <span data-ttu-id="f19c8-125">**Descrizione ed esempio**</span><span class="sxs-lookup"><span data-stu-id="f19c8-125">**Description and sample**</span></span>  
 <span data-ttu-id="f19c8-126">Consente di visualizzare una descrizione e un esempio del criterio selezionato.</span><span class="sxs-lookup"><span data-stu-id="f19c8-126">View a description and a sample of the selected criterion.</span></span>  
  
  
