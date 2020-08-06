---
title: Creazione di stored procedure estese | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- warnings [SQL Server]
- extended stored procedures [SQL Server], debugging
- extended stored procedures [SQL Server], creating
- messages [SQL Server], extended stored procedures
ms.assetid: 9f7c0cdb-6d88-44c0-b049-29953ae75717
author: rothja
ms.author: jroth
ms.openlocfilehash: d243b27b8542ec5fe10d795de1729d6c1fe484c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635606"
---
# <a name="creating-extended-stored-procedures"></a><span data-ttu-id="31ad4-102">Creazione di stored procedure estese</span><span class="sxs-lookup"><span data-stu-id="31ad4-102">Creating Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="31ad4-103">Utilizzare invece la funzionalità di integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="31ad4-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="31ad4-104">Una stored procedure estesa è una funzione con un prototipo:</span><span class="sxs-lookup"><span data-stu-id="31ad4-104">An extended stored procedure is a function with a prototype:</span></span>  
  
 <span data-ttu-id="31ad4-105">*Xp_extendedProcName* SRVRETCODE **(** SRVPROC \*\* \* );\*\*</span><span class="sxs-lookup"><span data-stu-id="31ad4-105">SRVRETCODE *xp_extendedProcName* **(** SRVPROC **\*);**</span></span>  
  
 <span data-ttu-id="31ad4-106">L'utilizzo del prefisso xp_ è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="31ad4-106">Using the prefix xp_ is optional.</span></span> <span data-ttu-id="31ad4-107">Per i nomi delle stored procedure estese viene fatta distinzione tra maiuscole e minuscole quando vi si fa riferimento in istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)], indipendentemente dalla tabella codici o dall'ordinamento installato nel server.</span><span class="sxs-lookup"><span data-stu-id="31ad4-107">Extended stored procedure names are case sensitive when referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, regardless of code page/sort order installed on the server.</span></span> <span data-ttu-id="31ad4-108">Quando si compila una DLL:</span><span class="sxs-lookup"><span data-stu-id="31ad4-108">When you build a DLL:</span></span>  
  
-   <span data-ttu-id="31ad4-109">Se è necessario un punto di ingresso, scrivere una funzione DllMain.</span><span class="sxs-lookup"><span data-stu-id="31ad4-109">If an entry point is necessary, write a DllMain function.</span></span>  
  
     <span data-ttu-id="31ad4-110">Questa funzione è facoltativa e, se non viene specificata nel codice sorgente, il compilatore collega la propria versione, che si limita a restituire TRUE.</span><span class="sxs-lookup"><span data-stu-id="31ad4-110">This function is optional; if you do not provide it in source code, the compiler links its own version, which does nothing but return TRUE.</span></span> <span data-ttu-id="31ad4-111">Se si specifica una funzione DllMain, il sistema operativo chiama questa funzione quando un thread o un processo viene collegato alla DLL o scollegato dalla DLL.</span><span class="sxs-lookup"><span data-stu-id="31ad4-111">If you provide a DllMain function, the operating system calls this function when a thread or process attaches to or detaches from the DLL.</span></span>  
  
-   <span data-ttu-id="31ad4-112">Tutte le funzioni chiamate dall'esterno della DLL, ovvero tutte le funzioni Efunction delle stored procedure estese, devono essere esportate.</span><span class="sxs-lookup"><span data-stu-id="31ad4-112">All functions called from outside the DLL (all extended stored procedure Efunctions) must be exported.</span></span>  
  
     <span data-ttu-id="31ad4-113">È possibile esportare una funzione elencando il nome nella sezione Esporta di un file con estensione def oppure è possibile anteporre il nome della funzione nel codice sorgente con __declspec (dllexport), un'estensione del compilatore Microsoft (si noti che \_ _declspec () inizia con due caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="31ad4-113">You can export a function by listing its name in the EXPORTS section of a .def file, or you can prefix the function name in the source code with __declspec(dllexport), a Microsoft compiler extension (Note that \__declspec() begins with two underscores).</span></span>  
  
 <span data-ttu-id="31ad4-114">I file seguenti sono necessari per la creazione della DLL di una stored procedure estesa.</span><span class="sxs-lookup"><span data-stu-id="31ad4-114">These files are required for creating an extended stored procedure DLL.</span></span>  
  
|<span data-ttu-id="31ad4-115">File</span><span class="sxs-lookup"><span data-stu-id="31ad4-115">File</span></span>|<span data-ttu-id="31ad4-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31ad4-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="31ad4-117">Srv.h</span><span class="sxs-lookup"><span data-stu-id="31ad4-117">Srv.h</span></span>|<span data-ttu-id="31ad4-118">File di intestazione dell'API della stored procedure estesa</span><span class="sxs-lookup"><span data-stu-id="31ad4-118">Extended Stored Procedure API header file</span></span>|  
|<span data-ttu-id="31ad4-119">Opends60.lib</span><span class="sxs-lookup"><span data-stu-id="31ad4-119">Opends60.lib</span></span>|<span data-ttu-id="31ad4-120">Libreria di importazione per Opends60.dll</span><span class="sxs-lookup"><span data-stu-id="31ad4-120">Import library for Opends60.dll</span></span>|  
  
 <span data-ttu-id="31ad4-121">Per creare la DLL di una stored procedure estesa, creare un progetto di tipo DLL.</span><span class="sxs-lookup"><span data-stu-id="31ad4-121">To create an extended stored procedure DLL, create a project of type Dynamic Link Library.</span></span> <span data-ttu-id="31ad4-122">Per ulteriori informazioni sulla creazione di una DLL, vedere la documentazione dell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="31ad4-122">For more information about creating a DLL, see the development environment documentation.</span></span>  
  
 <span data-ttu-id="31ad4-123">È estremamente consigliabile fare in modo che tutte le DLL delle stored procedure estese implementino ed esportino la funzione seguente:</span><span class="sxs-lookup"><span data-stu-id="31ad4-123">It is highly recommended that all extended stored procedure DLLs implement and export the following function:</span></span>  
  
