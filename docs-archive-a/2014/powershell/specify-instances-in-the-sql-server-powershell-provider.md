---
title: Specificare istanze nel provider SQL Server PowerShell| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 9373de68-fd43-45f2-b9a6-149c96610aeb
author: stevestein
ms.author: sstein
ms.openlocfilehash: cc04bacc1ff36b0b5ce526a377fcdb750ad134a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627848"
---
# <a name="specify-instances-in-the-sql-server-powershell-provider"></a><span data-ttu-id="b0c4c-102">Specifica di istanze nel provider SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0c4c-102">Specify Instances in the SQL Server PowerShell Provider</span></span>
  <span data-ttu-id="b0c4c-103">I percorsi specificati per il provider SQL Server PowerShell devono identificare l'istanza di [!INCLUDE[ssDE](../includes/ssde-md.md)] e il computer sulla quale è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-103">The paths specified for the SQL Server PowerShell provider must identify the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] and the computer it is running on.</span></span> <span data-ttu-id="b0c4c-104">La sintassi per la specifica del computer e l'istanza devono conformarsi sia alle regole per gli identificatori di SQL Server che ai percorsi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-104">The syntax for specifying the computer and the instance must comply with both the rules for SQL Server identifiers and Windows PowerShell paths.</span></span>  
  
