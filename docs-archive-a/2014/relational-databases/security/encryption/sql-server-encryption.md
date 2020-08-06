---
title: Crittografia di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], about encryption
- security [SQL Server], encryption
- cryptography [SQL Server], about cryptography
ms.assetid: ead0150e-4943-4ad5-84c8-36f85c7278f4
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 6fc68e6f3280a8e23d6a1bf4f364aadfffd69f85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726831"
---
# <a name="sql-server-encryption"></a><span data-ttu-id="c038a-102">Crittografia di SQL Server</span><span class="sxs-lookup"><span data-stu-id="c038a-102">SQL Server Encryption</span></span>
  <span data-ttu-id="c038a-103">La crittografia è il processo che consiste nell'offuscare i dati tramite l'utilizzo di una chiave o di una password.</span><span class="sxs-lookup"><span data-stu-id="c038a-103">Encryption is the process of obfuscating data by the use of a key or password.</span></span> <span data-ttu-id="c038a-104">È in grado di rendere i dati inutilizzabili se non si dispone della chiave di decrittografia o password corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c038a-104">This can make the data useless without the corresponding decryption key or password.</span></span> <span data-ttu-id="c038a-105">La crittografia non risolve i problemi relativi al controllo di accesso,</span><span class="sxs-lookup"><span data-stu-id="c038a-105">Encryption does not solve access control problems.</span></span> <span data-ttu-id="c038a-106">ma migliora la sicurezza limitando la perdita di dati anche se il controllo di accesso viene eluso.</span><span class="sxs-lookup"><span data-stu-id="c038a-106">However, it enhances security by limiting data loss even if access controls are bypassed.</span></span> <span data-ttu-id="c038a-107">Se, ad esempio, il computer host del database è configurato scorrettamente e un pirata informatico ottiene dati riservati, le informazioni sottratte potrebbero essere inutilizzabili se crittografate.</span><span class="sxs-lookup"><span data-stu-id="c038a-107">For example, if the database host computer is misconfigured and a hacker obtains sensitive data, that stolen information might be useless if it is encrypted.</span></span>  
  
 <span data-ttu-id="c038a-108">È possibile utilizzare la crittografia in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per connessioni, dati e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c038a-108">You can use encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] for connections, data, and stored procedures.</span></span> <span data-ttu-id="c038a-109">Nella tabella seguente sono disponibili ulteriori informazioni sulla crittografia in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c038a-109">The following table contains more information about encryption in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c038a-110">Sebbene la crittografia sia un strumento prezioso per garantire la sicurezza, se ne sconsiglia l'utilizzo per tutti i dati o le connessioni.</span><span class="sxs-lookup"><span data-stu-id="c038a-110">Although encryption is a valuable tool to help ensure security, it should not be considered for all data or connections.</span></span> <span data-ttu-id="c038a-111">Per decidere se implementare la crittografia oppure no, considerare le modalità di accesso ai dati utilizzate dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="c038a-111">When you are deciding whether to implement encryption, consider how users will access data.</span></span> <span data-ttu-id="c038a-112">Se per accedere gli utenti utilizzano una rete pubblica, la crittografia dei dati potrebbe essere necessaria per aumentare il livello di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c038a-112">If users access data over a public network, data encryption might be required to increase security.</span></span> <span data-ttu-id="c038a-113">Tuttavia, se tutti accedono attraverso una configurazione di Intranet sicura, la crittografia potrebbe non essere necessaria.</span><span class="sxs-lookup"><span data-stu-id="c038a-113">However, if all access involves a secure intranet configuration, encryption might not be required.</span></span> <span data-ttu-id="c038a-114">L'utilizzo della crittografia comporta anche l'adozione di una strategia di manutenzione per password, chiavi e certificati.</span><span class="sxs-lookup"><span data-stu-id="c038a-114">Any use of encryption should also include a maintenance strategy for passwords, keys, and certificates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c038a-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c038a-115">In This Section</span></span>  
 [<span data-ttu-id="c038a-116">Gerarchia di crittografia</span><span class="sxs-lookup"><span data-stu-id="c038a-116">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
 <span data-ttu-id="c038a-117">Informazioni sulla gerarchia di crittografia in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c038a-117">Information about the encryption hierarchy in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="c038a-118">Scelta di un algoritmo di crittografia</span><span class="sxs-lookup"><span data-stu-id="c038a-118">Choose an Encryption Algorithm</span></span>](choose-an-encryption-algorithm.md)  
 <span data-ttu-id="c038a-119">Informazioni sulla selezione di un algoritmo di crittografia efficace.</span><span class="sxs-lookup"><span data-stu-id="c038a-119">Information about how to select an effective encrypting algorithm.</span></span>  
  
 [<span data-ttu-id="c038a-120">Transparent Data Encryption &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="c038a-120">Transparent Data Encryption &#40;TDE&#41;</span></span>](transparent-data-encryption.md)  
 <span data-ttu-id="c038a-121">Informazioni generali sulla crittografia trasparente dei dati.</span><span class="sxs-lookup"><span data-stu-id="c038a-121">General information about how to encrypt data transparently.</span></span>  
  
 [<span data-ttu-id="c038a-122">Chiavi di crittografia del database e di SQL Server &#40;Motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="c038a-122">SQL Server and Database Encryption Keys &#40;Database Engine&#41;</span></span>](sql-server-and-database-encryption-keys-database-engine.md)  
 <span data-ttu-id="c038a-123">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], le chiavi di crittografia sono costituite da una combinazione di chiavi pubbliche, private e simmetriche utilizzate per proteggere dati riservati.</span><span class="sxs-lookup"><span data-stu-id="c038a-123">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], encryption keys include a combination of public, private, and symmetric keys that are used to protect sensitive data.</span></span> <span data-ttu-id="c038a-124">In questa sezione vengono illustrate l'implementazione e la gestione delle chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="c038a-124">This section explains how to implement and manage encryption keys.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="c038a-125">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="c038a-125">Related Content</span></span>  
 [<span data-ttu-id="c038a-126">Sicurezza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="c038a-126">Securing SQL Server</span></span>](../securing-sql-server.md)  
 <span data-ttu-id="c038a-127">Panoramica della sicurezza della piattaforma [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e del funzionamento con gli utenti e gli oggetti a protezione diretta.</span><span class="sxs-lookup"><span data-stu-id="c038a-127">Overview of how to help secure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] platform, and how to work with users and securable objects.</span></span>  
  
 [<span data-ttu-id="c038a-128">Funzioni di crittografia &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c038a-128">Cryptographic Functions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cryptographic-functions-transact-sql)  
 <span data-ttu-id="c038a-129">Informazioni sull'implementazione delle funzioni di crittografia.</span><span class="sxs-lookup"><span data-stu-id="c038a-129">Information about how to implement cryptographic functions.</span></span>  
  
 [<span data-ttu-id="c038a-130">ENCRYPTBYPASSPHRASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c038a-130">ENCRYPTBYPASSPHRASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbypassphrase-transact-sql)  
 <span data-ttu-id="c038a-131">Informazioni sull'utilizzo di una password per la crittografia dei dati.</span><span class="sxs-lookup"><span data-stu-id="c038a-131">Information about how to use a password to encrypt data.</span></span>  
  
 [<span data-ttu-id="c038a-132">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c038a-132">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
 <span data-ttu-id="c038a-133">Informazioni sull'utilizzo di una chiave simmetrica per la crittografia dei dati.</span><span class="sxs-lookup"><span data-stu-id="c038a-133">Information about how to use a symmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="c038a-134">ENCRYPTBYASYMKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c038a-134">ENCRYPTBYASYMKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbyasymkey-transact-sql)  
 <span data-ttu-id="c038a-135">Informazioni sull'utilizzo di una chiave simmetrica per la crittografia dei dati.</span><span class="sxs-lookup"><span data-stu-id="c038a-135">Information about how to use an asymmetric key to encrypt data.</span></span>  
  
 [<span data-ttu-id="c038a-136">ENCRYPTBYCERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c038a-136">ENCRYPTBYCERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbycert-transact-sql)  
 <span data-ttu-id="c038a-137">Informazioni sull'utilizzo di un certificato per la crittografia dei dati.</span><span class="sxs-lookup"><span data-stu-id="c038a-137">Information about how to use a certificate to encrypt data.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="c038a-138">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="c038a-138">External Resources</span></span>  
 [<span data-ttu-id="c038a-139">10 passaggi per la sicurezza di SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="c038a-139">10 Steps to SQL Server 2005 Security</span></span>](https://www.itprotoday.com/sql-server/10-steps-sql-server-2005-security)  
 <span data-ttu-id="c038a-140">Informazioni aggiornate sulla sicurezza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c038a-140">Current information about [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] security.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c038a-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c038a-141">See Also</span></span>  
 <span data-ttu-id="c038a-142">[sys.key_encryptions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c038a-142">[sys.key_encryptions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-encryptions-transact-sql) </span></span>  
 <span data-ttu-id="c038a-143">[Chiavi di crittografia del database e di SQL Server &#40;Motore di database&#41;](sql-server-and-database-encryption-keys-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="c038a-143">[SQL Server and Database Encryption Keys &#40;Database Engine&#41;](sql-server-and-database-encryption-keys-database-engine.md) </span></span>  
 [<span data-ttu-id="c038a-144">Eseguire il backup e il ripristino delle chiavi di crittografia di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="c038a-144">Back Up and Restore Reporting Services Encryption Keys</span></span>](../../../reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)  
  
  
