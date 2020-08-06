---
title: MSSQLSERVER_15661 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15661 (Database Engine error)
ms.assetid: 88b01bfb-74ce-4aa0-aec0-7885261c7ef3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 966e23e8d970c36eba81253228cc18ed4af3ff77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623310"
---
# <a name="mssqlserver_15661"></a><span data-ttu-id="72120-102">MSSQLSERVER_15661</span><span class="sxs-lookup"><span data-stu-id="72120-102">MSSQLSERVER_15661</span></span>
    
## <a name="details"></a><span data-ttu-id="72120-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="72120-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="72120-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="72120-104">Product Name</span></span>|<span data-ttu-id="72120-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="72120-105">SQL Server</span></span>|  
|<span data-ttu-id="72120-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="72120-106">Event ID</span></span>|<span data-ttu-id="72120-107">15661</span><span class="sxs-lookup"><span data-stu-id="72120-107">15661</span></span>|  
|<span data-ttu-id="72120-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="72120-108">Event Source</span></span>|<span data-ttu-id="72120-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="72120-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="72120-110">Componente</span><span class="sxs-lookup"><span data-stu-id="72120-110">Component</span></span>|<span data-ttu-id="72120-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="72120-111">SQLEngine</span></span>|  
|<span data-ttu-id="72120-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="72120-112">Symbolic Name</span></span>|<span data-ttu-id="72120-113">SQLErrorNum15661</span><span class="sxs-lookup"><span data-stu-id="72120-113">SQLErrorNum15661</span></span>|  
|<span data-ttu-id="72120-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="72120-114">Message Text</span></span>|<span data-ttu-id="72120-115">Impossibile utilizzare la stored procedure sp_estimate_data_compression_savings per le tabelle temporanee.</span><span class="sxs-lookup"><span data-stu-id="72120-115">The sp_estimate_data_compression_savings stored procedure cannot be used for temporary tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="72120-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="72120-116">Explanation</span></span>  
 <span data-ttu-id="72120-117">Una tabella temporanea è stata usata come argomento per la stored procedure sp_estimate_data_compression_savings.</span><span class="sxs-lookup"><span data-stu-id="72120-117">A temporary table was used as an argument for the sp_estimate_data_compression_savings stored procedure.</span></span> <span data-ttu-id="72120-118">Sebbene la compressione delle tabelle temporanee sia supportata, non è possibile usare sp_estimate_data_compression_savings per stimare il risparmio in caso di compressione.</span><span class="sxs-lookup"><span data-stu-id="72120-118">Although the compression of temporary tables is supported, you cannot use sp_estimate_data_compression_savings to estimate the compression savings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="72120-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="72120-119">User Action</span></span>  
 <span data-ttu-id="72120-120">Rimuovere la tabella temporanea come argomento per sp_estimate_data_compression_savings.</span><span class="sxs-lookup"><span data-stu-id="72120-120">Remove the temporary table as an argument for sp_estimate_data_compression_savings.</span></span>  
  
  
