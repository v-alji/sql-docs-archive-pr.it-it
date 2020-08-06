---
title: Modificare statistiche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], modifying
- modifying statistics
ms.assetid: b06299ca-ed52-411a-b245-45eac4628c99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6dd44da6d1a80050f37f08e49773f95af0e5a339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636624"
---
# <a name="modify-statistics"></a><span data-ttu-id="b2213-102">Modificare statistiche</span><span class="sxs-lookup"><span data-stu-id="b2213-102">Modify Statistics</span></span>
  <span data-ttu-id="b2213-103">È possibile modificare statistiche esistenti in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2213-103">You can modify existing statistics in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b2213-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="b2213-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b2213-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="b2213-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b2213-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b2213-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b2213-107">**Modificare statistiche tramite:**</span><span class="sxs-lookup"><span data-stu-id="b2213-107">**To modify statistics, using:**</span></span>  
  
     [<span data-ttu-id="b2213-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2213-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b2213-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b2213-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b2213-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b2213-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b2213-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b2213-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b2213-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b2213-112">Permissions</span></span>  
 <span data-ttu-id="b2213-113">Sono necessarie le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2213-113">Requires that:</span></span>  
  
-   <span data-ttu-id="b2213-114">L'utente deve disporre dell'autorizzazione ALTER per la tabella o la vista.</span><span class="sxs-lookup"><span data-stu-id="b2213-114">The user has ALTER permission on the table or view.</span></span>  
  
-   <span data-ttu-id="b2213-115">L'utente deve essere il proprietario della tabella o della vista indicizzata o un membro di uno dei seguenti ruoli: ruolo predefinito del server **sysadmin** , ruolo predefinito del database **db_owner** o ruolo predefinito del database **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="b2213-115">The user be the table or indexed view owner, or a member of one of the following roles: **sysadmin** fixed server role, **db_owner** fixed database role, or the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b2213-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2213-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-statistics"></a><span data-ttu-id="b2213-117">Per modificare le statistiche</span><span class="sxs-lookup"><span data-stu-id="b2213-117">To modify statistics</span></span>  
  
1.  <span data-ttu-id="b2213-118">In **Esplora oggetti**fare clic sul segno più per espandere il database in cui si desidera modificare una statistica.</span><span class="sxs-lookup"><span data-stu-id="b2213-118">In **Object Explorer**, click the plus sign to expand the database in which you want to modify a statistic.</span></span>  
  
2.  <span data-ttu-id="b2213-119">Fare clic sul segno più per espandere la cartella **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="b2213-119">Click the plus sign to expand the **Tables** folder.</span></span>  
  
3.  <span data-ttu-id="b2213-120">Fare clic sul segno più per espandere la tabella in cui si desidera modificare una statistica.</span><span class="sxs-lookup"><span data-stu-id="b2213-120">Click the plus sign to expand the table in which you want to modify a statistic.</span></span>  
  
4.  <span data-ttu-id="b2213-121">Fare clic sul segno più per espandere la cartella **Statistiche** .</span><span class="sxs-lookup"><span data-stu-id="b2213-121">Click the plus sign to expand the **Statistics** folder.</span></span>  
  
5.  <span data-ttu-id="b2213-122">Fare clic con il pulsante destro del mouse sull'oggetto statistiche che si vuole modificare e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b2213-122">Right-click the statistics object that you wish to modify and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="b2213-123">Nella pagina **Generali** della finestra di dialogo **Proprietà statistiche -** *nome_statistiche* fare clic su **Aggiungi**, **Rimuovi**, **Sposta su** o **Sposta giù**, o su qualsiasi combinazione, per modificare le proprietà delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b2213-123">In the **Statistics Properties -** *statistics_name* dialog box, on the **General** page, click **Add**, **Remove**, **Move Up**, or **Move Down**, or any combination, to alter the properties of the statistics.</span></span> <span data-ttu-id="b2213-124">Si noti che la posizione di una colonna nella griglia **Colonne statistiche** può avere un impatto significativo sull'utilità delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="b2213-124">Remember that a column's location within the **Statistics Columns** grid can substantially impact the usefulness of the statistics.</span></span>  
  
7.  <span data-ttu-id="b2213-125">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2213-125">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b2213-126">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b2213-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="b2213-127">**Per modificare le statistiche**</span><span class="sxs-lookup"><span data-stu-id="b2213-127">**To modify statistics**</span></span>  
  
 <span data-ttu-id="b2213-128">Non è possibile eseguire questa attività utilizzando istruzioni Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="b2213-128">This task cannot be performed using Transact-SQL statements.</span></span> <span data-ttu-id="b2213-129">Per modificare statistiche tramite Transact-SQL, è innanzitutto necessario eliminare la statistica esistente e quindi ricrearla con i nuovi attributi.</span><span class="sxs-lookup"><span data-stu-id="b2213-129">To modify statistics using Transact-SQL, you must first delete the existing statistic and then re-create it with new attributes.</span></span>  
  
 <span data-ttu-id="b2213-130">Per altre informazioni, vedere [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) e [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2213-130">For more information, see [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) and [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).</span></span>  
  
  
