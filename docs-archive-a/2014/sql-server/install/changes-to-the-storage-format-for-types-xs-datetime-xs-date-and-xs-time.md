---
title: 'Modifiche al formato di archiviazione per i tipi xs: dateTime, XS: date e xs: Time | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- xs:date
- xs:time
- storage format
- DateTime
ms.assetid: b9f758df-030c-4aec-8ade-1bf904aa2c61
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e1ad0b80ee6963dde4b906a38c72e5c0fd8bab72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628219"
---
# <a name="changes-to-the-storage-format-for-types-xsdatetime-xsdate-and-xstime"></a><span data-ttu-id="3be81-102">Modifiche al formato di archiviazione per i tipi xs:dateTime, xs:date e xs:time</span><span class="sxs-lookup"><span data-stu-id="3be81-102">Changes to the storage format for types xs:dateTime, xs:date, and xs:time</span></span>
  <span data-ttu-id="3be81-103">La regola XMLDATETIME identifica se i database contengono o meno dati XML tipizzati che non saranno più validi dopo l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3be81-103">The XMLDATETIME rule identifies whether or not your databases contain typed XML data that will become invalid after upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="3be81-104">Componente</span><span class="sxs-lookup"><span data-stu-id="3be81-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="3be81-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3be81-105">Description</span></span>  
 <span data-ttu-id="3be81-106">Il formato di archiviazione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] per i tipi xs: DateTime, XS: date e xs: Time è stato modificato per supportare valori con o senza informazioni sul fuso orario e per consentire la conservazione del fuso orario.</span><span class="sxs-lookup"><span data-stu-id="3be81-106">The storage format in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] for types xs:dateTime, xs:date, and xs:time has been changed to support values with or without time zone information and to allow for preservation of the time zone.</span></span>  
  
 <span data-ttu-id="3be81-107">Se una raccolta XML Schema fa riferimento a uno di tali tipi, gli indici XML di tutte le colonne associate alla raccolta verranno disabilitati dopo l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3be81-107">If an XML Schema Collection references one of those types, XML indexes on all columns that are associated with the collection will be disabled after upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="3be81-108">Sarà possibile sottoporli a query utilizzando SELECT e/o XQUERIES, ma l'indice XML non verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="3be81-108">You will be able to query them by using SELECT and/or XQUERIES, but the XML index will not be used.</span></span> <span data-ttu-id="3be81-109">Se viene rilevato un valore di anno negativo, verrà generato un errore di runtime.</span><span class="sxs-lookup"><span data-stu-id="3be81-109">If a negative year value is encountered, a runtime error will result.</span></span>  
  
 <span data-ttu-id="3be81-110">Inoltre, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] non supporta valori con anni negativi.</span><span class="sxs-lookup"><span data-stu-id="3be81-110">Additionally, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] does not support values with negative years.</span></span>  
  
 <span data-ttu-id="3be81-111">La regola XMLDATETIME controlla se una raccolta XML Schema fa riferimento a uno dei tipi interessati e se esistono colonne XML tipizzate da tali raccolte.</span><span class="sxs-lookup"><span data-stu-id="3be81-111">The XMLDATETIME rule checks if any of your XML Schema Collections reference one of the affected types and if there are any XML columns typed by such collections.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="3be81-112">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="3be81-112">Corrective Action</span></span>  
 <span data-ttu-id="3be81-113">Se la regola XMLDATETIME conferma che esistono colonne XML tipizzate in base a una raccolta di schemi che fa riferimento a xs:date, xs:time o xs:dateTime, è necessario rilevare innanzitutto se sono presenti o meno valori con anni negativi nei dati.</span><span class="sxs-lookup"><span data-stu-id="3be81-113">If the XMLDATETIME rule confirms that you have XML columns typed according to a schema collection that references xs:date, xs:time or xs:dateTime, you must first find out whether or not there are any values with negative years in your data.</span></span> <span data-ttu-id="3be81-114">La presenza di tali valori impedisce la ricompilazione degli indici XML dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3be81-114">The presence of such values would prevent you from rebuilding your XML indexes after upgrading.</span></span>  
  
 <span data-ttu-id="3be81-115">Con la query seguente vengono ricercate le raccolte di XML Schema che fanno riferimento ai tipi interessati e per tutte le colonne XML tipizzate.</span><span class="sxs-lookup"><span data-stu-id="3be81-115">The following query will search for XML schema collections that reference the affected types and for each typed XML column.</span></span> <span data-ttu-id="3be81-116">In questo modo è possibile stabilire se sono presenti o meno istanze con valori di anni negativi.</span><span class="sxs-lookup"><span data-stu-id="3be81-116">This will tell you whether or not there are instances with negative year values.</span></span>  
  
