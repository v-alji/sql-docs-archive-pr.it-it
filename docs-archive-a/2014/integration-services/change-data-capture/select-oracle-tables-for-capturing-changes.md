---
title: Selezionare le tabelle Oracle per l'acquisizione delle modifiche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- selOraTabDia
ms.assetid: 2e295dc8-999d-4c4d-96cc-1519674b47a4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e9064789dce83ff7d3917ed026c861743142e048
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720303"
---
# <a name="select-oracle-tables-for-capturing-changes"></a><span data-ttu-id="f3935-102">Selezionare le tabelle Oracle per l'acquisizione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="f3935-102">Select Oracle Tables for Capturing Changes</span></span>
  <span data-ttu-id="f3935-103">Utilizzare questa finestra di dialogo per selezionare le tabelle incluse nell'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="f3935-103">Use this dialog box to select the tables that are included in the CDC instance.</span></span> <span data-ttu-id="f3935-104">Le tabelle selezionate vengono aggiunte all'elenco nella pagina **Select Tables and Columns** della New Instance Wizard.</span><span class="sxs-lookup"><span data-stu-id="f3935-104">The tables selected are added to the list in the **Select Tables and Columns** page of the New Instance wizard.</span></span> <span data-ttu-id="f3935-105">In questa finestra di dialogo è possibile effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3935-105">You can do the following in this dialog box.</span></span>  
  
 <span data-ttu-id="f3935-106">Per impostazione predefinita, non viene inclusa alcuna tabella nell'elenco di tabelle della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="f3935-106">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="f3935-107">È possibile selezionare la casella di controllo all'inizio della colonna per selezionare tutte le tabelle o cercare tabelle specifiche.</span><span class="sxs-lookup"><span data-stu-id="f3935-107">You can select the check box at the top of the check box column to select all of the tables or search for specific tables.</span></span>  
  
 <span data-ttu-id="f3935-108">**Per cercare tabelle specifiche**</span><span class="sxs-lookup"><span data-stu-id="f3935-108">**To search for specific tables**</span></span>  
 <span data-ttu-id="f3935-109">Immettere i criteri di ricerca nel modo illustrato di seguito, quindi scegliere **Cerca**:</span><span class="sxs-lookup"><span data-stu-id="f3935-109">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="f3935-110">**Schema**: selezionare uno schema del database dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="f3935-110">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="f3935-111">Verranno incluse nell'elenco solo le tabelle aventi questo schema.</span><span class="sxs-lookup"><span data-stu-id="f3935-111">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="f3935-112">**Table Name Pattern**: immettere qualsiasi stringa di caratteri.</span><span class="sxs-lookup"><span data-stu-id="f3935-112">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="f3935-113">Verranno visualizzate solo le tabelle che includono la stringa di caratteri immessa.</span><span class="sxs-lookup"><span data-stu-id="f3935-113">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3935-114">È possibile immettere criteri in uno o entrambi questi campi.</span><span class="sxs-lookup"><span data-stu-id="f3935-114">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="f3935-115">**Display first 1000 matching tables**: per impostazione predefinita questa casella di controllo è selezionata.</span><span class="sxs-lookup"><span data-stu-id="f3935-115">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="f3935-116">La visualizzazione è limitata alle prime 1000 tabelle corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f3935-116">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="f3935-117">Se si deseleziona la casella di controllo, vengono visualizzate tutte le tabelle che soddisfano i criteri.</span><span class="sxs-lookup"><span data-stu-id="f3935-117">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="f3935-118">Se sono presenti molte tabelle, la visualizzazione dell'elenco potrebbe richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="f3935-118">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="f3935-119">**Per selezionare le tabelle da includere nell'istanza di CDC**</span><span class="sxs-lookup"><span data-stu-id="f3935-119">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="f3935-120">Fare clic sulla casella di controllo accanto alle tabelle che si desidera includere, quindi scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f3935-120">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="f3935-121">Le tabelle vengono aggiunte all'elenco nella pagina **Select Tables and Columns** della New Instance Wizard.</span><span class="sxs-lookup"><span data-stu-id="f3935-121">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="f3935-122">Fare clic su **Close** per chiudere la finestra di dialogo senza aggiungere tabelle aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="f3935-122">Click **Close** to close the dialog box without adding any additional tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3935-123">Se si seleziona una tabella che include un tipo di dati non supportato, verrà visualizzato un messaggio di errore e la tabella non verrà inclusa.</span><span class="sxs-lookup"><span data-stu-id="f3935-123">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3935-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3935-124">See Also</span></span>  
 <span data-ttu-id="f3935-125">[Procedura di creazione dell'istanza del database delle modifiche di SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="f3935-125">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="f3935-126">Selezionare tabelle e colonne Oracle</span><span class="sxs-lookup"><span data-stu-id="f3935-126">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
