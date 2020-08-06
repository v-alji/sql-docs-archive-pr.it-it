---
title: MSSQLSERVER_17053 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17053 (Database Engine error)
ms.assetid: e0a01f3d-d0aa-4c38-8bcc-82e59de50512
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 11137ba334b66f20c7d9a6caaaf7d1ef42c15dec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623309"
---
# <a name="mssqlserver_17053"></a><span data-ttu-id="5e07a-102">MSSQLSERVER_17053</span><span class="sxs-lookup"><span data-stu-id="5e07a-102">MSSQLSERVER_17053</span></span>
    
## <a name="details"></a><span data-ttu-id="5e07a-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5e07a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e07a-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="5e07a-104">Product Name</span></span>|<span data-ttu-id="5e07a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5e07a-105">SQL Server</span></span>|  
|<span data-ttu-id="5e07a-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="5e07a-106">Event ID</span></span>|<span data-ttu-id="5e07a-107">17053</span><span class="sxs-lookup"><span data-stu-id="5e07a-107">17053</span></span>|  
|<span data-ttu-id="5e07a-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="5e07a-108">Event Source</span></span>|<span data-ttu-id="5e07a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5e07a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5e07a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5e07a-110">Component</span></span>|<span data-ttu-id="5e07a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5e07a-111">SQLEngine</span></span>|  
|<span data-ttu-id="5e07a-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="5e07a-112">Symbolic Name</span></span>|<span data-ttu-id="5e07a-113">OS_ERROR</span><span class="sxs-lookup"><span data-stu-id="5e07a-113">OS_ERROR</span></span>|  
|<span data-ttu-id="5e07a-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5e07a-114">Message Text</span></span>|<span data-ttu-id="5e07a-115">%ls: Errore del sistema operativo %ls.</span><span class="sxs-lookup"><span data-stu-id="5e07a-115">%ls: Operating system error %ls encountered.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5e07a-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5e07a-116">Explanation</span></span>  
 <span data-ttu-id="5e07a-117">Si è verificato un errore del sistema operativo generico.</span><span class="sxs-lookup"><span data-stu-id="5e07a-117">Generic operating system error occurred.</span></span>  <span data-ttu-id="5e07a-118">Lo stato risultante non è chiaro.</span><span class="sxs-lookup"><span data-stu-id="5e07a-118">Not clear what the resulting state is.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5e07a-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="5e07a-119">User Action</span></span>  
 <span data-ttu-id="5e07a-120">In genere questo errore si verifica con altri errori e deve essere utilizzato per consentire di diagnosticare gli errori specifici.</span><span class="sxs-lookup"><span data-stu-id="5e07a-120">Usually this is in conjunction with some other error and should be used to help diagnose that failure.</span></span> <span data-ttu-id="5e07a-121">Alcuni esempi potrebbero essere costituiti da letture o scritture in file di dati o di log non eseguite in modo corretto, da operazioni di lettura o scrittura nel Registro di sistema o da altri errori relativi all'API Win32 non previsti.</span><span class="sxs-lookup"><span data-stu-id="5e07a-121">Examples would include reads or writes to data or log files that fail, registry read/write operations, or other unexpected Win32API failures.</span></span>  
  
  
