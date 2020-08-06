---
title: Modificare vincoli UNIQUE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying constraints
- UNIQUE constraints [SQL Server], modifying
- constraints [SQL Server], modifying
- constraints [SQL Server], unique
ms.assetid: fddbdc9e-958b-4614-8e88-6ca205d64a4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 74b044202f7e8e9bc762f025833cf2d0ff84c4c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638339"
---
# <a name="modify-unique-constraints"></a><span data-ttu-id="2886c-102">Modificare vincoli univoci</span><span class="sxs-lookup"><span data-stu-id="2886c-102">Modify Unique Constraints</span></span>
  <span data-ttu-id="2886c-103">È possibile modificare un vincolo UNIQUE in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2886c-103">You can modify a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2886c-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="2886c-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2886c-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="2886c-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2886c-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2886c-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2886c-107">**Per modificare un vincolo UNIQUE:**</span><span class="sxs-lookup"><span data-stu-id="2886c-107">**To modify a unique constraint using:**</span></span>  
  
     [<span data-ttu-id="2886c-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2886c-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2886c-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2886c-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2886c-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2886c-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2886c-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2886c-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2886c-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2886c-112">Permissions</span></span>  
 <span data-ttu-id="2886c-113">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="2886c-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2886c-114">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2886c-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-unique-constraint"></a><span data-ttu-id="2886c-115">Per modificare un vincolo UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2886c-115">To modify a unique constraint</span></span>  
  
1.  <span data-ttu-id="2886c-116">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulla tabella che contiene il vincolo UNIQUE e selezionare **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="2886c-116">In the **Object Explorer**, right-click the table containing the unique constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="2886c-117">Scegliere **Indici/chiavi...** nel menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="2886c-117">On the **Table Designer** menu, click **Indexes/Keys...**.</span></span>  
  
3.  <span data-ttu-id="2886c-118">Nella finestra di dialogo **Indici/chiavi** selezionare dall'elenco **Indice o chiave primari/univoci selezionati**il vincolo che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="2886c-118">In the **Indexes/Keys** dialog box, under **Selected Primary/Unique Key or Index**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="2886c-119">Completare un'operazione dalla tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="2886c-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="2886c-120">A</span><span class="sxs-lookup"><span data-stu-id="2886c-120">To</span></span>|<span data-ttu-id="2886c-121">seguire le operazioni di seguito riportate</span><span class="sxs-lookup"><span data-stu-id="2886c-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="2886c-122">Cambiare le colonne a cui è associato il vincolo</span><span class="sxs-lookup"><span data-stu-id="2886c-122">Change the columns that the constraint is associated with</span></span>|<span data-ttu-id="2886c-123">1) In **(Generale)** all'interno della griglia fare clic su **Colonne** e quindi sui puntini di sospensione **(...)** a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="2886c-123">1) In the grid under **(General)**, click **Columns** and then click the ellipses **(...)** to the right of the property.</span></span><br /><br /> <span data-ttu-id="2886c-124">2) Nella finestra di dialogo **Colonne indice** specificare la nuova colonna o l'ordinamento o entrambi per l'indice.</span><span class="sxs-lookup"><span data-stu-id="2886c-124">2) In the **Index Columns** dialog box, specify the new column or sort order or both for the index.</span></span>|  
    |<span data-ttu-id="2886c-125">Rinominare il vincolo</span><span class="sxs-lookup"><span data-stu-id="2886c-125">Rename the constraint</span></span>|<span data-ttu-id="2886c-126">In **Identità**all'interno della griglia, digitare un nuovo nome nella casella di testo **Nome** .</span><span class="sxs-lookup"><span data-stu-id="2886c-126">In the grid under **Identity**, type a new name in the **Name** box.</span></span> <span data-ttu-id="2886c-127">Scegliere un nome che non sia ancora presente nell'elenco **Indice o chiave primari/univoci selezionati** .</span><span class="sxs-lookup"><span data-stu-id="2886c-127">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="2886c-128">Impostare l'opzione cluster</span><span class="sxs-lookup"><span data-stu-id="2886c-128">Set the clustered option</span></span>|<span data-ttu-id="2886c-129">Nella griglia sotto **Progettazione tabelle** selezionare **Crea come CLUSTERED** e nell'elenco a discesa scegliere Sì per creare un indice cluster e No per crearne uno non cluster.</span><span class="sxs-lookup"><span data-stu-id="2886c-129">In the grid under **Table Designer**, select **Create As Clustered** and from the dropdown choose Yes to create a clustered index and No to create a nonclustered one.</span></span> <span data-ttu-id="2886c-130">Per ogni tabella è possibile creare un solo indice cluster.</span><span class="sxs-lookup"><span data-stu-id="2886c-130">Only one clustered index can exist per table.</span></span> <span data-ttu-id="2886c-131">Se esiste già un indice cluster in questa tabella, deselezionare questa opzione sull'indice originale.</span><span class="sxs-lookup"><span data-stu-id="2886c-131">If a clustered index already exists in this table, you must clear this setting on the original index.</span></span>|  
    |<span data-ttu-id="2886c-132">Definire un fattore di riempimento</span><span class="sxs-lookup"><span data-stu-id="2886c-132">Define a fill factor</span></span>|<span data-ttu-id="2886c-133">In **Progettazione tabelle**all'interno della griglia espandere la categoria **Specifica riempimento** e digitare un numero intero compreso tra 0 e 100 nella casella **Riempimento** .</span><span class="sxs-lookup"><span data-stu-id="2886c-133">In the grid under **Table Designer**, expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill Factor** box.</span></span>|  
  
5.  <span data-ttu-id="2886c-134">Scegliere **Salva**_nome tabella_ dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="2886c-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="to-modify-a-unique-constraint"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2886c-135">**Per modificare un vincolo UNIQUE**</span><span class="sxs-lookup"><span data-stu-id="2886c-135">**To modify a unique constraint**</span></span>  
  
 <span data-ttu-id="2886c-136">Per modificare un vincolo UNIQUE utilizzando Transact-SQL, è innanzitutto necessario eliminare il vincolo UNIQUE esistente e quindi ricrearlo con la nuova definizione.</span><span class="sxs-lookup"><span data-stu-id="2886c-136">To modify a UNIQUE constraint using Transact-SQL, you must first delete the existing UNIQUE constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="2886c-137">Per ulteriori informazioni, vedere [Delete Unique Constraints](delete-unique-constraints.md) e [Create Unique Constraints](create-unique-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="2886c-137">For more information, see [Delete Unique Constraints](delete-unique-constraints.md) and [Create Unique Constraints](create-unique-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
