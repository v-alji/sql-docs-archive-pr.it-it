---
title: Usare il rilevamento delle modifiche (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], making changes
- change tracking [SQL Server], troubleshooting
- updating data [SQL Server]
- troubleshooting [SQL Server], change tracking
- data changes [SQL Server]
- tracking data changes [SQL Server]
- data [SQL Server], changing
- change tracking [SQL Server], data restore
- change tracking [SQL Server], ensuring consistent results
- change tracking [SQL Server], handling changes
ms.assetid: 5aec22ce-ae6f-4048-8a45-59ed05f04dc5
author: rothja
ms.author: jroth
ms.openlocfilehash: bdb8205a789894caf8c8e2d3c3f491751757bab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637165"
---
# <a name="work-with-change-tracking-sql-server"></a><span data-ttu-id="15e9f-102">Utilizzare il rilevamento delle modifiche (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="15e9f-102">Work with Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="15e9f-103">Le applicazioni che utilizzano il rilevamento delle modifiche devono essere in grado di ottenere le modifiche registrate, di applicare tali modifiche a un altro archivio dati e di aggiornare il database di origine.</span><span class="sxs-lookup"><span data-stu-id="15e9f-103">Applications that use change tracking must be able to obtain tracked changes, apply these changes to another data store, and update the source database.</span></span> <span data-ttu-id="15e9f-104">In questo argomento viene descritto come eseguire queste attività e viene illustrato il ruolo svolto dal rilevamento delle modifiche quando si verifica un failover ed è necessario ripristinare un database da un backup.</span><span class="sxs-lookup"><span data-stu-id="15e9f-104">This topic describes how to perform these tasks, and also the role change tracking plays when a failover occurs and a database must be restored from a backup.</span></span>  
  
##  <a name="obtain-changes-by-using-change-tracking-functions"></a><a name="Obtain"></a> <span data-ttu-id="15e9f-105">Utilizzo delle funzioni di rilevamento delle modifiche per ottenere le modifiche</span><span class="sxs-lookup"><span data-stu-id="15e9f-105">Obtain Changes by Using Change Tracking Functions</span></span>  
 <span data-ttu-id="15e9f-106">Viene descritto come utilizzare le funzioni di rilevamento delle modifiche per ottenere le modifiche apportate al database e le informazioni relative.</span><span class="sxs-lookup"><span data-stu-id="15e9f-106">Describes how to use the change tracking functions to obtain changes and information about the changes that were made to a database.</span></span>  
  
### <a name="about-the-change-tracking-functions"></a><span data-ttu-id="15e9f-107">Informazioni sulle funzioni di rilevamento delle modifiche</span><span class="sxs-lookup"><span data-stu-id="15e9f-107">About the Change Tracking Functions</span></span>  
 <span data-ttu-id="15e9f-108">Per ottenere le modifiche apportate a un database e le relative informazioni, nelle applicazioni è possibile utilizzare le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15e9f-108">Applications can use the following functions to obtain the changes that are made in a database and information about the changes:</span></span>  
  
 <span data-ttu-id="15e9f-109">CHANGETABLE(CHANGES …)</span><span class="sxs-lookup"><span data-stu-id="15e9f-109">CHANGETABLE(CHANGES ...) function</span></span>  
 <span data-ttu-id="15e9f-110">Questa funzione per i set di righe viene utilizzata per eseguire query relative alle informazioni sulle modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-110">This rowset function is used to query for change information.</span></span> <span data-ttu-id="15e9f-111">La funzione esegue una query sui dati archiviati nelle tabelle per il rilevamento delle modifiche interne</span><span class="sxs-lookup"><span data-stu-id="15e9f-111">The function queries the data stored in the internal change tracking tables.</span></span> <span data-ttu-id="15e9f-112">e restituisce un set di risultati contenente le chiavi primarie delle righe modificate, insieme ad altre informazioni sulle modifiche, ad esempio l'operazione, le colonne aggiornate e la versione della riga.</span><span class="sxs-lookup"><span data-stu-id="15e9f-112">The function returns a results set that contains the primary keys of rows that have changed together with other change information such as the operation, columns updated and version for the row.</span></span>  
  
 <span data-ttu-id="15e9f-113">CHANGETABLE(CHANGES ...) accetta l'ultima versione sincronizzata come argomento.</span><span class="sxs-lookup"><span data-stu-id="15e9f-113">CHANGETABLE(CHANGES ...) takes a last synchronization version as an argument.</span></span> <span data-ttu-id="15e9f-114">L'ultima versione sincronizzata si ottiene utilizzando la variabile `@last_synchronization_version` .</span><span class="sxs-lookup"><span data-stu-id="15e9f-114">The last sychronization version is obtained using the `@last_synchronization_version` variable.</span></span> <span data-ttu-id="15e9f-115">La semantica dell'ultima versione sincronizzata è la seguente:</span><span class="sxs-lookup"><span data-stu-id="15e9f-115">The semantics of the last synchronization version are as follows:</span></span>  
  
-   <span data-ttu-id="15e9f-116">Il client chiamante ha ottenuto le modifiche e conosce tutte le modifiche fino all'ultima versione sincronizzata compresa.</span><span class="sxs-lookup"><span data-stu-id="15e9f-116">The calling client has obtained changes and knows about all changes up to and including the last synchronization version.</span></span>  
  
-   <span data-ttu-id="15e9f-117">Tutte le modifiche eseguite dopo l'ultima versione sincronizzata verranno pertanto restituite in CHANGETABLE(CHANGES …).</span><span class="sxs-lookup"><span data-stu-id="15e9f-117">CHANGETABLE(CHANGES ...) will therefore return all changes that have occurred after the last synchronization version.</span></span>  
  
     <span data-ttu-id="15e9f-118">Nella figura seguente viene illustrato il modo in cui CHANGETABLE(CHANGES ...) viene utilizzata per ottenere modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-118">The following illustration shows how CHANGETABLE(CHANGES ...) is used to obtain changes.</span></span>  
  
     <span data-ttu-id="15e9f-119">![Esempio di output di query per il rilevamento delle modifiche](../../database-engine/media/queryoutput.gif "Esempio di output di query per il rilevamento delle modifiche")</span><span class="sxs-lookup"><span data-stu-id="15e9f-119">![Example of change tracking query output](../../database-engine/media/queryoutput.gif "Example of change tracking query output")</span></span>  
  
 <span data-ttu-id="15e9f-120">Funzione CHANGE_TRACKING_CURRENT_VERSION()</span><span class="sxs-lookup"><span data-stu-id="15e9f-120">CHANGE_TRACKING_CURRENT_VERSION() function</span></span>  
 <span data-ttu-id="15e9f-121">Questa funzione viene utilizzata per ottenere la versione corrente che verrà utilizzata alla successiva esecuzione di query sulle modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-121">Is used to obtain the current version that will be used the next time when querying changes.</span></span> <span data-ttu-id="15e9f-122">Tale versione è quella relativa all'ultima transazione di cui è stato eseguito il commit.</span><span class="sxs-lookup"><span data-stu-id="15e9f-122">This version represents the version of the last committed transaction.</span></span>  
  
 <span data-ttu-id="15e9f-123">Funzione CHANGE_TRACKING_MIN_VALID_VERSION()</span><span class="sxs-lookup"><span data-stu-id="15e9f-123">CHANGE_TRACKING_MIN_VALID_VERSION()function</span></span>  
 <span data-ttu-id="15e9f-124">Questa funzione viene utilizzata per ottenere la versione minima valida che un client può avere per ottenere risultati validi da CHANGETABLE ().</span><span class="sxs-lookup"><span data-stu-id="15e9f-124">Is used to obtain the minimum valid version that a client can have and still obtain valid results from CHANGETABLE().</span></span> <span data-ttu-id="15e9f-125">Il client deve controllare l'ultima versione sincronizzata rispetto al valore restituito dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-125">The client should check the last synchronization version against the value thatis returned by this function.</span></span> <span data-ttu-id="15e9f-126">Se l'ultima versione sincronizzata è inferiore rispetto a quella restituita dalla funzione, il client non sarà in grado di ottenere risultati validi da CHANGETABLE() e sarà necessario reinizializzare i dati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-126">If the last synchronization version is less than the version returned by this function, the client will be unable to obtain valid results from CHANGETABLE() and will have to reinitialize.</span></span>  
  