```sql
CREATE PROCEDURE DateTimeInvestigation(@withdata bit)  
-- @withdata = 0: only get the affected meta data information  
-- @withdata = 1: get the affected meta data and instance information  
AS  
BEGIN  
-- First get XML containing all schema collections containing affected element and attributes  
-- components (model groups?)   
-- and columns that are affected by the schema collections.   
CREATE table #_dt_collector(x xml);   
;with dttypes as  
  (SELECT * FROM sys.xml_schema_components   
   where base_xml_component_id IN   
      (SELECT xml_component_id   
       FROM sys.xml_schema_types   
       where (name='dateTime' or name='date') and kind='P'  
      )   
   union all  
   SELECT * FROM sys.xml_schema_components  
   where xml_component_id IN   
      (SELECT xml_component_id   
       FROM sys.xml_schema_types   
       where (name='dateTime' or name='date') and kind='P'  
       or kind='N' or kind='Z')   
   ),   
dtplaced as  
  (SELECT scp.*   
   FROM sys.xml_schema_component_placements scp   
   JOIN dttypes on scp.placed_xml_component_id=dttypes.xml_component_id  
  )   
insert into #_dt_collector SELECT x FROM (SELECT  
  xsc.xml_collection_id as "@collid"  
, s.name as "@schema"  
, xscol.name as "@name"  
, count(xsc.xml_component_id) as "@affected_elems_and_attrs"  
, (SELECT S.Name as "@schema", T.Name as "@table"  
        , C.Name as "@column"   
   FROM sys.columns C   
   JOIN sys.tables T ON C.object_id = T.object_id  
   JOIN sys.schemas S ON S.schema_id = T.schema_id  
   WHERE C.xml_collection_id = xsc.xml_collection_id  
   FOR XML PATH('Columns'), TYPE  
  )   
FROM sys.xml_schema_components xsc  
JOIN dtplaced on xsc.xml_component_id=dtplaced.xml_component_id  
JOIN sys.xml_schema_collections xscol on xsc.xml_collection_id =xscol.xml_collection_id  
JOIN sys.schemas s on xscol.schema_id=s.schema_id  
group by xsc.xml_collection_id, s.name, xscol.name  
FOR XML PATH('XML_Schema_Collections'), TYPE) as T(x);   
if (@withdata = 0)    
  BEGIN  
  SELECT x as "*" FROM #_dt_collector for xml path(''), root('data');   
  drop table #_dt_collector;   
  return;   
  END;   
-- Declare cursor to find all columns bound to the schema collections  
DECLARE C CURSOR FOR  
SELECT S.Name, T.Name, C.Name   
FROM sys.columns C   
JOIN sys.tables T ON C.object_id = T.object_id  
JOIN sys.schemas S ON S.schema_id = T.schema_id  
WHERE C.xml_collection_id  
IN (SELECT distinct xsc.xml_collection_id  
    FROM sys.xml_schema_components xsc  
    JOIN (SELECT scp.*   
          FROM sys.xml_schema_component_placements scp   
          JOIN (SELECT * FROM sys.xml_schema_components   
                where base_xml_component_id    
                in (SELECT xml_component_id   
                    FROM sys.xml_schema_types   
                    where (name='dateTime' or name='date') and kind='P'  
                   )   
                union all  
                SELECT * FROM sys.xml_schema_components  
                where xml_component_id   
                in (SELECT xml_component_id   
                    FROM sys.xml_schema_types   
                    where (name='dateTime' or name='date') and kind='P'  
                    or kind='N' or kind='Z')   
               ) dttypes on scp.placed_xml_component_id=dttypes.xml_component_id  
          ) dtplaced on xsc.xml_component_id=dtplaced.xml_component_id);   
DECLARE @SchemaName nvarchar(max);   
DECLARE @TableName nvarchar(max);   
DECLARE @ColumnName nvarchar(max);   
DECLARE @strSQL nvarchar(MAX);   
OPEN C;   
FETCH NEXT FROM C INTO @SchemaName, @TableName, @ColumnName;   
WHILE (@@FETCH_STATUS = 0)   
BEGIN  
      SET @strSQL = 'INSERT INTO #_dt_collector SELECT x FROM ( ';   
      SET @strSQL = @strSQL +    
                    'SELECT ''' + @SchemaName + '.' + @TableName + '.' + @ColumnName   
                  + ''' as "@Column", ';   
      SET @strSQL = @strSQL +    
      'sum(' + @ColumnName + '.value(''count(//*[. instance of element(*,xs:dateTime?)])'', ''bigint'')) as "@dT_elements"  
     , sum(' + @ColumnName + '.value(''count(//*[. instance of element(*,xs:dateTime?)][substring(string(.),1,1) ="-"])'', ''bigint'')) as "@neg_dT_elements"  
     , sum(' + @ColumnName + '.value(''count(//*[. instance of element(*,xs:date?)])'', ''bigint'')) as "@date_elements"  
     , sum(' + @ColumnName + '.value(''count(//*[. instance of element(*,xs:date?)][substring(string(.),1,1) ="-"])'', ''bigint'')) as "@neg_date_elements"   
     , sum(' + @ColumnName + '.value(''count(for $d in //@*, $v in data($d)  
                      where $v instance of xs:dateTime?   
                      return 1)'', ''bigint'')) as "@dT_attributes"   
     , sum(' + @ColumnName + '.value(''count(for $d in //@*, $v in data($d)   
                      where $v instance of xs:dateTime?   
                      and substring(string($v),1,1)= "-"  
                      return 1)'', ''bigint'')) as "@neg_dt_attributes"  
     , sum(' + @ColumnName + '.value(''count(for $d in //@*, $v in data($d)   
                      where $v instance of xs:date?   
                      return 1)'', ''bigint'')) as "@date_attributes"   
     , sum('+ @ColumnName + '.value(''count(for $d in //@*, $v in data($d)   
                      where $v instance of xs:date?   
                      and substring(string($v),1,1)= "-"  
                      return 1)'', ''bigint'')) as "@neg_date_attributes"'  
      + ' FROM ' + @SchemaName + '.' + @TableName  
      + ' FOR XML PATH(''data''), type) T(x)';   
      --SELECT @strSQL;   
      EXEC sp_executesql @strSQL;   
      FETCH NEXT FROM C INTO @SchemaName, @TableName, @ColumnName;   
END;   
CLOSE C;   
DEALLOCATE C;   
SELECT x as "*" FROM #_dt_collector for xml path(''), root('data');   
drop table #_dt_collector;   
END;   
go  
-- Get the dependent columns per affected XML Schema Collection and the  
-- number of affected values  
EXECUTE DateTimeInvestigation 1;   
```  
  
 <span data-ttu-id="3be81-117">Se vengono individuati valori di anni negativi, sono disponibili più soluzioni:</span><span class="sxs-lookup"><span data-stu-id="3be81-117">If negative year values are found, you have multiple solutions:</span></span>  
  