```  
__declspec(dllexport) ULONG __GetXpVersion()  
{  
   return ODS_VERSION;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="31ad4-124">__declspec(dllexport) è un'estensione del compilatore specifica di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="31ad4-124">__declspec(dllexport) is a Microsoft-specific compiler extension.</span></span> <span data-ttu-id="31ad4-125">Se il compilatore non supporta questa direttiva, è necessario esportare questa funzione all'interno della sezione EXPORTS nel file DEF.</span><span class="sxs-lookup"><span data-stu-id="31ad4-125">If your compiler does not support this directive, you should export this function in your DEF file under the EXPORTS section.</span></span>  
  
 <span data-ttu-id="31ad4-126">Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene avviato con il flag di traccia-T260 o se un utente con privilegi di amministratore di sistema esegue DBCC TRACEON (260) e se la dll stored procedure estesa non supporta __GetXpVersion (), viene visualizzato un messaggio di avviso (errore 8131: la dll di stored procedure estesa '%' non esporta \_ _GetXpVersion (). viene stampato nel log degli errori di.</span><span class="sxs-lookup"><span data-stu-id="31ad4-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started with the trace flag -T260 or if a user with system administrator privileges runs DBCC TRACEON (260), and if the extended stored procedure DLL does not support __GetXpVersion(), a warning message (Error 8131: Extended stored procedure DLL '%' does not export \__GetXpVersion().) is printed to the error log.</span></span> <span data-ttu-id="31ad4-127">Si noti che \_ _GetXpVersion () inizia con due caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="31ad4-127">(Note that \__GetXpVersion() begins with two underscores.)</span></span>  
  
 <span data-ttu-id="31ad4-128">Se la DLL della stored procedure estesa consente l'esportazione di __GetXpVersion() ma la versione restituita dalla versione è precedente rispetto a quella richiesta dal server, nel log degli errori viene stampato un messaggio di avviso indicante la versione restituita dalla funzione e la versione prevista dal server.</span><span class="sxs-lookup"><span data-stu-id="31ad4-128">If the extended stored procedure DLL exports __GetXpVersion(), but the version returned by the function is less than that required by the server, a warning message stating the version returned by the function and the version expected by the server is printed to the error log.</span></span> <span data-ttu-id="31ad4-129">Se si riceve questo messaggio, viene restituito un valore non corretto da \_ _GetXpVersion () o si sta eseguendo la compilazione con una versione precedente di SRV. h.</span><span class="sxs-lookup"><span data-stu-id="31ad4-129">If you get this message, you are returning an incorrect value from \__GetXpVersion(), or you are compiling with an older version of srv.h.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31ad4-130">SetErrorMode, una funzione [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32, non deve essere chiamata nelle stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="31ad4-130">SetErrorMode, a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 function, should not be called in extended stored procedures.</span></span>  
  
 <span data-ttu-id="31ad4-131">Una stored procedure estesa con esecuzione prolungata deve piuttosto chiamare srv_got_attention periodicamente in modo che la procedura possa terminare se stessa in caso di interruzione della connessione o del batch.</span><span class="sxs-lookup"><span data-stu-id="31ad4-131">It is recommended that a long-running extended stored procedure should call srv_got_attention periodically so that the procedure can terminate itself if the connection is killed or the batch is aborted.</span></span>  
  
 <span data-ttu-id="31ad4-132">Per eseguire il debug della DLL di una stored procedure estesa, copiare la DLL nella directory [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn.</span><span class="sxs-lookup"><span data-stu-id="31ad4-132">To debug an extended stored procedure DLL, copy it to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn directory.</span></span> <span data-ttu-id="31ad4-133">Per specificare il file eseguibile per la sessione di debug, immettere il percorso e il nome del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file eseguibile, ad esempio c:\programmi\microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe.</span><span class="sxs-lookup"><span data-stu-id="31ad4-133">To specify the executable for the debugging session, enter the path and file name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executable file (for example, C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe).</span></span> <span data-ttu-id="31ad4-134">Per informazioni sugli argomenti sqlservr, vedere [applicazione sqlservr](../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="31ad4-134">For information about sqlservr arguments, see [sqlservr Application](../../tools/sqlservr-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31ad4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31ad4-135">See Also</span></span>  
 [<span data-ttu-id="31ad4-136">srv_got_attention &#40;API stored procedure estesa&#41;</span><span class="sxs-lookup"><span data-stu-id="31ad4-136">srv_got_attention &#40;Extended Stored Procedure API&#41;</span></span>](../extended-stored-procedures-reference/srv-got-attention-extended-stored-procedure-api.md)  
  
  