### <a name="obtaining-initial-data"></a><span data-ttu-id="15e9f-127">Acquisizione dei dati iniziali</span><span class="sxs-lookup"><span data-stu-id="15e9f-127">Obtaining Initial Data</span></span>  
 <span data-ttu-id="15e9f-128">Prima che un'applicazione sia in grado di ottenere modifiche per la prima volta, è necessario che invii una query per ottenere i dati iniziali e la versione sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="15e9f-128">Before an application can obtain changes for the first time, the application must send a query to obtain the initial data and the synchronization version.</span></span> <span data-ttu-id="15e9f-129">È necessario che nell'applicazione vengano ottenuti i dati appropriati direttamente dalla tabella, quindi venga utilizzata CHANGE_TRACKING_CURRENT_VERSION() per ottenere la versione iniziale.</span><span class="sxs-lookup"><span data-stu-id="15e9f-129">The application must obtain the appropriate data directly from the table, and then use CHANGE_TRACKING_CURRENT_VERSION() to obtain the initial version.</span></span> <span data-ttu-id="15e9f-130">Tale versione verrà passata a CHANGETABLE(CHANGES ...) la prima volta che le modifiche vengono ottenute.</span><span class="sxs-lookup"><span data-stu-id="15e9f-130">This version will be passed to CHANGETABLE(CHANGES ...) the first time that changes are obtained.</span></span>  
  
 <span data-ttu-id="15e9f-131">Nell'esempio seguente viene illustrato come ottenere la versione di sincronizzazione e il set di dati iniziali.</span><span class="sxs-lookup"><span data-stu-id="15e9f-131">The following example shows how to obtain the initial synchronization version and the initial data set.</span></span>  
  
```sql  
    -- Obtain the current synchronization version. This will be used next time that changes are obtained.  
    SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
    -- Obtain initial data set.  
    SELECT  
        P.ProductID, P.Name, P.ListPrice  
    FROM  
        SalesLT.Product AS P  
```  
  
### <a name="using-the-change-tracking-functions-to-obtain-changes"></a><span data-ttu-id="15e9f-132">Utilizzo delle funzioni di rilevamento delle modifiche per ottenere le modifiche</span><span class="sxs-lookup"><span data-stu-id="15e9f-132">Using the Change Tracking Functions to Obtain Changes</span></span>  
 <span data-ttu-id="15e9f-133">Per ottenere le righe modificate in una tabella e le relative informazioni, utilizzare CHANGETABLE(CHANGES ...). La query seguente, ad esempio, consente di ottenere le modifiche per la tabella `SalesLT.Product` .</span><span class="sxs-lookup"><span data-stu-id="15e9f-133">To obtain the changed rows for a table and information about the changes, use CHANGETABLE(CHANGES...). For example, the following query obtains changes for the `SalesLT.Product` table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, CT.SYS_CHANGE_OPERATION,  
    CT.SYS_CHANGE_COLUMNS, CT.SYS_CHANGE_CONTEXT  
FROM  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
  
```  
  
 <span data-ttu-id="15e9f-134">Poiché in un client viene in genere richiesto di ottenere i dati più recenti relativi a una riga anziché le sole chiavi primarie per la riga stessa,</span><span class="sxs-lookup"><span data-stu-id="15e9f-134">Usually, a client will want to obtain the latest data for a row instead of only the primary keys for the row.</span></span> <span data-ttu-id="15e9f-135">verrà creato un join tra i risultati di CHANGETABLE(CHANGES ...) e i dati presenti nella tabella utente.</span><span class="sxs-lookup"><span data-stu-id="15e9f-135">Therefore, an application would join the results from CHANGETABLE(CHANGES ...) with the data in the user table.</span></span> <span data-ttu-id="15e9f-136">Nella query seguente, ad esempio, viene creato un join con la tabella `SalesLT.Product` per ottenere i valori per le colonne `Name` e `ListPrice` .</span><span class="sxs-lookup"><span data-stu-id="15e9f-136">For example, the following query joins with the `SalesLT.Product` table to obtain the values for the `Name` and `ListPrice` columns.</span></span> <span data-ttu-id="15e9f-137">Si noti l'utilizzo di `OUTER JOIN`,</span><span class="sxs-lookup"><span data-stu-id="15e9f-137">Note the use of `OUTER JOIN`.</span></span> <span data-ttu-id="15e9f-138">necessario per garantire che le informazioni sulle modifiche vengano restituite per le righe eliminate dalla tabella utente.</span><span class="sxs-lookup"><span data-stu-id="15e9f-138">This is required to make sure that the change information is returned for those rows that have been deleted from the user table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
 <span data-ttu-id="15e9f-139">Per ottenere la versione da utilizzare nella successiva enumerazione delle modifiche, utilizzare CHANGE_TRACKING_CURRENT_VERSION(), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="15e9f-139">To obtain the version for use in the next change enumeration, use CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION()  
```  
  
 <span data-ttu-id="15e9f-140">Quando in un'applicazione vengono ottenute modifiche, è necessario utilizzare sia CHANGETABLE(CHANGES …) che CHANGE_TRACKING_CURRENT_VERSION(), come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="15e9f-140">When an application obtains changes, it must use both CHANGETABLE(CHANGES...) and CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
-- Obtain the current synchronization version. This will be used the next time CHANGETABLE(CHANGES...) is called.  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
-- Obtain incremental changes by using the synchronization version obtained the last time the data was synchronized.  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
### <a name="version-numbers"></a><span data-ttu-id="15e9f-141">Numeri di versione</span><span class="sxs-lookup"><span data-stu-id="15e9f-141">Version Numbers</span></span>  
 <span data-ttu-id="15e9f-142">Un database in cui è abilitato il rilevamento delle modifiche dispone di un contatore di versione che aumenta in base alle modifiche apportate alle tabelle in cui il rilevamento è attivato.</span><span class="sxs-lookup"><span data-stu-id="15e9f-142">A database that has change tracking enabled has a version counter that increases as changes are made to change tracked tables.</span></span> <span data-ttu-id="15e9f-143">A ciascuna riga modificata è associato un numero di versione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-143">Each changed row has a version number that is associated with it.</span></span> <span data-ttu-id="15e9f-144">Quando a un'applicazione viene inviata una richiesta per eseguire una query relativa alle modifiche, viene chiamata una funzione che specifica un numero di versione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-144">When a request is sent to an application to query for changes, a function is called that supplies a version number.</span></span> <span data-ttu-id="15e9f-145">Tale funzione restituisce informazioni su tutte le modifiche apportate a partire da tale versione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-145">The function returns information about all the changes that have been made since that version.</span></span> <span data-ttu-id="15e9f-146">Per alcuni aspetti, la versione del rilevamento delle modifiche è concettualmente analoga al tipo di dati `rowversion`.</span><span class="sxs-lookup"><span data-stu-id="15e9f-146">In some ways, change tracking version is similar in concept to the `rowversion` data type.</span></span>  
  
