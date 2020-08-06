---
title: MSSQLSERVER_21862 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21862 (Database Engine error)
ms.assetid: a1d393dd-453b-4d45-9aa5-7d371213e32b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b945350d9c7a862d4274f464afbd7fc5472f732c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715335"
---
# <a name="mssqlserver_21862"></a><span data-ttu-id="a3c0c-102">MSSQLSERVER_21862</span><span class="sxs-lookup"><span data-stu-id="a3c0c-102">MSSQLSERVER_21862</span></span>
    
## <a name="details"></a><span data-ttu-id="a3c0c-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a3c0c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3c0c-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="a3c0c-104">Product Name</span></span>|<span data-ttu-id="a3c0c-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a3c0c-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a3c0c-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="a3c0c-106">Event ID</span></span>|<span data-ttu-id="a3c0c-107">21862</span><span class="sxs-lookup"><span data-stu-id="a3c0c-107">21862</span></span>|  
|<span data-ttu-id="a3c0c-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="a3c0c-108">Event Source</span></span>|<span data-ttu-id="a3c0c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a3c0c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a3c0c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a3c0c-110">Component</span></span>|<span data-ttu-id="a3c0c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a3c0c-111">SQLEngine</span></span>|  
|<span data-ttu-id="a3c0c-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="a3c0c-112">Symbolic Name</span></span>|<span data-ttu-id="a3c0c-113">SQLErrorNum21862</span><span class="sxs-lookup"><span data-stu-id="a3c0c-113">SQLErrorNum21862</span></span>|  
|<span data-ttu-id="a3c0c-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a3c0c-114">Message Text</span></span>|<span data-ttu-id="a3c0c-115">Impossibile pubblicare le colonne FILESTREAM in una pubblicazione con metodo di sincronizzazione 'database snapshot' o 'database snapshot character'.</span><span class="sxs-lookup"><span data-stu-id="a3c0c-115">FILESTREAM columns cannot be published in a publication by using a synchronization method of either 'database snapshot' or 'database snapshot character'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3c0c-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a3c0c-116">Explanation</span></span>  
 <span data-ttu-id="a3c0c-117">Poiché non è possibile accedere ai dati FILESTREAM tramite uno snapshot del database, l'agente snapshot non sarà in grado di leggere dati FILESTREAM se viene specificato il parametro *database snapshot* o *database_snapshot_character* per il metodo di sincronizzazione della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="a3c0c-117">Because FILESTREAM data cannot be accessed through a database snapshot, the snapshot agent will be unable to read FILESTREAM data when either the *database snapshot* or *database_snapshot_character* parameter is specified for the synchronization method of the publication.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3c0c-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="a3c0c-118">User Action</span></span>  
 <span data-ttu-id="a3c0c-119">Impostare il metodo di sincronizzazione di pubblicazione su un valore diverso da *database snapshot* o *database_snapshot_character* oppure escludere la colonna FILESTREAM dalla pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="a3c0c-119">Change the publication synchronization method to something other than *database snapshot* or *database_snapshot_character*, or just exclude the FILESTREAM column from the publication.</span></span>  
  
  
