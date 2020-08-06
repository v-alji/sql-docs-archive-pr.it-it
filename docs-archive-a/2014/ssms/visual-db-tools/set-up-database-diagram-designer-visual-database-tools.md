---
title: Impostare Progettazione diagrammi di database (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.diagnostic.InstallSqlDiagramSupport
helpviewer_keywords:
- Database Diagram Designer
- database diagrams [SQL Server], Database Diagram Designer
- diagrams [SQL Server], Database Diagram Designer
ms.assetid: 927321ee-b459-4f5b-9719-4a7a95639143
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d59fa2ed197a410de6b68e388e76d2bf21c334d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719307"
---
# <a name="set-up-database-diagram-designer-visual-database-tools"></a><span data-ttu-id="0eb47-102">Impostazione di Progettazione diagrammi di database (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="0eb47-102">Set Up Database Diagram Designer (Visual Database Tools)</span></span>
  <span data-ttu-id="0eb47-103">Per usare Progettazione diagrammi di database, è necessario che un membro del ruolo **proprietario_database** ne effettui preventivamente la configurazione per il controllo dell'accesso ai diagrammi.</span><span class="sxs-lookup"><span data-stu-id="0eb47-103">To use Database Diagram Designer, it must first be set up by a member of the **db_owner** role to control access to diagrams.</span></span>  
  
### <a name="to-set-up-database-diagramming"></a><span data-ttu-id="0eb47-104">Per impostare i diagrammi di database</span><span class="sxs-lookup"><span data-stu-id="0eb47-104">To set up database diagramming</span></span>  
  
1.  <span data-ttu-id="0eb47-105">In Esplora oggetti espandere un nodo di database.</span><span class="sxs-lookup"><span data-stu-id="0eb47-105">From Object Explorer, expand a database node.</span></span>  
  
2.  <span data-ttu-id="0eb47-106">Espandere il nodo dei diagrammi di database al di sotto della connessione al database.</span><span class="sxs-lookup"><span data-stu-id="0eb47-106">Expand the Database Diagrams node under the database connection.</span></span>  
  
3.  <span data-ttu-id="0eb47-107">Quando viene chiesto se si intende configurare i diagrammi di database, scegliere **Sì** .</span><span class="sxs-lookup"><span data-stu-id="0eb47-107">Select **Yes** when prompted if you want to set up database diagramming.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0eb47-108">Nel database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verranno create la tabella del diagramma di database, le stored procedure di sistema e una funzione di sistema.</span><span class="sxs-lookup"><span data-stu-id="0eb47-108">This will create the database diagram table, system stored procedures, and a system function on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
4.  <span data-ttu-id="0eb47-109">Tramite Visual Studio verranno creati i seguenti oggetti nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0eb47-109">Visual Studio will create the following objects on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="0eb47-110">Tabella sysdiagrams</span><span class="sxs-lookup"><span data-stu-id="0eb47-110">sysdiagrams table</span></span>  
  
    2.  <span data-ttu-id="0eb47-111">Stored procedure sp_alterdiagram</span><span class="sxs-lookup"><span data-stu-id="0eb47-111">sp_alterdiagram stored procedure</span></span>  
  
    3.  <span data-ttu-id="0eb47-112">Stored procedure sp_creatediagram</span><span class="sxs-lookup"><span data-stu-id="0eb47-112">sp_creatediagram stored procedure</span></span>  
  
    4.  <span data-ttu-id="0eb47-113">Stored procedure sp_dropdiagram</span><span class="sxs-lookup"><span data-stu-id="0eb47-113">sp_dropdiagram stored procedure</span></span>  
  
    5.  <span data-ttu-id="0eb47-114">Stored procedure sp_renamediagram</span><span class="sxs-lookup"><span data-stu-id="0eb47-114">sp_renamediagram stored procedure</span></span>  
  
    6.  <span data-ttu-id="0eb47-115">Funzione fn_diagramobjects</span><span class="sxs-lookup"><span data-stu-id="0eb47-115">fn_diagramobjects function</span></span>  
  
    7.  <span data-ttu-id="0eb47-116">Stored procedure sp_helpdiagrams</span><span class="sxs-lookup"><span data-stu-id="0eb47-116">sp_helpdiagrams stored procedure</span></span>  
  
    8.  <span data-ttu-id="0eb47-117">Stored procedure sp_helpdiagramsdefinition</span><span class="sxs-lookup"><span data-stu-id="0eb47-117">sp_helpdiagramsdefinition stored procedure</span></span>  
  
    9. <span data-ttu-id="0eb47-118">Stored procedure sp_upgraddiagrams</span><span class="sxs-lookup"><span data-stu-id="0eb47-118">sp_upgraddiagrams stored procedure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb47-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0eb47-119">See Also</span></span>  
 <span data-ttu-id="0eb47-120">[Informazioni sulla proprietà del diagramma di database &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0eb47-120">[Understand Database Diagram Ownership &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 <span data-ttu-id="0eb47-121">[Aggiornare i diagrammi di database delle precedenti edizioni &#40;Visual Database Tools&#41;](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0eb47-121">[Upgrade Database Diagrams from Previous Editions &#40;Visual Database Tools&#41;](upgrade-database-diagrams-from-previous-editions-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="0eb47-122">ALTER AUTHORIZATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0eb47-122">ALTER AUTHORIZATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-authorization-transact-sql)  
  
  
