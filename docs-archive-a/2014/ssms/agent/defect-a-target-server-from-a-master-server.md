---
title: Escludere un server di destinazione da un server master | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
ms.assetid: a6da262b-7b38-4ce4-bfd6-6a557c6e8a84
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2b17703fa87f5c0d3e7146a1660ac1ca7c7c1d81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715047"
---
# <a name="defect-a-target-server-from-a-master-server"></a><span data-ttu-id="dab11-102">Escludere un server di destinazione da un server master</span><span class="sxs-lookup"><span data-stu-id="dab11-102">Defect a Target Server from a Master Server</span></span>
  <span data-ttu-id="dab11-103">In questo argomento viene descritto come escludere un server di destinazione da un server master in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)] o SQL Server Management Objects (SMO).</span><span class="sxs-lookup"><span data-stu-id="dab11-103">This topic describes how to defect a target server from a master server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="dab11-104">Eseguire questa procedura dal server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dab11-104">Run this procedure from the target server.</span></span>  
  
 <span data-ttu-id="dab11-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="dab11-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="dab11-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="dab11-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="dab11-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="dab11-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="dab11-108">**Per escludere un server di destinazione utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="dab11-108">**To defect a target server, using:**</span></span>  
  
     [<span data-ttu-id="dab11-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dab11-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="dab11-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dab11-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="dab11-111">SMO</span><span class="sxs-lookup"><span data-stu-id="dab11-111">SMO</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="dab11-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="dab11-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="dab11-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="dab11-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="dab11-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="dab11-114">Permissions</span></span>  
 <span data-ttu-id="dab11-115">Per eseguire questa stored procedure, è necessario essere un membro del ruolo predefinito del server `sysadmin`.</span><span class="sxs-lookup"><span data-stu-id="dab11-115">To execute this stored procedure, a user must be a member of the `sysadmin` fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="dab11-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="dab11-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="dab11-117">Per escludere un server di destinazione da un server master</span><span class="sxs-lookup"><span data-stu-id="dab11-117">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="dab11-118">In **Esplora oggetti**espandere un server configurato come server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dab11-118">In **Object Explorer**, expand a server that is configured as a target server.</span></span>  
  
2.  <span data-ttu-id="dab11-119">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, scegliere **Amministrazione multiserver**e fare clic su **Escludi**.</span><span class="sxs-lookup"><span data-stu-id="dab11-119">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Defect**.</span></span>  
  
3.  <span data-ttu-id="dab11-120">Fare clic su **Sì** per confermare l'esclusione del server di destinazione da un server master.</span><span class="sxs-lookup"><span data-stu-id="dab11-120">Click **Yes** to confirm that you want to defect this target server from a master server.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="dab11-121">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="dab11-121">Using Transact-SQL</span></span>  
  
#### <a name="to-defect-a-target-server-from-a-master-server"></a><span data-ttu-id="dab11-122">Per escludere un server di destinazione da un server master</span><span class="sxs-lookup"><span data-stu-id="dab11-122">To defect a target server from a master server</span></span>  
  
1.  <span data-ttu-id="dab11-123">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dab11-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="dab11-124">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="dab11-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="dab11-125">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="dab11-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
```sql
sp_msx_defect ;  
```  
  
 <span data-ttu-id="dab11-126">Per ulteriori informazioni, vedere [sp_msx_defect &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dab11-126">For more information, see [sp_msx_defect &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-msx-defect-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects-smo"></a><a name="PowerShellProcedure"></a><span data-ttu-id="dab11-127">Utilizzo di SQL Server Management Objects (SMO)</span><span class="sxs-lookup"><span data-stu-id="dab11-127">Using SQL Server Management Objects (SMO)</span></span>  
 <span data-ttu-id="dab11-128">Utilizzare la `MsxDefect Method`.</span><span class="sxs-lookup"><span data-stu-id="dab11-128">Use the `MsxDefect Method`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab11-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dab11-129">See Also</span></span>  
 <span data-ttu-id="dab11-130">[Creazione di un ambiente multiserver](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="dab11-130">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="dab11-131">[Amministrazione automatizzata in un'organizzazione](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="dab11-131">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="dab11-132">Escludere più server di destinazione da un server master</span><span class="sxs-lookup"><span data-stu-id="dab11-132">Defect Multiple Target Servers from a Master Server</span></span>](defect-multiple-target-servers-from-a-master-server.md)  
