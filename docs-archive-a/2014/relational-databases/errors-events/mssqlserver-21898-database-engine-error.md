---
title: MSSQLSERVER_21898 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21898 (Database Engine error)
ms.assetid: 02405b21-3d4e-4c2d-b4b3-d7b1ec05edb4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 78ce7eacf7f026bf9977af2c367b954a3639b357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715324"
---
# <a name="mssqlserver_21898"></a><span data-ttu-id="4c01a-102">MSSQLSERVER_21898</span><span class="sxs-lookup"><span data-stu-id="4c01a-102">MSSQLSERVER_21898</span></span>
    
## <a name="details"></a><span data-ttu-id="4c01a-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="4c01a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4c01a-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="4c01a-104">Product Name</span></span>|<span data-ttu-id="4c01a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4c01a-105">SQL Server</span></span>|  
|<span data-ttu-id="4c01a-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="4c01a-106">Event ID</span></span>|<span data-ttu-id="4c01a-107">21898</span><span class="sxs-lookup"><span data-stu-id="4c01a-107">21898</span></span>|  
|<span data-ttu-id="4c01a-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="4c01a-108">Event Source</span></span>|<span data-ttu-id="4c01a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4c01a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4c01a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4c01a-110">Component</span></span>|<span data-ttu-id="4c01a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4c01a-111">SQLEngine</span></span>|  
|<span data-ttu-id="4c01a-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="4c01a-112">Symbolic Name</span></span>|<span data-ttu-id="4c01a-113">SQLErrorNum21898</span><span class="sxs-lookup"><span data-stu-id="4c01a-113">SQLErrorNum21898</span></span>|  
|<span data-ttu-id="4c01a-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="4c01a-114">Message Text</span></span>|<span data-ttu-id="4c01a-115">Il server di pubblicazione '%s' utilizza il database di distribuzione '%s' e non '%s' che è richiesto per ospitare il database di pubblicazione '%s.'</span><span class="sxs-lookup"><span data-stu-id="4c01a-115">The publisher '%s' uses distribution database '%s' and not '%s' which is required in order to host the publishing database '%s'.</span></span> <span data-ttu-id="4c01a-116">Eseguire `sp_changedistpublisher` sul database di distribuzione '%s' per modificare il database di distribuzione utilizzato dal server di pubblicazione in '%s'.</span><span class="sxs-lookup"><span data-stu-id="4c01a-116">Run `sp_changedistpublisher` at distributor '%s' to change the distribution database used by the publisher to '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4c01a-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="4c01a-117">Explanation</span></span>  
 <span data-ttu-id="4c01a-118">`sp_validate_redirected_publisher`In  viene eseguita una query su msdb.dbo.MSdistpublishers sul database di distribuzione locale per verificare che il database di distribuzione utilizzato dal nuovo server di pubblicazione sia uguale a quello utilizzato dal server di pubblicazione originale.</span><span class="sxs-lookup"><span data-stu-id="4c01a-118">`sp_validate_redirected_publisher` queries msdb.dbo.MSdistpublishers at the local distributor to verify that the distribution database used by the new publisher is the same as the distribution database used by the original publisher.</span></span> <span data-ttu-id="4c01a-119">Questo errore viene restituito quando questi database sono diversi, rendendo il server di pubblicazione un host non adatto al database del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="4c01a-119">This error is returned when these databases are different, making the publisher an unsuitable host for the publisher database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4c01a-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="4c01a-120">User Action</span></span>  
 <span data-ttu-id="4c01a-121">Eseguire la stored procedure `sp_changedistpublisher` per modificare il database di distribuzione per il nuovo server di pubblicazione utilizzato dal server di pubblicazione originale.</span><span class="sxs-lookup"><span data-stu-id="4c01a-121">Execute stored procedure `sp_changedistpublisher` to change the distribution database for the new publisher to that used by the original publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c01a-122">Con l'esecuzione di `sp_changedistpublisher` il problema verrà indirizzato se è stato immesso il database di distribuzione errato durante l'esecuzione di `sp_adddistpublisher` sul database di distribuzione per il server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="4c01a-122">Running `sp_changedistpublisher` will address the problem if the wrong distribution database was entered when `sp_adddistpublisher` was run at the distributor for the publisher.</span></span> <span data-ttu-id="4c01a-123">Tuttavia, se il server di pubblicazione remoto dispone di pubblicazioni esistenti di un altro database di pubblicazione che utilizza il database di distribuzione identificato, questa modifica non è adatta.</span><span class="sxs-lookup"><span data-stu-id="4c01a-123">However, if the remote publisher has existing publications from another publishing database that make use of the identified distribution database, this change is not appropriate.</span></span> <span data-ttu-id="4c01a-124">La replica con il database di distribuzione denominato deve essere rimossa sistematicamente e quindi ristabilita usando il database di distribuzione del server di pubblicazione originale affinché il nuovo server di pubblicazione funzioni come un host adatto.</span><span class="sxs-lookup"><span data-stu-id="4c01a-124">Replication using the named distribution database needs to be systematically removed and then reestablished using the original publisher's distribution database in order for the new publisher to function as a suitable host.</span></span>  
  
  
