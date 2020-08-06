---
title: Aggiunta di una stored procedure estesa a SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], adding
- adding extended stored procedures
- collations [SQL Server], extended stored procedures
ms.assetid: 10f1bb74-3b43-4efd-b7ab-7a85a8600a50
author: rothja
ms.author: jroth
ms.openlocfilehash: 03ac8c2a0fa9ce77db59d50b3a7b9da42415e013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635608"
---
# <a name="adding-an-extended-stored-procedure-to-sql-server"></a><span data-ttu-id="0b775-102">Aggiunta di una stored procedure estesa a SQL Server</span><span class="sxs-lookup"><span data-stu-id="0b775-102">Adding an Extended Stored Procedure to SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="0b775-103">Utilizzare invece la funzionalità di integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="0b775-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="0b775-104">Una DLL che contiene funzioni di stored procedure estese funge da estensione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b775-104">A DLL that contains extended stored procedure functions acts as an extension to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0b775-105">Per installare la DLL, copiare il file in una directory, ad esempio quella che contiene i [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file dll standard (C:\Programmi\Microsoft SQL Server\MSSQL12.0.\* x\*\MSSQL\Binn per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="0b775-105">To install the DLL, copy the file to a directory, such as the one that contains the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files (C:\Program Files\Microsoft SQL Server\MSSQL12.0.*x*\MSSQL\Binn by default).</span></span>  
  
 <span data-ttu-id="0b775-106">Dopo che la DLL della stored procedure estesa è stata copiata nel server, un amministratore di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve registrare in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ogni funzione di stored procedure estesa presente nella DLL.</span><span class="sxs-lookup"><span data-stu-id="0b775-106">After the extended stored procedure DLL has been copied to the server, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator must register to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] each extended stored procedure function in the DLL.</span></span> <span data-ttu-id="0b775-107">È possibile eseguire questa operazione utilizzando la stored procedure di sistema sp_addextendedproc.</span><span class="sxs-lookup"><span data-stu-id="0b775-107">This is done using the sp_addextendedproc system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0b775-108">L'amministratore di sistema deve esaminare con attenzione una stored procedure estesa per assicurarsi che non contenga codice dannoso o malware prima di aggiungerla al server e prima di concedere autorizzazioni di esecuzione ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="0b775-108">The system administrator should thoroughly review an extended stored procedure to ensure that it does not contain harmful or malicious code before adding it to the server and granting execute permissions to other users.</span></span>  <span data-ttu-id="0b775-109">Convalidare sempre input di tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0b775-109">Validate all user input.</span></span> <span data-ttu-id="0b775-110">Non concatenare l'input dell'utente prima di convalidarlo.</span><span class="sxs-lookup"><span data-stu-id="0b775-110">Do not concatenate user input before validating it.</span></span> <span data-ttu-id="0b775-111">Non eseguire mai un comando creato dall'input dell'utente non convalidato.</span><span class="sxs-lookup"><span data-stu-id="0b775-111">Never execute a command constructed from unvalidated user input.</span></span>  
  
 <span data-ttu-id="0b775-112">Il primo parametro di sp_addextendedproc specifica il nome della funzione, mentre il secondo specifica il nome della DLL nella quale risiede la funzione.</span><span class="sxs-lookup"><span data-stu-id="0b775-112">The first parameter of sp_addextendedproc specifies the name of the function, and the second parameter specifies the name of the DLL in which that function resides.</span></span> <span data-ttu-id="0b775-113">È consigliabile specificare il percorso completo della DLL.</span><span class="sxs-lookup"><span data-stu-id="0b775-113">It is recommended that you specify the complete path of the DLL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0b775-114">Le DLL esistenti non registrate con un percorso completo non funzionano dopo l'aggiornamento a SQL Server 2005 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0b775-114">Existing DLLs that were not registered with a complete path will not work after upgrading to SQL Server 2005 or later.</span></span> <span data-ttu-id="0b775-115">Per correggere il problema, utilizzare sp_dropextendedproc per annullare la registrazione della DLL e quindi sp_addextendedproc per registrarla di nuovo specificando il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="0b775-115">To correct the problem, use sp_dropextendedproc to unregister the DLL, and then reregister it with sp_addextendedproc, specifying the complete path.</span></span>  
  
 <span data-ttu-id="0b775-116">Il nome della funzione specificato in `sp_addextendedproc` deve corrispondere esattamente a quello presente nella DLL, anche nell'uso di maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0b775-116">The name of the function specified in `sp_addextendedproc` must be exactly the same, including the case, as the function's name in the DLL.</span></span> <span data-ttu-id="0b775-117">Il comando seguente, ad esempio, registra una funzione `xp_hello,` che si trova in una dll denominata `xp_hello.dll` come stored procedure estesa di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0b775-117">For example, this command registers a function `xp_hello,` located in a dll named `xp_hello.dll`, as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure:</span></span>  
  
