---
title: Accesso ai dati da oggetti di database CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], data access
- routines [CLR integration]
- data access [CLR integration]
- ADO.NET [CLR integration]
- internal data access [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], data access
- managed code [SQL Server], database objects
- .NET Data Access Provider for SQL Server [CLR integration]
- managed code [SQL Server], data access
- SqlClient provider
- in-process data access providers [CLR integration]
ms.assetid: 9a0f4dee-71c1-42e9-a85e-52382807010f
author: rothja
ms.author: jroth
ms.openlocfilehash: d229d490a9f3a7bc6f613259ee0535218de47975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636724"
---
# <a name="data-access-from-clr-database-objects"></a><span data-ttu-id="f18a7-102">Accesso ai dati da oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="f18a7-102">Data Access from CLR Database Objects</span></span>
  <span data-ttu-id="f18a7-103">Una routine Common Language Runtime (CLR) può accedere facilmente ai dati archiviati nell'istanza di [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] in cui è in esecuzione, nonché i dati archiviati in istanze remote.</span><span class="sxs-lookup"><span data-stu-id="f18a7-103">A common language runtime (CLR) routine may easily access data stored in the instance of [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] in which it runs, as well as data stored in remote instances.</span></span> <span data-ttu-id="f18a7-104">I dati specifici cui può accedere la routine sono determinati dal contesto utente in cui viene eseguito il codice.</span><span class="sxs-lookup"><span data-stu-id="f18a7-104">Which particular data the routine can access is determined by the user context in which the code is running.</span></span> <span data-ttu-id="f18a7-105">Accedere ai dati da un oggetto di database CLR utilizzando il .NET Framework provider di dati per i [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dati da applicazioni client e di livello intermedio gestite.</span><span class="sxs-lookup"><span data-stu-id="f18a7-105">Access data from within a CLR database object by using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data from managed client and middle-tier applications.</span></span> <span data-ttu-id="f18a7-106">Per questo motivo, è possibile sfruttare la propria esperienza in ADO.NET e `SqlClient` in applicazioni client e di livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="f18a7-106">Because of this, you can leverage your knowledge of ADO.NET and `SqlClient` in client and middle-tier applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f18a7-107">Per impostazione predefinita, ai metodi con tipo definito dall'utente e alle funzioni definite dall'utente non è consentito eseguire accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="f18a7-107">User-defined type methods and user-defined functions are not allowed to perform data access by default.</span></span> <span data-ttu-id="f18a7-108">È necessario impostare la proprietà `DataAccess` di `SqlMethodAttribute` o `SqlFunctionAttribute` su `DataAccessKind.Read` per consentire l'accesso ai dati di sola lettura da metodi con tipo definito dall'utente o funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f18a7-108">You must set the `DataAccess` property of `SqlMethodAttribute` or `SqlFunctionAttribute` to `DataAccessKind.Read` to enable read-only data access from user-defined type (UDT) methods or user-defined functions.</span></span> <span data-ttu-id="f18a7-109">Le operazioni di modifica dei dati non sono consentite da tipi definiti dall'utente o funzioni definite dall'utente e, in caso di un tentativo a tale scopo, vengono generate eccezioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f18a7-109">Data modification operations are not allowed from UDTs or user-defined functions, and throws exceptions at execution time if attempted.</span></span>  
  
 <span data-ttu-id="f18a7-110">In questa sezione vengono illustrate solo le specifiche differenze funzionali e di comportamento durante l'accesso ai dati da un oggetto di database CLR.</span><span class="sxs-lookup"><span data-stu-id="f18a7-110">This section discusses only the specific functional and behavioral differences when accessing data from within a CLR database object.</span></span> <span data-ttu-id="f18a7-111">Per ulteriori informazioni su caratteristiche e funzionalità di ADO.NET, vedere la documentazione di ADO.NET inclusa in .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="f18a7-111">For more information about the features and functionality of ADO.NET, see the ADO.NET documentation included in the .NET Framework SDK.</span></span>  
  
 <span data-ttu-id="f18a7-112">Nella tabella seguente vengono elencati gli argomenti disponibili in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="f18a7-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="f18a7-113">Connessione di contesto</span><span class="sxs-lookup"><span data-stu-id="f18a7-113">Context Connection</span></span>](context-connection.md)  
 <span data-ttu-id="f18a7-114">Viene descritta la connessione di contesto a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f18a7-114">Describes the context connection to SQL Server.</span></span>  
  
 [<span data-ttu-id="f18a7-115">Rappresentazione e credenziali per le connessioni</span><span class="sxs-lookup"><span data-stu-id="f18a7-115">Impersonation and Credentials for Connections</span></span>](impersonation-and-credentials-for-connections.md)  
 <span data-ttu-id="f18a7-116">Viene descritta la rappresentazione di connessioni e credenziali di connessione.</span><span class="sxs-lookup"><span data-stu-id="f18a7-116">Describes impersonating connections and connection credentials.</span></span>  
  
 [<span data-ttu-id="f18a7-117">Estensioni specifiche in-process di SQL Server ad ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f18a7-117">SQL Server In-Process Specific Extensions to ADO.NET</span></span>](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md)  
 <span data-ttu-id="f18a7-118">Vengono descritti gli oggetti `SqlPipe`, `SqlContext`, `SqlTriggerContext` e `SqlDataRecord` specifici in-process.</span><span class="sxs-lookup"><span data-stu-id="f18a7-118">Discusses the in-process specific `SqlPipe`, `SqlContext`, `SqlTriggerContext`, and `SqlDataRecord` objects.</span></span>  
  
 [<span data-ttu-id="f18a7-119">Integrazione con CLR e transazioni</span><span class="sxs-lookup"><span data-stu-id="f18a7-119">CLR Integration and Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="f18a7-120">Viene descritta l'integrazione del nuovo framework di transazioni fornito nello spazio dei nomi System.Transactions con ADO.NET e l'integrazione CLR di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f18a7-120">Describes how the new transaction framework provided in the System.Transactions namespace integrates with ADO.NET and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span>  
  
 [<span data-ttu-id="f18a7-121">Serializzazione XML da oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="f18a7-121">XML Serialization from CLR Database Objects</span></span>](../../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md)  
 <span data-ttu-id="f18a7-122">Viene illustrato come consentire scenari di serializzazione XML di oggetti di database CLR all'interno di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f18a7-122">Explains how to enable XML serialization scenarios of CLR database objects inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
  
