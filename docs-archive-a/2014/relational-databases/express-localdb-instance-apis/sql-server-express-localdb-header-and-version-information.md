---
title: Informazioni sulla versione e l'intestazione del database locale SQL Server Express | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: 506b5161-b902-4894-b87b-9192d7b1664a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 138081852cf505b03265fd9c5f39eae6ed2af39b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637334"
---
# <a name="sql-server-express-localdb-header-and-version-information"></a><span data-ttu-id="eb30b-102">Informazioni sulla versione e intestazione del database locale di SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="eb30b-102">SQL Server Express LocalDB Header and Version Information</span></span>
  <span data-ttu-id="eb30b-103">Non esiste alcun file di intestazione separato per l'API dell'istanza del database locale di SQL Server Express. Le firme e i codici di errore della funzione del database locale sono definiti nel file di intestazione (sqlncli.h) di SQL Server Native Client.</span><span class="sxs-lookup"><span data-stu-id="eb30b-103">There is no separate header file for the SQL Server Express LocalDB instance API; the LocalDB function signatures and error codes are defined in the SQL Server Native Client header file (sqlncli.h).</span></span> <span data-ttu-id="eb30b-104">Per utilizzare l'API dell'istanza del database locale, è necessario includere il file di intestazione sqlncli.h nel progetto.</span><span class="sxs-lookup"><span data-stu-id="eb30b-104">To use the LocalDB instance API, you must include the sqlncli.h header file in your project.</span></span>  
  
## <a name="localdb-versioning"></a><span data-ttu-id="eb30b-105">Controllo delle versioni del database locale</span><span class="sxs-lookup"><span data-stu-id="eb30b-105">LocalDB Versioning</span></span>  
 <span data-ttu-id="eb30b-106">Per l'installazione del database locale viene utilizzato un solo set di file binari per la versione di SQL Server principale.</span><span class="sxs-lookup"><span data-stu-id="eb30b-106">The LocalDB installation uses a single set of binaries per major SQL Server version.</span></span> <span data-ttu-id="eb30b-107">Queste versioni del database locale sono gestite e installate con patch in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="eb30b-107">These LocalDB versions are maintained and patched independently.</span></span> <span data-ttu-id="eb30b-108">Pertanto, l'utente deve specificare quale versione di base (ovvero, versione di SQL Server principale) del database locale utilizzerà.</span><span class="sxs-lookup"><span data-stu-id="eb30b-108">This means that the user has to specify which LocalDB baseline release (that is, major SQL Server version) he or she will be using.</span></span> <span data-ttu-id="eb30b-109">La versione è specificata nel formato della versione standard definito dalla classe .NET Framework **System. Version** :</span><span class="sxs-lookup"><span data-stu-id="eb30b-109">The version is specified in the standard version format defined by the .NET Framework **System.Version** class:</span></span>  
  
 <span data-ttu-id="eb30b-110">*principale.secondario[.build[.revisione]]*</span><span class="sxs-lookup"><span data-stu-id="eb30b-110">*major.minor[.build[.revision]]*</span></span>  
  
 <span data-ttu-id="eb30b-111">I primi due numeri nella stringa di versione (*principale* e *secondaria*) sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="eb30b-111">The first two numbers in the version string (*major* and *minor*) are mandatory.</span></span> <span data-ttu-id="eb30b-112">Gli ultimi due numeri nella stringa di versione (*compilazione* e *Revisione*) sono facoltativi e il valore predefinito è zero se l'utente li lascia fuori. Ciò significa che se l'utente specifica solo "12,2" come numero di versione del database locale, verrà considerato come se l'utente avesse specificato "12.2.0.0".</span><span class="sxs-lookup"><span data-stu-id="eb30b-112">The last two numbers in the version string (*build* and *revision*) are optional and default to zero if the user leaves them out. This means that if the user specifies only "12.2" as the LocalDB version number, it will be treated as if the user specified "12.2.0.0".</span></span>  
  
 <span data-ttu-id="eb30b-113">La versione per l'installazione del database locale è definita nella chiave del Registro di sistema MSSQLServer\CurrentVersion sotto la chiave del Registro di sistema dell'istanza di SQL Server, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="eb30b-113">The version for the LocalDB installation is defined in the MSSQLServer\CurrentVersion registry key under the SQL Server instance registry key, for example:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL12E.LOCALDB\ MSSQLServer\CurrentVersion: "CurrentVersion"="12.0.2531.0"  
