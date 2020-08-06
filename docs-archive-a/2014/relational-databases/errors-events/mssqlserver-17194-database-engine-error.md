---
title: MSSQLSERVER_17194 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "17194"
helpviewer_keywords:
- 17194 (Database Engine error)
ms.assetid: 0d03eb20-28a7-4ceb-8903-7f9420a620f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3f56a104841c4825bba1f60b3588fadd63555c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627787"
---
# <a name="mssqlserver_17194"></a><span data-ttu-id="1ef35-102">MSSQLSERVER_17194</span><span class="sxs-lookup"><span data-stu-id="1ef35-102">MSSQLSERVER_17194</span></span>
    
## <a name="details"></a><span data-ttu-id="1ef35-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1ef35-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ef35-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="1ef35-104">Product Name</span></span>|<span data-ttu-id="1ef35-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ef35-105">SQL Server</span></span>|  
|<span data-ttu-id="1ef35-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="1ef35-106">Event ID</span></span>|<span data-ttu-id="1ef35-107">17194</span><span class="sxs-lookup"><span data-stu-id="1ef35-107">17194</span></span>|  
|<span data-ttu-id="1ef35-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="1ef35-108">Event Source</span></span>|<span data-ttu-id="1ef35-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1ef35-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1ef35-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1ef35-110">Component</span></span>|<span data-ttu-id="1ef35-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1ef35-111">SQLEngine</span></span>|  
|<span data-ttu-id="1ef35-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="1ef35-112">Symbolic Name</span></span>||  
|<span data-ttu-id="1ef35-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="1ef35-113">Message Text</span></span>|<span data-ttu-id="1ef35-114">Impossibile caricare la libreria di provider SSL necessaria per l'accesso. La connessione è stata chiusa.</span><span class="sxs-lookup"><span data-stu-id="1ef35-114">The server was unable to load the SSL provider library needed to log in; the connection has been closed.</span></span> <span data-ttu-id="1ef35-115">SSL viene utilizzato per crittografare la sequenza di accesso o tutte le comunicazioni, a seconda della configurazione del server.</span><span class="sxs-lookup"><span data-stu-id="1ef35-115">SSL is used to encrypt either the login sequence or all communications, depending on how the administrator has configured the server.</span></span> <span data-ttu-id="1ef35-116">Vedere la documentazione online per informazioni su questo messaggio di errore:  0xXXXX.</span><span class="sxs-lookup"><span data-stu-id="1ef35-116">See Books Online for information on this error message:  0xXXXX.</span></span> <span data-ttu-id="1ef35-117">[CLIENT: 11.11.11.11]</span><span class="sxs-lookup"><span data-stu-id="1ef35-117">[CLIENT: 11.11.11.11]</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1ef35-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="1ef35-118">Explanation</span></span>  
 <span data-ttu-id="1ef35-119">Questo errore indica che la connessione è stata chiusa dal client.</span><span class="sxs-lookup"><span data-stu-id="1ef35-119">This error indicates that the client has closed the connection.</span></span> <span data-ttu-id="1ef35-120">Questo errore potrebbe verificarsi poiché è scaduto il timeout della connessione.</span><span class="sxs-lookup"><span data-stu-id="1ef35-120">This error could occur because the connection time-out has expired.</span></span> <span data-ttu-id="1ef35-121">Nel messaggio di errore viene visualizzato un valore del sistema operativo che descrive il problema sottostante.</span><span class="sxs-lookup"><span data-stu-id="1ef35-121">The error message displays a value from the operating system that describes the underlying problem.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1ef35-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="1ef35-122">User Action</span></span>  
 <span data-ttu-id="1ef35-123">Se il codice di errore nel messaggio è 0x2746 (valore decimale 10054), la connessione è stata reimpostata dal client, in genere a causa di un timeout. Per risolvere l'errore, aumentare il timeout della connessione nel client o nel programma che esegue la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1ef35-123">If the error code in the message is 0x2746 (decimal value 10054), this means that the connection was reset by the client, typically because of a time-out. To resolve the error, increase the connection time-out on the client or calling program.</span></span>  
  
 <span data-ttu-id="1ef35-124">Per determinare una possibile soluzione per altri valori del messaggio di errore, usare il comando **net helpmsg** del sistema operativo e specificare il valore decimale del codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1ef35-124">To determine a possible solution for other error message values, use the operating system command **net helpmsg** and specify the decimal value of the error code.</span></span>  
  
 <span data-ttu-id="1ef35-125">Per altre informazioni sulla connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Configurazione di rete del server](../../database-engine/configure-windows/server-network-configuration.md) e [Configurazione di rete dei client](../../database-engine/configure-windows/client-network-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1ef35-125">For more information about how to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Server Network Configuration](../../database-engine/configure-windows/server-network-configuration.md) and [Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="1ef35-126">Solo interno</span><span class="sxs-lookup"><span data-stu-id="1ef35-126">Internal-Only</span></span>  
  
