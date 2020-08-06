---
title: Set di risultati di automazione OLE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: conceptual
helpviewer_keywords:
- data types [SQL Server], OLE Automation
- two-dimensional arrays
- one-dimensional arrays
- result sets [SQL Server], OLE Automation
- OLE Automation [SQL Server], result sets
- arrays [SQL Server]
ms.assetid: b2f99e33-2303-427c-94b9-9d55f8e2a6ab
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7c9bdc4d51d989db2d4d676b29e0824c0e5b59a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638375"
---
# <a name="ole-automation-result-sets"></a><span data-ttu-id="e7d7a-102">Set di risultati di automazione OLE</span><span class="sxs-lookup"><span data-stu-id="e7d7a-102">OLE Automation Result Sets</span></span>
  <span data-ttu-id="e7d7a-103">Se una proprietà o un metodo di automazione OLE restituisce dati in una matrice a una o a due dimensioni, tale matrice verrà restituita al client come set di risultati:</span><span class="sxs-lookup"><span data-stu-id="e7d7a-103">If an OLE Automation property or method returns data in an array with one or two dimensions, the array is returned to the client as a result set:</span></span>  
  
-   <span data-ttu-id="e7d7a-104">Una matrice unidimensionale viene restituita al client come set di risultati a riga singola con lo stesso numero di colonne del numero di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="e7d7a-104">A one-dimensional array is returned to the client as a single-row result set with as many columns as there are elements in the array.</span></span> <span data-ttu-id="e7d7a-105">La matrice (10), ad esempio, viene restituita come singola riga con 10 colonne.</span><span class="sxs-lookup"><span data-stu-id="e7d7a-105">For example, an array(10) is returned as a single row of 10 columns.</span></span>  
  
-   <span data-ttu-id="e7d7a-106">Una matrice bidimensionale viene restituita al client come set di risultati costituito da un numero di colonne pari al numero di elementi della prima dimensione della matrice e un numero di righe pari al numero di elementi della seconda dimensione della matrice.</span><span class="sxs-lookup"><span data-stu-id="e7d7a-106">A two-dimensional array is returned to the client as a result set with as many columns as there are elements in the first dimension of the array and with as many rows as there are elements in the second dimension of the array.</span></span> <span data-ttu-id="e7d7a-107">La matrice (2,3), ad esempio, viene restituita come 2 colonne in 3 righe.</span><span class="sxs-lookup"><span data-stu-id="e7d7a-107">For example, an array(2,3) is returned as 2 columns in 3 rows.</span></span>  
  
 <span data-ttu-id="e7d7a-108">Quando il valore restituito da una proprietà o da un metodo è una matrice, sp_OAGetProperty o sp_OAMethod restituisce un set di risultati al client.</span><span class="sxs-lookup"><span data-stu-id="e7d7a-108">When a property return value or method return value is an array, sp_OAGetProperty or sp_OAMethod returns a result set to the client.</span></span> <span data-ttu-id="e7d7a-109">I parametri di output dei metodi non possono essere rappresentati da matrici. Queste procedure eseguono un'analisi di tutti i valori di dati della matrice per determinare quali sono i tipi di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appropriati e la lunghezza di dati da utilizzare per ogni colonna del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="e7d7a-109">(Method output parameters cannot be arrays.) These procedures scan all the data values in the array to determine the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types and data lengths to use for each column in the result set.</span></span> <span data-ttu-id="e7d7a-110">Per una colonna specifica queste procedure utilizzano il tipo di dati e la lunghezza necessari per rappresentare tutti i valori di dati della colonna.</span><span class="sxs-lookup"><span data-stu-id="e7d7a-110">For a particular column, these procedures use the data type and length required to represent all data values in that column.</span></span>  
  
 <span data-ttu-id="e7d7a-111">Se a tutti i valori di dati di una colonna è associato lo stesso tipo di dati, tale tipo verrà applicato all'intera colonna.</span><span class="sxs-lookup"><span data-stu-id="e7d7a-111">When all data values in a column share the same data type, that data type is used for the whole column.</span></span> <span data-ttu-id="e7d7a-112">Se ai valori sono invece associati tipi di dati diversi, il tipo di dati dell'intera colonna verrà scelto in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e7d7a-112">When data values in a column are different data types, the data type of the whole column is chosen based on the following table.</span></span> <span data-ttu-id="e7d7a-113">Per utilizzare la tabella seguente, individuare un tipo di dati lungo l'asse della riga sinistra e un secondo tipo di dati lungo l'asse della colonna superiore.</span><span class="sxs-lookup"><span data-stu-id="e7d7a-113">To use the following table, find one data type along the left row axis and a second data type along the top column axis.</span></span> <span data-ttu-id="e7d7a-114">L'intersezione della riga e della colonna descrive il tipo di dati della colonna del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="e7d7a-114">The intersection of the row and column describes the data type of the result set column.</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
||`int`|`float`|`money`|`datetime`|`varchar`|`nvarchar`|  
|`int`|`int`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`float`|`float`|`float`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`money`|`money`|`money`|`money`|`varchar`|`varchar`|`nvarchar`|  
|`datetime`|`varchar`|`varchar`|`varchar`|`datetime`|`varchar`|`nvarchar`|  
|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`varchar`|`nvarchar`|  
|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|`nvarchar`|  
  
## <a name="related-content"></a><span data-ttu-id="e7d7a-115">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="e7d7a-115">Related Content</span></span>  
 [<span data-ttu-id="e7d7a-116">Stored procedure di automazione &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e7d7a-116">OLE Automation Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/ole-automation-stored-procedures-transact-sql)  
  
 [<span data-ttu-id="e7d7a-117">Opzione di configurazione del server Ole Automation Procedures</span><span class="sxs-lookup"><span data-stu-id="e7d7a-117">Ole Automation Procedures Server Configuration Option</span></span>](../../database-engine/configure-windows/ole-automation-procedures-server-configuration-option.md)  
  
  
