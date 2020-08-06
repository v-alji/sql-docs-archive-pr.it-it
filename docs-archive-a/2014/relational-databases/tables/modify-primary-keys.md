---
title: Modificare chiavi primarie | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying primary keys
- primary keys [SQL Server], modifying
ms.assetid: 8e2a15ba-1cd1-4408-b860-16c3ee37d635
author: stevestein
ms.author: sstein
ms.openlocfilehash: f24deeac45491f9097d90ee0407464f928a0713b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623099"
---
# <a name="modify-primary-keys"></a><span data-ttu-id="a75ed-102">Modifica di chiavi primarie</span><span class="sxs-lookup"><span data-stu-id="a75ed-102">Modify Primary Keys</span></span>
  <span data-ttu-id="a75ed-103">È possibile modificare chiave primaria in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a75ed-103">You can modify a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a75ed-104">È possibile modificare la chiave primaria di una tabella modificando l'ordine della colonna, il nome dell'indice, l'opzione cluster o il fattore di riempimento.</span><span class="sxs-lookup"><span data-stu-id="a75ed-104">You can modify the primary key of a table by changing the column order, index name, clustered option, or fill factor.</span></span>  
  
 <span data-ttu-id="a75ed-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a75ed-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a75ed-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a75ed-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a75ed-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a75ed-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a75ed-108">**Per modificare una chiave primaria:**</span><span class="sxs-lookup"><span data-stu-id="a75ed-108">**To modify a primary key, using:**</span></span>  
  
     [<span data-ttu-id="a75ed-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a75ed-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a75ed-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a75ed-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a75ed-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a75ed-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a75ed-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a75ed-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a75ed-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a75ed-113">Permissions</span></span>  
 <span data-ttu-id="a75ed-114">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="a75ed-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a75ed-115">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a75ed-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-primary-key"></a><span data-ttu-id="a75ed-116">Per modificare una chiave primaria</span><span class="sxs-lookup"><span data-stu-id="a75ed-116">To modify a primary key</span></span>  
  
1.  <span data-ttu-id="a75ed-117">Aprire Progettazione tabelle per la tabella di cui modificare la chiave primaria, fare clic con il pulsante destro del mouse in Progettazione tabelle e scegliere **Indici/chiavi** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="a75ed-117">Open the Table Designer for the table whose primary key you want to modify, right-click in the Table Designer, and choose **Indexes/Keys** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="a75ed-118">Nella finestra di dialogo **Indici/chiavi** selezionare l'indice di chiave primaria dall'elenco **Indice o chiave primaria/univoca** .</span><span class="sxs-lookup"><span data-stu-id="a75ed-118">In the **Indexes/Keys** dialog box, select the primary key index from the **Selected Primary/Unique Key or Index** list.</span></span>  
  
3.  <span data-ttu-id="a75ed-119">Completare un'operazione dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="a75ed-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="a75ed-120">A</span><span class="sxs-lookup"><span data-stu-id="a75ed-120">To</span></span>|<span data-ttu-id="a75ed-121">seguire le operazioni di seguito riportate</span><span class="sxs-lookup"><span data-stu-id="a75ed-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="a75ed-122">Rinominare la chiave primaria</span><span class="sxs-lookup"><span data-stu-id="a75ed-122">Rename the primary key</span></span>|<span data-ttu-id="a75ed-123">Digitare un nuovo nome nella casella **Nome** .</span><span class="sxs-lookup"><span data-stu-id="a75ed-123">Type a new name in the **Name** box.</span></span> <span data-ttu-id="a75ed-124">Scegliere un nome che non sia ancora presente nell'elenco **Indice o chiave primari/univoci selezionati** .</span><span class="sxs-lookup"><span data-stu-id="a75ed-124">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="a75ed-125">Impostare l'opzione cluster</span><span class="sxs-lookup"><span data-stu-id="a75ed-125">Set the clustered option</span></span>|<span data-ttu-id="a75ed-126">Per creare un indice cluster per la chiave primaria, selezionare **Crea come CLUSTERED**, quindi selezionare l'opzione dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="a75ed-126">To create a clustered index for the primary key, select **Create as CLUSTERED**, and select the option from the drop-down list box.</span></span> <span data-ttu-id="a75ed-127">Per ogni tabella è possibile creare un solo indice cluster.</span><span class="sxs-lookup"><span data-stu-id="a75ed-127">Only one clustered index can exist per table.</span></span> <span data-ttu-id="a75ed-128">Se questa opzione non è disponibile per l'indice desiderato, deselezionare dapprima la relativa opzione sull'indice cluster esistente.</span><span class="sxs-lookup"><span data-stu-id="a75ed-128">If this option is not available for your index, you must first clear this setting on the existing clustered index.</span></span><br /><br /> <span data-ttu-id="a75ed-129">Se questa opzione non viene selezionata, viene creato un indice unico non cluster.</span><span class="sxs-lookup"><span data-stu-id="a75ed-129">If this option is not selected, a unique nonclustered index is created.</span></span>|  
    |<span data-ttu-id="a75ed-130">Definire un fattore di riempimento</span><span class="sxs-lookup"><span data-stu-id="a75ed-130">Define a fill factor</span></span>|<span data-ttu-id="a75ed-131">Espandere la categoria **Specifica riempimento** e digitare un numero intero compreso tra 0 e 100 nella casella **Riempimento** .</span><span class="sxs-lookup"><span data-stu-id="a75ed-131">Expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill factor** box.</span></span> <span data-ttu-id="a75ed-132">Per altre informazioni sui fattori di riempimento e sul loro uso, vedere [Specificare un fattore di riempimento per un indice](../indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="a75ed-132">For more information about fill factors and their uses, see [Specify Fill Factor for an Index](../indexes/specify-fill-factor-for-an-index.md).</span></span>|  
    |<span data-ttu-id="a75ed-133">Cambiare l'ordine delle colonne</span><span class="sxs-lookup"><span data-stu-id="a75ed-133">Change the column order</span></span>|<span data-ttu-id="a75ed-134">Selezionare **Colonne**, quindi fare clic sui puntini di sospensione **(...)** a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="a75ed-134">Select **Columns**, and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="a75ed-135">Nella finestra di dialogo  **Colonne indice** rimuovere le colonne dalla chiave primaria,</span><span class="sxs-lookup"><span data-stu-id="a75ed-135">In the  **Index Columns** dialog box, remove the columns from the primary key.</span></span> <span data-ttu-id="a75ed-136">quindi aggiungerle nuovamente nell'ordine desiderato.</span><span class="sxs-lookup"><span data-stu-id="a75ed-136">Then add the columns back in the order you want.</span></span> <span data-ttu-id="a75ed-137">Per rimuovere una colonna dalla chiave, eliminare semplicemente il nome colonna dall'elenco **Nome colonna** .</span><span class="sxs-lookup"><span data-stu-id="a75ed-137">To remove a column from the key, simply remove the column name from the **Column** name list.</span></span>|  
  
4.  <span data-ttu-id="a75ed-138">Scegliere **Salva**_nome tabella_ dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="a75ed-138">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a75ed-139">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a75ed-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="a75ed-140">**Per modificare una chiave primaria**</span><span class="sxs-lookup"><span data-stu-id="a75ed-140">**To modify a primary key**</span></span>  
  
 <span data-ttu-id="a75ed-141">Per modificare un vincolo PRIMARY KEY utilizzando Transact-SQL, è innanzitutto necessario eliminare il vincolo PRIMARY KEY esistente e quindi crearlo di nuovo con la nuova definizione.</span><span class="sxs-lookup"><span data-stu-id="a75ed-141">To modify a PRIMARY KEY constraint using Transact-SQL, you must first delete the existing PRIMARY KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="a75ed-142">Per ulteriori informazioni, vedere [Delete Primary Keys](delete-primary-keys.md) e [Create Primary Keys](create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="a75ed-142">For more information, see [Delete Primary Keys](delete-primary-keys.md) and [Create Primary Keys](create-primary-keys.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