### <a name="validating-the-last-synchronized-version"></a><span data-ttu-id="15e9f-147">Convalida dell'ultima versione sincronizzata</span><span class="sxs-lookup"><span data-stu-id="15e9f-147">Validating the Last Synchronized Version</span></span>  
 <span data-ttu-id="15e9f-148">Le informazioni sulle modifiche vengono mantenute per un periodo di tempo limitato,</span><span class="sxs-lookup"><span data-stu-id="15e9f-148">Information about changes is maintained for a limited time.</span></span> <span data-ttu-id="15e9f-149">la cui lunghezza viene controllata dal parametro CHANGE_RETENTION che può essere specificato nell'istruzione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="15e9f-149">The length of time is controlled by the CHANGE_RETENTION parameter that can be specified as part of the ALTER DATABASE.</span></span>  
  
 <span data-ttu-id="15e9f-150">È necessario tenere presente che il periodo di tempo specificato per CHANGE_RETENTION determina la frequenza con cui per tutte le applicazioni è necessario richiedere le modifiche apportate al database.</span><span class="sxs-lookup"><span data-stu-id="15e9f-150">Be aware that the time specified for CHANGE_RETENTION determines how frequently all applications must request changes from the database.</span></span> <span data-ttu-id="15e9f-151">Se a un'applicazione è associato un valore relativo a *last_synchronization_version* meno recente rispetto a quello della versione sincronizzata valida minima per una tabella, tale applicazione non può eseguire un'enumerazione delle modifiche valida.</span><span class="sxs-lookup"><span data-stu-id="15e9f-151">If an application has a value for *last_synchronization_version* that is older than the minimum valid synchronization version for a table, that application cannot perform valid change enumeration.</span></span> <span data-ttu-id="15e9f-152">poiché alcune informazioni sulle modifiche potrebbero essere state eliminate.</span><span class="sxs-lookup"><span data-stu-id="15e9f-152">This is because some change information might have been cleaned up.</span></span> <span data-ttu-id="15e9f-153">Affinché in un'applicazione possano essere ottenute le modifiche tramite CHANGETABLE(CHANGES …), è necessario che venga convalidato il valore relativo a *last_synchronization_version* di cui è previsto il passaggio a CHANGETABLE(CHANGES …). Se il valore di *last_synchronization_version* non è valido, è necessario che nell'applicazione vengano reinizializzati tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-153">Before an application obtains changes by using CHANGETABLE(CHANGES ...), the application must validate the value for *last_synchronization_version* that it plans to pass to CHANGETABLE(CHANGES ...). If the value of *last_synchronization_version* is not valid, that application must reinitialize all the data.</span></span>  
  
 <span data-ttu-id="15e9f-154">Nell'esempio seguente viene illustrato come verificare la validità del valore di `last_synchronization_version` per ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="15e9f-154">The following example shows how to verify the validity of the value of `last_synchronization_version` for each table.</span></span>  
  
```sql  
-- Check individual table.  
IF (@last_synchronization_version < CHANGE_TRACKING_MIN_VALID_VERSION(  
                                   OBJECT_ID('SalesLT.Product')))  
BEGIN  
  -- Handle invalid version and do not enumerate changes.  
  -- Client must be reinitialized.  
END  
```  
  
 <span data-ttu-id="15e9f-155">Come illustrato nell'esempio seguente, la validità del valore di `last_synchronization_version` può essere verificata in relazione a tutte le tabelle del database.</span><span class="sxs-lookup"><span data-stu-id="15e9f-155">As the following example shows, the validity of the value of `last_synchronization_version` can be checked against all tables in the database.</span></span>  
  
```sql  
-- Check all tables with change tracking enabled  
IF EXISTS (  
  SELECT COUNT(*) FROM sys.change_tracking_tables  
  WHERE min_valid_version > @last_synchronization_version )  
BEGIN  
  -- Handle invalid version & do not enumerate changes  
  -- Client must be reinitialized  
END  
```  
  
### <a name="using-column-tracking"></a><span data-ttu-id="15e9f-156">Utilizzo del rilevamento a livello di colonna</span><span class="sxs-lookup"><span data-stu-id="15e9f-156">Using Column Tracking</span></span>  
 <span data-ttu-id="15e9f-157">Il rilevamento a livello di colonna consente di ottenere i dati relativi alle sole colonne modificate anziché all'intera riga.</span><span class="sxs-lookup"><span data-stu-id="15e9f-157">Column tracking enables applications to obtain the data for only the columns that have changed instead of the whole row.</span></span> <span data-ttu-id="15e9f-158">Si consideri ad esempio uno scenario in cui in una tabella sono presenti una o più colonne di notevoli dimensioni, ma modificate raramente, e altre colonne che subiscono modifiche frequenti.</span><span class="sxs-lookup"><span data-stu-id="15e9f-158">For example, consider the scenario in which a table has one or more columns that are large, but rarely change; and also has other columns that frequently change.</span></span> <span data-ttu-id="15e9f-159">Senza il rilevamento a livello di colonna, un'applicazione è in grado di rilevare solo che una riga è stata modificata e che è necessario sincronizzare tutti i dati, inclusi quelli presenti nelle colonne di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="15e9f-159">Without column tracking, an application can only determine that a row has changed and would have to synchronize all the data that includes the large column data.</span></span> <span data-ttu-id="15e9f-160">Il rilevamento a livello di colonna consente tuttavia di stabilire se i dati presenti nelle colonne di grandi dimensioni sono stati modificati e di eseguire la sincronizzazione solo in quest'ultimo caso.</span><span class="sxs-lookup"><span data-stu-id="15e9f-160">However, by using column tracking, an application can determine whether the large column data changed and only synchronize the data if it has changed.</span></span>  
  
 <span data-ttu-id="15e9f-161">Le informazioni sul rilevamento a livello di colonna vengono visualizzate nella colonna SYS_CHANGE_COLUMNS restituita dalla funzione CHANGETABLE(CHANGES …).</span><span class="sxs-lookup"><span data-stu-id="15e9f-161">Column tracking information appears in the SYS_CHANGE_COLUMNS column that is returned by the CHANGETABLE(CHANGES ...) function.</span></span>  
  
 <span data-ttu-id="15e9f-162">Il rilevamento a livello di colonna può essere utilizzato in modo che per una colonna cui non sono state apportate modifiche venga restituito il valore NULL.</span><span class="sxs-lookup"><span data-stu-id="15e9f-162">Column tracking can be used so that NULL is returned for a column that has not changed.</span></span> <span data-ttu-id="15e9f-163">Se la colonna può essere impostata su NULL, è necessario che venga restituita una colonna separata per indicare se la colonna è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="15e9f-163">If the column can be changed to NULL, a separate column must be returned to indicate whether the column changed.</span></span>  
  
 <span data-ttu-id="15e9f-164">Nell'esempio seguente se la colonna `CT_ThumbnailPhoto` non ha subito modifiche, verrà restituito il valore `NULL` .</span><span class="sxs-lookup"><span data-stu-id="15e9f-164">In the following example, the `CT_ThumbnailPhoto` column will be `NULL` if that column did not change.</span></span> <span data-ttu-id="15e9f-165">A tale colonna potrebbe inoltre essere associato il valore `NULL` poiché è stata impostata su `NULL` . È possibile utilizzare la colonna `CT_ThumbNailPhoto_Changed` per determinare se la colonna ha subito modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-165">This column could also be `NULL` because it was changed to `NULL` - the application can use the `CT_ThumbNailPhoto_Changed` column to determine whether the column changed.</span></span>  
  
```sql  
DECLARE @PhotoColumnId int = COLUMNPROPERTY(  
    OBJECT_ID('SalesLT.Product'),'ThumbNailPhoto', 'ColumnId')  
  
SELECT  
    CT.ProductID, P.Name, P.ListPrice, -- Always obtain values.  
    CASE  
           WHEN CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) = 1  
            THEN ThumbNailPhoto  
            ELSE NULL  
      END AS CT_ThumbNailPhoto,  
      CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) AS  
                                   CT_ThumbNailPhoto_Changed  
     CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
     CT.SYS_CHANGE_CONTEXT  
FROM  
     SalesLT.Product AS P  
INNER JOIN  
     CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
     P.ProductID = CT.ProductID AND  
     CT.SYS_CHANGE_OPERATION = 'U'  
```  
  
### <a name="obtaining-consistent-and-correct-results"></a><span data-ttu-id="15e9f-166">Acquisizione di risultati coerenti e corretti</span><span class="sxs-lookup"><span data-stu-id="15e9f-166">Obtaining Consistent and Correct Results</span></span>  
 <span data-ttu-id="15e9f-167">Per ottenere i dati modificati relativi a una tabella, è necessario effettuare più operazioni.</span><span class="sxs-lookup"><span data-stu-id="15e9f-167">Obtaining the changed data for a table requires multiple steps.</span></span> <span data-ttu-id="15e9f-168">È necessario inoltre tenere presente che potrebbero venire restituiti risultati incoerenti o non corretti se non vengono considerati e gestiti problemi specifici.</span><span class="sxs-lookup"><span data-stu-id="15e9f-168">Be aware that inconsistent or incorrect results could be returned if certain issues are not considered and handled.</span></span>  
  
 <span data-ttu-id="15e9f-169">Per ottenere le modifiche apportate a una tabella Sales e a una tabella SalesOrders, in un'applicazione è necessario ad esempio effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15e9f-169">For example, to obtain the changes that were made to a Sales table and SalesOrders table, an application would perform the following steps:</span></span>  
  
