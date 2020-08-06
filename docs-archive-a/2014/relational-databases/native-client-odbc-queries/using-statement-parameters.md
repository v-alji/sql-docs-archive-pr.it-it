---
title: Utilizzo dei parametri dell'istruzione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- ODBC, parameters
- statements [ODBC], parameters
- parameter markers [ODBC]
- SQL Server Native Client ODBC driver, statements
- ODBC applications, statements
ms.assetid: 2427d886-ec6c-49d7-b0b6-0d998b64cdb9
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b7e207416e60af94efd59555980a0edff68a38b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624103"
---
# <a name="using-statement-parameters"></a><span data-ttu-id="cbda8-102">Utilizzo dei parametri delle istruzioni</span><span class="sxs-lookup"><span data-stu-id="cbda8-102">Using Statement Parameters</span></span>
  <span data-ttu-id="cbda8-103">Un parametro è una variabile in un'istruzione SQL che consente a un'applicazione ODBC di:</span><span class="sxs-lookup"><span data-stu-id="cbda8-103">A parameter is a variable in an SQL statement that can enable an ODBC application to:</span></span>  
  
-   <span data-ttu-id="cbda8-104">Fornire in modo efficiente valori per le colonne di una tabella.</span><span class="sxs-lookup"><span data-stu-id="cbda8-104">Efficiently provide values for columns in a table.</span></span>  
  
-   <span data-ttu-id="cbda8-105">Migliorare l'interazione dell'utente nella costruzione di criteri di query.</span><span class="sxs-lookup"><span data-stu-id="cbda8-105">Enhance user interaction in constructing query criteria.</span></span>  
  
-   <span data-ttu-id="cbda8-106">Gestire i dati di tipo **Text**, **ntext**e **Image** e i [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipi di dati C specifici di.</span><span class="sxs-lookup"><span data-stu-id="cbda8-106">Manage **text**, **ntext**, and **image** data and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific C data types.</span></span>  
  
 <span data-ttu-id="cbda8-107">Una tabella **parts** , ad esempio, include colonne denominate **partID**, **Description**e **Price**.</span><span class="sxs-lookup"><span data-stu-id="cbda8-107">For example, a **Parts** table has columns named **PartID**, **Description**, and **Price**.</span></span> <span data-ttu-id="cbda8-108">Per aggiungere una parte senza parametri, è necessario costruire un'istruzione SQL come:</span><span class="sxs-lookup"><span data-stu-id="cbda8-108">To add a part without parameters requires constructing an SQL statement such as:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (2100, 'Drive shaft', 50.00)  
```  
  
 <span data-ttu-id="cbda8-109">Sebbene questa istruzione sia accettabile per l'inserimento di una riga con un set di valori noto, non risulta particolarmente efficace quando un'applicazione richiede l'inserimento di diverse righe.</span><span class="sxs-lookup"><span data-stu-id="cbda8-109">Although this statement is acceptable for inserting one row with a known set of values, it is awkward when an application is required to insert several rows.</span></span> <span data-ttu-id="cbda8-110">In ODBC il problema viene risolto consentendo a un'applicazione di sostituire qualsiasi valore dei dati in un'istruzione SQL con un marcatore di parametro,</span><span class="sxs-lookup"><span data-stu-id="cbda8-110">ODBC addresses this by letting an application to replace any data value in an SQL statement by a parameter maker.</span></span> <span data-ttu-id="cbda8-111">rappresentato da un punto interrogativo (?).</span><span class="sxs-lookup"><span data-stu-id="cbda8-111">This is denoted by a question mark (?).</span></span> <span data-ttu-id="cbda8-112">Nell'esempio seguente tre valori di dati vengono sostituiti con marcatori di parametro:</span><span class="sxs-lookup"><span data-stu-id="cbda8-112">In the following example, three data values are replaced with parameter markers:</span></span>  
  
```  
INSERT INTO Parts (PartID, Description, Price) VALUES (?, ?, ?)  
```  
  
 <span data-ttu-id="cbda8-113">Gli indicatori di parametro vengono quindi associati a variabili dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cbda8-113">The parameter markers are then bound to application variables.</span></span> <span data-ttu-id="cbda8-114">Per inserire una nuova riga, l'applicazione deve solo impostare i valori delle variabili ed eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="cbda8-114">To insert a new row, the application has only to set the values of the variables and execute the statement.</span></span> <span data-ttu-id="cbda8-115">Il driver recupera quindi i valori correnti delle variabili e li invia all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="cbda8-115">The driver then retrieves the current values of the variables and sends them to the data source.</span></span> <span data-ttu-id="cbda8-116">Se l'istruzione viene eseguita più volte, l'applicazione può rendere ancora più efficiente il processo preparando l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="cbda8-116">If the statement is executed multiple times, the application can make the process even more efficient by preparing the statement.</span></span>  
  
 <span data-ttu-id="cbda8-117">A ogni marcatore di parametro è associato il numero ordinale assegnato ai parametri, da sinistra verso destra.</span><span class="sxs-lookup"><span data-stu-id="cbda8-117">Each parameter marker is referenced by its ordinal number assigned to the parameters from left to right.</span></span> <span data-ttu-id="cbda8-118">Il marcatore di parametro all'estrema sinistra in un'istruzione SQL presenta un valore ordinale pari a 1, il successivo è l'ordinale 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="cbda8-118">The leftmost parameter marker in an SQL statement has an ordinal value of 1; the next one is ordinal 2, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cbda8-119">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="cbda8-119">In This Section</span></span>  
  
-   [<span data-ttu-id="cbda8-120">Associazione di parametri</span><span class="sxs-lookup"><span data-stu-id="cbda8-120">Binding Parameters</span></span>](using-statement-parameters-binding-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="cbda8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbda8-121">See Also</span></span>  
 [<span data-ttu-id="cbda8-122">Esecuzione di query &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="cbda8-122">Executing Queries &#40;ODBC&#41;</span></span>](executing-queries-odbc.md)  
  
  
