---
title: MSSQLSERVER_9524 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9524 (Database Engine error)
ms.assetid: 12da7931-e124-4466-889c-046f1b7b7bfd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6c46ee0ef0bd1be299614e2cb04a3d6cd99d92e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627743"
---
# <a name="mssqlserver_9524"></a><span data-ttu-id="8a8ce-102">MSSQLSERVER_9524</span><span class="sxs-lookup"><span data-stu-id="8a8ce-102">MSSQLSERVER_9524</span></span>
    
## <a name="details"></a><span data-ttu-id="8a8ce-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8a8ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a8ce-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="8a8ce-104">Product Name</span></span>|<span data-ttu-id="8a8ce-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8a8ce-105">SQL Server</span></span>|  
|<span data-ttu-id="8a8ce-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="8a8ce-106">Event ID</span></span>|<span data-ttu-id="8a8ce-107">9254</span><span class="sxs-lookup"><span data-stu-id="8a8ce-107">9254</span></span>|  
|<span data-ttu-id="8a8ce-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="8a8ce-108">Event Source</span></span>|<span data-ttu-id="8a8ce-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8a8ce-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8a8ce-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8a8ce-110">Component</span></span>|<span data-ttu-id="8a8ce-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8a8ce-111">SQLEngine</span></span>|  
|<span data-ttu-id="8a8ce-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="8a8ce-112">Symbolic Name</span></span>|<span data-ttu-id="8a8ce-113">XMLERR_INVALID_COLUMNSET_XML</span><span class="sxs-lookup"><span data-stu-id="8a8ce-113">XMLERR_INVALID_COLUMNSET_XML</span></span>|  
|<span data-ttu-id="8a8ce-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="8a8ce-114">Message Text</span></span>|<span data-ttu-id="8a8ce-115">Il contenuto XML fornito non è conforme al formato XML richiesto per i set di colonne di tipo sparse.</span><span class="sxs-lookup"><span data-stu-id="8a8ce-115">The XML content provided does not conform to the required XML format for sparse column sets.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8a8ce-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8a8ce-116">Explanation</span></span>  
 <span data-ttu-id="8a8ce-117">È stato eseguito il tentativo di modificare un set di colonne.</span><span class="sxs-lookup"><span data-stu-id="8a8ce-117">An attempt was made to modify a column set.</span></span> <span data-ttu-id="8a8ce-118">Il contenuto XML di un set di colonne deve soddisfare le restrizioni del formato relativo.</span><span class="sxs-lookup"><span data-stu-id="8a8ce-118">The XML content of a column set must meet the format restrictions of a column set.</span></span> <span data-ttu-id="8a8ce-119">Il formato generale di un set di colonne è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8a8ce-119">The general format of a column set is as follows:</span></span>  
  
 `<column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...`  
  
 <span data-ttu-id="8a8ce-120">Per ulteriori informazioni sui set di colonne, vedere l'argomento "Utilizzo di set di colonne" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a8ce-120">For more information about column sets, see the topic "Using Column Sets" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8a8ce-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="8a8ce-121">User Action</span></span>  
 <span data-ttu-id="8a8ce-122">Correggere il formato del codice XML per il set di colonne nell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="8a8ce-122">Correct the format of the XML for the column set in the statement.</span></span>  
  
  