1.  <span data-ttu-id="15e9f-170">Convalidare l'ultima versione sincronizzata utilizzando CHANGE_TRACKING_MIN_VALID_VERSION().</span><span class="sxs-lookup"><span data-stu-id="15e9f-170">Validate the last synchronized version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
2.  <span data-ttu-id="15e9f-171">Ottenere la versione che può essere utilizzata per ottenere le modifiche la volta successiva utilizzando CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="15e9f-171">Obtain the version that can be used to obtain change the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
3.  <span data-ttu-id="15e9f-172">Ottenere le modifiche per la tabella Sales utilizzando CHANGETABLE(CHANGES …).</span><span class="sxs-lookup"><span data-stu-id="15e9f-172">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...).</span></span>  
  
4.  <span data-ttu-id="15e9f-173">Ottenere le modifiche per la tabella SalesOrders utilizzando CHANGETABLE(CHANGES …).</span><span class="sxs-lookup"><span data-stu-id="15e9f-173">Obtain the changes for the SalesOrders table by using CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="15e9f-174">Nel database sono in esecuzione due processi che possono influenzare i risultati restituiti dalle operazioni precedenti:</span><span class="sxs-lookup"><span data-stu-id="15e9f-174">Two processes are occurring in the database that can affect the results that are returned by the previous steps:</span></span>  
  
-   <span data-ttu-id="15e9f-175">Il processo di pulizia viene eseguito in background e rimuove le informazioni sul rilevamento delle modifiche precedenti rispetto al periodo di memorizzazione specificato.</span><span class="sxs-lookup"><span data-stu-id="15e9f-175">The cleanup process runs in the background and removes change tracking information that is older than the specified retention period.</span></span>  
  
     <span data-ttu-id="15e9f-176">Il processo di pulizia è un processo eseguito separatamente in background che utilizza il periodo di memorizzazione specificato quando si configura il rilevamento delle modifiche per il database.</span><span class="sxs-lookup"><span data-stu-id="15e9f-176">The cleanup process is a separate background process that uses the retention period that is specified when you configure change tracking for the database.</span></span> <span data-ttu-id="15e9f-177">Quando il processo di pulizia viene eseguito nel periodo di tempo che intercorre tra la convalida dell'ultima versione sincronizzata e la chiamata di funzione CHANGETABLE(CHANGES ...), può verificarsi un problema</span><span class="sxs-lookup"><span data-stu-id="15e9f-177">The issue is that the cleanup process can occur in the time between when the last synchronization version was validated and when the call to CHANGETABLE(CHANGES...) is made.</span></span> <span data-ttu-id="15e9f-178">poiché l'ultima versione sincronizzata valida potrebbe non esserlo più nel momento in cui vengono ottenute le modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-178">A last synchronization version that was just valid might no longer be valid by the time the changes are obtained.</span></span> <span data-ttu-id="15e9f-179">È possibile pertanto che vengano restituiti risultati non corretti.</span><span class="sxs-lookup"><span data-stu-id="15e9f-179">Therefore, incorrect results might be returned.</span></span>  
  
-   <span data-ttu-id="15e9f-180">Operazioni DML in corso nelle tabelle Sales e SalesOrders, ad esempio le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15e9f-180">Ongoing DML operations are occurring in the Sales and SalesOrders tables, such as the following operations:</span></span>  
  
    -   <span data-ttu-id="15e9f-181">Esecuzione di modifiche alle tabelle dopo che è stata ottenuta la versione per la volta successiva mediante CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="15e9f-181">Changes can be made to the tables after the version for next time has been obtained by using CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="15e9f-182">È pertanto possibile che vengano restituite più modifiche del previsto.</span><span class="sxs-lookup"><span data-stu-id="15e9f-182">Therefore, more changes can be returned than expected.</span></span>  
  
    -   <span data-ttu-id="15e9f-183">Esecuzione del commit di una transazione nel periodo di tempo che intercorre tra la chiamata di funzione per ottenere le modifiche apportate alla tabella Sales e quella per ottenere le modifiche apportate alla tabella SalesOrders.</span><span class="sxs-lookup"><span data-stu-id="15e9f-183">A transaction could commit in the time between the call to obtain changes from the Sales table and the call to obtain changes from the SalesOrders table.</span></span> <span data-ttu-id="15e9f-184">Ai risultati relativi alla tabella SalesOrder potrebbe pertanto essere associato un valore di chiave esterna che non esiste nella tabella Sales.</span><span class="sxs-lookup"><span data-stu-id="15e9f-184">Therefore, the results for the SalesOrder table could have foreign key value that does not exist in the Sales table.</span></span>  
  
 <span data-ttu-id="15e9f-185">Per risolvere i problemi elencati in precedenza, è consigliabile utilizzare l'isolamento dello snapshot</span><span class="sxs-lookup"><span data-stu-id="15e9f-185">To overcome the previously listed challenges, we recommend that you use snapshot isolation.</span></span> <span data-ttu-id="15e9f-186">che consente di garantire la coerenza delle informazioni sulle modifiche e di evitare situazioni di race condition correlate all'attività di pulizia eseguita in background.</span><span class="sxs-lookup"><span data-stu-id="15e9f-186">This will help to ensure consistency of change information and avoid race conditions that are related to the background cleanup task.</span></span> <span data-ttu-id="15e9f-187">Se non si utilizzano transazioni snapshot, lo sviluppo di un'applicazione che utilizza il rilevamento delle modifiche potrebbe risultare notevolmente più impegnativo.</span><span class="sxs-lookup"><span data-stu-id="15e9f-187">If you do not use snapshot transactions, developing an application that uses change tracking could require significantly more effort.</span></span>  
  
#### <a name="using-snapshot-isolation"></a><span data-ttu-id="15e9f-188">Utilizzo dell'isolamento dello snapshot</span><span class="sxs-lookup"><span data-stu-id="15e9f-188">Using Snapshot Isolation</span></span>  
 <span data-ttu-id="15e9f-189">Il rilevamento delle modifiche è stato progettato per funzionare in modo ottimale con l'isolamento dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="15e9f-189">Change tracking has been designed to work well with snapshot isolation.</span></span> <span data-ttu-id="15e9f-190">È necessario che l'isolamento dello snapshot sia abilitato nel database.</span><span class="sxs-lookup"><span data-stu-id="15e9f-190">Snapshot isolation must be enabled for the database.</span></span> <span data-ttu-id="15e9f-191">Tutti i passaggi necessari per ottenere le modifiche devono essere contenuti in una transazione snapshot</span><span class="sxs-lookup"><span data-stu-id="15e9f-191">All the steps that are required to obtain changes must be included inside a snapshot transaction.</span></span> <span data-ttu-id="15e9f-192">in modo che tutte le modifiche apportate ai dati durante l'acquisizione delle modifiche stesse non siano visibili alle query eseguite nella transazione snapshot.</span><span class="sxs-lookup"><span data-stu-id="15e9f-192">This will ensure that all changes that are made to data while obtaining changes will not be visible to the queries inside the snapshot transaction.</span></span>  
  
 <span data-ttu-id="15e9f-193">Per ottenere dati all'interno di una transazione snapshot, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15e9f-193">To obtain data inside a snapshot transaction, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="15e9f-194">Impostare il livello di isolamento della transazione sullo snapshot e avviare una transazione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-194">Set the transaction isolation level to snapshot and start a transaction.</span></span>  
  
2.  <span data-ttu-id="15e9f-195">Convalidare l'ultima versione sincronizzata utilizzando CHANGE_TRACKING_MIN_VALID_VERSION().</span><span class="sxs-lookup"><span data-stu-id="15e9f-195">Validate the last synchronization version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
3.  <span data-ttu-id="15e9f-196">Ottenere la versione da utilizzare successivamente tramite CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="15e9f-196">Obtain the version to be used the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
4.  <span data-ttu-id="15e9f-197">Ottenere le modifiche per la tabella Sales utilizzando CHANGETABLE(CHANGES …)</span><span class="sxs-lookup"><span data-stu-id="15e9f-197">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...)</span></span>  
  
