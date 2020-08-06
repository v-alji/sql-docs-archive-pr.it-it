---
title: MSSQLSERVER_4064 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4064 (Database Engine error)
ms.assetid: 32112b90-0a2f-4834-a027-756811732be7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 201098aadeb6bd091f0312532138f692ae8079b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636723"
---
# <a name="mssqlserver_4064"></a><span data-ttu-id="3a159-102">MSSQLSERVER_4064</span><span class="sxs-lookup"><span data-stu-id="3a159-102">MSSQLSERVER_4064</span></span>
    
## <a name="details"></a><span data-ttu-id="3a159-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3a159-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3a159-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="3a159-104">Product Name</span></span>|<span data-ttu-id="3a159-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3a159-105">SQL Server</span></span>|  
|<span data-ttu-id="3a159-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="3a159-106">Event ID</span></span>|<span data-ttu-id="3a159-107">4064</span><span class="sxs-lookup"><span data-stu-id="3a159-107">4064</span></span>|  
|<span data-ttu-id="3a159-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="3a159-108">Event Source</span></span>|<span data-ttu-id="3a159-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3a159-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3a159-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3a159-110">Component</span></span>|<span data-ttu-id="3a159-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3a159-111">SQLEngine</span></span>|  
|<span data-ttu-id="3a159-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="3a159-112">Symbolic Name</span></span>|<span data-ttu-id="3a159-113">DB_UFAIL_FATAL</span><span class="sxs-lookup"><span data-stu-id="3a159-113">DB_UFAIL_FATAL</span></span>|  
|<span data-ttu-id="3a159-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="3a159-114">Message Text</span></span>|<span data-ttu-id="3a159-115">Impossibile aprire il database utente predefinito.</span><span class="sxs-lookup"><span data-stu-id="3a159-115">Cannot open user default database.</span></span> <span data-ttu-id="3a159-116">Accesso non riuscito.</span><span class="sxs-lookup"><span data-stu-id="3a159-116">Login failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3a159-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="3a159-117">Explanation</span></span>  
 <span data-ttu-id="3a159-118">L'account di accesso di SQL Server non è in grado di connettersi a causa di un problema con il relativo database predefinito.</span><span class="sxs-lookup"><span data-stu-id="3a159-118">The SQL Server login was unable to connect because of a problem with its default database.</span></span> <span data-ttu-id="3a159-119">Il database non è valido oppure l'account di accesso non dispone dell'autorizzazione CONNECT per il database.</span><span class="sxs-lookup"><span data-stu-id="3a159-119">Either the database itself is invalid or the login lacks CONNECT permission on the database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3a159-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="3a159-120">User Action</span></span>  
 <span data-ttu-id="3a159-121">Utilizzare ALTER LOGIN per modificare il database predefinito dell'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="3a159-121">Use ALTER LOGIN to change the login's default database.</span></span> <span data-ttu-id="3a159-122">Concedere l'autorizzazione CONNECT all'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="3a159-122">Grant CONNECT permission to the login.</span></span>  
  
  
