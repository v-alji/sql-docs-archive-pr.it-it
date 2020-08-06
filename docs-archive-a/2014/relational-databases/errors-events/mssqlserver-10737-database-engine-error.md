---
title: MSSQLSERVER_10737 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10737 (Database Engine error)
ms.assetid: 208af6ed-b271-4ab8-803e-7666025385c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: df8a4de014552d3aca00b3eb244f7ff8df56756b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635652"
---
# <a name="mssqlserver_10737"></a><span data-ttu-id="4019d-102">MSSQLSERVER_10737</span><span class="sxs-lookup"><span data-stu-id="4019d-102">MSSQLSERVER_10737</span></span>
    
## <a name="details"></a><span data-ttu-id="4019d-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4019d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4019d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="4019d-104">Product Name</span></span>|<span data-ttu-id="4019d-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4019d-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4019d-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="4019d-106">Event ID</span></span>|<span data-ttu-id="4019d-107">10737</span><span class="sxs-lookup"><span data-stu-id="4019d-107">10737</span></span>|  
|<span data-ttu-id="4019d-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="4019d-108">Event Source</span></span>|<span data-ttu-id="4019d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4019d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4019d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4019d-110">Component</span></span>|<span data-ttu-id="4019d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4019d-111">SQLEngine</span></span>|  
|<span data-ttu-id="4019d-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="4019d-112">Symbolic Name</span></span>|<span data-ttu-id="4019d-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span><span class="sxs-lookup"><span data-stu-id="4019d-113">REBUILD_PARTITION_ALL_NOT_SPECIFIED</span></span>|  
|<span data-ttu-id="4019d-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="4019d-114">Message Text</span></span>|<span data-ttu-id="4019d-115">Quando in un'istruzione ALTER TABLE REBUILD o ALTER INDEX REBUILD si specifica una partizione in una clausola DATA_COMPRESSION, è necessario specificare PARTITION=ALL.</span><span class="sxs-lookup"><span data-stu-id="4019d-115">In an ALTER TABLE REBUILD or ALTER INDEX REBUILD statement, when a partition is specified in a DATA_COMPRESSION clause, PARTITION=ALL must be specified.</span></span> <span data-ttu-id="4019d-116">La clausola PARTITION=ALL viene utilizzata per ribadire che tutte le partizioni della tabella o dell'indice verranno ricompilate anche se nella clausola DATA_COMPRESSION viene specificato un solo subset.</span><span class="sxs-lookup"><span data-stu-id="4019d-116">The PARTITION=ALL clause is used to reinforce that all partitions of the table or index will be rebuilt, even if only a subset is specified in the DATA_COMPRESSION clause.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="4019d-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="4019d-117">User Action</span></span>  
 <span data-ttu-id="4019d-118">Aggiungere la clausola PARTITION=ALL all'istruzione ALTER TABLE o ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="4019d-118">Add the PARTITION=ALL clause to the ALTER TABLE or ALTER INDEX statement.</span></span> <span data-ttu-id="4019d-119">In alternativa, per ricompilare una partizione specifica, usare REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).</span><span class="sxs-lookup"><span data-stu-id="4019d-119">Or, to rebuild a specific partition, use REBUILD PARTITION = \<partition-number-expr> WITH (DATA_COMPRESSION={ON | OFF}).</span></span>  
  
  
