---
title: Colonne data-at-execution e di tipo text, ntext o image | Microsoft Docs
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
- data types [ODBC], image
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- ODBC data types, text columns
- data-at-execution
- ODBC data-at-execution
- image columns [ODBC]
ms.assetid: 67ffb1a6-f38d-4712-ba64-96bdd41ec2b2
author: rothja
ms.author: jroth
ms.openlocfilehash: 404fade34862fe4705ec440eef7f466a9073250b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725640"
---
# <a name="data-at-execution-and-text-ntext-or-image-columns"></a><span data-ttu-id="1665e-102">Colonne data-at-execution di tipo text, ntext o image</span><span class="sxs-lookup"><span data-stu-id="1665e-102">Data-at-Execution and Text, ntext, or Image Columns</span></span>
  <span data-ttu-id="1665e-103">ODBC data-at-execution è una caratteristica che consente alle applicazioni di utilizzare quantità estremamente elevate di dati su colonne o parametri associati.</span><span class="sxs-lookup"><span data-stu-id="1665e-103">ODBC data-at-execution is a feature that enables applications to work with extremely large amounts of data on bound columns or parameters.</span></span> <span data-ttu-id="1665e-104">Quando si recuperano colonne di tipo **Text**, **ntext**o **Image** di dimensioni molto grandi, un'applicazione potrebbe non essere in grado di allocare semplicemente un buffer enorme, associare la colonna al buffer e recuperare la riga.</span><span class="sxs-lookup"><span data-stu-id="1665e-104">When retrieving very large **text**, **ntext**, or **image** columns, an application may not be able to simply allocate a huge buffer, bind the column into the buffer, and fetch the row.</span></span> <span data-ttu-id="1665e-105">Quando si aggiornano colonne di tipo **Text**, **ntext**o **Image** di dimensioni molto grandi, l'applicazione potrebbe non essere in grado di allocare semplicemente un buffer enorme, associarlo a un marcatore di parametro in un'istruzione SQL ed eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="1665e-105">When updating very large **text**, **ntext**, or **image** columns, the application might not be able to simply allocate a huge buffer, bind it to a parameter marker in an SQL statement, and then execute the statement.</span></span> <span data-ttu-id="1665e-106">In questi casi, l'applicazione deve utilizzare [SQLGetData](../native-client-odbc-api/sqlgetdata.md) o [SQLPutData](../native-client-odbc-api/sqlputdata.md) con le opzioni data-at-execution.</span><span class="sxs-lookup"><span data-stu-id="1665e-106">In these cases, the application must use [SQLGetData](../native-client-odbc-api/sqlgetdata.md) or [SQLPutData](../native-client-odbc-api/sqlputdata.md) with its data-at-execution options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1665e-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1665e-107">See Also</span></span>  
 [<span data-ttu-id="1665e-108">Gestione di colonne di tipo text e image</span><span class="sxs-lookup"><span data-stu-id="1665e-108">Managing Text and Image Columns</span></span>](managing-text-and-image-columns.md)  
  
  