```  
sp_addextendedproc 'xp_hello', 'c:\Program Files\Microsoft SQL Server\MSSQL12.0.MSSQLSERVER\MSSQL\Binn\xp_hello.dll';  
```  
  
 <span data-ttu-id="0b775-118">Se il nome della funzione specificato in `sp_addextendedproc` non corrisponde esattamente al nome presente nella DLL, il nuovo nome verrà registrato in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ma non sarà possibile utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="0b775-118">If the name of the function specified in `sp_addextendedproc` does not exactly match the function name in the DLL, the new name will be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but the name will not be usable.</span></span> <span data-ttu-id="0b775-119">Se, ad esempio, `xp_Hello` viene registrato come [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedure esteso disponibile in `xp_hello.dll` , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non sarà in grado di trovare la funzione nella dll se si utilizza `xp_Hello` per chiamare la funzione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="0b775-119">For example, although `xp_Hello` is registered as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure located in `xp_hello.dll`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to find the function in the DLL if you use `xp_Hello` to call the function later.</span></span>  
  
```  
--Register the function (xp_hello) with an initial upper case  
sp_addextendedproc 'xp_Hello', 'c:\xp_hello.dll';  
  
--Use the newly registered name to call the function  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
--This is the error message  
Server: Msg 17750, Level 16, State 1, Procedure xp_Hello, Line 1  
Could not load the DLL xp_hello.dll, or one of the DLLs it references. Reason: 127(The specified procedure could not be found.).  
```  
  
 <span data-ttu-id="0b775-120">Se il nome della funzione specificato in `sp_addextendedproc` corrisponde esattamente al nome della funzione nella DLL e per le regole di confronto dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non viene fatta distinzione tra maiuscole e minuscole, l'utente può chiamare la stored procedure estesa utilizzando una qualsiasi combinazione di lettere maiuscole e minuscole per il nome.</span><span class="sxs-lookup"><span data-stu-id="0b775-120">If the name of the function specified in `sp_addextendedproc` matches exactly the function name in the DLL, and the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-insensitive, the user can call the extended stored procedure using any combination of lower- and upper-case letters of the name.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will succeed in calling xp_hello  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HelLO @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
```  
  
 <span data-ttu-id="0b775-121">Quando le regole di confronto dell' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istanza fanno distinzione tra maiuscole e minuscole, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non sarà in grado di chiamare il stored procedure esteso, anche se è stato registrato con lo stesso nome e le stesse regole di confronto della funzione nella dll, se la procedura viene chiamata con un case diverso.</span><span class="sxs-lookup"><span data-stu-id="0b775-121">When the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-sensitive, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to call the extended stored procedure -- even if it was registered with exactly the same name and collation as the function in the DLL -- if the procedure is called with a different case.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will result in an error  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
  
--This is the error  
Server: Msg 2812, Level 16, State 62, Line 1  
```  
  
 <span data-ttu-id="0b775-122">Non è necessario arrestare e riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b775-122">It is not necessary to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b775-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b775-123">See Also</span></span>  
 <span data-ttu-id="0b775-124">[sp_addextendedproc &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0b775-124">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="0b775-125">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0b775-125">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