1.  <span data-ttu-id="b0c4c-105">**Prima di iniziare:**  [Limitazioni e restrizioni](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="b0c4c-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="b0c4c-106">**Per specificare un'istanza:**  [Esempi](#Examples)</span><span class="sxs-lookup"><span data-stu-id="b0c4c-106">**To specify an instance:**  [Examples](#Examples)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="b0c4c-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b0c4c-107">Before You Begin</span></span>  
 <span data-ttu-id="b0c4c-108">Il primo nodo che segue SQLSERVER:\SQL in un percorso del provider SQL Server è il nome del computer che esegue l'istanza di [!INCLUDE[ssDE](../includes/ssde-md.md)], ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0c4c-108">The first node following the SQLSERVER:\SQL in a SQL Server provider path is the name of the computer that is running the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)]; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer  
```  
  
 <span data-ttu-id="b0c4c-109">Se si esegue Windows PowerShell nello stesso computer dell'istanza del [!INCLUDE[ssDE](../includes/ssde-md.md)], è possibile utilizzare localhost o (local) al posto del nome del computer.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-109">If you are running Windows PowerShell on the same computer as the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], you can use either localhost or (local) instead of the name of the computer.</span></span> <span data-ttu-id="b0c4c-110">Gli script che utilizzano localhost o (local) possono essere eseguiti in qualsiasi computer senza che debbano essere modificati per riflettere i diversi nomi dei computer.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-110">Scripts that use localhost or (local) can be run on any computer without having to be changed to reflect the different computer names.</span></span>  
  
 <span data-ttu-id="b0c4c-111">È possibile eseguire più istanze del programma eseguibile [!INCLUDE[ssDE](../includes/ssde-md.md)] sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-111">You can run multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)] executable program on the same computer.</span></span> <span data-ttu-id="b0c4c-112">Il nodo che segue il nome del computer in un percorso del provider SQL Server identifica l'istanza; ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0c4c-112">The node following the computer name in a SQL Server provider path identifies the instance; for example:</span></span>  
  
```  
SQLSERVER:\SQL\MyComputer\MyInstance  
```  
  
 <span data-ttu-id="b0c4c-113">Ciascun computer può disporre di un'istanza predefinita di [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b0c4c-113">Each computer can have one default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="b0c4c-114">Non viene specificato un nome per l'istanza predefinita quando viene installata.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-114">You do not specify a name for the default instance when you install it.</span></span> <span data-ttu-id="b0c4c-115">Specificando solo un nome del computer in una stringa di connessione si è connessi all'istanza predefinita nel computer.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-115">If you specify only a computer name in a connection string, you are connected to the default instance on that computer.</span></span> <span data-ttu-id="b0c4c-116">Tutte le altre istanze nel computer devono essere istanze denominate.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-116">All other instances on the computer must be named instances.</span></span> <span data-ttu-id="b0c4c-117">Il nome dell'istanza viene specificato durante l'installazione e nelle stringhe di connessione è necessario specificare il nome del computer e il nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-117">You specify the instance name during setup, and connection strings must specify both the computer name and the instance name.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="b0c4c-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b0c4c-118">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b0c4c-119">Non è possibile utilizzare il punto (.) per specificare il computer locale negli script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-119">You cannot use a period (.) to specify the local computer in PowerShell scripts.</span></span> <span data-ttu-id="b0c4c-120">Il punto non è supportato perché viene interpretato da PowerShell come un comando.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-120">The period is not supported because the period is interpreted as a command by PowerShell.</span></span>  
  
 <span data-ttu-id="b0c4c-121">I caratteri parentesi in (local) vengono in genere gestiti da Windows PowerShell come comandi.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-121">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="b0c4c-122">È necessario codificarli o utilizzare caratteri di escape per l'utilizzo in un percorso o racchiudere il percorso tra doppie virgolette.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-122">You must either encode them or escape them for use in a path, or enclose the path in double-quotation marks.</span></span> <span data-ttu-id="b0c4c-123">Per ulteriori informazioni, vedere Codifica e decodifica degli identificatori di SLQ Server.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-123">For more information, see Encode and Decode SQL Server Identifiers.</span></span>  
  
 <span data-ttu-id="b0c4c-124">Il provider di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] richiede di specificare sempre un nome dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-124">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider requires that you always specify an instance name.</span></span> <span data-ttu-id="b0c4c-125">Per le istanze predefinite, è necessario specificare un nome dell'istanza DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-125">For default instances, you must specify an instance name of DEFAULT.</span></span>  
  
##  <a name="examples-computer-and-instance-names"></a><a name="Examples"></a><span data-ttu-id="b0c4c-126">Esempi Nomi di computer e di istanze</span><span class="sxs-lookup"><span data-stu-id="b0c4c-126">Examples; Computer and Instance Names</span></span>  
 <span data-ttu-id="b0c4c-127">In questo esempio viene utilizzato localhost e DEFAULT per specificare l'istanza predefinita nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-127">This example uses localhost and DEFAULT to specify the default instance on the local computer:</span></span>  
  
```powershell
Set-Location SQLSERVER:\SQL\localhost\DEFAULT
```  
  
 <span data-ttu-id="b0c4c-128">I caratteri parentesi in (local) vengono in genere gestiti da Windows PowerShell come comandi.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-128">The parenthesis characters in (local) are normally treated as commands by Windows PowerShell.</span></span> <span data-ttu-id="b0c4c-129">È necessario:</span><span class="sxs-lookup"><span data-stu-id="b0c4c-129">You must either:</span></span>  
  
-   <span data-ttu-id="b0c4c-130">Racchiudere la stringa del percorso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-130">Enclose the path string in quotes:</span></span>  
  
    ```powershell
    Set-Location "SQLSERVER:\SQL\(local)\DEFAULT"  
    ```  
  
-   <span data-ttu-id="b0c4c-131">Utilizzare caratteri di escape per la parentesi utilizzando il carattere apice inverso (\`).</span><span class="sxs-lookup"><span data-stu-id="b0c4c-131">Escape the parenthesis using the back tick character (\`):</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
    ```  
  
-   <span data-ttu-id="b0c4c-132">Codificare le parentesi utilizzando la rappresentazione esadecimale.</span><span class="sxs-lookup"><span data-stu-id="b0c4c-132">Encode the parenthesis using their hexadecimal representation:</span></span>  
  
    ```powershell
    Set-Location SQLSERVER:\SQL\%28local%29\DEFAULT  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b0c4c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0c4c-133">See Also</span></span>  
 <span data-ttu-id="b0c4c-134">[Identificatori di SQL Server in PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="b0c4c-134">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="b0c4c-135">[Provider di SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="b0c4c-135">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="b0c4c-136">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0c4c-136">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
