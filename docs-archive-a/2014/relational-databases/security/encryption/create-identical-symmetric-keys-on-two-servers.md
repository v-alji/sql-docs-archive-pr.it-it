---
title: Creare chiavi simmetriche identiche su due server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- symmetric keys [SQL Server], creating
ms.assetid: a13d0b21-a43b-43c0-9c22-7ba8f3d15e80
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 38eaccffff89b0be7e59f628fcfb9b6e772a02b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725399"
---
# <a name="create-identical-symmetric-keys-on-two-servers"></a><span data-ttu-id="a2213-102">Creare chiavi simmetriche identiche su due server</span><span class="sxs-lookup"><span data-stu-id="a2213-102">Create Identical Symmetric Keys on Two Servers</span></span>
  <span data-ttu-id="a2213-103">In questo argomento viene descritto come creare chiavi simmetriche identiche in due server diversi in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] tramite [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2213-103">This topic describes how to create identical symmetric keys on two different servers in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a2213-104">Al fine di decrittografare l'argomento ciphertext, è necessario disporre della chiave usata per crittografarlo.</span><span class="sxs-lookup"><span data-stu-id="a2213-104">In order to decrypt ciphertext, you need the key that was used to encrypt it.</span></span> <span data-ttu-id="a2213-105">Quando la crittografia e la decrittografia vengono eseguite in un unico database, la chiave viene archiviata nel database ed è disponibile, a seconda delle autorizzazioni, sia per la crittografia che per la decrittografia.</span><span class="sxs-lookup"><span data-stu-id="a2213-105">When both encryption and decryption occur in a single database, the key is stored in the database and it is available, depending on permissions, for both encryption and decryption.</span></span> <span data-ttu-id="a2213-106">Viceversa, quando la crittografia e la decrittografia vengono eseguite in database separati, la chiave archiviata in un database non è disponibile per l'utilizzo nell'altro database.</span><span class="sxs-lookup"><span data-stu-id="a2213-106">But when encryption and decryption occur in separate databases or on separate servers, the key stored in one database is not available for use on the second database</span></span>  
  
 <span data-ttu-id="a2213-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a2213-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a2213-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a2213-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a2213-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a2213-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a2213-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a2213-110">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="a2213-111">Per creare chiavi simmetriche identiche su due server diversi tramite Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a2213-111">To create identical symmetric keys on two different servers, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a2213-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a2213-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a2213-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a2213-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a2213-114">Quando si crea una chiave simmetrica è necessario crittografarla con almeno uno degli elementi seguenti: certificato, password, chiave simmetrica, chiave asimmetrica o PROVIDER.</span><span class="sxs-lookup"><span data-stu-id="a2213-114">When a symmetric key is created, the symmetric key must be encrypted by using at least one of the following: certificate, password, symmetric key, asymmetric key, or PROVIDER.</span></span> <span data-ttu-id="a2213-115">Una chiave può essere crittografata con più elementi di ogni tipo,</span><span class="sxs-lookup"><span data-stu-id="a2213-115">The key can have more than one encryption of each type.</span></span> <span data-ttu-id="a2213-116">ovvero una singola chiave simmetrica può essere crittografata contemporaneamente con più certificati, password, chiavi simmetriche e chiavi asimmetriche.</span><span class="sxs-lookup"><span data-stu-id="a2213-116">In other words, a single symmetric key can be encrypted by using multiple certificates, passwords, symmetric keys, and asymmetric keys at the same time.</span></span>  
  
-   <span data-ttu-id="a2213-117">Se si crittografa una chiave simmetrica con una password anziché con la chiave pubblica della chiave master del database, viene usato l'algoritmo di crittografia TRIPLE DES.</span><span class="sxs-lookup"><span data-stu-id="a2213-117">When a symmetric key is encrypted with a password instead of the public key of the database master key, the TRIPLE DES encryption algorithm is used.</span></span> <span data-ttu-id="a2213-118">Per questo motivo, le chiavi create con un algoritmo di crittografia avanzato, come AES, vengono a loro volta protette con un algoritmo meno avanzato.</span><span class="sxs-lookup"><span data-stu-id="a2213-118">Because of this, keys that are created with a strong encryption algorithm, such as AES, are themselves secured by a weaker algorithm.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a2213-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a2213-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a2213-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a2213-120">Permissions</span></span>  
 <span data-ttu-id="a2213-121">È richiesta l'autorizzazione ALTER ANY SYMMETRIC KEY per il database.</span><span class="sxs-lookup"><span data-stu-id="a2213-121">Requires ALTER ANY SYMMETRIC KEY permission on the database.</span></span> <span data-ttu-id="a2213-122">Se si specifica AUTHORIZATION, è richiesta l'autorizzazione IMPERSONATE per l'utente di database o l'autorizzazione ALTER per il ruolo applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2213-122">If AUTHORIZATION is specified, requires IMPERSONATE permission on the database user or ALTER permission on the application role.</span></span> <span data-ttu-id="a2213-123">Se la crittografia viene applicata con un certificato o una chiave asimmetrica, è richiesta l'autorizzazione VIEW DEFINITION per il certificato o la chiave asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="a2213-123">If encryption is by certificate or asymmetric key, requires VIEW DEFINITION permission on the certificate or asymmetric key.</span></span> <span data-ttu-id="a2213-124">Solo gli account di accesso di Windows e di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e i ruoli applicazione possono disporre di chiavi simmetriche.</span><span class="sxs-lookup"><span data-stu-id="a2213-124">Only Windows logins, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins, and application roles can own symmetric keys.</span></span> <span data-ttu-id="a2213-125">I gruppi e i ruoli non possono disporre di chiavi simmetriche.</span><span class="sxs-lookup"><span data-stu-id="a2213-125">Groups and roles cannot own symmetric keys.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a2213-126">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a2213-126">Using Transact-SQL</span></span>  
  
#### <a name="to-create-identical-symmetric-keys-on-two-different-servers"></a><span data-ttu-id="a2213-127">Per creare chiavi simmetriche identiche su due server diversi</span><span class="sxs-lookup"><span data-stu-id="a2213-127">To create identical symmetric keys on two different servers</span></span>  
  
1.  <span data-ttu-id="a2213-128">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a2213-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a2213-129">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a2213-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a2213-130">Creare una chiave eseguendo le seguenti istruzioni CREATE MASTER KEY, CREATE CERTIFICATE e CREATE SYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="a2213-130">Create a key by running the following CREATE MASTER KEY, CREATE CERTIFICATE, and CREATE SYMMETRIC KEY statements.</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'My p@55w0Rd';  
    GO  
    CREATE CERTIFICATE [cert_keyProtection] WITH SUBJECT = 'Key Protection';  
    GO  
    CREATE SYMMETRIC KEY [key_DataShare] WITH  
        KEY_SOURCE = 'My key generation bits. This is a shared secret!',  
        ALGORITHM = AES_256,   
        IDENTITY_VALUE = 'Key Identity generation bits. Also a shared secret'  
        ENCRYPTION BY CERTIFICATE [cert_keyProtection];  
    GO  
    ```  
  
4.  <span data-ttu-id="a2213-131">Connettersi a un'istanza del server separata, aprire una finestra Query diversa ed eseguire le istruzioni SQL precedenti per creare la stessa chiave nel secondo server.</span><span class="sxs-lookup"><span data-stu-id="a2213-131">Connect to a separate server instance, open a different Query Window, and run the SQL statements above to create the same key on the second server.</span></span>  
  
5.  <span data-ttu-id="a2213-132">Verificare le chiavi eseguendo prima l'istruzione OPEN SYMMETRIC KEY e quindi l'istruzione SELECT seguente nel primo server.</span><span class="sxs-lookup"><span data-stu-id="a2213-132">Test the keys by first running the OPEN SYMMETRIC KEY statement and the SELECT statement below on the first server.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    SELECT encryptbykey(key_guid('key_DataShare'), 'MyData' )  
    GO  
    -- For example, the output might look like this: 0x2152F8DA8A500A9EDC2FAE26D15C302DA70D25563DAE7D5D1102E3056CE9EF95CA3E7289F7F4D0523ED0376B155FE9C3  
    ```  
  
6.  <span data-ttu-id="a2213-133">Nell'altro server incollare il risultato dell'istruzione SELECT precedente nel codice indicato di seguito come valore di `@blob` ed eseguire il codice per verificare che la chiave duplicata sia in grado di decrittografare il testo crittografato.</span><span class="sxs-lookup"><span data-stu-id="a2213-133">On the second server, paste the result of the previous SELECT statement into the following code as the value of `@blob` and run the following code to verify that the duplicate key can decrypt the ciphertext.</span></span>  
  
    ```  
    OPEN SYMMETRIC KEY [key_DataShare]   
        DECRYPTION BY CERTIFICATE cert_keyProtection;  
    GO  
    DECLARE @blob varbinary(8000);  
    SET @blob = SELECT CONVERT(varchar(8000), decryptbykey(@blob));  
    GO  
    ```  
  
7.  <span data-ttu-id="a2213-134">Chiudere la chiave simmetrica in entrambi i server.</span><span class="sxs-lookup"><span data-stu-id="a2213-134">Close the symmetric key on both servers.</span></span>  
  
    ```  
    CLOSE SYMMETRIC KEY [key_DataShare];  
    GO  
    ```  
  
 <span data-ttu-id="a2213-135">Per altre informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2213-135">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="a2213-136">CREATE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a2213-136">CREATE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-master-key-transact-sql)  
  
-   [<span data-ttu-id="a2213-137">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a2213-137">CREATE CERTIFICATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-certificate-transact-sql)  
  
-   [<span data-ttu-id="a2213-138">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a2213-138">CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-symmetric-key-transact-sql)  
  
-   [<span data-ttu-id="a2213-139">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a2213-139">ENCRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/encryptbykey-transact-sql)  
  
-   [<span data-ttu-id="a2213-140">DECRYPTBYKEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a2213-140">DECRYPTBYKEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/decryptbykey-transact-sql)  
  
-   [<span data-ttu-id="a2213-141">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a2213-141">OPEN SYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/open-symmetric-key-transact-sql)  
  
  
