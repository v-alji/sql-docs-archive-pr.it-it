---
title: WITH CHECK OPTION non è supportata nelle viste che contengono TOP in modalità di compatibilità 90 o successive | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- TOP clause
- WITH CHECK OPTION clause
ms.assetid: 1b9581d0-bad9-43e0-b8fc-f32d8a8a04ca
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ee7775c875e33f104341a1da39f5fe6c9326f284
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628090"
---
# <a name="with-check-option-is-not-supported-in-views-that-contain-top-in-90-or-later-compatibility-modes"></a><span data-ttu-id="1e33c-102">WITH CHECK OPTION non è supportata nelle viste che contengono TOP nella modalità di compatibilità 90 o successiva</span><span class="sxs-lookup"><span data-stu-id="1e33c-102">WITH CHECK OPTION is not supported in views that contain TOP in 90 or later compatibility modes</span></span>
  <span data-ttu-id="1e33c-103">È presente una vista definita utilizzando la clausola WITH CHECK OPTION e una clausola TOP nell'istruzione SELECT della vista o in una vista a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="1e33c-103">Upgrade Advisor detected a view that uses the WITH CHECK OPTION and a TOP clause in the SELECT statement of the view or in a referenced view.</span></span> <span data-ttu-id="1e33c-104">In modalità di compatibilità del database 80 e precedenti, le viste definite in questo modo consentono la modifica dei dati tramite la vista. Questo comportamento non è corretto e può dare luogo a risultati non accurati.</span><span class="sxs-lookup"><span data-stu-id="1e33c-104">Views defined this way incorrectly allow data to be modified through the view and may produce inaccurate results when the database compatibility mode is set to 80 and earlier.</span></span> <span data-ttu-id="1e33c-105">I dati non possono essere inseriti o aggiornati tramite una vista che utilizza una clausola WITH CHECK OPTION se tale vista o una vista a cui fa riferimento utilizza la clausola TOP e la modalità di compatibilità del database è 90 o successiva.</span><span class="sxs-lookup"><span data-stu-id="1e33c-105">Data cannot be inserted or updated through a view that uses WITH CHECK OPTION when the view or a referenced view uses the TOP clause and the database compatibility mode is set to 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="1e33c-106">Componente</span><span class="sxs-lookup"><span data-stu-id="1e33c-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="1e33c-107">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="1e33c-107">Corrective Action</span></span>  
 <span data-ttu-id="1e33c-108">Quando si esegue l'aggiornamento, la modalità di compatibilità dei database utente non cambia.</span><span class="sxs-lookup"><span data-stu-id="1e33c-108">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="1e33c-109">Prima di impostare la modalità di compatibilità del database su 100 o successiva, modificare le viste che utilizzano le clausole WITH CHECK OPTION e TOP se è richiesta la modifica di dati tramite la vista.</span><span class="sxs-lookup"><span data-stu-id="1e33c-109">Before you change the database compatibility mode to 100 or later, modify views that use both WITH CHECK OPTION and TOP if data modification through the view is required.</span></span> <span data-ttu-id="1e33c-110">Per ulteriori informazioni, vedere [sp_dbcmptlevel &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-dbcmptlevel-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1e33c-110">For more information, see [sp_dbcmptlevel &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dbcmptlevel-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e33c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e33c-111">See Also</span></span>  
 <span data-ttu-id="1e33c-112">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="1e33c-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="1e33c-113">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="1e33c-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
