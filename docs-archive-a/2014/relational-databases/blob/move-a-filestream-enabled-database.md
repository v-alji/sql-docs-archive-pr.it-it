---
title: Spostare un database abilitato per FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], moving a FILESTREAM-enabled database
ms.assetid: dd4d270d-9283-431a-aa6b-e571fced1893
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79740ee86a89566113650865e3fd6ec54c7cb918
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712051"
---
# <a name="move-a-filestream-enabled-database"></a><span data-ttu-id="0df82-102">Spostamento di un database abilitato per FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="0df82-102">Move a FILESTREAM-Enabled Database</span></span>
  <span data-ttu-id="0df82-103">In questo argomento viene illustrato come spostare un database abilitato per FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="0df82-103">This topic shows how to move a FILESTREAM-enabled database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0df82-104">Gli esempi di questo argomento presuppongono l'uso del database Archive creato in [Creare un database abilitato per FILESTREAM](create-a-filestream-enabled-database.md).</span><span class="sxs-lookup"><span data-stu-id="0df82-104">The examples in this topic require the Archive database that is created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md).</span></span>  
  
### <a name="to-move-a-filestream-enabled-database"></a><span data-ttu-id="0df82-105">Per spostare un database abilitato per FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="0df82-105">To move a FILESTREAM-enabled database</span></span>  
  
1.  <span data-ttu-id="0df82-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]fare clic su **Nuova query** per aprire l'editor di query.</span><span class="sxs-lookup"><span data-stu-id="0df82-106">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click **New Query** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="0df82-107">Copiare lo script [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente nell'editor di query e fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0df82-107">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="0df82-108">Lo script consentirà di visualizzare la posizione dei file fisici del database utilizzati dal database FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="0df82-108">This script displays the location of the physical database files that the FILESTREAM database uses.</span></span>  
  
    ```sql  
    USE Archive  
    GO  
    SELECT type_desc, name, physical_name from sys.database_files  
    ```  
  
3.  <span data-ttu-id="0df82-109">Copiare lo script [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente nell'editor di query e fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0df82-109">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="0df82-110">Questo codice consente di attivare la modalità offline per il database `Archive` .</span><span class="sxs-lookup"><span data-stu-id="0df82-110">This code takes the `Archive` database offline.</span></span>  
  
    ```sql  
    USE master  
    EXEC sp_detach_db Archive  
    GO  
    ```  
  
4.  <span data-ttu-id="0df82-111">Creare la cartella `C:\moved_location`, quindi spostarvi i file e le cartelle elencati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="0df82-111">Create the folder `C:\moved_location`, and then move the files and folders that are listed in step 2 into it.</span></span>  
  
5.  <span data-ttu-id="0df82-112">Copiare lo script [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente nell'editor di query e fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0df82-112">Copy the following [!INCLUDE[tsql](../../includes/tsql-md.md)] script into the Query Editor, and then click **Execute**.</span></span> <span data-ttu-id="0df82-113">Questo script consente di impostare la modalità non online per il database `Archive` .</span><span class="sxs-lookup"><span data-stu-id="0df82-113">This script sets the `Archive` database online.</span></span>  
  
    ```sql  
    CREATE DATABASE Archive ON  
    PRIMARY ( NAME = Arch1,  
        FILENAME = 'c:\moved_location\archdat1.mdf'),  
    FILEGROUP FileStreamGroup1 CONTAINS FILESTREAM( NAME = Arch3,  
        FILENAME = 'c:\moved_location\filestream1')  
    LOG ON  ( NAME = Archlog1,  
        FILENAME = 'c:\moved_location\archlog1.ldf')  
    FOR ATTACH  
    GO  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0df82-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0df82-114">See Also</span></span>  
 [<span data-ttu-id="0df82-115">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0df82-115">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
