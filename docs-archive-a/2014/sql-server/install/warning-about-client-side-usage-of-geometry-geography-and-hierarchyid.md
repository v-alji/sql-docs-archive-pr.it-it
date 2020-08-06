---
title: Avviso relativo all'utilizzo lato client di GEOMETRY, GEOGRAPHY e HIERARCHYID | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 500ee6b3-2154-45d2-a3cf-8760166d9413
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 66898aa056800c0a7573b5afa73762785706ff7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628113"
---
# <a name="warning-about-client-side-usage-of-geometry-geography-and-hierarchyid"></a><span data-ttu-id="a6e1d-102">Avviso relativo all'utilizzo sul lato client di GEOMETRY, GEOGRAPHY e HIERARCHYID</span><span class="sxs-lookup"><span data-stu-id="a6e1d-102">Warning about client side usage of GEOMETRY, GEOGRAPHY and HIERARCHYID</span></span>
  <span data-ttu-id="a6e1d-103">L'assembly **Microsoft.SqlServer.Types.dll**, che contiene i tipi di dati spaziali, è stato aggiornato dalla versione 10,0 alla versione 11,0.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-103">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="a6e1d-104">È possibile che le applicazioni personalizzate che fanno riferimento a questo assembly abbiano esito negativo quando sussistono determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-104">Custom applications that reference this assembly may fail when certain conditions are true.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a6e1d-105">Componente</span><span class="sxs-lookup"><span data-stu-id="a6e1d-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a6e1d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6e1d-106">Description</span></span>  
 <span data-ttu-id="a6e1d-107">L'assembly **Microsoft.SqlServer.Types.dll**, che contiene i tipi di dati spaziali, è stato aggiornato dalla versione 10,0 alla versione 11,0.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-107">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="a6e1d-108">È possibile che le applicazioni personalizzate che fanno riferimento a questo assembly abbiano esito negativo quando sussistono le condizioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-108">Custom applications that reference this assembly may fail when the following conditions are true.</span></span>  
  
-   <span data-ttu-id="a6e1d-109">Quando si sposta un'applicazione personalizzata da un computer in cui è [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] stato installato in un computer in cui [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] è installato solo, l'applicazione avrà esito negativo perché la versione 10,0 dell'assembly **SqlTypes** a cui viene fatto riferimento non è presente.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-109">When you move a custom application from a computer on which [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] was installed to a computer on which only [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is installed, the application will fail because the referenced version 10.0 of the **SqlTypes** assembly is not present.</span></span> <span data-ttu-id="a6e1d-110">È possibile che venga visualizzato questo messaggio di errore: `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span><span class="sxs-lookup"><span data-stu-id="a6e1d-110">You may see this error message: `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span></span>  
  
-   <span data-ttu-id="a6e1d-111">Quando si fa riferimento all'assembly **SqlTypes** versione 11,0 e viene installata anche la versione 10,0, è possibile che venga visualizzato questo messaggio di errore:`"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span><span class="sxs-lookup"><span data-stu-id="a6e1d-111">When you reference the **SqlTypes** assembly version 11.0, and version 10.0 is also installed, you may see this error message: `"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span></span>  
  
-   <span data-ttu-id="a6e1d-112">Quando si fa riferimento all'assembly **SqlTypes** versione 11,0 da un'applicazione personalizzata destinata a .NET 3,5, 4 o 4,5, l'applicazione avrà esito negativo perché SqlClient per progettazione carica la versione 10,0 dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-112">When you reference the **SqlTypes** assembly version 11.0 from a custom application that targets .NET 3.5, 4, or 4.5, the application will fail because SqlClient by design loads version 10.0 of the assembly.</span></span> <span data-ttu-id="a6e1d-113">Questo errore si verifica quando l'applicazione chiama uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6e1d-113">This failure occurs when the application calls one of the following methods:</span></span>  
  
    -   <span data-ttu-id="a6e1d-114">Metodo `GetValue` della classe `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="a6e1d-114">`GetValue` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="a6e1d-115">Metodo `GetValues` della classe `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="a6e1d-115">`GetValues` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="a6e1d-116">Operatore di indice parentesi quadre [] della classe `SqlDataReader`</span><span class="sxs-lookup"><span data-stu-id="a6e1d-116">bracket index operator [] of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="a6e1d-117">Metodo `ExecuteScalar` della classe `SqlCommand`</span><span class="sxs-lookup"><span data-stu-id="a6e1d-117">`ExecuteScalar` method of the `SqlCommand` class</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a6e1d-118">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="a6e1d-118">Corrective Action</span></span>  
 <span data-ttu-id="a6e1d-119">È possibile risolvere questo problema usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6e1d-119">You can work around this issue by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="a6e1d-120">È possibile risolvere questo problema nel codice chiamando il metodo `GetSqlBytes`, anziché i metodi Get elencati in precedenza, per recuperare i tipi di sistema CLR di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a6e1d-120">You can work around this issue in your code by calling the `GetSqlBytes` method, instead of the Get methods listed above, to retrieve CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system types, as shown in the following example:</span></span>  
  
    ```csharp  
    string query = "SELECT [SpatialColumn] FROM [SpatialTable]";  
          using (SqlConnection conn = new SqlConnection("..."))  
          {  
                SqlCommand cmd = new SqlCommand(query, conn);  
  
                conn.Open();  
                SqlDataReader reader = cmd.ExecuteReader();  
  
                while (reader.Read())  
                {  
                      // In version 11.0 only  
                      SqlGeometry g =   
    SqlGeometry.Deserialize(reader.GetSqlBytes(0));  
  
                      // In version 10.0 or 11.0  
                      SqlGeometry g2 = new SqlGeometry();  
                      g.Read(new BinaryReader(reader.GetSqlBytes(0).Stream));  
                }  
          }  
    ```  
  
-   <span data-ttu-id="a6e1d-121">È possibile risolvere questo problema usando il reindirizzamento degli assembly nel file di configurazione dell'applicazione, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a6e1d-121">You can work around this issue by using assembly redirection in the application configuration file, as shown in the following example:</span></span>  
  
    ```xml  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
        ...  
        <dependentAssembly>  
            <assemblyIdentity name="Microsoft.SqlServer.Types" publicKeyToken="89845dcd8080cc91" culture="neutral" />  
            <bindingRedirect oldVersion="10.0.0.0" newVersion="11.0.0.0" />  
        </dependentAssembly>  
        ...  
    </assemblyBinding>  
    ```  
  
-   <span data-ttu-id="a6e1d-122">È possibile risolvere questo problema nella stringa di connessione specificando il valore "SQL Server 2012" per l'attributo "Type System Version" per forzare il caricamento della versione 11.0 dell'assembly da parte di SqlClient.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-122">You can work around this issue in your connection string by specifying a value of "SQL Server 2012" for the "Type System Version" attribute to force SqlClient to load version 11.0 of the assembly.</span></span> <span data-ttu-id="a6e1d-123">Questo attributo della stringa di connessione è disponibile unicamente in .NET 4.5 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a6e1d-123">This connection string attribute is available only in .NET 4.5 and above.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e1d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6e1d-124">See Also</span></span>  
 <span data-ttu-id="a6e1d-125">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a6e1d-125">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a6e1d-126">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="a6e1d-126">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md
)  
  
  
