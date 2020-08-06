---
title: Caratteristiche di esecuzione delle stored procedure estese | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], executing
- executing extended stored procedures [SQL Server]
ms.assetid: 6fe1f7e8-cc02-49df-8a2a-d47a96ec3567
author: rothja
ms.author: jroth
ms.openlocfilehash: edbd73797699d65f694e91bc3035e0dc9366c9d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624729"
---
# <a name="execution-characteristics-of-extended-stored-procedures"></a><span data-ttu-id="af956-102">Caratteristiche dell'esecuzione di stored procedure estese</span><span class="sxs-lookup"><span data-stu-id="af956-102">Execution Characteristics of Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="af956-103">Utilizzare invece la funzionalità di integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="af956-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="af956-104">L'esecuzione di una stored procedure estesa presenta tre caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="af956-104">The execution of an extended stored procedure has these characteristics:</span></span>  
  
-   <span data-ttu-id="af956-105">La funzione stored procedure estesa viene eseguita nel contesto di sicurezza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="af956-105">The extended stored procedure function is executed under the security context of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="af956-106">La funzione della stored procedure estesa viene eseguita nello spazio di processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af956-106">The extended stored procedure function runs in the process space of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="af956-107">Il thread associato all'esecuzione della stored procedure estesa è lo stesso utilizzato per la connessione client.</span><span class="sxs-lookup"><span data-stu-id="af956-107">The thread associated with the execution of the extended stored procedure is the same one used for the client connection.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="af956-108">Prima di aggiungere stored procedure estese al server e concedere le autorizzazioni di esecuzione ad altri utenti, è necessario che l'amministratore di sistema esamini con attenzione ogni stored procedure estesa per verificare che non contenga codice dannoso o malware.</span><span class="sxs-lookup"><span data-stu-id="af956-108">Before adding extended stored procedures to the server and granting execute permissions to other users, the system administrator should thoroughly review each extended stored procedure to make sure that it does not contain harmful or malicious code.</span></span>  
  
-  
  
 <span data-ttu-id="af956-109">Una volta caricata la DLL di stored procedure estesa, la DLL rimane caricata nello spazio degli indirizzi del server fino a quando non [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene arrestato o l'amministratore Scarica in modo esplicito la dll tramite DBCC *Dll_Name* (free).</span><span class="sxs-lookup"><span data-stu-id="af956-109">After the extended stored procedure DLL is loaded, the DLL remains loaded in the address space of the server until [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is stopped or the administrator explicitly unloads the DLL by using DBCC *DLL_name* (FREE).</span></span>  
  
 <span data-ttu-id="af956-110">La stored procedure estesa può essere eseguita da [!INCLUDE[tsql](../../includes/tsql-md.md)] come stored procedure mediante l'istruzione EXECUTE:</span><span class="sxs-lookup"><span data-stu-id="af956-110">The extended stored procedure can be executed from [!INCLUDE[tsql](../../includes/tsql-md.md)] as a stored procedure by using the EXECUTE statement:</span></span>  
  
```  
EXECUTE @retval = xp_extendedProcName @param1, @param2 OUTPUT  
```  
  
## <a name="parameters"></a><span data-ttu-id="af956-111">Parametri</span><span class="sxs-lookup"><span data-stu-id="af956-111">Parameters</span></span>  
 <span data-ttu-id="af956-112">\@ *retval*</span><span class="sxs-lookup"><span data-stu-id="af956-112">\@ *retval*</span></span>  
 <span data-ttu-id="af956-113">È un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="af956-113">Is a return value.</span></span>  
  
 <span data-ttu-id="af956-114">\@*param1*</span><span class="sxs-lookup"><span data-stu-id="af956-114">\@ *param1*</span></span>  
 <span data-ttu-id="af956-115">È un parametro di input.</span><span class="sxs-lookup"><span data-stu-id="af956-115">Is an input parameter.</span></span>  
  
 <span data-ttu-id="af956-116">\@*param2*</span><span class="sxs-lookup"><span data-stu-id="af956-116">\@ *param2*</span></span>  
 <span data-ttu-id="af956-117">È un parametro di input/output.</span><span class="sxs-lookup"><span data-stu-id="af956-117">Is an input/output parameter.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="af956-118">Le stored procedure estese offrono miglioramenti delle prestazioni ed estendono la funzionalità [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)],</span><span class="sxs-lookup"><span data-stu-id="af956-118">Extended stored procedures offer performance enhancements and extend [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="af956-119">tuttavia dal momento che la DLL della stored procedure estesa e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] condividono lo stesso spazio degli indirizzi, una procedura problematica può compromettere il funzionamento di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af956-119">However, because the extended stored procedure DLL and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] share the same address space, a problem procedure can adversely affect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functioning.</span></span> <span data-ttu-id="af956-120">Sebbene le eccezioni generate dalla DLL delle stored procedure estese vengano gestite da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è possibile danneggiare le aree dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af956-120">Although exceptions thrown by the extended stored procedure DLL are handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is possible to damage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data areas.</span></span> <span data-ttu-id="af956-121">Come precauzione di sicurezza, solo gli amministratori di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono aggiungere stored procedure estese a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af956-121">As a security precaution, only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrators can add extended stored procedures to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="af956-122">È consigliabile testare completamente tali procedure prima dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="af956-122">These procedures should be thoroughly tested before they are installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af956-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af956-123">See Also</span></span>  
 <span data-ttu-id="af956-124">[Programmazione di stored procedure estese](database-engine-extended-stored-procedures-programming.md) </span><span class="sxs-lookup"><span data-stu-id="af956-124">[Programming Extended Stored Procedures](database-engine-extended-stored-procedures-programming.md) </span></span>  
 [<span data-ttu-id="af956-125">Esecuzione di query su stored procedure estese installate in SQL Server</span><span class="sxs-lookup"><span data-stu-id="af956-125">Querying Extended Stored Procedures Installed in SQL Server</span></span>](querying-extended-stored-procedures-installed-in-sql-server.md)  
  
  
