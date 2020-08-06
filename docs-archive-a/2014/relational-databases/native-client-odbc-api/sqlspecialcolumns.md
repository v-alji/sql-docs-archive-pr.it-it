---
title: SQLSpecialColumns | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLSpecialColumns function
ms.assetid: dffe02ed-8f79-4c9a-af34-98130bbe5462
author: rothja
ms.author: jroth
ms.openlocfilehash: c36ff73606e95ed7ee5e713b81acf7c177a42563
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628664"
---
# <a name="sqlspecialcolumns"></a><span data-ttu-id="42443-102">SQLSpecialColumns</span><span class="sxs-lookup"><span data-stu-id="42443-102">SQLSpecialColumns</span></span>
  <span data-ttu-id="42443-103">Quando vengono richiesti identificatori di riga (*IdentifierType* SQL_BEST_ROWID), **SQLSpecialColumns** restituisce un set di risultati vuoto (nessuna riga di dati) per qualsiasi ambito richiesto diverso da SQL_SCOPE_CURROW.</span><span class="sxs-lookup"><span data-stu-id="42443-103">When requesting row identifiers (*IdentifierType* SQL_BEST_ROWID), **SQLSpecialColumns** returns an empty result set (no data rows) for any requested scope other than SQL_SCOPE_CURROW.</span></span> <span data-ttu-id="42443-104">Il set di risultati generato indica che le colonne sono valide solo all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="42443-104">The generated result set indicates that the columns are only valid within this scope.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="42443-105">non supporta pseudocolonne per gli identificatori.</span><span class="sxs-lookup"><span data-stu-id="42443-105">does not support pseudocolumns for identifiers.</span></span> <span data-ttu-id="42443-106">Il set di risultati **SQLSpecialColumns** identificherà tutte le colonne come SQL_PC_NOT_PSEUDO.</span><span class="sxs-lookup"><span data-stu-id="42443-106">The **SQLSpecialColumns** result set will identify all columns as SQL_PC_NOT_PSEUDO.</span></span>  
  
 <span data-ttu-id="42443-107">**SQLSpecialColumns** può essere eseguito su un cursore statico.</span><span class="sxs-lookup"><span data-stu-id="42443-107">**SQLSpecialColumns** can be executed on a static cursor.</span></span> <span data-ttu-id="42443-108">Un tentativo di eseguire **SQLSpecialColumns** su un oggetto aggiornabile (gestito da keyset o dinamico) restituisce SQL_SUCCESS_WITH_INFO indicante che il tipo di cursore è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="42443-108">An attempt to execute **SQLSpecialColumns** on an updatable (keyset-driven or dynamic) returns SQL_SUCCESS_WITH_INFO indicating the cursor type has been changed.</span></span>  
  
## <a name="sqlspecialcolumns-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="42443-109">Supporto di SQLSpecialColumns per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="42443-109">SQLSpecialColumns Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="42443-110">Per informazioni sui valori restituiti per le colonne DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH e DECIMAL_DIGTS per i tipi data/ora, vedere [metadati del catalogo](../native-client-odbc-date-time/metadata-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="42443-110">For information about the values returned for the columns DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH, and DECIMAL_DIGTS for date/time types, see [Catalog Metadata](../native-client-odbc-date-time/metadata-catalog.md).</span></span>  
  
 <span data-ttu-id="42443-111">Per informazioni più generali, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="42443-111">For more general information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlspecialcolumns-support-for-large-clr-udts"></a><span data-ttu-id="42443-112">Supporto di SQLSpecialColumns per tipi CLR definiti dall'utente di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="42443-112">SQLSpecialColumns Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="42443-113">**SQLSpecialColumns** supporta i tipi CLR definiti dall'utente di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="42443-113">**SQLSpecialColumns** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="42443-114">Per ulteriori informazioni, vedere [tipi CLR definiti dall'utente di grandi dimensioni &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="42443-114">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42443-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42443-115">See Also</span></span>  
 <span data-ttu-id="42443-116">[SQLSpecialColumns (funzione)](https://go.microsoft.com/fwlink/?LinkId=59371) </span><span class="sxs-lookup"><span data-stu-id="42443-116">[SQLSpecialColumns Function](https://go.microsoft.com/fwlink/?LinkId=59371) </span></span>  
 [<span data-ttu-id="42443-117">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="42443-117">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
