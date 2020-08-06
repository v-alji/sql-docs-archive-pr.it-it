---
title: Tabella di esempio HumanResources.myTeam (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- myTeam sample table [SQL Server]
- bulk importing [SQL Server], examples
- bulk exporting [SQL Server], examples
ms.assetid: 27da45a0-c1f4-4bf4-ab24-6196e80d3834
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7d4e0cbbf42c2bdd25e3dd7c9577e4d0ec44549a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635593"
---
# <a name="humanresourcesmyteam-sample-table-sql-server"></a><span data-ttu-id="3da24-102">Tabella di esempio HumanResources.myTeam (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3da24-102">HumanResources.myTeam Sample Table (SQL Server)</span></span>
  <span data-ttu-id="3da24-103">Molti degli esempi di codice inclusi nell'argomento relativo all' [importazione ed esportazione di dati bulk](bulk-import-and-export-of-data-sql-server.md) richiedono una tabella di prova speciale denominata **myTeam**.</span><span class="sxs-lookup"><span data-stu-id="3da24-103">Many of the code examples in [Importing and Exporting Bulk Data](bulk-import-and-export-of-data-sql-server.md) require a special-purpose test table named **myTeam**.</span></span> <span data-ttu-id="3da24-104">Prima che sia possibile eseguire gli esempi, è necessario creare la tabella **myTeam** nello schema **HumanResources** del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3da24-104">Before you can run the examples, you must create the **myTeam** table in the **HumanResources** schema of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] <span data-ttu-id="3da24-105">è uno dei database di esempio disponibili in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3da24-105">is one of the sample databases in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="3da24-106">Nella tabella **myTeam** sono incluse le colonne seguenti.</span><span class="sxs-lookup"><span data-stu-id="3da24-106">The **myTeam** table is contains the following columns.</span></span>  
  
|<span data-ttu-id="3da24-107">Colonna</span><span class="sxs-lookup"><span data-stu-id="3da24-107">Column</span></span>|<span data-ttu-id="3da24-108">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="3da24-108">Data type</span></span>|<span data-ttu-id="3da24-109">Supporto di valori Null</span><span class="sxs-lookup"><span data-stu-id="3da24-109">Nullability</span></span>|<span data-ttu-id="3da24-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3da24-110">Description</span></span>|  
|------------|---------------|-----------------|-----------------|  
|<span data-ttu-id="3da24-111">**EmployeeID**</span><span class="sxs-lookup"><span data-stu-id="3da24-111">**EmployeeID**</span></span>|`smallint`|<span data-ttu-id="3da24-112">Non Null</span><span class="sxs-lookup"><span data-stu-id="3da24-112">Not null</span></span>|<span data-ttu-id="3da24-113">Chiave primaria per le righe.</span><span class="sxs-lookup"><span data-stu-id="3da24-113">Primary key for the rows.</span></span> <span data-ttu-id="3da24-114">ID dipendente di un membro del team.</span><span class="sxs-lookup"><span data-stu-id="3da24-114">Employee ID of a member of my team.</span></span>|  
|<span data-ttu-id="3da24-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3da24-115">**Name**</span></span>|`nvarchar(50)`|<span data-ttu-id="3da24-116">Non Null</span><span class="sxs-lookup"><span data-stu-id="3da24-116">Not null</span></span>|<span data-ttu-id="3da24-117">Nome di un membro del team.</span><span class="sxs-lookup"><span data-stu-id="3da24-117">Name of a member of my team.</span></span>|  
|<span data-ttu-id="3da24-118">**Titolo**</span><span class="sxs-lookup"><span data-stu-id="3da24-118">**Title**</span></span>|`nvarchar(50)`|<span data-ttu-id="3da24-119">Nullable</span><span class="sxs-lookup"><span data-stu-id="3da24-119">Nullable</span></span>|<span data-ttu-id="3da24-120">Titolo professionale del dipendente nel team.</span><span class="sxs-lookup"><span data-stu-id="3da24-120">Title the employee performs on my team.</span></span>|  
|<span data-ttu-id="3da24-121">**Background**</span><span class="sxs-lookup"><span data-stu-id="3da24-121">**Background**</span></span>|`nvarchar(50)`|<span data-ttu-id="3da24-122">Non Null</span><span class="sxs-lookup"><span data-stu-id="3da24-122">Not null</span></span>|<span data-ttu-id="3da24-123">Data e ora dell'ultimo aggiornamento della riga.</span><span class="sxs-lookup"><span data-stu-id="3da24-123">Date and time the row was last updated.</span></span> <span data-ttu-id="3da24-124">Valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3da24-124">(Default)</span></span>|  
  
 <span data-ttu-id="3da24-125">**Per creare HumanResources.myTeam**</span><span class="sxs-lookup"><span data-stu-id="3da24-125">**To create HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="3da24-126">Utilizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="3da24-126">Use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    --Create HumanResources.MyTeam:   
    USE AdventureWorks;  
    GO  
    CREATE TABLE HumanResources.myTeam   
    (EmployeeID smallint NOT NULL,  
    Name nvarchar(50) NOT NULL,  
    Title nvarchar(50) NULL,  
    Background nvarchar(50) NOT NULL DEFAULT ''  
    );  
    GO  
    ```  
  
 <span data-ttu-id="3da24-127">**Per popolare HumanResources.myTeam**</span><span class="sxs-lookup"><span data-stu-id="3da24-127">**To populate HumanResources.myTeam**</span></span>  
  
-   <span data-ttu-id="3da24-128">Eseguire le istruzioni `INSERT` seguenti per popolare la tabella con due righe:</span><span class="sxs-lookup"><span data-stu-id="3da24-128">Execute following `INSERT` statements to populate the table with two rows:</span></span>  
  
    ```  
    USE AdventureWorks;  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(77,'Mia Doppleganger','Administrative Assistant','Microsoft Office');  
    GO  
    INSERT INTO HumanResources.myTeam(EmployeeID,Name,Title,Background)  
       VALUES(49,'Hirum Mollicat','I.T. Specialist','Report Writing and Data Mining');  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="3da24-129">Queste istruzioni ignorano la quarta colonna, `Background`,</span><span class="sxs-lookup"><span data-stu-id="3da24-129">These statements skip the fourth column, `Background`.</span></span> <span data-ttu-id="3da24-130">che ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3da24-130">This has a default value.</span></span> <span data-ttu-id="3da24-131">Ignorando la colonna, l'istruzione `INSERT` lascia la colonna vuota.</span><span class="sxs-lookup"><span data-stu-id="3da24-131">Skipping this column causes this `INSERT` statement to leave this column blank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da24-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3da24-132">See Also</span></span>  
 [<span data-ttu-id="3da24-133">Informazioni sull'importazione ed esportazione bulk di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3da24-133">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](bulk-import-and-export-of-data-sql-server.md)  
  
  
