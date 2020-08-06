---
title: MSSQLSERVER_11409 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 11409 (Database Engine error)
ms.assetid: 99b71a1c-a72d-4ca9-9d00-4230c9042ba5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4249e13a3530f69978c78f2e2ca6e4583eed46a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624243"
---
# <a name="mssqlserver_11409"></a><span data-ttu-id="6d483-102">MSSQLSERVER_11409</span><span class="sxs-lookup"><span data-stu-id="6d483-102">MSSQLSERVER_11409</span></span>
    
## <a name="details"></a><span data-ttu-id="6d483-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6d483-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6d483-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="6d483-104">Product Name</span></span>|<span data-ttu-id="6d483-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6d483-105">SQL Server</span></span>|  
|<span data-ttu-id="6d483-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="6d483-106">Event ID</span></span>|<span data-ttu-id="6d483-107">11409</span><span class="sxs-lookup"><span data-stu-id="6d483-107">11409</span></span>|  
|<span data-ttu-id="6d483-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="6d483-108">Event Source</span></span>|<span data-ttu-id="6d483-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6d483-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6d483-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6d483-110">Component</span></span>|<span data-ttu-id="6d483-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6d483-111">SQLEngine</span></span>|  
|<span data-ttu-id="6d483-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="6d483-112">Symbolic Name</span></span>|<span data-ttu-id="6d483-113">ALTERCOL_COLSET_DROP</span><span class="sxs-lookup"><span data-stu-id="6d483-113">ALTERCOL_COLSET_DROP</span></span>|  
|<span data-ttu-id="6d483-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="6d483-114">Message Text</span></span>|<span data-ttu-id="6d483-115">Impossibile eliminare il set di colonne '%.\*ls' nella tabella '%.\*ls' poiché la tabella contiene più di 1025 colonne.</span><span class="sxs-lookup"><span data-stu-id="6d483-115">Cannot drop column set '%.\*ls' in table '%.\*ls' because the table contains more than 1025 columns.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6d483-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="6d483-116">Explanation</span></span>  
 <span data-ttu-id="6d483-117">Le tabelle possono contenere un massimo di 1024 colonne non definite come colonne di tipo sparse o calcolate.</span><span class="sxs-lookup"><span data-stu-id="6d483-117">Tables can contain a maximum of 1024 columns that are not designated as sparse, or computed.</span></span> <span data-ttu-id="6d483-118">Quando le colonne di tipo sparse provocano il superamento di 1024 colonne nella tabella, è necessario definire un set di colonne per la tabella.</span><span class="sxs-lookup"><span data-stu-id="6d483-118">When sparse columns cause the table to exceed 1024 columns, a column set must be defined for the table.</span></span> <span data-ttu-id="6d483-119">Nella tabella cui viene fatto riferimento sono contenute più di 1024 colonne ed è stato effettuato un tentativo di rimuovere il set di colonne.</span><span class="sxs-lookup"><span data-stu-id="6d483-119">The table referenced has more than 1024 columns and you have attempted to remove the column set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6d483-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="6d483-120">User Action</span></span>  
 <span data-ttu-id="6d483-121">È necessario mantenere il set di colonne con le colonne correnti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="6d483-121">With the current columns in the table, you must retain the column set.</span></span>  
  
 <span data-ttu-id="6d483-122">Per rimuovere il set di colonne, rimuovere innanzitutto le colonne dalla tabella fino a quando il relativo numero non supera 1024,</span><span class="sxs-lookup"><span data-stu-id="6d483-122">To remove the column set, first remove columns from the table, until you have no more than 1024 columns.</span></span> <span data-ttu-id="6d483-123">quindi rimuovere il set di colonne.</span><span class="sxs-lookup"><span data-stu-id="6d483-123">Then, you can remove the column set.</span></span>  
  
  
