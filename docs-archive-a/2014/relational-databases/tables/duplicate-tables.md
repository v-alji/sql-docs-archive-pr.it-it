---
title: Duplicare le tabelle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- tables [SQL Server], duplicating
- duplicating tables
- table copying [SQL Server]
ms.assetid: c6b07423-d1e5-4e5e-8681-5088921f5df3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 793a38416f86a5b43a3e3bb2420127d7acf2af1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626622"
---
# <a name="duplicate-tables"></a><span data-ttu-id="8a897-102">Duplicare le tabelle</span><span class="sxs-lookup"><span data-stu-id="8a897-102">Duplicate Tables</span></span>
  <span data-ttu-id="8a897-103">È possibile duplicare una tabella esistente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] creando una nuova tabella e copiando quindi le informazioni di colonna da una tabella esistente.</span><span class="sxs-lookup"><span data-stu-id="8a897-103">You can duplicate an existing table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] by creating a new table and then copying column information from an existing table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8a897-104">Questa operazione consente di duplicare solo la struttura di una tabella, non le righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="8a897-104">This operation duplicates only the structure of a table; it does not duplicate any table rows.</span></span>  
  
 <span data-ttu-id="8a897-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="8a897-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8a897-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="8a897-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8a897-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8a897-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8a897-108">**Per duplicare una tabella:**</span><span class="sxs-lookup"><span data-stu-id="8a897-108">**To duplicate a table, using:**</span></span>  
  
     [<span data-ttu-id="8a897-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8a897-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8a897-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8a897-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8a897-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8a897-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8a897-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8a897-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8a897-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8a897-113">Permissions</span></span>  
 <span data-ttu-id="8a897-114">È necessaria l'autorizzazione CREATE TABLE nel database di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8a897-114">Requires CREATE TABLE permission in the destination database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8a897-115">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8a897-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-duplicate-a-table"></a><span data-ttu-id="8a897-116">Per duplicare una tabella</span><span class="sxs-lookup"><span data-stu-id="8a897-116">To duplicate a table</span></span>  
  
1.  <span data-ttu-id="8a897-117">Verificare di essere connessi al database in cui si desidera creare la tabella e che tale database sia selezionato in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="8a897-117">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="8a897-118">In Esplora oggetti fare clic con il pulsante destro del mouse su **Tabelle** e scegliere **Nuova tabella**.</span><span class="sxs-lookup"><span data-stu-id="8a897-118">In Object Explorer, right-click **Tables** and click **New Table**.</span></span>  
  
3.  <span data-ttu-id="8a897-119">In Esplora oggetti fare clic con il pulsante destro del mouse sulla tabella da copiare e scegliere **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="8a897-119">In Object Explorer right-click the table you want to copy and click **Design**.</span></span>  
  
4.  <span data-ttu-id="8a897-120">Selezionare le colonne della tabella esistente e quindi scegliere **Copia** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8a897-120">Select the columns in the existing table and, from the **Edit** menu, click **Copy**.</span></span>  
  
5.  <span data-ttu-id="8a897-121">Tornare nella nuova tabella e selezionare la prima riga.</span><span class="sxs-lookup"><span data-stu-id="8a897-121">Switch back to the new table and select the first row.</span></span>  
  
6.  <span data-ttu-id="8a897-122">Scegliere **Incolla** dal menu **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8a897-122">From the **Edit** menu, click **Paste**.</span></span>  
  
7.  <span data-ttu-id="8a897-123">Scegliere **Salva** table name **dal menu**_File_.</span><span class="sxs-lookup"><span data-stu-id="8a897-123">From the **File** menu, click **Save**_table name_.</span></span>  
  
8.  <span data-ttu-id="8a897-124">Nella finestra di dialogo **Scegli nome** digitare un nome per la nuova tabella e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a897-124">In the **Choose Name** dialog box, type a name for the new table and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8a897-125">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8a897-125">Using Transact-SQL</span></span>  
  
#### <a name="to-duplicate-a-table-in-query-editor"></a><span data-ttu-id="8a897-126">Per duplicare una tabella in Editor di query</span><span class="sxs-lookup"><span data-stu-id="8a897-126">To duplicate a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="8a897-127">Verificare di essere connessi al database in cui si desidera creare la tabella e che tale database sia selezionato in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="8a897-127">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="8a897-128">Fare clic con li pulsante destro del mouse sulla tabella da duplicare, scegliere **Crea script per tabella**, quindi **CREATE in**e selezionare **Nuova finestra editor di query**.</span><span class="sxs-lookup"><span data-stu-id="8a897-128">Right-click the table you wish to duplicate, point to **Script Table as**, then point to **CREATE to**, and then select **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="8a897-129">Consente di modificare il nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="8a897-129">Change the name of the table.</span></span>  
  
4.  <span data-ttu-id="8a897-130">Rimuovere qualsiasi colonna non necessaria nella nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="8a897-130">Remove any columns that are not needed in the new table.</span></span>  
  
5.  <span data-ttu-id="8a897-131">Fare clic su **Execute**.</span><span class="sxs-lookup"><span data-stu-id="8a897-131">Click **Execute**.</span></span>  
  
  