```  
  
 <span data-ttu-id="eb30b-114">È supportata la modalità side-by-side di più versioni del database locale sulla stessa workstation.</span><span class="sxs-lookup"><span data-stu-id="eb30b-114">Multiple LocalDB versions on the same workstation are supported side-by-side.</span></span> <span data-ttu-id="eb30b-115">Tuttavia, il codice utente utilizza sempre la dll **SQLUserInstance** disponibile più recente nel computer locale per la connessione alle istanze del database locale.</span><span class="sxs-lookup"><span data-stu-id="eb30b-115">However, user code always uses the latest available **SQLUserInstance** DLL on the local computer to connect to LocalDB instances.</span></span>  
  
## <a name="locating-the-sqluserinstance-dll"></a><span data-ttu-id="eb30b-116">Individuazione della DLL SQLUserInstance</span><span class="sxs-lookup"><span data-stu-id="eb30b-116">Locating the SQLUserInstance DLL</span></span>  
 <span data-ttu-id="eb30b-117">Per individuare la dll **SQLUserInstance** , il provider client utilizza la seguente chiave del registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="eb30b-117">To locate the **SQLUserInstance** DLL, the client provider uses the following registry key:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions]  
```  
  
 <span data-ttu-id="eb30b-118">In questa chiave è disponibile un elenco di chiavi, una per ogni versione del database locale installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="eb30b-118">Under this key there is a list of keys, one for each version of LocalDB installed on the computer.</span></span> <span data-ttu-id="eb30b-119">Ognuna di queste chiavi è denominata con il numero di versione del database locale nel formato *\<major-version>* .*\<minor-version>*</span><span class="sxs-lookup"><span data-stu-id="eb30b-119">Each of these keys is named with the LocalDB version number in the format *\<major-version>*.*\<minor-version>*</span></span> <span data-ttu-id="eb30b-120">ad esempio, la chiave per [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] è denominata 12,0.</span><span class="sxs-lookup"><span data-stu-id="eb30b-120">(for example, the key for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is named 12.0).</span></span> <span data-ttu-id="eb30b-121">In ogni chiave della versione è disponibile una coppia nome/valore di `InstanceAPIPath` che consente di definire il percorso completo al file SQLUserInstance.dll installato con tale versione.</span><span class="sxs-lookup"><span data-stu-id="eb30b-121">Under each version key there is an `InstanceAPIPath` name-value pair that defines the full path to the SQLUserInstance.dll file installed with that version.</span></span> <span data-ttu-id="eb30b-122">Nell'esempio seguente vengono mostrate le voci del Registro di sistema per un computer in cui sono installate le versioni 11.0 e 12.0 del database locale:</span><span class="sxs-lookup"><span data-stu-id="eb30b-122">The following example shows the registry entries for a computer that has LocalDB versions 11.0 and 12.0 installed:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
```  
  
 <span data-ttu-id="eb30b-123">Il provider client deve trovare la versione più recente tra tutte le versioni installate e caricare il file dll **SQLUserInstance** dal `InstanceAPIPath` valore associato.</span><span class="sxs-lookup"><span data-stu-id="eb30b-123">The client provider must find the latest version among all installed versions and load the **SQLUserInstance** DLL file from the associated `InstanceAPIPath` value.</span></span>  
  
### <a name="wow64-mode-on-64-bit-windows"></a><span data-ttu-id="eb30b-124">Modalità WOW64 in Windows a 64 bit</span><span class="sxs-lookup"><span data-stu-id="eb30b-124">WOW64 Mode on 64-bit Windows</span></span>  
 <span data-ttu-id="eb30b-125">Le installazioni a 64 bit del database locale disporranno di un set aggiuntivo di chiavi del Registro di sistema per consentire applicazioni a 32 bit in esecuzione in modalità WOW64 (Windows-32-on-Windows-64) per l'utilizzo del database locale.</span><span class="sxs-lookup"><span data-stu-id="eb30b-125">64-bit installations of LocalDB will have an additional set of registry keys to allow 32-bit applications running in Windows-32-on-Windows-64 (WOW64) mode to use LocalDB.</span></span> <span data-ttu-id="eb30b-126">In particolare, in Windows a 64 bit il file MSI del database locale consentirà la creazione delle chiavi del Registro di sistema seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb30b-126">Specifically, on 64-bit Windows, the LocalDB MSI will create the following registry keys:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
  
```  
  
 <span data-ttu-id="eb30b-127">i programmi a 64 bit che leggono la chiave vedranno i `Installed Versions` valori che puntano a versioni a 64 bit della dll **SQLUserInstance** , mentre i programmi a 32 bit (in esecuzione in Windows a 64 bit in modalità WOW64) verranno reindirizzati automaticamente a una `Installed Versions` chiave che si trova in `Wow6432Node` hive.</span><span class="sxs-lookup"><span data-stu-id="eb30b-127">64-bit programs reading the `Installed Versions` key will see values pointing to 64-bit versions of the **SQLUserInstance** DLL, while 32-bit programs (running on 64-bit Windows in WOW64 mode) will be automatically redirected to an `Installed Versions` key located under the `Wow6432Node` hive.</span></span> <span data-ttu-id="eb30b-128">Questa chiave contiene valori che puntano a versioni a 32 bit della dll **SQLUserInstance** .</span><span class="sxs-lookup"><span data-stu-id="eb30b-128">This key contains values pointing to 32-bit versions of the **SQLUserInstance** DLL.</span></span>  
  
