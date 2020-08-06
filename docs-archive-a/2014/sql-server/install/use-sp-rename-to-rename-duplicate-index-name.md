---
title: Usare sp_rename per rinominare il nome di indice duplicato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- table names [SQL Server]
- duplicate table names
- index names [SQL Server]
- sp_rename
- duplicate index names
ms.assetid: ee66c7a5-eb6d-4fcf-970c-ab099d78c8d9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b8ffe3b9befd0c7239d32094e5738e0fb2947c5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726443"
---
# <a name="use-sp_rename-to-rename-duplicate-index-name"></a><span data-ttu-id="f2a56-102">Utilizzare sp_rename per rinominare gli indici duplicati</span><span class="sxs-lookup"><span data-stu-id="f2a56-102">Use sp_rename to rename duplicate index name</span></span>
  <span data-ttu-id="f2a56-103">Sono stati rilevati nomi di indici di tabella o di vista duplicati.</span><span class="sxs-lookup"><span data-stu-id="f2a56-103">Upgrade Advisor has detected duplicate table or view index names.</span></span> <span data-ttu-id="f2a56-104">Rinominare gli indici prima di eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f2a56-104">Rename the indexes to remove duplicates before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f2a56-105">Componente</span><span class="sxs-lookup"><span data-stu-id="f2a56-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="f2a56-106">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="f2a56-106">Corrective Action</span></span>  
  
1.  <span data-ttu-id="f2a56-107">Individuare gli indici duplicati eseguendo la query seguente:</span><span class="sxs-lookup"><span data-stu-id="f2a56-107">Locate the duplicate indexes by executing the following query.</span></span>  
  
    ```  
    SELECT DISTINCT OBJECT_NAME(o.id), name  
    FROM sysindexes as o  
    WHERE EXISTS   
        (SELECT name FROM sysindexes  as i  
          WHERE i.id = o.id  
          AND i.name = o.name and i.indid < o.indid);  
    ```  
  
2.  <span data-ttu-id="f2a56-108">Utilizzare **sp_rename** per modificare uno dei nomi degli indici.</span><span class="sxs-lookup"><span data-stu-id="f2a56-108">Use **sp_rename** to change one of the index names.</span></span> <span data-ttu-id="f2a56-109">Poiché i nomi di indice sono uguali, non è possibile determinare quale indice verrà rinominato.</span><span class="sxs-lookup"><span data-stu-id="f2a56-109">Because the index names are the same, you cannot determine which index will be renamed.</span></span> <span data-ttu-id="f2a56-110">Questa operazione consente quindi di differenziare gli indici.</span><span class="sxs-lookup"><span data-stu-id="f2a56-110">This step allows you to differentiate the indexes.</span></span>  
  
    ```  
    EXEC sp_rename N'table_name.index_name', N'new_index_name', N'INDEX'  
    ```  
  
3.  <span data-ttu-id="f2a56-111">Per verificare quale indice è stato rinominato eseguire la query seguente,</span><span class="sxs-lookup"><span data-stu-id="f2a56-111">Verify which index was renamed by executing the following query.</span></span> <span data-ttu-id="f2a56-112">che restituisce tutti gli indici, inclusi i nomi delle colonne chiave sulla tabella o vista specificata:</span><span class="sxs-lookup"><span data-stu-id="f2a56-112">This query returns all indexes (including key column names) on the specified table or view.</span></span>  
  
    ```  
    SELECT i.name AS IndexName, c.name AS ColumnName, ik.colid, ik.keyno  
    FROM sysindexes i  
    JOIN sysindexkeys ik ON i.id = ik.id and i.indid = ik.indid   
    JOIN syscolumns c ON c.id = ik.id and ik.colid = c.colid  
    WHERE i.id = OBJECT_ID('table_or_view_name')  
    ```  
  
4.  <span data-ttu-id="f2a56-113">Se necessario, utilizzare di nuovo **sp_rename** per correggere i nomi degli indici.</span><span class="sxs-lookup"><span data-stu-id="f2a56-113">If necessary, use **sp_rename** again to correct the index names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a56-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2a56-114">See Also</span></span>  
 <span data-ttu-id="f2a56-115">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f2a56-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f2a56-116">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="f2a56-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
