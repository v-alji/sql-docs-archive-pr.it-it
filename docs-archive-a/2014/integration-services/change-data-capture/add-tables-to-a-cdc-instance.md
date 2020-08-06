---
title: Aggiungere tabelle a un'istanza di CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- addTabs
ms.assetid: ad260e19-c021-4035-9311-c02fc96ceaea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: edcd84db9e3c464334d407987cb3567f78edd44e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712324"
---
# <a name="add-tables-to-a-cdc-instance"></a><span data-ttu-id="837c7-102">Aggiungere tabelle a un'istanza di CDC</span><span class="sxs-lookup"><span data-stu-id="837c7-102">Add Tables to a CDC Instance</span></span>
  <span data-ttu-id="837c7-103">Utilizzare la finestra di dialogo Table Selection per aggiungere tabelle aggiuntive dall'origine Oracle all'istanza di CDC.</span><span class="sxs-lookup"><span data-stu-id="837c7-103">Use the Table Selection dialog box to add additional tables from the Oracle source to the CDC instance.</span></span> <span data-ttu-id="837c7-104">Le tabelle selezionate vengono aggiunte all'elenco presente nella scheda **Tables** dell'editor delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="837c7-104">The tables selected are added to the list in the **Tables** tab of the Properties editor.</span></span>  
  
 <span data-ttu-id="837c7-105">Per impostazione predefinita, non viene inclusa alcuna tabella nell'elenco di tabelle della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="837c7-105">By default, no tables are included in the list of tables in this dialog box.</span></span> <span data-ttu-id="837c7-106">È possibile selezionare la casella di controllo **(Select All)** o cercare tabelle specifiche.</span><span class="sxs-lookup"><span data-stu-id="837c7-106">You can select the **(Select All)** check box or search for specific tables.</span></span>  
  
 <span data-ttu-id="837c7-107">**Per cercare tabelle specifiche**</span><span class="sxs-lookup"><span data-stu-id="837c7-107">**To search for specific tables**</span></span>  
 <span data-ttu-id="837c7-108">Immettere i criteri di ricerca nel modo illustrato di seguito, quindi scegliere **Cerca**:</span><span class="sxs-lookup"><span data-stu-id="837c7-108">Enter search criteria as follows, and then click **Search**:</span></span>  
  
-   <span data-ttu-id="837c7-109">**Schema**: selezionare uno schema del database dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="837c7-109">**Schema**: Select a database schema from the list.</span></span> <span data-ttu-id="837c7-110">Verranno incluse nell'elenco solo le tabelle aventi questo schema.</span><span class="sxs-lookup"><span data-stu-id="837c7-110">Only tables that have that schema will be included in the list.</span></span>  
  
-   <span data-ttu-id="837c7-111">**Table Name Pattern**: immettere qualsiasi stringa di caratteri.</span><span class="sxs-lookup"><span data-stu-id="837c7-111">**Table Name Pattern**: Enter any string of characters.</span></span> <span data-ttu-id="837c7-112">Verranno visualizzate solo le tabelle che includono la stringa di caratteri immessa.</span><span class="sxs-lookup"><span data-stu-id="837c7-112">Only tables that include the character string entered are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="837c7-113">È possibile immettere criteri in uno o entrambi questi campi.</span><span class="sxs-lookup"><span data-stu-id="837c7-113">You can enter criteria in one or both of these fields.</span></span>  
  
-   <span data-ttu-id="837c7-114">**Display first 1000 matching tables**: per impostazione predefinita questa casella di controllo è selezionata.</span><span class="sxs-lookup"><span data-stu-id="837c7-114">**Display first 1000 matching tables**: By default this check box is selected.</span></span> <span data-ttu-id="837c7-115">La visualizzazione è limitata alle prime 1000 tabelle corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="837c7-115">It limits the display to the first 1000 matching tables.</span></span> <span data-ttu-id="837c7-116">Se si deseleziona la casella di controllo, vengono visualizzate tutte le tabelle che soddisfano i criteri.</span><span class="sxs-lookup"><span data-stu-id="837c7-116">If you clear the check box, all tables that match the criteria are displayed.</span></span> <span data-ttu-id="837c7-117">Se sono presenti molte tabelle, la visualizzazione dell'elenco potrebbe richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="837c7-117">If there are a large number of tables, it may take a long time to display the list.</span></span>  
  
 <span data-ttu-id="837c7-118">**Per selezionare le tabelle da includere nell'istanza di CDC**</span><span class="sxs-lookup"><span data-stu-id="837c7-118">**To select tables to include in the CDC instance**</span></span>  
 <span data-ttu-id="837c7-119">Fare clic sulla casella di controllo accanto alle tabelle che si desidera includere, quindi scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="837c7-119">Click the check box next to any of the tables you want to include, and then click **Add**.</span></span> <span data-ttu-id="837c7-120">Le tabelle vengono aggiunte all'elenco nella pagina **Select Tables and Columns** della New Instance Wizard.</span><span class="sxs-lookup"><span data-stu-id="837c7-120">The tables are added to the list in the New Instance Wizard **Select Tables and Columns** page.</span></span>  
  
 <span data-ttu-id="837c7-121">Fare clic su **Chiudi** per chiudere la finestra di dialogo senza aggiungere tabelle.</span><span class="sxs-lookup"><span data-stu-id="837c7-121">Click **Close** to close the dialog box without adding any tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="837c7-122">Se si seleziona una tabella che include un tipo di dati non supportato, verrà visualizzato un messaggio di errore e la tabella non verrà inclusa.</span><span class="sxs-lookup"><span data-stu-id="837c7-122">If you select a table that includes a non-supported data type, you will see an error message and the table will not be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="837c7-123">È possibile visualizzare l'elenco di tabelle nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="837c7-123">You can view the list of tables in the viewer.</span></span> <span data-ttu-id="837c7-124">Quando si utilizza il visualizzatore le informazioni sono in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="837c7-124">When using the viewer the information is read only.</span></span> <span data-ttu-id="837c7-125">Nel visualizzatore è inoltre incluso un elenco delle colonne acquisite nella tabella.</span><span class="sxs-lookup"><span data-stu-id="837c7-125">The viewer also includes a list of the captured columns in the table.</span></span> <span data-ttu-id="837c7-126">Per informazioni su come accedere al visualizzatore, vedere [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="837c7-126">For information on how to access the viewer, see [How to Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="837c7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="837c7-127">See Also</span></span>  
 <span data-ttu-id="837c7-128">[Procedura di modifica delle proprietà dell'istanza di CDC](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="837c7-128">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 <span data-ttu-id="837c7-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="837c7-129">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="837c7-130">Selezionare le tabelle Oracle per l'acquisizione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="837c7-130">Select Oracle Tables for Capturing Changes</span></span>](select-oracle-tables-for-capturing-changes.md)  
  
  
