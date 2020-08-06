---
title: Opzioni (risultati query-SQL Server-multiserver) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.sqleditors.multiserverresultssettings
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLMultiServerResults
ms.assetid: d6768bd8-9cb5-4606-a726-a33a1df9e1bb
author: rothja
ms.author: jroth
ms.openlocfilehash: 8273ad5edc65dd7351533209e9fa670c49f75f7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721727"
---
# <a name="options-query-results-sql-server-multi-server"></a><span data-ttu-id="a1483-102">Opzioni (Risultati query/SQL Server/Multiserver)</span><span class="sxs-lookup"><span data-stu-id="a1483-102">Options (Query Results-SQL Server-Multi-Server)</span></span>
  <span data-ttu-id="a1483-103">Quando si esegue una query su più server contemporaneamente, utilizzare questa pagina per specificare le opzioni per la visualizzazione dei set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a1483-103">When you are querying multiple servers at the same time, use this page to specify the options for displaying result sets.</span></span> <span data-ttu-id="a1483-104">Con la funzione Unisci risultati, i set di risultati di tutti i server vengono combinati in un singolo set.</span><span class="sxs-lookup"><span data-stu-id="a1483-104">Merge results combines the result sets from all servers into a single result set.</span></span> <span data-ttu-id="a1483-105">Quando si uniscono i risultati, il server che risponde per primo imposta lo schema per il set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a1483-105">When merging results, the first server to respond sets the schema for the result set.</span></span> <span data-ttu-id="a1483-106">Perché sia possibile unire i set di risultati, la query deve restituire lo stesso numero di colonne con nomi uguali da ogni server.</span><span class="sxs-lookup"><span data-stu-id="a1483-106">To merge the result sets, the query must return the same number of columns with the same column names from each server.</span></span> <span data-ttu-id="a1483-107">Quando si uniscono i risultati, viene visualizzato un messaggio per ogni server che non corrisponde allo schema (numero di colonne e nomi di colonna) restituito dal server che ha risposto per primo.</span><span class="sxs-lookup"><span data-stu-id="a1483-107">When merging results, a message is displayed for each server that does not match the schema (column count and column names) that is returned by the first server to return results.</span></span>  
  
 <span data-ttu-id="a1483-108">Quando non si uniscono i risultati, il set di risultati restituito da ciascun server verrà visualizzato nella rispettiva griglia con uno schema proprio.</span><span class="sxs-lookup"><span data-stu-id="a1483-108">When you do not merge results, the result set from each server will be displayed in its own grid with its own schema.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a1483-109">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a1483-109">UI element list</span></span>  
 <span data-ttu-id="a1483-110">**Unisci risultati**</span><span class="sxs-lookup"><span data-stu-id="a1483-110">**Merge results**</span></span>  
 <span data-ttu-id="a1483-111">Selezionare questa casella di controllo per combinare i set di risultati di molti server nella stessa griglia.</span><span class="sxs-lookup"><span data-stu-id="a1483-111">Select this check box to combine the result sets from several servers into the same grid.</span></span>  
  
 <span data-ttu-id="a1483-112">**Aggiungi nome del server ai risultati**</span><span class="sxs-lookup"><span data-stu-id="a1483-112">**Add server name to the results**</span></span>  
 <span data-ttu-id="a1483-113">Selezionare questa casella di controllo per includere una colonna aggiuntiva contenente il nome del server che ha generato ogni riga.</span><span class="sxs-lookup"><span data-stu-id="a1483-113">Select this check box to include an additional column that provides the name of the server that produced each row.</span></span>  
  
 <span data-ttu-id="a1483-114">**Aggiungi nome di accesso ai risultati**</span><span class="sxs-lookup"><span data-stu-id="a1483-114">**Add login name to the results**</span></span>  
 <span data-ttu-id="a1483-115">Selezionare questa casella di controllo per includere una colonna aggiuntiva contenente il nome di accesso utilizzato per connettersi al server che ha generato ogni riga.</span><span class="sxs-lookup"><span data-stu-id="a1483-115">Select this check box to include an additional column that provides the login that was used to connect to the server that provided each row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1483-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1483-116">See Also</span></span>  
 <span data-ttu-id="a1483-117">[Creare un server di gestione centrale e un gruppo di server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span><span class="sxs-lookup"><span data-stu-id="a1483-117">[Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md) </span></span>  
 [<span data-ttu-id="a1483-118">Eseguire istruzioni su più server contemporaneamente &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a1483-118">Execute Statements Against Multiple Servers Simultaneously &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/execute-statements-against-multiple-servers-simultaneously.md)  
  
  
