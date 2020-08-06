---
title: Gestione di colonne di testo e immagini | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- data types [ODBC], mapping
- ODBC data types, text columns
- image columns [ODBC]
ms.assetid: 7b543556-ff36-4d35-ac08-de96223d92cd
author: rothja
ms.author: jroth
ms.openlocfilehash: e9d7d5b0f48c68e8ac911f5e274c9afdb8cfe17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725615"
---
# <a name="managing-text-and-image-columns"></a><span data-ttu-id="0ae7c-102">Gestione di colonne di tipo text e image</span><span class="sxs-lookup"><span data-stu-id="0ae7c-102">Managing Text and Image Columns</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="0ae7c-103">i dati di tipo **Text**, **ntext**e **Image** (detti anche Long Data) sono tipi di dati stringa di tipo carattere o binario che possono contenere valori troppo grandi per essere contenuti in colonne **char**, **varchar**, **Binary**o **varbinary** .</span><span class="sxs-lookup"><span data-stu-id="0ae7c-103">**text**, **ntext**, and **image** data (also referred to as long data) are character or binary string data types that can hold data values too large to fit into **char**, **varchar**, **binary**, or **varbinary** columns.</span></span> <span data-ttu-id="0ae7c-104">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo di dati **Text** viene mappato al tipo di dati ODBC SQL_LONGVARCHAR; **ntext** esegue il mapping a SQL_WLONGVARCHAR; e il mapping di **Immagini** a SQL_LONGVARBINARY.</span><span class="sxs-lookup"><span data-stu-id="0ae7c-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **text** data type maps to the ODBC SQL_LONGVARCHAR data type; **ntext** maps to SQL_WLONGVARCHAR; and **image** maps to SQL_LONGVARBINARY.</span></span> <span data-ttu-id="0ae7c-105">Alcuni elementi di dati, ad esempio i documenti lunghi o le bitmap di grandi dimensioni, potrebbero essere troppo grandi per essere archiviati correttamente in memoria.</span><span class="sxs-lookup"><span data-stu-id="0ae7c-105">Some data items, such as long documents or large bitmaps, may be too large to store reasonably in memory.</span></span> <span data-ttu-id="0ae7c-106">Per recuperare dati Long da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in parti sequenziali, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client consente a un'applicazione di chiamare [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span><span class="sxs-lookup"><span data-stu-id="0ae7c-106">To retrieve long data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in sequential parts, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to call [SQLGetData](../native-client-odbc-api/sqlgetdata.md).</span></span> <span data-ttu-id="0ae7c-107">Per inviare dati Long in parti sequenziali, l'applicazione può chiamare [SQLPutData](../native-client-odbc-api/sqlputdata.md).</span><span class="sxs-lookup"><span data-stu-id="0ae7c-107">To send long data in sequential parts, the application can call [SQLPutData](../native-client-odbc-api/sqlputdata.md).</span></span> <span data-ttu-id="0ae7c-108">I parametri per i quali i dati vengono inviati in fase di esecuzione sono noti come parametri data-at-execution.</span><span class="sxs-lookup"><span data-stu-id="0ae7c-108">Parameters for which data is sent at execution time are known as data-at-execution parameters.</span></span>  
  
 <span data-ttu-id="0ae7c-109">Un'applicazione può effettivamente scrivere o recuperare qualsiasi tipo di dati (non solo i dati di tipo Long) con **SQLPutData** o **SQLGetData**, sebbene sia possibile inviare o recuperare solo dati di tipo **carattere** e **binario** in parti.</span><span class="sxs-lookup"><span data-stu-id="0ae7c-109">An application can actually write or retrieve any type of data (not just long data) with **SQLPutData** or **SQLGetData**, although only **character** and **binary** data can be sent or retrieved in parts.</span></span> <span data-ttu-id="0ae7c-110">Tuttavia, se i dati sono sufficientemente piccoli da adattarsi a un singolo buffer, in genere non esiste alcun motivo per utilizzare **SQLPutData** o **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="0ae7c-110">However, if the data is small enough to fit in a single buffer, there is generally no reason to use **SQLPutData** or **SQLGetData**.</span></span> <span data-ttu-id="0ae7c-111">È molto più semplice associare il singolo buffer al parametro o alla colonna.</span><span class="sxs-lookup"><span data-stu-id="0ae7c-111">It is much easier to bind the single buffer to the parameter or column.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ae7c-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0ae7c-112">In This Section</span></span>  
  
-   [<span data-ttu-id="0ae7c-113">Colonne di tipo text e image associate e non associate</span><span class="sxs-lookup"><span data-stu-id="0ae7c-113">Bound vs. Unbound Text and Image Columns</span></span>](bound-vs-unbound-text-and-image-columns.md)  
  
-   [<span data-ttu-id="0ae7c-114">Modifiche registrate e non registrate</span><span class="sxs-lookup"><span data-stu-id="0ae7c-114">Logged vs. Unlogged Modifications</span></span>](logged-vs-unlogged-modifications.md)  
  
-   [<span data-ttu-id="0ae7c-115">Colonne data-at-execution di tipo text, ntext o image</span><span class="sxs-lookup"><span data-stu-id="0ae7c-115">Data-at-Execution and Text, ntext, or Image Columns</span></span>](data-at-execution-and-text-ntext-or-image-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="0ae7c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ae7c-116">See Also</span></span>  
 [<span data-ttu-id="0ae7c-117">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="0ae7c-117">SQL Server Native Client &#40;ODBC&#41;</span></span>](../native-client/odbc/sql-server-native-client-odbc.md)  
  
  
