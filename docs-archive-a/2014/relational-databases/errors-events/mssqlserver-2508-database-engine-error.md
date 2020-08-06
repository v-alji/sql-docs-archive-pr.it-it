---
title: MSSQLSERVER_2508 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2508 (Database Engine error)
ms.assetid: c37d40e5-c665-4d66-a727-5cb845634fcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11dd1c72c8cae868b7ebcb02e72ef0db81aeafe2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715315"
---
# <a name="mssqlserver_2508"></a><span data-ttu-id="6be09-102">MSSQLSERVER_2508</span><span class="sxs-lookup"><span data-stu-id="6be09-102">MSSQLSERVER_2508</span></span>
    
## <a name="details"></a><span data-ttu-id="6be09-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6be09-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6be09-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="6be09-104">Product Name</span></span>|<span data-ttu-id="6be09-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6be09-105">SQL Server</span></span>|  
|<span data-ttu-id="6be09-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="6be09-106">Event ID</span></span>|<span data-ttu-id="6be09-107">2508</span><span class="sxs-lookup"><span data-stu-id="6be09-107">2508</span></span>|  
|<span data-ttu-id="6be09-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="6be09-108">Event Source</span></span>|<span data-ttu-id="6be09-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6be09-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6be09-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6be09-110">Component</span></span>|<span data-ttu-id="6be09-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6be09-111">SQLEngine</span></span>|  
|<span data-ttu-id="6be09-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="6be09-112">Symbolic Name</span></span>|<span data-ttu-id="6be09-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span><span class="sxs-lookup"><span data-stu-id="6be09-113">DBCC_OUT_OF_DATE_PAGE_OR_ROW_COUNT</span></span>|  
|<span data-ttu-id="6be09-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="6be09-114">Message Text</span></span>|<span data-ttu-id="6be09-115">Il conteggio %.\*ls per l'oggetto "%.\*ls", con ID di indice %d, ID di partizione %I64d e ID di unità di allocazione %I64d (tipo %.\*ls), non è corretto.</span><span class="sxs-lookup"><span data-stu-id="6be09-115">The %.\*ls count for object "%.\*ls", index ID %d, partition ID %I64d, alloc unit ID %I64d (type %.\*ls) is incorrect.</span></span> <span data-ttu-id="6be09-116">Eseguire DBCC UPDATEUSAGE.</span><span class="sxs-lookup"><span data-stu-id="6be09-116">Run DBCC UPDATEUSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6be09-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="6be09-117">Explanation</span></span>  
 <span data-ttu-id="6be09-118">Nelle versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] i valori relativi al conteggio delle righe delle tabelle e degli indici e i numeri delle pagine possono essere errati.</span><span class="sxs-lookup"><span data-stu-id="6be09-118">In versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the values for the table and index row counts and page counts can become incorrect.</span></span> <span data-ttu-id="6be09-119">Nei database creati con versioni precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] i conteggi potrebbero non essere corretti.</span><span class="sxs-lookup"><span data-stu-id="6be09-119">Databases that were created on versions prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] may contain incorrect counts.</span></span> <span data-ttu-id="6be09-120">Il comando DBCC CHECKDB è stato migliorato per rilevare tali errori e restituisce questo messaggio di avviso quando si verifica un errore di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="6be09-120">DBCC CHECKDB has been enhanced to detect these errors and returns this warning message when the error encountered.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6be09-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="6be09-121">User Action</span></span>  
 <span data-ttu-id="6be09-122">Eseguire DBCC UPDATEUSAGE sull'oggetto o l'indice specificato oppure sul database in cui è contenuto l'oggetto per correggere i conteggi non validi.</span><span class="sxs-lookup"><span data-stu-id="6be09-122">Run DBCC UPDATEUSAGE against the specified object or index, or against the database in which the object is contained to correct the invalid counts.</span></span>  
  
  
