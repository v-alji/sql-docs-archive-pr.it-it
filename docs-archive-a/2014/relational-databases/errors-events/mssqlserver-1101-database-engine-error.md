---
title: MSSQLSERVER_1101 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1101 (Database Engine error)
ms.assetid: d63b67d5-59f5-4f77-904e-5ba67f2dd850
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 631b0ab1466815cbacfd71b4f9fd714fabd0f7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636178"
---
# <a name="mssqlserver_1101"></a><span data-ttu-id="bc268-102">MSSQLSERVER_1101</span><span class="sxs-lookup"><span data-stu-id="bc268-102">MSSQLSERVER_1101</span></span>
    
## <a name="details"></a><span data-ttu-id="bc268-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bc268-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bc268-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="bc268-104">Product Name</span></span>|<span data-ttu-id="bc268-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc268-105">SQL Server</span></span>|  
|<span data-ttu-id="bc268-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="bc268-106">Event ID</span></span>|<span data-ttu-id="bc268-107">1101</span><span class="sxs-lookup"><span data-stu-id="bc268-107">1101</span></span>|  
|<span data-ttu-id="bc268-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="bc268-108">Event Source</span></span>|<span data-ttu-id="bc268-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bc268-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bc268-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bc268-110">Component</span></span>|<span data-ttu-id="bc268-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bc268-111">SQLEngine</span></span>|  
|<span data-ttu-id="bc268-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="bc268-112">Symbolic Name</span></span>|<span data-ttu-id="bc268-113">NOALLOCPG</span><span class="sxs-lookup"><span data-stu-id="bc268-113">NOALLOCPG</span></span>|  
|<span data-ttu-id="bc268-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="bc268-114">Message Text</span></span>|<span data-ttu-id="bc268-115">Impossibile allocare una nuova pagina per il database '%.\*ls' a causa di spazio su disco insufficiente nel filegroup '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="bc268-115">Could not allocate a new page for database '%.\*ls' because of insufficient disk space in filegroup '%.\*ls'.</span></span> <span data-ttu-id="bc268-116">Liberare lo spazio necessario eliminando oggetti dal filegroup, aggiungendo file al filegroup oppure attivando l'aumento automatico delle dimensioni per i file esistenti nel filegroup.</span><span class="sxs-lookup"><span data-stu-id="bc268-116">Create the necessary space by dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bc268-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="bc268-117">Explanation</span></span>  
 <span data-ttu-id="bc268-118">Nel filegroup indicato non vi è spazio disponibile su disco.</span><span class="sxs-lookup"><span data-stu-id="bc268-118">No disk space available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bc268-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="bc268-119">User Action</span></span>  
 <span data-ttu-id="bc268-120">Eseguire le azioni seguenti per tentare di liberare spazio sufficiente nel filegroup.</span><span class="sxs-lookup"><span data-stu-id="bc268-120">The following actions may make space available in the filegroup.</span></span>  
  
-   <span data-ttu-id="bc268-121">Attivare l'aumento automatico delle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="bc268-121">Turn on AUTOGROW.</span></span>  
  
-   <span data-ttu-id="bc268-122">Aggiungere altri file al gruppo di file.</span><span class="sxs-lookup"><span data-stu-id="bc268-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="bc268-123">Liberare spazio su disco eliminando indici o tabelle non necessari dal filegroup.</span><span class="sxs-lookup"><span data-stu-id="bc268-123">Free up disk space by dropping unnecessary indexes or tables in the filegroup.</span></span>  
  
  