5.  <span data-ttu-id="15e9f-198">Ottenere le modifiche per la tabella SalesOrders utilizzando CHANGETABLE(CHANGES …)</span><span class="sxs-lookup"><span data-stu-id="15e9f-198">Obtain the changes for the Salesorders table by using CHANGETABLE(CHANGES ...)</span></span>  
  
6.  <span data-ttu-id="15e9f-199">Eseguire il commit della transazione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-199">Commit the transaction.</span></span>  
  
 <span data-ttu-id="15e9f-200">Poiché tutti i passaggi necessari per ottenere le modifiche sono contenuti in una transazione snapshot, tenere in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="15e9f-200">Some points to remember as all steps to obtain changes are inside a snapshot transaction:</span></span>  
  
-   <span data-ttu-id="15e9f-201">Se il processo di pulizia viene eseguito dopo la convalida dell'ultima versione sincronizzata, i risultati restituiti da CHANGETABLE(CHANGES …) saranno ancora validi poiché le operazioni di eliminazione eseguite dal processo di pulizia non saranno visibili all'interno della transazione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-201">If cleanup occurs after the last synchronization version is validated, the results from CHANGETABLE(CHANGES ...) will still be valid as the delete operations performed by cleanup will not be visible inside the transaction.</span></span>  
  
-   <span data-ttu-id="15e9f-202">Qualsiasi modifica apportata alla tabella Sales o SalesOrders dopo che è stata ottenuta la versione sincronizzata successiva non sarà visibile e le chiamate a CHANGETABLE(CHANGES …) non restituiranno mai modifiche con una versione successiva a quella restituita da CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="15e9f-202">Any changes that are made to the Sales table or the SalesOrders table after the next synchronization version is obtained will not be visible, and the calls to CHANGETABLE(CHANGES ...) will never return changes with a version later than that returned by CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="15e9f-203">Verrà inoltre mantenuta la coerenza tra le tabelle Sales e SalesOrders poiché le transazioni di cui era stato eseguito il commit nel periodo di tempo che intercorre tra le chiamate a CHANGETABLE(CHANGES …) non saranno visibili.</span><span class="sxs-lookup"><span data-stu-id="15e9f-203">Consistency between the Sales table and the SalesOrders table will also be maintained, because the transactions that were committed in the time between calls to CHANGETABLE(CHANGES ...) will not be visible.</span></span>  
  
 <span data-ttu-id="15e9f-204">Nell'esempio seguente viene illustrato il modo in cui l'isolamento dello snapshot viene abilitato per un database.</span><span class="sxs-lookup"><span data-stu-id="15e9f-204">The following example shows how snapshot isolation is enabled for a database.</span></span>  
  
```sql  
-- The database must be configured to enable snapshot isolation.  
ALTER DATABASE AdventureWorksLT  
    SET ALLOW_SNAPSHOT_ISOLATION ON;  
```  
  
 <span data-ttu-id="15e9f-205">Una transazione snapshot viene utilizzata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="15e9f-205">A snapshot transaction is used as follows:</span></span>  
  
