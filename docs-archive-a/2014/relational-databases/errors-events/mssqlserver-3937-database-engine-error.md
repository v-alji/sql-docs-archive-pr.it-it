---
title: MSSQLSERVER_3937 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3937 (Database Engine error)
ms.assetid: 312d5bbe-c8de-42db-af4b-4ccb448ce6ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac466e6eb50ad4b7a8848a1159963cb0fd35e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715307"
---
# <a name="mssqlserver_3937"></a><span data-ttu-id="f4419-102">MSSQLSERVER_3937</span><span class="sxs-lookup"><span data-stu-id="f4419-102">MSSQLSERVER_3937</span></span>
    
## <a name="details"></a><span data-ttu-id="f4419-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f4419-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4419-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f4419-104">Product Name</span></span>|<span data-ttu-id="f4419-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f4419-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f4419-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f4419-106">Event ID</span></span>|<span data-ttu-id="f4419-107">3937</span><span class="sxs-lookup"><span data-stu-id="f4419-107">3937</span></span>|  
|<span data-ttu-id="f4419-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f4419-108">Event Source</span></span>|<span data-ttu-id="f4419-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f4419-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f4419-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f4419-110">Component</span></span>|<span data-ttu-id="f4419-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f4419-111">SQLEngine</span></span>|  
|<span data-ttu-id="f4419-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f4419-112">Symbolic Name</span></span>|<span data-ttu-id="f4419-113">XACT_FILESTREAM_ROLLBACK_ERROR</span><span class="sxs-lookup"><span data-stu-id="f4419-113">XACT_FILESTREAM_ROLLBACK_ERROR</span></span>|  
|<span data-ttu-id="f4419-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f4419-114">Message Text</span></span>|<span data-ttu-id="f4419-115">Durante il rollback di una transazione, si è verificato un errore nel tentativo di notificare l'esecuzione del rollback di una transazione al driver del filtro FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="f4419-115">An error occurred while trying to notify the FILESTREAM filter driver that a transaction was rolled back.</span></span> <span data-ttu-id="f4419-116">Codice errore: 0x%0x.</span><span class="sxs-lookup"><span data-stu-id="f4419-116">Error code: 0x%0x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f4419-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f4419-117">Explanation</span></span>  
 <span data-ttu-id="f4419-118">Durante l'invio di una notifica di esecuzione del rollback di una transazione, è stato restituito un errore dal driver RsFx,</span><span class="sxs-lookup"><span data-stu-id="f4419-118">An error was returned by the RsFx driver when issuing a rollback notification for a transaction.</span></span> <span data-ttu-id="f4419-119">probabilmente a causa di risorse insufficienti.</span><span class="sxs-lookup"><span data-stu-id="f4419-119">This is probably caused by a resource shortage.</span></span> <span data-ttu-id="f4419-120">Questa situazione potrebbe provocare una piccola perdita di memoria nel driver del filtro RsFx, in cui tuttavia verrà liberato spazio quando il processo sqlservr.exe che creato la transazione termina.</span><span class="sxs-lookup"><span data-stu-id="f4419-120">This can cause a small memory leak in the RsFx filter driver, but this will be freed when the sqlservr.exe process that created the transaction exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f4419-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f4419-121">User Action</span></span>  
  
