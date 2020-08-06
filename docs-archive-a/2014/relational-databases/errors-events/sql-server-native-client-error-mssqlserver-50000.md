---
title: MSSQLSERVER_50000 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: reference
helpviewer_keywords:
- 50000 [SQL Server Native Client setup error]
ms.assetid: 5426d87a-d5d9-4984-b211-b07d69e834a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cc805042bff7259a311ca3f2acf4c26db59381b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716364"
---
# <a name="mssqlserver_50000"></a><span data-ttu-id="7faaa-102">MSSQLSERVER_50000</span><span class="sxs-lookup"><span data-stu-id="7faaa-102">MSSQLSERVER_50000</span></span>
    
## <a name="details"></a><span data-ttu-id="7faaa-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7faaa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7faaa-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="7faaa-104">Product Name</span></span>|<span data-ttu-id="7faaa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7faaa-105">SQL Server</span></span>|  
|<span data-ttu-id="7faaa-106">Versione prodotto</span><span class="sxs-lookup"><span data-stu-id="7faaa-106">Product Version</span></span>|<span data-ttu-id="7faaa-107">11.0</span><span class="sxs-lookup"><span data-stu-id="7faaa-107">11.0</span></span>|  
|<span data-ttu-id="7faaa-108">ID evento</span><span class="sxs-lookup"><span data-stu-id="7faaa-108">Event ID</span></span>|<span data-ttu-id="7faaa-109">50000</span><span class="sxs-lookup"><span data-stu-id="7faaa-109">50000</span></span>|  
|<span data-ttu-id="7faaa-110">Origine evento</span><span class="sxs-lookup"><span data-stu-id="7faaa-110">Event Source</span></span>|<span data-ttu-id="7faaa-111">SETUP</span><span class="sxs-lookup"><span data-stu-id="7faaa-111">SETUP</span></span>|  
|<span data-ttu-id="7faaa-112">Componente</span><span class="sxs-lookup"><span data-stu-id="7faaa-112">Component</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7faaa-113">Native Client</span><span class="sxs-lookup"><span data-stu-id="7faaa-113">Native Client</span></span>|  
|<span data-ttu-id="7faaa-114">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="7faaa-114">Symbolic Name</span></span>||  
|<span data-ttu-id="7faaa-115">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="7faaa-115">Message Text</span></span>|<span data-ttu-id="7faaa-116">Errore di rete durante il tentativo di lettura dal file '%. \* ls.'</span><span class="sxs-lookup"><span data-stu-id="7faaa-116">A network error occurred while attempting to read from the file '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7faaa-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="7faaa-117">Explanation</span></span>  
 <span data-ttu-id="7faaa-118">È stato eseguito il tentativo di installare (o aggiornare) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client in un computer in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client è già stato installato da un file MSI che è stato rinominato da sqlncli.msi.</span><span class="sxs-lookup"><span data-stu-id="7faaa-118">An attempt was made to install (or update) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client on a computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is already installed, and where the existing installation was from an MSI file that was renamed from sqlncli.msi.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7faaa-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7faaa-119">User Action</span></span>  
 <span data-ttu-id="7faaa-120">Per risolvere il problema, disinstallare la versione esistente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="7faaa-120">To resolve this error, uninstall the existing version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="7faaa-121">Per prevenire questo errore, non installare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client da un file MSI non denominato sqlncli.msi.</span><span class="sxs-lookup"><span data-stu-id="7faaa-121">To prevent this error, do not install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client from an MSI file that is not named sqlncli.msi.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="7faaa-122">Solo interno</span><span class="sxs-lookup"><span data-stu-id="7faaa-122">Internal-Only</span></span>  
  
