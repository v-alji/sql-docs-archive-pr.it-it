---
title: MSSQLSERVER_3151 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3151 (Database Engine error)
ms.assetid: a8657a91-ec75-4649-a09a-21920e0030ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34414754ea9d25ad89f6aba767197eb1dfc10d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628734"
---
# <a name="mssqlserver_3151"></a><span data-ttu-id="a3bed-102">MSSQLSERVER_3151</span><span class="sxs-lookup"><span data-stu-id="a3bed-102">MSSQLSERVER_3151</span></span>
    
## <a name="details"></a><span data-ttu-id="a3bed-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a3bed-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3bed-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="a3bed-104">Product Name</span></span>|<span data-ttu-id="a3bed-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3bed-105">SQL Server</span></span>|  
|<span data-ttu-id="a3bed-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="a3bed-106">Event ID</span></span>|<span data-ttu-id="a3bed-107">3151</span><span class="sxs-lookup"><span data-stu-id="a3bed-107">3151</span></span>|  
|<span data-ttu-id="a3bed-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="a3bed-108">Event Source</span></span>|<span data-ttu-id="a3bed-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a3bed-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a3bed-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a3bed-110">Component</span></span>|<span data-ttu-id="a3bed-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a3bed-111">SQLEngine</span></span>|  
|<span data-ttu-id="a3bed-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="a3bed-112">Symbolic Name</span></span>|<span data-ttu-id="a3bed-113">LDDB_MASTER_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="a3bed-113">LDDB_MASTER_LOAD_FAILED</span></span>|  
|<span data-ttu-id="a3bed-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a3bed-114">Message Text</span></span>|<span data-ttu-id="a3bed-115">Impossibile ripristinare il database master.</span><span class="sxs-lookup"><span data-stu-id="a3bed-115">Failed to restore master database.</span></span> <span data-ttu-id="a3bed-116">SQL Server verrà chiuso.</span><span class="sxs-lookup"><span data-stu-id="a3bed-116">Shutting down SQL Server.</span></span> <span data-ttu-id="a3bed-117">Controllare i log degli errori e ricompilare il database master.</span><span class="sxs-lookup"><span data-stu-id="a3bed-117">Check the error logs, and rebuild the master database.</span></span> <span data-ttu-id="a3bed-118">Per ulteriori informazioni sulla ricompilazione del database master, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a3bed-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3bed-119">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a3bed-119">Explanation</span></span>  
 <span data-ttu-id="a3bed-120">Si tratta di un messaggio di errore generale che indica vari problemi relativi al database **master**.</span><span class="sxs-lookup"><span data-stu-id="a3bed-120">This is a general error message indicating various problems with the **master** database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3bed-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="a3bed-121">User Action</span></span>  
 <span data-ttu-id="a3bed-122">Per ulteriori informazioni esaminare i log degli errori.</span><span class="sxs-lookup"><span data-stu-id="a3bed-122">Check the error logs for more information.</span></span> <span data-ttu-id="a3bed-123">Per creare un database **master** utilizzabile, eseguire Setup.exe con l'opzione REBUILDDATABASE.</span><span class="sxs-lookup"><span data-stu-id="a3bed-123">To create a usable **master** database, run Setup.exe with the REBUILDDATABASE option.</span></span> <span data-ttu-id="a3bed-124">Per altre informazioni, vedere "Procedura: Installare SQL Server dal prompt dei comandi" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a3bed-124">For more information see "How to: Install SQL Server from the Command Prompt" in SQL Server Books Online.</span></span>  
  
  
