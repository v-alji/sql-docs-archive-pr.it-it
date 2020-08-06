---
title: SQLFreeHandle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLFreeHandle function
ms.assetid: d374e5c8-ed35-43bf-8dd6-c37e38d9b5f1
author: rothja
ms.author: jroth
ms.openlocfilehash: f51f031bec05715e0345507278113f4f16179a77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627221"
---
# <a name="sqlfreehandle"></a>SQLFreeHandle
  In modalità di commit manuale, la chiamata di **SQLFreeHandle** su un handle di istruzione con una transazione aperta causa un rollback delle modifiche in sospeso al database. La chiamata di **SQLFreeHandle** su un handle di istruzione chiude sempre tutti i cursori aperti e ignora i risultati in sospeso, liberando tutte le risorse associate all'handle di istruzione.  
  
## <a name="see-also"></a>Vedere anche  
 [SQLFreeHandle (funzione)](https://go.microsoft.com/fwlink/?LinkId=59345)   
 [Dettagli di implementazione dell'API ODBC](odbc-api-implementation-details.md)  
  
  
