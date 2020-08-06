---
title: Impostare l'opzione di database PAGE_VERIFY su CHECKSUM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 686b9a4a-ea61-4263-9ab8-f444a3077679
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13296a976722390668b8ca6d901cf0dd080e5cc3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724516"
---
# <a name="set-the-page_verify-database-option-to-checksum"></a><span data-ttu-id="10b7b-102">Impostazione dell'opzione di database PAGE_VERIFY su CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="10b7b-102">Set the PAGE_VERIFY Database Option to CHECKSUM</span></span>
  <span data-ttu-id="10b7b-103">Questa regola consente di controllare se l'opzione di database PAGE_VERIFY è impostata su CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="10b7b-103">This rule checks whether PAGE_VERIFY database option is set to CHECKSUM.</span></span> <span data-ttu-id="10b7b-104">Se per l'opzione di database PAGE_VERIFY si specifica CHECKSUM, il [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] calcola un checksum sul contenuto dell'intera pagina e archivia il valore nell'intestazione di pagina quando viene scritta una pagina nel disco.</span><span class="sxs-lookup"><span data-stu-id="10b7b-104">When CHECKSUM is enabled for the PAGE_VERIFY database option, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] calculates a checksum over the contents of the whole page, and stores the value in the page header when a page is written to disk.</span></span> <span data-ttu-id="10b7b-105">Quando si esegue la lettura della pagina dal disco, il checksum viene ricalcolato e confrontato con il valore di checksum archiviato nell'intestazione della pagina.</span><span class="sxs-lookup"><span data-stu-id="10b7b-105">When the page is read from disk, the checksum is recomputed and compared to the checksum value that is stored in the page header.</span></span> <span data-ttu-id="10b7b-106">In questo modo viene garantito un livello elevato di integrità dei file di dati.</span><span class="sxs-lookup"><span data-stu-id="10b7b-106">This helps provide a high level of data-file integrity.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="10b7b-107">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="10b7b-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="10b7b-108">Impostare l'opzione di database PAGE_VERIFY su CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="10b7b-108">Set the PAGE_VERIFY database option to CHECKSUM.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="10b7b-109">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="10b7b-109">For More Information</span></span>  
 [<span data-ttu-id="10b7b-110">Opzioni ALTER DATABASE SET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="10b7b-110">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
  
