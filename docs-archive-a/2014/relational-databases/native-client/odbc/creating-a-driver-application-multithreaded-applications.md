---
title: Applicazioni multithread | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- threads [SQL Server], multithreaded applications
- ODBC applications, multithreaded applications
- asynchronous operations [SQL Server Native Client]
- SQL Server Native Client ODBC driver, multithreaded applications
- multithreaded applications [SQL Server Native Client]
ms.assetid: d352c91a-6e08-4e50-9f3e-a37892d9c2cc
author: rothja
ms.author: jroth
ms.openlocfilehash: b680086f76e0c1a1e8c8cfc2f4ef82099957b3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635512"
---
# <a name="multithreaded-applications"></a><span data-ttu-id="316c4-102">Applicazioni a thread multipli</span><span class="sxs-lookup"><span data-stu-id="316c4-102">Multithreaded Applications</span></span>
  <span data-ttu-id="316c4-103">Il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client è un driver a thread multipli.</span><span class="sxs-lookup"><span data-stu-id="316c4-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver is a multithreaded driver.</span></span> <span data-ttu-id="316c4-104">La scrittura di un'applicazione a thread multipli costituisce un'alternativa all'utilizzo di chiamate asincrone per elaborare più chiamate ODBC.</span><span class="sxs-lookup"><span data-stu-id="316c4-104">Writing a multithreaded application is an alternative to using asynchronous calls to process multiple ODBC calls.</span></span> <span data-ttu-id="316c4-105">Un thread può effettuare una chiamata ODBC asincrona e altri thread possono eseguire l'elaborazione mentre il primo thread è bloccato in attesa della risposta alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="316c4-105">A thread can make a synchronous ODBC call, and other threads can process while the first thread is blocked waiting for the response to its call.</span></span> <span data-ttu-id="316c4-106">Questo modello è più efficiente dell'esecuzione di chiamate asincrone, in quanto elimina l'overhead quale il traffico di rete e l'esecuzione di test di chiamate a funzioni ODBC ripetute per SQL_STILL_EXECUTING.</span><span class="sxs-lookup"><span data-stu-id="316c4-106">This model is more efficient than making asynchronous calls because it eliminates overhead such as network traffic and making repeated ODBC function calls testing for SQL_STILL_EXECUTING.</span></span>  
  
 <span data-ttu-id="316c4-107">La modalità asincrona non rappresenta ancora un metodo efficace per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="316c4-107">Asynchronous mode is still an effective method of processing.</span></span> <span data-ttu-id="316c4-108">I miglioramenti nelle prestazioni di un modello a thread multipli non sono sufficienti a giustificare la riscrittura delle applicazioni asincrone.</span><span class="sxs-lookup"><span data-stu-id="316c4-108">The performance improvements of a multithreaded model are not enough to justify rewriting asynchronous applications.</span></span> <span data-ttu-id="316c4-109">Se gli utenti convertono applicazioni DB-Library che utilizzano il modello asincrono DB-Library, sarà più semplice convertirle nel modello asincrono ODBC.</span><span class="sxs-lookup"><span data-stu-id="316c4-109">If users are converting DB-Library applications that use the DB-Library asynchronous model, it is easier to convert them to the ODBC asynchronous model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="316c4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="316c4-110">See Also</span></span>  
 [<span data-ttu-id="316c4-111">Creazione di un'applicazione driver ODBC di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="316c4-111">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
  
