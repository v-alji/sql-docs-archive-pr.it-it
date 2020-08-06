---
title: Scegliere un algoritmo di crittografia | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- cryptography [SQL Server], algorithms
- encryption [SQL Server], algorithms
- security [SQL Server], encryption
- algorithms [SQL Server encryption]
ms.assetid: 8227028c-a9c9-489d-bd27-fbf8242634ae
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 3b2c5292b4a00a3ad81e53fdbc603bb584130613
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725403"
---
# <a name="choose-an-encryption-algorithm"></a><span data-ttu-id="3b3fa-102">Scelta di un algoritmo di crittografia</span><span class="sxs-lookup"><span data-stu-id="3b3fa-102">Choose an Encryption Algorithm</span></span>
  <span data-ttu-id="3b3fa-103">La crittografia è una delle molte difese in profondità che gli amministratori possono utilizzare per proteggere un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b3fa-103">Encryption is one of several defenses-in-depth that are available to the administrator who wants to secure an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3b3fa-104">Gli algoritmi di crittografia definiscono trasformazioni dei dati che non possono essere facilmente invertite da utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-104">Encryption algorithms define data transformations that cannot be easily reversed by unauthorized users.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="3b3fa-105">consente ad amministratori e sviluppatori di scegliere tra diversi algoritmi, tra cui DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, RC4 a 128 bit, DESX, AES a 128 bit, AES a 192 bit e AES a 256 bit.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-105">allows administrators and developers to choose from among several algorithms, including DES, Triple DES, TRIPLE_DES_3KEY, RC2, RC4, 128-bit RC4, DESX, 128-bit AES, 192-bit AES, and 256-bit AES.</span></span>  
  
 <span data-ttu-id="3b3fa-106">Nessun algoritmo è ideale in tutte le situazioni e la valutazione dei vantaggi relativi a ogni algoritmo esula dall'ambito della documentazione online di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3b3fa-106">No single algorithm is ideal for all situations, and guidance on the merits of each is beyond the scope of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span> <span data-ttu-id="3b3fa-107">Sono comunque validi i principi generali seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b3fa-107">However, the following general principles apply:</span></span>  
  
-   <span data-ttu-id="3b3fa-108">La crittografia avanzata utilizza in genere una quantità di risorse della CPU maggiore rispetto alla crittografia vulnerabile.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-108">Strong encryption generally consumes more CPU resources than weak encryption.</span></span>  
  
-   <span data-ttu-id="3b3fa-109">Le chiavi lunghe consentono in genere una crittografia più avanzata rispetto a quelle brevi.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-109">Long keys generally yield stronger encryption than short keys.</span></span>  
  
-   <span data-ttu-id="3b3fa-110">La crittografia asimmetrica è meno avanzata della crittografia simmetrica che usa la stessa lunghezza di chiave, ma è relativamente lenta.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-110">Asymmetric encryption is weaker than symmetric encryption using the same key length, but it is relatively slow.</span></span>  
  
-   <span data-ttu-id="3b3fa-111">Le crittografie a blocchi con chiavi lunghe sono più avanzate rispetto alle crittografie a flussi.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-111">Block ciphers with long keys are stronger than stream ciphers.</span></span>  
  
-   <span data-ttu-id="3b3fa-112">Le password lunghe e complesse sono più avanzate rispetto alle password brevi.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-112">Long, complex passwords are stronger than short passwords.</span></span>  
  
-   <span data-ttu-id="3b3fa-113">Se si crittografano molti dati, è necessario crittografarli tramite una chiave simmetrica e crittografare la chiave simmetrica con una asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-113">If you are encrypting lots of data, you should encrypt the data using a symmetric key, and encrypt the symmetric key with an asymmetric key.</span></span>  
  
