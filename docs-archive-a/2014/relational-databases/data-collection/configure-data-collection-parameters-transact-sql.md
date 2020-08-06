---
title: Configurare i parametri per la raccolta dati (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
ms.assetid: 850905b6-35d2-4ed1-ab51-de64daa832b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a8333b47612b4fbd933ef132e886b8125ffb58a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718263"
---
# <a name="configure-data-collection-parameters-transact-sql"></a><span data-ttu-id="f186d-102">Configurazione dei parametri per la raccolta dati (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f186d-102">Configure Data Collection Parameters (Transact-SQL)</span></span>
  <span data-ttu-id="f186d-103">Prima di creare un set di raccolta personalizzato è necessario configurare i parametri della raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="f186d-103">Before you create a custom collection set, you must first configure data collection parameters.</span></span> <span data-ttu-id="f186d-104">A tale scopo, utilizzare le stored procedure fornite con l'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="f186d-104">You can do this by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="f186d-105">Il completamento di questa attività comporta l'utilizzo dell'editor di query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per effettuare la procedura descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="f186d-105">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f186d-106">I parametri per la raccolta dati possono essere configurati una volta sola.</span><span class="sxs-lookup"><span data-stu-id="f186d-106">You only configure data collection parameters once.</span></span> <span data-ttu-id="f186d-107">Dopo la configurazione, tali parametri vengono utilizzati per qualsiasi set di raccolta aggiuntivo creato.</span><span class="sxs-lookup"><span data-stu-id="f186d-107">After configuration, these parameters are used for any additional collection sets that you create.</span></span>  
  
### <a name="configure-data-collection-parameters"></a><span data-ttu-id="f186d-108">Configurazione dei parametri per la raccolta dati</span><span class="sxs-lookup"><span data-stu-id="f186d-108">Configure data collection parameters</span></span>  
  
1.  <span data-ttu-id="f186d-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi al database in cui si desidera creare un set di raccolta personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f186d-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the database where you want to create a custom collection set.</span></span>  
  
2.  <span data-ttu-id="f186d-110">Nell'editor di query eseguire le istruzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="f186d-110">In Query Editor, issue the following statements.</span></span>  
  
    ```sql  
    USE msdb;  
    EXEC sp_syscollector_set_warehouse_instance_name N'INSTANCE_NAME';-- where instance name is the name of the SQL Server instance  
    EXEC sp_syscollector_set_warehouse_database_name N'MDW';  
    EXEC sp_syscollector_set_cache_directory N'D:\tempdata';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f186d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f186d-111">See Also</span></span>  
 <span data-ttu-id="f186d-112">[Raccolta dati](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="f186d-112">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="f186d-113">Stored procedure dell'agente di raccolta dati &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f186d-113">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
