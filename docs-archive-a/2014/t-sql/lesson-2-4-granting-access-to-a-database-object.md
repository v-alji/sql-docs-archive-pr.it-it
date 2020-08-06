---
title: Concessione dell'accesso a un oggetto di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- granting access to database objects
ms.assetid: a44d9bbf-f58e-4734-b7f4-eb3b492b777b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 22bd0bb1f01e59ec30f7cf1bbf128c890d3d5d64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636982"
---
# <a name="granting-access-to-a-database-object"></a><span data-ttu-id="a55b0-102">Concessione dell'accesso a un oggetto di database</span><span class="sxs-lookup"><span data-stu-id="a55b0-102">Granting Access to a Database Object</span></span>
  <span data-ttu-id="a55b0-103">In qualità di amministratore, l'utente è autorizzato a eseguire l'istruzione SELECT dalla tabella **Products** e dalla vista **vw_Names** , nonché a eseguire la procedura **pr_Names** . All'utente Mary non sono tuttavia concesse tali autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a55b0-103">As an administrator, you can execute the SELECT from the **Products** table and the **vw_Names** view, and execute the **pr_Names** procedure; however, Mary cannot.</span></span> <span data-ttu-id="a55b0-104">Per concedere a tale utente le autorizzazioni necessarie, utilizzare l'istruzione GRANT.</span><span class="sxs-lookup"><span data-stu-id="a55b0-104">To grant Mary the necessary permissions, use the GRANT statement.</span></span>  
  
### <a name="procedure-title"></a><span data-ttu-id="a55b0-105">Titolo della procedura</span><span class="sxs-lookup"><span data-stu-id="a55b0-105">Procedure Title</span></span>  
  
1.  <span data-ttu-id="a55b0-106">Eseguire l'istruzione seguente per concedere a `Mary` l'autorizzazione `EXECUTE` per la stored procedure `pr_Names` .</span><span class="sxs-lookup"><span data-stu-id="a55b0-106">Execute the following statement to give `Mary` the `EXECUTE` permission for the `pr_Names` stored procedure.</span></span>  
  
    ```  
    GRANT EXECUTE ON pr_Names TO Mary;  
    GO  
    ```  
  
 <span data-ttu-id="a55b0-107">In questo scenario, all'utente Mary è consentito solo l'accesso alla tabella **Products** usando la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="a55b0-107">In this scenario, Mary can only access the **Products** table by using the stored procedure.</span></span> <span data-ttu-id="a55b0-108">Se si desidera autorizzare l'utente Mary a eseguire un'istruzione SELECT sulla vista, è inoltre necessario eseguire `GRANT SELECT ON vw_Names TO Mary`.</span><span class="sxs-lookup"><span data-stu-id="a55b0-108">If you want Mary to be able to execute a SELECT statement against the view, then you must also execute `GRANT SELECT ON vw_Names TO Mary`.</span></span> <span data-ttu-id="a55b0-109">Per rimuovere l'accesso agli oggetti di database, utilizzare l'istruzione REVOKE.</span><span class="sxs-lookup"><span data-stu-id="a55b0-109">To remove access to database objects, use the REVOKE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a55b0-110">Se la tabella, la vista e la stored procedure non appartengono allo stesso schema, la procedura per la concessione delle autorizzazioni risulta più complessa.</span><span class="sxs-lookup"><span data-stu-id="a55b0-110">If the table, the view, and the stored procedure are not owned by the same schema, granting permissions becomes more complex.</span></span>  
  
## <a name="about-grant"></a><span data-ttu-id="a55b0-111">Informazioni sull'istruzione GRANT</span><span class="sxs-lookup"><span data-stu-id="a55b0-111">About GRANT</span></span>  
 <span data-ttu-id="a55b0-112">È necessario disporre dell'autorizzazione EXECUTE per eseguire una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="a55b0-112">You must have EXECUTE permission to execute a stored procedure.</span></span> <span data-ttu-id="a55b0-113">Per accedere e modificare i dati, è necessario disporre delle autorizzazioni SELECT, INSERT, UPDATE e DELETE.</span><span class="sxs-lookup"><span data-stu-id="a55b0-113">You must have SELECT, INSERT, UPDATE, and DELETE permissions to access and change data.</span></span> <span data-ttu-id="a55b0-114">L'istruzione GRANT è inoltre utilizzata per altre autorizzazioni , ad esempio quella per creare tabelle.</span><span class="sxs-lookup"><span data-stu-id="a55b0-114">The GRANT statement is also used for other permissions, such as permission to create tables.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="a55b0-115">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="a55b0-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="a55b0-116">Riepilogo: Configurazione delle autorizzazioni per gli oggetti di database</span><span class="sxs-lookup"><span data-stu-id="a55b0-116">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="a55b0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a55b0-117">See Also</span></span>  
 <span data-ttu-id="a55b0-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a55b0-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="a55b0-119">REVOKE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a55b0-119">REVOKE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/revoke-transact-sql)  
  
  