-   <span data-ttu-id="3be81-118">Eliminare le righe.</span><span class="sxs-lookup"><span data-stu-id="3be81-118">Delete the rows.</span></span>  
  
-   <span data-ttu-id="3be81-119">Aggiornare tali valori.</span><span class="sxs-lookup"><span data-stu-id="3be81-119">Update those values.</span></span>  
  
-   <span data-ttu-id="3be81-120">Cancellare l'intera colonna XML.</span><span class="sxs-lookup"><span data-stu-id="3be81-120">Clear the entire XML column.</span></span>  
  
-   <span data-ttu-id="3be81-121">Ritipizzare la colonna XML con una raccolta di schemi che non utilizza xs:date o xs:dateTime (utilizzare ad esempio xs:string)</span><span class="sxs-lookup"><span data-stu-id="3be81-121">Retype the XML column with a schema collection that doesn't use xs:date or xs:dateTime (use xs:string for example)</span></span>  
  
 <span data-ttu-id="3be81-122">Dopo avere risolto i problemi relativi ad anni negativi, è possibile eseguire l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3be81-122">After you have reconciled negative year issues, you can upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="3be81-123">Per utilizzare indici XML in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], dopo l'aggiornamento è necessario ricompilare gli indici XML o ritipizzare le colonne XML per tutte le colonne che utilizzano xs:date, xs:time o xs:dateTime.</span><span class="sxs-lookup"><span data-stu-id="3be81-123">To use XML indexes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after the upgrade, you must rebuild XML indexes or retype XML columns for all columns that use xs:date, xs:time or xs:dateTime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be81-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3be81-124">See Also</span></span>  
 [<span data-ttu-id="3be81-125">Problemi di aggiornamento del motore di database</span><span class="sxs-lookup"><span data-stu-id="3be81-125">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
  
