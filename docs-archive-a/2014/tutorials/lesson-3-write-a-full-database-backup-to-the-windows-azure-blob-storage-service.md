---
title: 'Lezione 3: scrivere un backup completo del database nel servizio di archiviazione BLOB di Azure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 454c8296-64e9-46ed-b141-5ebfbc8a4fe2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 17e7e6b608d248a48cde52f1107bb910f06d64ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711200"
---
# <a name="lesson-3-write-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="85a8c-102">Lezione 3: Scrivere un backup completo del database nel servizio Archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="85a8c-102">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>
  <span data-ttu-id="85a8c-103">In questa lezione viene illustrato l'utilizzo dell'istruzione tsql per eseguire un backup completo del database nel servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="85a8c-103">This lesson demonstrates the use of tsql statement to perform a full database backup to Azure Blob storage service.</span></span>  
  
## <a name="perform-a-full-database-backup-to-the-azure-blob-storage-service"></a><span data-ttu-id="85a8c-104">Eseguire un backup completo del database nel servizio di archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="85a8c-104">Perform a Full Database Backup to the Azure Blob Storage Service</span></span>  
 <span data-ttu-id="85a8c-105">Per creare un backup completo del database, attenersi ai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="85a8c-105">To create a full database backup, use the following steps:</span></span>  
  
1.  <span data-ttu-id="85a8c-106">Connettersi a [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85a8c-106">Connect to [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="85a8c-107">In **Esplora oggetti**connettersi all'istanza di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85a8c-107">In the **Object Explorer**, connect to the instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
3.  <span data-ttu-id="85a8c-108">Sulla barra del menu Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="85a8c-108">On the Standard menu bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="85a8c-109">Copiare e incollare l'esempio seguente nella finestra Query, modificare se necessario, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="85a8c-109">Copy and paste the following example into the query window, modify as needed, and click **Execute**.</span></span>  
  
    ```  
    BACKUP DATABASE[AdventureWorks2012]   
    TO URL = 'https://mystorageaccount.blob.core.windows.net/privatecontainertest/AdventureWorks2012.bak'   
    /* URL includes the endpoint for the BLOB service, followed by the container name, and the name of the backup file*/   
    WITH CREDENTIAL = 'mycredential';  
    /* name of the credential you created in the previous step */   
    GO  
  
    ```  
  
5.  <span data-ttu-id="85a8c-110">In Esplora oggetti connettersi alla risorsa di archiviazione Azure.</span><span class="sxs-lookup"><span data-stu-id="85a8c-110">In the object explorer, connect to Azure Storage.</span></span> <span data-ttu-id="85a8c-111">Sfogliare per individuare il contenitore e i file di backup appena creati.</span><span class="sxs-lookup"><span data-stu-id="85a8c-111">Browse to find the container and the newly created backup files.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="85a8c-112">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="85a8c-112">Next Lesson</span></span>  
 <span data-ttu-id="85a8c-113">[Lezione 4: eseguire un ripristino da un backup completo del database](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md).</span><span class="sxs-lookup"><span data-stu-id="85a8c-113">[Lesson 4: Perform a Restore From a Full Database Backup](../../2014/tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md).</span></span>  
  
  
