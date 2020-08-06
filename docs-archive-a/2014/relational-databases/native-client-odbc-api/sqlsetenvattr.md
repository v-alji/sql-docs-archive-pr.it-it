---
title: SQLSetEnvAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLSetEnvAttr function
ms.assetid: d4114571-feca-4330-b2e4-7bfd1050b812
author: rothja
ms.author: jroth
ms.openlocfilehash: f0dbd4d01de9ca769c46a93f810f0149f5b86981
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637253"
---
# <a name="sqlsetenvattr"></a><span data-ttu-id="8638d-102">SQLSetEnvAttr</span><span class="sxs-lookup"><span data-stu-id="8638d-102">SQLSetEnvAttr</span></span>
  <span data-ttu-id="8638d-103">Il [riferimento per programmatori ODBC](https://go.microsoft.com/fwlink/?LinkId=45250) definisce il modo in cui i driver ODBC devono interpretare le specifiche dell'attributo **SQLSetEnvAttr** dalle applicazioni scritte in ODBC 2. *x* o ODBC 3. API *x* .</span><span class="sxs-lookup"><span data-stu-id="8638d-103">The [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250) defines how ODBC drivers should interpret the **SQLSetEnvAttr** attribute specifications from applications written to either the ODBC 2.*x* or ODBC 3.*x* API.</span></span> <span data-ttu-id="8638d-104">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client è conforme a tali regole.</span><span class="sxs-lookup"><span data-stu-id="8638d-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with those rules.</span></span>  
  
 <span data-ttu-id="8638d-105">Uno degli attributi controllati da **SQLSetEnvAttr** è se deve essere usato il pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="8638d-105">One of the attributes controlled by **SQLSetEnvAttr** is whether connection pooling is to be used.</span></span> <span data-ttu-id="8638d-106">Se il pool di connessioni viene utilizzato con il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client, il parametro *DriverCompletion* deve essere impostato su SQL_DRIVER_NOPROMPT durante la connessione con [SQLDriverConnect](sqldriverconnect.md) o **SQLConnect**.</span><span class="sxs-lookup"><span data-stu-id="8638d-106">If connection pooling is used with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, the *DriverCompletion* parameter must be set to SQL_DRIVER_NOPROMPT when connecting with either [SQLDriverConnect](sqldriverconnect.md) or **SQLConnect**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8638d-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8638d-107">See Also</span></span>  
 <span data-ttu-id="8638d-108">[SQLSetEnvAttr (funzione)](https://go.microsoft.com/fwlink/?LinkId=59369) </span><span class="sxs-lookup"><span data-stu-id="8638d-108">[SQLSetEnvAttr Function](https://go.microsoft.com/fwlink/?LinkId=59369) </span></span>  
 [<span data-ttu-id="8638d-109">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="8638d-109">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
