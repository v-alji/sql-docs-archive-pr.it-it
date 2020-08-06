---
title: MSSQLSERVER_102 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 102 (Database Engine error)
ms.assetid: 264dc1a2-c8a0-4c89-b5f6-951baf950299
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 18c330b8d6a534ca11e2ad2c03f89793f8c832e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624249"
---
# <a name="mssqlserver_102"></a><span data-ttu-id="d1f2e-102">MSSQLSERVER_102</span><span class="sxs-lookup"><span data-stu-id="d1f2e-102">MSSQLSERVER_102</span></span>
    
## <a name="details"></a><span data-ttu-id="d1f2e-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d1f2e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1f2e-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="d1f2e-104">Product Name</span></span>|<span data-ttu-id="d1f2e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d1f2e-105">SQL Server</span></span>|  
|<span data-ttu-id="d1f2e-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="d1f2e-106">Event ID</span></span>|<span data-ttu-id="d1f2e-107">102</span><span class="sxs-lookup"><span data-stu-id="d1f2e-107">102</span></span>|  
|<span data-ttu-id="d1f2e-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="d1f2e-108">Event Source</span></span>|<span data-ttu-id="d1f2e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d1f2e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d1f2e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d1f2e-110">Component</span></span>|<span data-ttu-id="d1f2e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d1f2e-111">SQLEngine</span></span>|  
|<span data-ttu-id="d1f2e-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="d1f2e-112">Symbolic Name</span></span>|<span data-ttu-id="d1f2e-113">P_SYNTAXERR2</span><span class="sxs-lookup"><span data-stu-id="d1f2e-113">P_SYNTAXERR2</span></span>|  
|<span data-ttu-id="d1f2e-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="d1f2e-114">Message Text</span></span>|<span data-ttu-id="d1f2e-115">Sintassi non corretta in prossimità di '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="d1f2e-115">Incorrect syntax near '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d1f2e-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="d1f2e-116">Explanation</span></span>  
 <span data-ttu-id="d1f2e-117">Indica un errore di sintassi.</span><span class="sxs-lookup"><span data-stu-id="d1f2e-117">Indicates a syntax error.</span></span> <span data-ttu-id="d1f2e-118">Le informazioni aggiuntive non sono disponibili perché l'errore non consente l'elaborazione dell'istruzione da parte di [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1f2e-118">Additional information is not available because the error prevents the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from processing the statement.</span></span>  
  
 <span data-ttu-id="d1f2e-119">Questa situazione può essere causata dal tentativo di creare una chiave simmetrica utilizzando la crittografia deprecata RC4 o RC4_128 quando la modalità di compatibilità non è 90 o 100.</span><span class="sxs-lookup"><span data-stu-id="d1f2e-119">Can be caused by attempting to create a symmetric key using the deprecated RC4 or RC4_128 encryption, when not in 90 or 100 compatibility mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d1f2e-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="d1f2e-120">User Action</span></span>  
 <span data-ttu-id="d1f2e-121">Ricercare errori di sintassi nell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1f2e-121">Search the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement for syntax errors.</span></span>  
  
 <span data-ttu-id="d1f2e-122">Se si crea una chiave simmetrica utilizzando RC4 o RC4_128, selezionare un metodo di crittografia più recente, ad esempio uno degli algoritmi AES</span><span class="sxs-lookup"><span data-stu-id="d1f2e-122">If creating a symmetric key using the RC4 or RC4_128, select a newer encryption such as one of the AES algorithms.</span></span> <span data-ttu-id="d1f2e-123">(opzione consigliata). Se è necessario utilizzare RC4, eseguire ALTER DATABASE SET COMPATIBILITY_LEVEL per impostare il database sul livello di compatibilità 90 o 100.</span><span class="sxs-lookup"><span data-stu-id="d1f2e-123">(Recommended.) If you must use RC4, use ALTER DATABASE SET COMPATIBILITY_LEVEL to set the database to compatibility level 90 or 100.</span></span> <span data-ttu-id="d1f2e-124">(Non consigliato.)</span><span class="sxs-lookup"><span data-stu-id="d1f2e-124">(Not recommended.)</span></span>  
  
  
