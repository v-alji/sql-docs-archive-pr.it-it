---
title: SQL Server estensioni specifiche in-process per ADO.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data access [CLR integration]
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], in-process extensions
- in-process data access providers [CLR integration]
- extensions [CLR integration]
ms.assetid: 781b812e-eb14-472a-85fa-aa4cdb929bee
author: rothja
ms.author: jroth
ms.openlocfilehash: 37d8aedc1d8f93739c2e9386665adfc67b43e312
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637380"
---
# <a name="sql-server-in-process-specific-extensions-to-adonet"></a><span data-ttu-id="5ccba-102">Estensioni specifiche in-process di SQL Server ad ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5ccba-102">SQL Server In-Process Specific Extensions to ADO.NET</span></span>
  <span data-ttu-id="5ccba-103">Sono disponibili quattro estensioni funzionali principali ad ADO.NET specifiche per l'utilizzo in-process.</span><span class="sxs-lookup"><span data-stu-id="5ccba-103">There are four main functional extensions to ADO.NET that are specifically for in-process use.</span></span> <span data-ttu-id="5ccba-104">Tali estensioni verranno analizzate dettagliatamente negli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ccba-104">The following topics will cover these extensions in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ccba-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5ccba-105">In This Section</span></span>  
 [<span data-ttu-id="5ccba-106">Oggetto SqlContext</span><span class="sxs-lookup"><span data-stu-id="5ccba-106">SqlContext Object</span></span>](sqlcontext-object.md)  
 <span data-ttu-id="5ccba-107">Questa classe fornisce accesso alle altre estensioni mediante l'astrazione del contesto di un chiamante di una routine di SQL Server che esegue codice gestito in-process.</span><span class="sxs-lookup"><span data-stu-id="5ccba-107">This class provides access to the other extensions by abstracting the context of a caller of a SQL Server routine that executes managed code in-process.</span></span>  
  
 [<span data-ttu-id="5ccba-108">Oggetto SqlPipe</span><span class="sxs-lookup"><span data-stu-id="5ccba-108">SqlPipe Object</span></span>](sqlpipe-object.md)  
 <span data-ttu-id="5ccba-109">Questa classe contiene routine per l'invio di risultati tabulari e messaggi al client.</span><span class="sxs-lookup"><span data-stu-id="5ccba-109">This class contains routines to send tabular results and messages to the client.</span></span>  
  
 [<span data-ttu-id="5ccba-110">Oggetto SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="5ccba-110">SqlTriggerContext Object</span></span>](sqltriggercontext-object.md)  
 <span data-ttu-id="5ccba-111">Questa classe fornisce informazioni sul contesto nel quale viene eseguito un trigger.</span><span class="sxs-lookup"><span data-stu-id="5ccba-111">This class provides information on the context in which a trigger is run.</span></span>  
  
 [<span data-ttu-id="5ccba-112">Oggetto SqlDataRecord</span><span class="sxs-lookup"><span data-stu-id="5ccba-112">SqlDataRecord Object</span></span>](sqldatarecord-object.md)  
 <span data-ttu-id="5ccba-113">La classe SqlDataRecord rappresenta una sola riga di dati, insieme ai rispettivi metadati correlati, e consente alle stored procedure di restituire set di risultati personalizzati al client.</span><span class="sxs-lookup"><span data-stu-id="5ccba-113">The SqlDataRecord class represents a single row of data, along with its related metadata, and allows stored procedures to return custom result sets to the client.</span></span>  
  
  
