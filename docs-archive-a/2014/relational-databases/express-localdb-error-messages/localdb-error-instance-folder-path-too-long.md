---
title: LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c178a308-8d99-47fc-8a49-5a480dc592f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 32ae8ebe102008d08a6059328ed57cd118ece019
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637341"
---
# <a name="localdb_error_instance_folder_path_too_long"></a><span data-ttu-id="ad735-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span><span class="sxs-lookup"><span data-stu-id="ad735-102">LOCALDB_ERROR_INSTANCE_FOLDER_PATH_TOO_LONG</span></span>
    
## <a name="details"></a><span data-ttu-id="ad735-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ad735-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ad735-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="ad735-104">Product Name</span></span>|<span data-ttu-id="ad735-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ad735-105">SQL Server</span></span>|  
|<span data-ttu-id="ad735-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="ad735-106">Event ID</span></span>|<span data-ttu-id="ad735-107">260</span><span class="sxs-lookup"><span data-stu-id="ad735-107">260</span></span>|  
|<span data-ttu-id="ad735-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="ad735-108">Event Source</span></span>|<span data-ttu-id="ad735-109">Runtime database locale di SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="ad735-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="ad735-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ad735-110">Component</span></span>|<span data-ttu-id="ad735-111">API di Runtime database locale</span><span class="sxs-lookup"><span data-stu-id="ad735-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="ad735-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="ad735-112">Message Text</span></span>|<span data-ttu-id="ad735-113">La lunghezza del percorso completo della cartella di istanze del database locale è superiore a MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="ad735-113">The full path length of the Local Database instance folder is longer than MAX_PATH.</span></span> <span data-ttu-id="ad735-114">L'istanza deve essere archiviata nella cartella:%% LOCALAPPDATA%% \ Microsoft\Microsoft SQL Server Local DB\Instances \\<nome istanza \> .</span><span class="sxs-lookup"><span data-stu-id="ad735-114">The instance must be stored in folder: %%LOCALAPPDATA%%\Microsoft\Microsoft SQL Server Local DB\Instances\\<instance name\>.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ad735-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="ad735-115">Explanation</span></span>  
 <span data-ttu-id="ad735-116">Percorso di archiviazione richiesto per l'istanza più lungo di MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="ad735-116">The path where the instance should be stored is longer than MAX_PATH.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ad735-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="ad735-117">User Action</span></span>  
 <span data-ttu-id="ad735-118">Creare un nuovo percorso più corto di MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="ad735-118">Create a new path that is shorter than MAX_PATH.</span></span>  
  
  
