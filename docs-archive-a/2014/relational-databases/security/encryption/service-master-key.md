---
title: Chiave master del servizio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- service master key [SQL Server]
- service master key [SQL Server], about service master key
ms.assetid: 85f2095d-2590-4f59-8a29-7e100edd02bb
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: baeeffd49ac89ce85cf64932fbfd4982d7243887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726840"
---
# <a name="service-master-key"></a><span data-ttu-id="85fdd-102">chiave master del servizio</span><span class="sxs-lookup"><span data-stu-id="85fdd-102">Service Master Key</span></span>
  <span data-ttu-id="85fdd-103">La chiave master del servizio è la radice della gerarchia di crittografia di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85fdd-103">The Service Master Key is the root of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption hierarchy.</span></span> <span data-ttu-id="85fdd-104">e viene generata automaticamente la prima volta che risulta necessaria per crittografare un'altra chiave.</span><span class="sxs-lookup"><span data-stu-id="85fdd-104">It is generated automatically the first time it is needed to encrypt another key.</span></span> <span data-ttu-id="85fdd-105">Per impostazione predefinita, la chiave master del servizio viene crittografata mediante l'API Windows per la protezione dei dati e la chiave del computer locale.</span><span class="sxs-lookup"><span data-stu-id="85fdd-105">By default, the Service Master Key is encrypted using the Windows data protection API and using the local machine key.</span></span> <span data-ttu-id="85fdd-106">La chiave master del servizio può essere aperta solo dall'account di servizio Windows nel quale è stata creata oppure da un'entità con accesso sia al nome che alla password del'account di servizio.</span><span class="sxs-lookup"><span data-stu-id="85fdd-106">The Service Master Key can only be opened by the Windows service account under which it was created or by a principal with access to both the service account name and its password.</span></span>  
  
 <span data-ttu-id="85fdd-107">Per rigenerare o ripristinare la chiave master del servizio è necessario decrittografare e crittografare nuovamente l'intera gerarchia di crittografia.</span><span class="sxs-lookup"><span data-stu-id="85fdd-107">Regenerating or restoring the Service Master Key involves decrypting and re-encrypting the complete encryption hierarchy.</span></span> <span data-ttu-id="85fdd-108">Poiché questa operazione utilizza molte risorse, è opportuno programmarla durante un periodo di bassa richiesta, a meno che la chiave non sia compromessa.</span><span class="sxs-lookup"><span data-stu-id="85fdd-108">Unless the key has been compromised, this resource-intensive operation should be scheduled during a period of low demand.</span></span>  
  
 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] <span data-ttu-id="85fdd-109">usa l'algoritmo di crittografia AES per proteggere la chiave master del servizio (SMK) e la chiave master del database (DMK).</span><span class="sxs-lookup"><span data-stu-id="85fdd-109">uses the AES encryption algorithm to protect the service master key (SMK) and the database master key (DMK).</span></span> <span data-ttu-id="85fdd-110">AES è un algoritmo di crittografia più recente rispetto a 3DES utilizzato nelle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="85fdd-110">AES is a newer encryption algorithm than 3DES used in earlier versions.</span></span> <span data-ttu-id="85fdd-111">Dopo aver aggiornato un'istanza di [!INCLUDE[ssDE](../../../includes/ssde-md.md)] a [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] le chiavi SMK e DMK devono essere rigenerate per aggiornare le chiavi master ad AES.</span><span class="sxs-lookup"><span data-stu-id="85fdd-111">After upgrading an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] the SMK and DMK should be regenerated in order to upgrade the master keys to AES.</span></span> <span data-ttu-id="85fdd-112">Per altre informazioni sulla rigenerazione della chiave SMK, vedere [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-service-master-key-transact-sql) e [ALTER MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="85fdd-112">For more information about regenerating the SMK, see [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-service-master-key-transact-sql) and [ALTER MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-master-key-transact-sql).</span></span>  
  
## <a name="best-practice"></a><span data-ttu-id="85fdd-113">Procedura consigliata</span><span class="sxs-lookup"><span data-stu-id="85fdd-113">Best Practice</span></span>  
 <span data-ttu-id="85fdd-114">Eseguire il backup della chiave master del servizio e archiviare la copia di backup in un altro luogo adeguatamente protetto.</span><span class="sxs-lookup"><span data-stu-id="85fdd-114">Back up the Service Master Key and store the backed up copy in a secure, off-site location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="85fdd-115">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="85fdd-115">Related Tasks</span></span>  
 [<span data-ttu-id="85fdd-116">BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="85fdd-116">BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-service-master-key-transact-sql)  
  
 [<span data-ttu-id="85fdd-117">RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="85fdd-117">RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-service-master-key-transact-sql)  
  
 [<span data-ttu-id="85fdd-118">ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="85fdd-118">ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-service-master-key-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="85fdd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85fdd-119">See Also</span></span>  
 [<span data-ttu-id="85fdd-120">Gerarchia di crittografia</span><span class="sxs-lookup"><span data-stu-id="85fdd-120">Encryption Hierarchy</span></span>](encryption-hierarchy.md)  
  
  
