---
title: 'Lezione 4: eseguire un ripristino da un backup completo del database | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 580f76e6-9802-4abc-9043-db6de592c733
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9906ea14c2f76a49644a8f76fbd894adf8b9d500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627577"
---
# <a name="lesson-4-perform-a-restore-from-a-full-database-backup"></a><span data-ttu-id="fb961-102">Lezione 4: Eseguire un ripristino da un backup completo del database</span><span class="sxs-lookup"><span data-stu-id="fb961-102">Lesson 4: Perform a Restore From a Full Database Backup</span></span>
  <span data-ttu-id="fb961-103">In questa lezione viene illustrato l'utilizzo di un'istruzione tsql per eseguire un ripristino da un backup completo del database creato nella lezione precedente.</span><span class="sxs-lookup"><span data-stu-id="fb961-103">This lesson demonstrates the use of a tsql statement to perform a restore from a full database backup created in the previous lesson.</span></span>  
  
## <a name="perform-a-restore-of-a-database-backup"></a><span data-ttu-id="fb961-104">Eseguire un ripristino di un backup del database</span><span class="sxs-lookup"><span data-stu-id="fb961-104">Perform a Restore of a Database Backup</span></span>  
 <span data-ttu-id="fb961-105">Per ripristinare un backup completo del database, attenersi ai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fb961-105">To restore a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="fb961-106">Connettersi a [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb961-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="fb961-107">In **Esplora oggetti**connettersi all'istanza di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb961-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="fb961-108">Sulla barra del menu Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="fb961-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="fb961-109">Copiare e incollare l'esempio seguente nella finestra Query e modificare se necessario.</span><span class="sxs-lookup"><span data-stu-id="fb961-109">Copy and paste the following example into the query window, modify as needed.</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks2012   
    FROM URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    WITH CREDENTIAL = 'mycredential';  
    , STATS = 5 - use this to see monitor the progress  
    GO  
  
    ```  
  
5.  <span data-ttu-id="fb961-110">Verificare l'istruzione T-SQL e fare clic su **Esegui** .</span><span class="sxs-lookup"><span data-stu-id="fb961-110">Verify the T-SQL statement and click **Execute**</span></span>  
  
### <a name="return-to-tutorials-portal"></a><span data-ttu-id="fb961-111">Ritornare al portale delle esercitazioni</span><span class="sxs-lookup"><span data-stu-id="fb961-111">Return to Tutorials Portal</span></span>  
 <span data-ttu-id="fb961-112">[Esercitazione: SQL Server il backup e il ripristino nel servizio di archiviazione BLOB di Azure](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="fb961-112">[Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service](../relational-databases/tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service.md).</span></span>  
  
  