## <a name="using-localdb_define_proxy_functions"></a><span data-ttu-id="eb30b-129">Utilizzo di LOCALDB_DEFINE_PROXY_FUNCTIONS</span><span class="sxs-lookup"><span data-stu-id="eb30b-129">Using LOCALDB_DEFINE_PROXY_FUNCTIONS</span></span>  
 <span data-ttu-id="eb30b-130">L'API dell'istanza del database locale definisce una costante denominata LOCALDB_DEFINE_PROXY_FUNCTIONS che automatizza l'individuazione e il caricamento della dll **SQLUserInstance** .</span><span class="sxs-lookup"><span data-stu-id="eb30b-130">The LocalDB instance API defines a constant named LOCALDB_DEFINE_PROXY_FUNCTIONS that automates the discovery and loading of the **SqlUserInstance** DLL.</span></span>  
  
 <span data-ttu-id="eb30b-131">La sezione di codice abilitata da questa costante fornisce un'implementazione di proxy per ognuna delle API del database locale.</span><span class="sxs-lookup"><span data-stu-id="eb30b-131">The section of code enabled by this constant provides an implementation of proxies for each of the LocalDB APIs.</span></span> <span data-ttu-id="eb30b-132">Le implementazioni del proxy usano una funzione comune per l'associazione ai punti di ingresso nella dll **SQLUserInstance** installata più recente e quindi le inviano.</span><span class="sxs-lookup"><span data-stu-id="eb30b-132">The proxy implementations use a common function to bind to entry points in the latest installed **SqlUserInstance** DLL, and then forward the requests.</span></span>  
  
 <span data-ttu-id="eb30b-133">Le funzioni del proxy sono abilitate solo se la costante LOCALDB_DEFINE_PROXY_FUNCTIONS è definita nel codice utente prima di includere il file sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="eb30b-133">The proxy functions are enabled only if the constant LOCALDB_DEFINE_PROXY_FUNCTIONS is defined in the user code before including the sqlncli.h file.</span></span> <span data-ttu-id="eb30b-134">La costante deve essere definita in un unico modulo di origine (file con estensione cpp) in quanto consente di definire nomi di funzioni esterni per tutti i punti di ingresso dell'API.</span><span class="sxs-lookup"><span data-stu-id="eb30b-134">The constant should be defined in only one source module (.cpp file) because it defines external function names for all of the API entry points.</span></span> <span data-ttu-id="eb30b-135">Inoltre, tale costante fornisce un'implementazione di proxy per ognuna delle API del database locale.</span><span class="sxs-lookup"><span data-stu-id="eb30b-135">It provides an implementation of proxies for each of the LocalDB APIs.</span></span>  
  
 <span data-ttu-id="eb30b-136">Nell'esempio di codice seguente viene mostrato come utilizzare la macro dal codice C++ nativo:</span><span class="sxs-lookup"><span data-stu-id="eb30b-136">The following code example shows how to use the macro from the native C++ code:</span></span>  
  
```  
// Define the LOCALDB_DEFINE_PROXY_FUNCTIONS constant to enable the LocalDB proxy functions   
// The #define has to take place BEFORE the API header file (sqlncli.h) is included  
#define LOCALDB_DEFINE_PROXY_FUNCTIONS  
#include <sqlncli.h>  
...  
HRESULT hr = S_OK;  
  
// Create LocalDB instance by calling the create API proxy function included by macro  
if (FAILED(hr = LocalDBCreateInstance( L"12.0", L"name", 0)))  
{  
...  
}  
...  
  
```  
  
  
