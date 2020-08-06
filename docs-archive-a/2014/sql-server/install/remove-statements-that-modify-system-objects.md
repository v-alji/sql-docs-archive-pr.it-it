---
title: Rimuovere istruzioni che modificano oggetti di sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- direct system catalog updates [SQL Server]
- system catalogs [SQL Server]
ms.assetid: 221b46c2-c27e-4df8-bd8c-8b990d6d5e98
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 526181bc4bf7ab81df2eaa25f19e7627c9b7af10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726488"
---
# <a name="remove-statements-that-modify-system-objects"></a><span data-ttu-id="2e222-102">Rimuovere le istruzioni che modificano oggetti di sistema</span><span class="sxs-lookup"><span data-stu-id="2e222-102">Remove statements that modify system objects</span></span>
  <span data-ttu-id="2e222-103">Sono state rilevate istruzioni che aggiornano il catalogo di sistema.</span><span class="sxs-lookup"><span data-stu-id="2e222-103">Upgrade Advisor detected statements that update the system catalog.</span></span> <span data-ttu-id="2e222-104">Gli aggiornamenti diretti del catalogo di sistema non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="2e222-104">Direct system catalog updates are not allowed.</span></span> <span data-ttu-id="2e222-105">Modificare gli script SQL in modo che utilizzino API ufficiali e documentate.</span><span class="sxs-lookup"><span data-stu-id="2e222-105">Modify your SQL scripts to use official and documented APIs.</span></span>  
  
## <a name="component"></a><span data-ttu-id="2e222-106">Componente</span><span class="sxs-lookup"><span data-stu-id="2e222-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="2e222-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e222-107">Description</span></span>  
 <span data-ttu-id="2e222-108">Gli aggiornamenti diretti del catalogo di sistema non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="2e222-108">Direct system catalog updates are not allowed.</span></span> <span data-ttu-id="2e222-109">Qualsiasi tentativo di eseguire questa operazione restituirà l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="2e222-109">Any attempt to do so will generate the following error:</span></span>  
  
 `Server: Msg 259, Level 16, State 1, Line 1`  
  
 `Ad hoc updates to system catalogs are not allowed.`  
  
## <a name="corrective-action"></a><span data-ttu-id="2e222-110">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="2e222-110">Corrective Action</span></span>  
 <span data-ttu-id="2e222-111">Modificare gli script SQL in modo che utilizzino API ufficiali e documentate.</span><span class="sxs-lookup"><span data-stu-id="2e222-111">Modify your SQL scripts to use official and documented APIs.</span></span> <span data-ttu-id="2e222-112">Utilizzare, ad esempio, ALTER DATABASE *database_name* set Emergency anziché eseguire un'istruzione Update sulla tabella di sistema **sysdatabases** .</span><span class="sxs-lookup"><span data-stu-id="2e222-112">For example, use ALTER DATABASE *database_name* SET EMERGENCY instead of running an UPDATE statement on the **sysdatabases** system table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e222-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e222-113">See Also</span></span>  
 <span data-ttu-id="2e222-114">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2e222-114">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="2e222-115">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="2e222-115">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