-   <span data-ttu-id="3b3fa-114">I dati crittografati non possono essere compressi, ma i dati compressi possono essere crittografati.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-114">Encrypted data cannot be compressed, but compressed data can be encrypted.</span></span> <span data-ttu-id="3b3fa-115">Se si utilizza la compressione, è necessario comprimere i dati prima di crittografarli.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-115">If you use compression, you should compress data before encrypting it.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3b3fa-116">L'algoritmo RC4 è supportato solo per motivi di compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-116">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="3b3fa-117">È possibile crittografare il nuovo materiale usando RC4 o RC4_128 solo quando il livello di compatibilità del database è 90 o 100.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-117">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="3b3fa-118">(Non consigliato.) Usare un algoritmo più recente, ad esempio uno degli algoritmi AES.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-118">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="3b3fa-119">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] e versioni successive il materiale crittografato utilizzando RC4 o RC4_128 può essere decrittografato in qualsiasi livello di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-119">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] and higher material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
>   
>  <span data-ttu-id="3b3fa-120">L'utilizzo ripetuto della stessa funzione KEY_GUID RC4 o RC4_128 su blocchi di dati diversi produrrà la stessa chiave RC4 perché [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] non fornisce automaticamente un valore salt.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-120">Repeated use of the same RC4 or RC4_128 KEY_GUID on different blocks of data will result in the same RC4 key because [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not provide a salt automatically.</span></span> <span data-ttu-id="3b3fa-121">L'utilizzo ripetuto della stessa chiave RC4 è un errore noto che comporta una crittografia molto debole.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-121">Using the same RC4 key repeatedly is a well-known error that will result in very weak encryption.</span></span> <span data-ttu-id="3b3fa-122">Per questo motivo le parole chiave RC4 e RC4_128 sono deprecate.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-122">Therefore, we have deprecated the RC4 and RC4_128 keywords.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="3b3fa-123">Per altre informazioni sugli algoritmi e sulla tecnologia di crittografia, vedere [Concetti chiave sulla sicurezza](https://go.microsoft.com/fwlink/?LinkId=62082) nella Guida per gli sviluppatori di .NET Framework in MSDN.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-123">For more information about encryption algorithms and encryption technology, see [Key Security Concepts](https://go.microsoft.com/fwlink/?LinkId=62082) in the .NET Framework Developer's Guide on MSDN.</span></span>  
  
 <span data-ttu-id="3b3fa-124">**Chiarimento relativo agli algoritmi DES:**</span><span class="sxs-lookup"><span data-stu-id="3b3fa-124">**Clarification regarding DES algorithms:**</span></span>  
  
-   <span data-ttu-id="3b3fa-125">La crittografia DESX è stata menzionata erroneamente.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-125">DESX was incorrectly named.</span></span> <span data-ttu-id="3b3fa-126">Le chiavi simmetriche create con ALGORITHM = DESX utilizzano in realtà la crittografia TRIPLE DES con una chiave a 192 bit.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-126">Symmetric keys created with ALGORITHM = DESX actually use the TRIPLE DES cipher with a 192-bit key.</span></span> <span data-ttu-id="3b3fa-127">L'algoritmo DESX non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-127">The DESX algorithm is not provided.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
-   <span data-ttu-id="3b3fa-128">Le chiavi simmetriche create con ALGORITHM = TRIPLE_DES_3KEY utilizzano TRIPLE DES con una chiave a 192 bit.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-128">Symmetric keys created with ALGORITHM = TRIPLE_DES_3KEY use TRIPLE DES with a 192-bit key.</span></span>  
  
-   <span data-ttu-id="3b3fa-129">Le chiavi simmetriche create con ALGORITHM = TRIPLE_DES utilizzano TRIPLE DES con una chiave a 128 bit.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-129">Symmetric keys created with ALGORITHM = TRIPLE_DES use TRIPLE DES with a 128-bit key.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="3b3fa-130">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="3b3fa-130">Related Tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b3fa-131">Crittografia tramite una chiave simmetrica.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-131">Encrypting using a symmetric key.</span></span>|[<span data-ttu-id="3b3fa-132">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3b3fa-132">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)|  
|<span data-ttu-id="3b3fa-133">Crittografia tramite una chiave asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-133">Encrypting using an asymmetric key.</span></span>|[<span data-ttu-id="3b3fa-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3b3fa-134">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)|  
|<span data-ttu-id="3b3fa-135">Crittografia tramite certificato.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-135">Encrypting using a certificate.</span></span>|[<span data-ttu-id="3b3fa-136">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3b3fa-136">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)|  
|<span data-ttu-id="3b3fa-137">Crittografia dei file di database mediante Transparent Data Encryption.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-137">Encrypting database files using transparent data encryption.</span></span>|[<span data-ttu-id="3b3fa-138">Transparent Data Encryption &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="3b3fa-138">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)|  
|<span data-ttu-id="3b3fa-139">Come crittografare una colonna di una tabella.</span><span class="sxs-lookup"><span data-stu-id="3b3fa-139">How to encrypt one column of a table.</span></span>|[<span data-ttu-id="3b3fa-140">Crittografia di una colonna di dati</span><span class="sxs-lookup"><span data-stu-id="3b3fa-140">Encrypt a Column of Data</span></span>](encrypt-a-column-of-data.md)|  
  
## <a name="see-also"></a><span data-ttu-id="3b3fa-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b3fa-141">See Also</span></span>  
 <span data-ttu-id="3b3fa-142">[Crittografia di SQL Server](sql-server-encryption.md) </span><span class="sxs-lookup"><span data-stu-id="3b3fa-142">[SQL Server Encryption](sql-server-encryption.md) </span></span>  
 [<span data-ttu-id="3b3fa-143">Gerarchia di crittografia</span><span class="sxs-lookup"><span data-stu-id="3b3fa-143">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  
