---
title: Configurazione di motore di database-FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], about FILESTREAM
ms.assetid: 641a10a1-ae52-4d26-8f1c-a032a4aeff02
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab12b507246a3e13ac59be213813604d531d9a28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720897"
---
# <a name="database-engine-configuration---filestream"></a><span data-ttu-id="29b3c-102">Configurazione del Motore di database - Filestream</span><span class="sxs-lookup"><span data-stu-id="29b3c-102">Database Engine Configuration - Filestream</span></span>
  <span data-ttu-id="29b3c-103">Utilizzare questa pagina per abilitare FILESTREAM per l'installazione corrente di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29b3c-103">Use this page to enable FILESTREAM for this installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="29b3c-104">FILESTREAM integra [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] con un file system NTFS archiviando `varbinary(max)` dati BLOB (Binary Large Object) come file nel file System.</span><span class="sxs-lookup"><span data-stu-id="29b3c-104">FILESTREAM integrates the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with an NTFS file system by storing `varbinary(max)` binary large object (BLOB) data as files on the file system.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="29b3c-105">offre istruzioni che consentono di inserire, aggiornare ed eseguire query, ricerche e back up dei dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="29b3c-105">statements can insert, update, query, search, and back up FILESTREAM data.</span></span> <span data-ttu-id="29b3c-106">Le interfacce del file system Win32 forniscono accesso ai dati tramite flusso.</span><span class="sxs-lookup"><span data-stu-id="29b3c-106">Win32 file system interfaces provide streaming access to the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="29b3c-107">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="29b3c-107">UI element list</span></span>  
 <span data-ttu-id="29b3c-108">**Abilita FILESTREAM per l'accesso Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="29b3c-108">**Enable FILESTREAM for Transact-SQL access**</span></span>  
 <span data-ttu-id="29b3c-109">Selezionare questa opzione per abilitare FILESTREAM per l'accesso [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29b3c-109">Select to enable FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="29b3c-110">È necessario che questo controllo sia selezionato affinché le altre opzioni di controllo siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="29b3c-110">This control must be checked before the other control options will be available.</span></span>  
  
 <span data-ttu-id="29b3c-111">**Abilita FILESTREAM per l'accesso tramite il flusso di I/O dei file**</span><span class="sxs-lookup"><span data-stu-id="29b3c-111">**Enable FILESTREAM for file I/O streaming access**</span></span>  
 <span data-ttu-id="29b3c-112">Selezionare questa opzione per abilitare l'accesso tramite flusso Win32 per FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="29b3c-112">Select to enable Win32 streaming access for FILESTREAM.</span></span>  
  
 <span data-ttu-id="29b3c-113">**Nome condivisione di Windows**</span><span class="sxs-lookup"><span data-stu-id="29b3c-113">**Windows share name**</span></span>  
 <span data-ttu-id="29b3c-114">Utilizzare questo controllo per immettere il nome della condivisione di Windows in cui verranno archiviati i dati FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="29b3c-114">Use this control to enter the name of the Windows share in which the FILESTREAM data will be stored.</span></span>  
  
 <span data-ttu-id="29b3c-115">**Consenti ai client remoti l'accesso tramite flusso ai dati FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="29b3c-115">**Allow remote clients to have streaming access to FILESTREAM data**</span></span>  
 <span data-ttu-id="29b3c-116">Selezionare questo controllo per consentire ai client remoti di accedere ai dati FILESTREAM nel server corrente.</span><span class="sxs-lookup"><span data-stu-id="29b3c-116">Select this control to allow remote clients to access this FILESTREAM data on this server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b3c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29b3c-117">See Also</span></span>  
 <span data-ttu-id="29b3c-118">[Abilitare e configurare FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="29b3c-118">[Enable and Configure FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="29b3c-119">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="29b3c-119">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
