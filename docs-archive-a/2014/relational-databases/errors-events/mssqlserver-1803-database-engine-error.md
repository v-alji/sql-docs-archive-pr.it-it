---
title: MSSQLSERVER_1803 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1803 (Database Engine error)
ms.assetid: d4315390-82f1-4c4c-8d1b-1a4989537cca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11302f882846c49c6e9998608967e7042ac9860c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629859"
---
# <a name="mssqlserver_1803"></a><span data-ttu-id="12837-102">MSSQLSERVER_1803</span><span class="sxs-lookup"><span data-stu-id="12837-102">MSSQLSERVER_1803</span></span>
    
## <a name="details"></a><span data-ttu-id="12837-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="12837-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="12837-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="12837-104">Product Name</span></span>|<span data-ttu-id="12837-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="12837-105">SQL Server</span></span>|  
|<span data-ttu-id="12837-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="12837-106">Event ID</span></span>|<span data-ttu-id="12837-107">1803</span><span class="sxs-lookup"><span data-stu-id="12837-107">1803</span></span>|  
|<span data-ttu-id="12837-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="12837-108">Event Source</span></span>|<span data-ttu-id="12837-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="12837-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="12837-110">Componente</span><span class="sxs-lookup"><span data-stu-id="12837-110">Component</span></span>|<span data-ttu-id="12837-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="12837-111">SQLEngine</span></span>|  
|<span data-ttu-id="12837-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="12837-112">Symbolic Name</span></span>|<span data-ttu-id="12837-113">NO_SPACE</span><span class="sxs-lookup"><span data-stu-id="12837-113">NO_SPACE</span></span>|  
|<span data-ttu-id="12837-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="12837-114">Message Text</span></span>|<span data-ttu-id="12837-115">Istruzione CREATE DATABASE non riuscita.</span><span class="sxs-lookup"><span data-stu-id="12837-115">CREATE DATABASE failed.</span></span> <span data-ttu-id="12837-116">Per contenere una copia del database modello, il file primario deve essere di almeno %d MB.</span><span class="sxs-lookup"><span data-stu-id="12837-116">Primary file must be at least %d MB to accommodate a copy of the model database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="12837-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="12837-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="12837-118">crea un database eseguendo una copia del database modello.</span><span class="sxs-lookup"><span data-stu-id="12837-118">creates a database by making a copy of the model database.</span></span> <span data-ttu-id="12837-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rinomina quindi la copia e aumenta le dimensioni del nuovo database fino a quelle richieste.</span><span class="sxs-lookup"><span data-stu-id="12837-119">Then [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] renames the copy, and enlarges the new database to the requested size.</span></span> <span data-ttu-id="12837-120">In questo caso l'utente ha tentato di creare un database di dimensioni inferiori rispetto al database modello.</span><span class="sxs-lookup"><span data-stu-id="12837-120">In this case, the user tried to create a database smaller than the model database.</span></span> <span data-ttu-id="12837-121">L'operazione non è riuscita perché le dimensioni del file di dati primario sono minori rispetto a quelle del database modello.</span><span class="sxs-lookup"><span data-stu-id="12837-121">The operation failed because the copy of the model database could not fit on the primary data file, because the file was smaller than the model database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="12837-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="12837-122">User Action</span></span>  
 <span data-ttu-id="12837-123">Creare il database aumentando le dimensioni dei file di database.</span><span class="sxs-lookup"><span data-stu-id="12837-123">Create the database by using a larger database file size.</span></span> <span data-ttu-id="12837-124">Ridurre quindi il database se si desidera utilizzare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o l'istruzione DBCC SHRINKDATABASE.</span><span class="sxs-lookup"><span data-stu-id="12837-124">Then shrink the database if you want by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or the DBCC SHRINKDATABASE statement.</span></span>  
  
  