```sql  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
  -- Verify that version of the previous synchronization is valid.  
  -- Obtain the version to use next time.  
  -- Obtain changes.  
COMMIT TRAN  
```  
  
 <span data-ttu-id="15e9f-206">Per altre informazioni sulle transazioni snapshot, vedere [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15e9f-206">For more information about snapshot transactions, see [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
#### <a name="alternatives-to-using-snapshot-isolation"></a><span data-ttu-id="15e9f-207">Alternative all'utilizzo dell'isolamento dello snapshot</span><span class="sxs-lookup"><span data-stu-id="15e9f-207">Alternatives to Using Snapshot Isolation</span></span>  
 <span data-ttu-id="15e9f-208">Oltre all'isolamento dello snapshot, è possibile utilizzare metodi alternativi che tuttavia richiedono l'esecuzione di un numero maggiore di operazioni per garantire che tutti i requisiti relativi all'applicazione siano soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="15e9f-208">There are alternatives to using snapshot isolation, but they require more work to make sure all application requirements are met.</span></span> <span data-ttu-id="15e9f-209">Per garantire che il valore di *last_synchronization_version* sia valido e che i dati non vengano rimossi dal processo di pulizia prima dell'acquisizione delle modifiche, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15e9f-209">To make sure the *last_synchronization_version* is valid and data is not removed by the cleanup process before changes are obtained, do the following:</span></span>  
  
1.  <span data-ttu-id="15e9f-210">Verificare il valore di *last_synchronization_version* dopo le chiamate a CHANGETABLE ().</span><span class="sxs-lookup"><span data-stu-id="15e9f-210">Check *last_synchronization_version* after the calls to CHANGETABLE().</span></span>  
  
2.  <span data-ttu-id="15e9f-211">Verificare il valore di *last_synchronization_version* come parte di ogni query per ottenere le modifiche tramite CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="15e9f-211">Check *last_synchronization_version* as part of each query to obtain changes by using CHANGETABLE().</span></span>  
  
 <span data-ttu-id="15e9f-212">È possibile che vengano eseguite modifiche dopo che è stata ottenuta la versione sincronizzata per l'enumerazione successiva.</span><span class="sxs-lookup"><span data-stu-id="15e9f-212">Changes can occur after the synchronization version for the next enumeration has been obtained.</span></span> <span data-ttu-id="15e9f-213">Questa situazione può essere gestita in due modi diversi.</span><span class="sxs-lookup"><span data-stu-id="15e9f-213">There are two ways to handle this situation.</span></span> <span data-ttu-id="15e9f-214">L'approccio utilizzato dipende dall'applicazione e dalla modalità di gestione degli effetti collaterali associati a ciascun approccio:</span><span class="sxs-lookup"><span data-stu-id="15e9f-214">The option that is used depends on the application and how it can handle the side-effects of each approach:</span></span>  
  
-   <span data-ttu-id="15e9f-215">Ignorare le modifiche con versione superiore rispetto alla nuova versione sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="15e9f-215">Ignore changes that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="15e9f-216">In base a questo approccio, verrà ignorata ogni riga nuova o aggiornata creata o aggiornata prima delle nuove versioni sincronizzate, ma aggiornata in seguito.</span><span class="sxs-lookup"><span data-stu-id="15e9f-216">This approach has the side effect that a new or updated row would be skipped if it was created or updated before the new synchronization version, but then updated afterward.</span></span> <span data-ttu-id="15e9f-217">Se è presente una nuova riga, potrebbe verificarsi un problema di integrità referenziale se in un'altra tabella era stata creata una riga che faceva riferimento alla riga ignorata.</span><span class="sxs-lookup"><span data-stu-id="15e9f-217">If there is a new row, a referential integrity problem might occur if there was a row in another table that was created that referenced the skipped row.</span></span> <span data-ttu-id="15e9f-218">Se è presente una riga aggiornata, tale riga verrà ignorata e non verrà sincronizzata fino alla volta successiva.</span><span class="sxs-lookup"><span data-stu-id="15e9f-218">If there is an updated existing row, the row will be skipped and not synchronized until the next time.</span></span>  
  
-   <span data-ttu-id="15e9f-219">Includere tutte le modifiche, anche quelle con versione superiore rispetto alla nuova versione sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="15e9f-219">Include all changes, even those that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="15e9f-220">Le righe con versione superiore alla nuova versione sincronizzata verranno ottenute anche alla sincronizzazione successiva.</span><span class="sxs-lookup"><span data-stu-id="15e9f-220">The rows that have a version larger than the new synchronization version will be obtained again on the next synchronization.</span></span> <span data-ttu-id="15e9f-221">Questa situazione deve essere prevista e gestita dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-221">This must be expected and handled by the application.</span></span>  
  
 <span data-ttu-id="15e9f-222">Oltre ai due approcci precedenti, è possibile definirne altri che utilizzino entrambe le opzioni, in base all'operazione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-222">In addition to the previous two options, you can devise approach that combines both options, depending on the operation.</span></span> <span data-ttu-id="15e9f-223">Potrebbe ad esempio essere necessario utilizzare un'applicazione per cui è preferibile ignorare le modifiche più recenti rispetto alla versione sincronizzata successiva in cui la riga è stata creata o eliminata, ma per cui gli aggiornamenti non vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-223">For example, you might want an application for which it is best to ignore changes newer than the next synchronization version in which the row was created or deleted, but updates are not ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="15e9f-224">Poiché la scelta dell'approccio più efficiente per l'applicazione quando si utilizza il rilevamento delle modifiche o qualsiasi meccanismo di rilevamento personalizzato richiede l'esecuzione di un'analisi approfondita,</span><span class="sxs-lookup"><span data-stu-id="15e9f-224">Choosing the approach that will work for the application when you are using change tracking (or any custom tracking mechanism), requires significant analysis.</span></span> <span data-ttu-id="15e9f-225">l'utilizzo dell'isolamento dello snapshot è notevolmente più semplice.</span><span class="sxs-lookup"><span data-stu-id="15e9f-225">Therefore, it is much simpler to use snapshot isolation.</span></span>  
  
##  <a name="how-change-tracking-handles-changes-to-a-database"></a><a name="Handles"></a><span data-ttu-id="15e9f-226">Gestione delle modifiche apportate a un database in Rilevamento modifiche</span><span class="sxs-lookup"><span data-stu-id="15e9f-226">How Change Tracking Handles Changes to a Database</span></span>  
 <span data-ttu-id="15e9f-227">Alcune applicazioni che utilizzano il rilevamento delle modifiche eseguono la sincronizzazione bidirezionale con un altro archivio dati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-227">Some applications that use change tracking perform two-way synchronization with another data store.</span></span> <span data-ttu-id="15e9f-228">Questo significa che le modifiche apportate al database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono aggiornate nell'altro archivio dati, mentre le modifiche apportate all'archivio vengono aggiornate nel database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15e9f-228">That is, changes that are made in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database are updated in the other data store, and changes that are made in the other store are updated in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="15e9f-229">Quando aggiorna il database locale in base alle modifiche di un altro archivio dati, un'applicazione deve effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15e9f-229">When an application updates the local database with changes from another data store, the application must perform the following operations:</span></span>  
  
-   <span data-ttu-id="15e9f-230">Verificare la presenza di conflitti.</span><span class="sxs-lookup"><span data-stu-id="15e9f-230">Check for conflicts.</span></span>  
  
     <span data-ttu-id="15e9f-231">Un conflitto si verifica quando gli stessi dati vengono modificati contemporaneamente in entrambi gli archivi dati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-231">A conflict occurs when the same data is changed at the same time in both data stores.</span></span> <span data-ttu-id="15e9f-232">L'applicazione deve essere in grado di verificare la presenza di un conflitto e di ottenere informazioni sufficienti per consentirne la risoluzione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-232">The application must be able to check for a conflict and obtain enough information to enable the conflict to be resolved.</span></span>  
  
-   <span data-ttu-id="15e9f-233">Archiviare le informazioni sul contesto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-233">Store application context information.</span></span>  
  
     <span data-ttu-id="15e9f-234">L'applicazione archivia i dati che dispongono di informazioni sul rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-234">The application stores data that has the change tracking information.</span></span> <span data-ttu-id="15e9f-235">Dopo che le modifiche sono state ottenute dal database locale, tali informazioni saranno disponibili con altre informazioni sul rilevamento delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-235">This information would be available together with other change tracking information when changes were obtained from the local database.</span></span> <span data-ttu-id="15e9f-236">Un esempio comune di tali informazioni contestuali è rappresentato da un identificatore per l'archivio dati che costituiva l'origine della modifica.</span><span class="sxs-lookup"><span data-stu-id="15e9f-236">A common example of this contextual information is an identifier for the data store that was the source of the change.</span></span>  
  
 <span data-ttu-id="15e9f-237">Per eseguire le operazioni precedenti, un'applicazione di sincronizzazione può utilizzare le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15e9f-237">To perform the previous operations, a synchronization application can use the following functions:</span></span>  
  
-   <span data-ttu-id="15e9f-238">CHANGETABLE(VERSION...)</span><span class="sxs-lookup"><span data-stu-id="15e9f-238">CHANGETABLE(VERSION...)</span></span>  
  
     <span data-ttu-id="15e9f-239">Quando un'applicazione apporta modifiche, può utilizzare questa funzione per verificare la presenza di conflitti.</span><span class="sxs-lookup"><span data-stu-id="15e9f-239">When an application is making changes, it can use this function to check for conflicts.</span></span> <span data-ttu-id="15e9f-240">La funzione ottiene le informazioni sul rilevamento delle modifiche più recenti per una riga specificata in una tabella con rilevamento.</span><span class="sxs-lookup"><span data-stu-id="15e9f-240">The function obtains the latest change tracking information for a specified row in a change tracked table.</span></span> <span data-ttu-id="15e9f-241">In tali informazioni è inclusa la versione della riga in cui è stata eseguita l'ultima modifica.</span><span class="sxs-lookup"><span data-stu-id="15e9f-241">The change tracking information includes the version of the row that was last changed.</span></span> <span data-ttu-id="15e9f-242">Questa informazione consente a un'applicazione di determinare se la riga è stata modificata dopo l'ultima sincronizzazione dell'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="15e9f-242">This information enables an application to determine whether the row was changed after the last time that the application was synchronized.</span></span>  
  
-   <span data-ttu-id="15e9f-243">WITH CHANGE_TRACKING_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="15e9f-243">WITH CHANGE_TRACKING_CONTEXT</span></span>  
  
     <span data-ttu-id="15e9f-244">Un'applicazione può utilizzare questa clausola per archiviare dati relativi al contesto.</span><span class="sxs-lookup"><span data-stu-id="15e9f-244">An application can use this clause to store context data.</span></span>  
  
### <a name="checking-for-conflicts"></a><span data-ttu-id="15e9f-245">Verifica della presenza di conflitti</span><span class="sxs-lookup"><span data-stu-id="15e9f-245">Checking for Conflicts</span></span>  
 <span data-ttu-id="15e9f-246">In uno scenario di sincronizzazione bidirezionale l'applicazione client deve determinare se una riga non è stata aggiornata dall'ultima volta in cui l'applicazione ha ottenuto le modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-246">In a two-way synchronization scenario, the client application must determine whether a row has not been updated since the application last obtained the changes.</span></span>  
  
 <span data-ttu-id="15e9f-247">Nell'esempio seguente viene illustrato come utilizzare la funzione CHANGETABLE(VERSION ...) per verificare la presenza di conflitti nel modo più efficiente, senza eseguire una query separata.</span><span class="sxs-lookup"><span data-stu-id="15e9f-247">The following example shows how to use the CHANGETABLE(VERSION ...) function to check for conflicts in the most efficient way, without a separate query.</span></span> <span data-ttu-id="15e9f-248">Nell'esempio, `CHANGETABLE(VERSION ...)` determina `SYS_CHANGE_VERSION` per la riga specificata da `@product id`.</span><span class="sxs-lookup"><span data-stu-id="15e9f-248">In the example, `CHANGETABLE(VERSION ...)` determines the `SYS_CHANGE_VERSION` for the row specified by `@product id`.</span></span> <span data-ttu-id="15e9f-249">`CHANGETABLE(CHANGES ...)` può ottenere le stesse informazioni, ma sarebbe meno efficiente.</span><span class="sxs-lookup"><span data-stu-id="15e9f-249">`CHANGETABLE(CHANGES ...)` can obtain the same information, but that would be less efficient.</span></span> <span data-ttu-id="15e9f-250">Se il valore di `SYS_CHANGE_VERSION` per la riga è maggiore del valore di `@last_sync_version`, si verifica un conflitto.</span><span class="sxs-lookup"><span data-stu-id="15e9f-250">If the value of `SYS_CHANGE_VERSION` for the row is larger than the value of `@last_sync_version`, there is a conflict.</span></span> <span data-ttu-id="15e9f-251">In questo caso la riga non verrà aggiornata.</span><span class="sxs-lookup"><span data-stu-id="15e9f-251">If there is a conflict, the row will not be updated.</span></span> <span data-ttu-id="15e9f-252">Il controllo `ISNULL()` è necessario perché per la riga potrebbero non essere disponibili informazioni sulle modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-252">The `ISNULL()` check is required because there might be no change information available for the row.</span></span> <span data-ttu-id="15e9f-253">Nel caso in cui la riga non sia stata aggiornata dal momento in cui è stato abilitato il rilevamento delle modifiche o dal momento in cui le informazioni sulle modifiche sono state eliminate, non sarebbe infatti disponibile alcuna informazione sulle modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-253">No change information would exist if the row had not been updated since change tracking was enabled or since the change information was cleaned up.</span></span>  
  
```sql  
-- Assumption: @last_sync_version has been validated.  
  
UPDATE  
    SalesLT.Product  
SET  
    ListPrice = @new_listprice  
FROM  
    SalesLT.Product AS P  
WHERE  
    ProductID = @product_id AND  
    @last_sync_version >= ISNULL (  
        SELECT CT.SYS_CHANGE_VERSION  
        FROM CHANGETABLE(VERSION SalesLT.Product,  
                        (ProductID), (P.ProductID)) AS CT),  
        0)  
```  
  
 <span data-ttu-id="15e9f-254">Il codice seguente consente di controllare il conteggio delle righe aggiornate e di identificare ulteriori informazioni sul conflitto.</span><span class="sxs-lookup"><span data-stu-id="15e9f-254">The following code can check the updated row count and can identify more information about the conflict.</span></span>  
  
```sql  
-- If the change cannot be made, find out more information.  
IF (@@ROWCOUNT = 0)  
BEGIN  
    -- Obtain the complete change information for the row.  
    SELECT  
        CT.SYS_CHANGE_VERSION, CT.SYS_CHANGE_CREATION_VERSION,  
        CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS  
    FROM  
        CHANGETABLE(CHANGES SalesLT.Product, @last_sync_version) AS CT  
    WHERE  
        CT.ProductID = @product_id;  
  
    -- Check CT.SYS_CHANGE_VERSION to verify that it really was a conflict.  
    -- Check CT.SYS_CHANGE_OPERATION to determine the type of conflict:  
    -- update-update or update-delete.  
    -- The row that is specified by @product_id might no longer exist   
    -- if it has been deleted.  
END  
```  
  
### <a name="setting-context-information"></a><span data-ttu-id="15e9f-255">Impostazione delle informazioni sul contesto</span><span class="sxs-lookup"><span data-stu-id="15e9f-255">Setting Context Information</span></span>  
 <span data-ttu-id="15e9f-256">Utilizzando la clausola WITH CHANGE_TRACKING_CONTEXT un'applicazione può archiviare le informazioni sul contesto con le informazioni sulle modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-256">By using the WITH CHANGE_TRACKING_CONTEXT clause, an application can store context information together with the change information.</span></span> <span data-ttu-id="15e9f-257">Tali informazioni possono quindi essere ottenute dalla colonna SYS_CHANGE_CONTEXT restituita da CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="15e9f-257">This information can then be obtained from the SYS_CHANGE_CONTEXT column that is returned by CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="15e9f-258">Le informazioni sul contesto vengono utilizzate in genere per identificare l'origine delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="15e9f-258">Context information is typically used to identify the source of the changes.</span></span> <span data-ttu-id="15e9f-259">Se è possibile identificare l'origine della modifica, tali informazioni possono essere utilizzate da un archivio dati per evitare di ottenere modifiche alla successiva sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-259">If the source of the change can be identified, that information can be used by a data store to avoid obtaining changes when it synchronizes again.</span></span>  
  
```sql  
  -- Try to update the row and check for a conflict.  
  WITH CHANGE_TRACKING_CONTEXT (@source_id)  
  UPDATE  
     SalesLT.Product  
  SET  
      ListPrice = @new_listprice  
  FROM  
      SalesLT.Product AS P  
  WHERE  
     ProductID = @product_id AND  
     @last_sync_version >= ISNULL (  
         (SELECT CT.SYS_CHANGE_VERSION FROM CHANGETABLE(VERSION SalesLT.Product,  
         (ProductID), (P.ProductID)) AS CT),  
         0)  
```  
  
### <a name="ensuring-consistent-and-correct-results"></a><span data-ttu-id="15e9f-260">Come garantire risultati coerenti e corretti</span><span class="sxs-lookup"><span data-stu-id="15e9f-260">Ensuring Consistent and Correct Results</span></span>  
 <span data-ttu-id="15e9f-261">Al momento della convalida del valore di @last_sync_version, è necessario che in un'applicazione venga considerato il processo di pulizia</span><span class="sxs-lookup"><span data-stu-id="15e9f-261">An application must consider the cleanup process when it validates the value of @last_sync_version.</span></span> <span data-ttu-id="15e9f-262">poiché i dati potrebbero essere stati rimossi i dati dopo la chiamata a CHANGE_TRACKING_MIN_VALID_VERSION (), ma prima che sia stato eseguito l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="15e9f-262">This is because data could have been removed after CHANGE_TRACKING_MIN_VALID_VERSION() was called, but before the update was made.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15e9f-263">È consigliabile utilizzare l'isolamento dello snapshot e apportare le modifiche all'interno di una transazione snapshot.</span><span class="sxs-lookup"><span data-stu-id="15e9f-263">We recommend that you use snapshot isolation and make the changes within a snapshot transaction.</span></span>  
  
```sql  
-- Prerequisite is to ensure ALLOW_SNAPSHOT_ISOLATION is ON for the database.  
  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
    -- Verify that last_sync_version is valid.  
    IF (@last_sync_version <  
CHANGE_TRACKING_MIN_VALID_VERSION(OBJECT_ID('SalesLT.Product')))  
    BEGIN  
       RAISERROR (N'Last_sync_version too old', 16, -1);  
    END  
    ELSE  
    BEGIN  
        -- Try to update the row.  
        -- Check @@ROWCOUNT and check for a conflict.  
    END  
COMMIT TRAN  
```  
  
> [!NOTE]  
>  <span data-ttu-id="15e9f-264">È possibile che la riga in fase di aggiornamento all'interno della transazione snapshot sia stata aggiornata in un'altra transazione dopo l'avvio della transazione stessa.</span><span class="sxs-lookup"><span data-stu-id="15e9f-264">There is a possibility that the row being updated within the snapshot transaction could have been updated in another transaction after the snapshot transaction was started.</span></span> <span data-ttu-id="15e9f-265">In questo caso, si verifica un conflitto nell'aggiornamento dell'isolamento dello snapshot e la transazione verrà terminata.</span><span class="sxs-lookup"><span data-stu-id="15e9f-265">In this case, a snapshot isolation update conflict will occur and lead to the transaction being terminated.</span></span> <span data-ttu-id="15e9f-266">Se si verifica questa situazione, riprovare a eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="15e9f-266">If this happens, retry the update.</span></span> <span data-ttu-id="15e9f-267">In questo modo verrà individuato un conflitto nel rilevamento delle modifiche e nessuna riga verrà modificata.</span><span class="sxs-lookup"><span data-stu-id="15e9f-267">This will then lead to a change tracking conflict being detected and no rows being changed.</span></span>  
  
##  <a name="change-tracking-and-data-restore"></a><a name="DataRestore"></a><span data-ttu-id="15e9f-268">Rilevamento modifiche e ripristino dei dati</span><span class="sxs-lookup"><span data-stu-id="15e9f-268">Change Tracking and Data Restore</span></span>  
 <span data-ttu-id="15e9f-269">Le applicazioni che richiedono la sincronizzazione è necessario considerare il caso in cui un database con il rilevamento delle modifiche abilitato viene ripristinato a una versione precedente dei dati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-269">Applications that require synchronization must consider the case in which a database that has change tracking enabled reverts to an earlier version of the data.</span></span> <span data-ttu-id="15e9f-270">Questa situazione può verificarsi dopo il ripristino di un database da un backup, quando si verifica un failover a un database mirror asincrono o quando si verifica un errore durante l'utilizzo del log shipping.</span><span class="sxs-lookup"><span data-stu-id="15e9f-270">This can occur after a database is restored from a backup, when there is a failover to an asynchronous database mirror, or when there is a failure when using log shipping.</span></span> <span data-ttu-id="15e9f-271">Nel seguente scenario viene illustrato il problema:</span><span class="sxs-lookup"><span data-stu-id="15e9f-271">The following scenario illustrates the issue:</span></span>  
  
1.  <span data-ttu-id="15e9f-272">Nella tabella T1 è attivato il rilevamento delle modifiche e la versione minima valida della tabella è 50.</span><span class="sxs-lookup"><span data-stu-id="15e9f-272">Table T1 is change tracked, and the minimum valid version for table is 50.</span></span>  
  
2.  <span data-ttu-id="15e9f-273">Un'applicazione client sincronizza i dati alla versione 100 e ottiene informazioni su tutte le modifiche tra le versioni 50 e 100.</span><span class="sxs-lookup"><span data-stu-id="15e9f-273">A client application synchronizes data at version 100 and obtains information about all changes between versions 50 and 100.</span></span>  
  
3.  <span data-ttu-id="15e9f-274">Le modifiche aggiuntive vengono apportate alla tabella T1 dopo la versione 100.</span><span class="sxs-lookup"><span data-stu-id="15e9f-274">Additional changes are made to table T1 after version 100.</span></span>  
  
4.  <span data-ttu-id="15e9f-275">Alla versione 120 si verifica un errore e l'amministratore del database ripristina il database con perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-275">At version 120, there is a failure and the database administrator restores the database with data loss.</span></span> <span data-ttu-id="15e9f-276">Dopo l'operazione di ripristino, la tabella contiene dati fino alla versione 70 e la versione minima sincronizzata è ancora 50.</span><span class="sxs-lookup"><span data-stu-id="15e9f-276">After the restore operation, the table contains data up through version 70, and the minimum synchronized version is still 50.</span></span>  
  
     <span data-ttu-id="15e9f-277">Ciò significa che l'archivio dati sincronizzato ha dati che non esistono più nell'archivio dati primario.</span><span class="sxs-lookup"><span data-stu-id="15e9f-277">This means that the synchronized data store has data that no longer exists in the primary data store.</span></span>  
  
5.  <span data-ttu-id="15e9f-278">T1 viene aggiornato molte volte.</span><span class="sxs-lookup"><span data-stu-id="15e9f-278">T1 is updated many times.</span></span> <span data-ttu-id="15e9f-279">La versione corrente viene portata a 130.</span><span class="sxs-lookup"><span data-stu-id="15e9f-279">This brings the current version to 130.</span></span>  
  
6.  <span data-ttu-id="15e9f-280">L'applicazione client esegue nuovamente la sincronizzazione e fornisce l'ultima versione sincronizzata: 100.</span><span class="sxs-lookup"><span data-stu-id="15e9f-280">The client application synchronizes again and supplies a last-synchronized version of 100.</span></span> <span data-ttu-id="15e9f-281">Il client convalida il numero, in quanto 100 è maggiore di 50.</span><span class="sxs-lookup"><span data-stu-id="15e9f-281">The client validates this number successfully because 100 is greater than 50.</span></span>  
  
     <span data-ttu-id="15e9f-282">Il client ottiene le modifiche tra la versione 100 e la 130.</span><span class="sxs-lookup"><span data-stu-id="15e9f-282">The client obtains changes between version 100 and 130.</span></span> <span data-ttu-id="15e9f-283">A questo punto, il client non riconosce che le modifiche tra 70 e 100 non sono come le modifiche precedenti.</span><span class="sxs-lookup"><span data-stu-id="15e9f-283">At this point, the client is not aware that the changes between 70 and 100 are not the same as before.</span></span> <span data-ttu-id="15e9f-284">I dati nel client e nel server non sono sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-284">The data on the client and server are not synchronized.</span></span>  
  
 <span data-ttu-id="15e9f-285">Se il database è stato recuperato in un punto successivo alla versione 100, non si verificheranno problemi con la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-285">Note that if the database was recovered to a point after version 100, there would be no problems with synchronization.</span></span> <span data-ttu-id="15e9f-286">Il client e il server sincronizzeranno correttamente i dati durante il successivo intervallo di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-286">The client and server would synchronize data correctly during the next synchronization interval.</span></span>  
  
 <span data-ttu-id="15e9f-287">Il rilevamento delle modifiche non fornisce il supporto per il recupero dalla perdita di dati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-287">Change tracking does not provide support for recovering from the loss of data.</span></span> <span data-ttu-id="15e9f-288">Tuttavia, sono disponibili due opzioni per il rilevamento di questi tipi di problemi di sincronizzazione:</span><span class="sxs-lookup"><span data-stu-id="15e9f-288">However, there are two options for detecting these types of synchronization issues:</span></span>  
  
-   <span data-ttu-id="15e9f-289">Archiviare un ID della versione del database nel server e aggiornare tale valore ogni volta che un database viene recuperato o perde dati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-289">Store a database version ID on the server, and update this value whenever a database is recovered or otherwise loses data.</span></span> <span data-ttu-id="15e9f-290">Ciascuna applicazione client archivia l'ID e ciascun client convalida tale ID quando viene eseguita la sincronizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-290">Each client application would store the ID, and each client would have to validate this ID when it synchronizes data.</span></span> <span data-ttu-id="15e9f-291">Se si verifica la perdita di dati, gli ID non corrisponderanno e i client verranno reinizializzati.</span><span class="sxs-lookup"><span data-stu-id="15e9f-291">If data loss occurs, the IDs will not match and the clients would reinitialize.</span></span> <span data-ttu-id="15e9f-292">Se la perdita di dati non si sovrappone all'ultimo limite di date sincronizzato, il client potrebbe essere reinizializzato inutilmente.</span><span class="sxs-lookup"><span data-stu-id="15e9f-292">One drawback is if the data loss had not crossed the last synchronized boundary, the client might do unnecessary reinitialization.</span></span>  
  
-   <span data-ttu-id="15e9f-293">Quando un client esegue una query per le modifiche, registrare il numero dell'ultima versione sincronizzata per ciascun client nel server.</span><span class="sxs-lookup"><span data-stu-id="15e9f-293">When a client queries for changes, record the last synchronization version number for each client on the server.</span></span> <span data-ttu-id="15e9f-294">Se si verifica un problema con i dati, i numeri delle ultime versioni sincronizzate non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="15e9f-294">If there is a problem with the data, the last synchronized version numbers would not match.</span></span> <span data-ttu-id="15e9f-295">Ciò indica che è necessario eseguire la reinizializzazione.</span><span class="sxs-lookup"><span data-stu-id="15e9f-295">This indicates that a reinitialization is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e9f-296">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15e9f-296">See Also</span></span>  
 <span data-ttu-id="15e9f-297">[Tenere traccia delle modifiche ai dati &#40;SQL Server&#41;](../track-changes/track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15e9f-297">[Track Data Changes &#40;SQL Server&#41;](../track-changes/track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="15e9f-298">[Informazioni sul rilevamento delle modifiche &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15e9f-298">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="15e9f-299">[Gestire Rilevamento modifiche &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15e9f-299">[Manage Change Tracking &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="15e9f-300">[Abilitare e disabilitare Rilevamento modifiche &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15e9f-300">[Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="15e9f-301">[CHANGETABLE &#40;&#41;Transact-SQL](/sql/relational-databases/system-functions/changetable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15e9f-301">[CHANGETABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/changetable-transact-sql) </span></span>  
 <span data-ttu-id="15e9f-302">[CHANGE_TRACKING_MIN_VALID_VERSION &#40;&#41;Transact-SQL](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15e9f-302">[CHANGE_TRACKING_MIN_VALID_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span></span>  
 <span data-ttu-id="15e9f-303">[CHANGE_TRACKING_CURRENT_VERSION &#40;&#41;Transact-SQL](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15e9f-303">[CHANGE_TRACKING_CURRENT_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span></span>  
 [<span data-ttu-id="15e9f-304">WITH CHANGE_TRACKING_CONTEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="15e9f-304">WITH CHANGE_TRACKING_CONTEXT &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/with-change-tracking-context-transact-sql)  
  
  
