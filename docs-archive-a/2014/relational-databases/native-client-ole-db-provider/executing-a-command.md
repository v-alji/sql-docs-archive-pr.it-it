---
title: Esecuzione di un comando | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- commands [SQL Server Native Client]
- OLE DB, executing commands
- sessions [SQL Server Native Client]
- OLE DB extensions for XML
- SQL Server Native Client OLE DB provider, command execution
ms.assetid: bb0b3cbf-fe45-46ba-b2ec-c5a39e3c7081
author: rothja
ms.author: jroth
ms.openlocfilehash: 41e8da036d5a4b6469a31213247ad7d4edb7dbfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636042"
---
# <a name="executing-a-command"></a><span data-ttu-id="528cd-102">Esecuzione di un comando</span><span class="sxs-lookup"><span data-stu-id="528cd-102">Executing a Command</span></span>
  <span data-ttu-id="528cd-103">Una volta stabilita la connessione a un'origine dati, il consumer chiama il metodo **IDBCreateSession::CreateSession** per creare una sessione.</span><span class="sxs-lookup"><span data-stu-id="528cd-103">After the connection to a data source is established, the consumer calls the **IDBCreateSession::CreateSession** method to create a session.</span></span> <span data-ttu-id="528cd-104">La sessione funge da comando, set di righe o factory di transazioni.</span><span class="sxs-lookup"><span data-stu-id="528cd-104">The session acts as a command, rowset, or transaction factory.</span></span>  
  
 <span data-ttu-id="528cd-105">Per utilizzare direttamente singoli indici o tabelle, il consumer richiede l'interfaccia `IOpenRowset`.</span><span class="sxs-lookup"><span data-stu-id="528cd-105">To work directly with individual tables or indexes, the consumer requests the `IOpenRowset` interface.</span></span> <span data-ttu-id="528cd-106">Il metodo `IOpenRowset::OpenRowset` viene aperto e restituisce un set di righe che include tutte le righe di un singolo indice o tabella di base.</span><span class="sxs-lookup"><span data-stu-id="528cd-106">The `IOpenRowset::OpenRowset` method opens and returns a rowset that includes all rows from a single base table or index.</span></span>  
  
 <span data-ttu-id="528cd-107">Per eseguire un comando, ad esempio SELECT \* from authors, il consumer richiede l' `IDBCreateCommand` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="528cd-107">To execute a command (such as SELECT \* FROM Authors), the consumer requests the `IDBCreateCommand` interface.</span></span> <span data-ttu-id="528cd-108">Il consumer può eseguire il metodo `IDBCreateCommand::CreateCommand` per creare un oggetto comando e richiedere l'interfaccia `ICommandText`.</span><span class="sxs-lookup"><span data-stu-id="528cd-108">The consumer can execute the `IDBCreateCommand::CreateCommand` method to create a command object and request for the `ICommandText` interface.</span></span> <span data-ttu-id="528cd-109">Il metodo `ICommandText::SetCommandText` viene utilizzato per specificare il comando da eseguire.</span><span class="sxs-lookup"><span data-stu-id="528cd-109">The `ICommandText::SetCommandText` method is used to specify the command that is to be executed.</span></span>  
  
 <span data-ttu-id="528cd-110">Per eseguire il comando, viene utilizzato `Execute`.</span><span class="sxs-lookup"><span data-stu-id="528cd-110">The `Execute` command is used to execute the command.</span></span> <span data-ttu-id="528cd-111">Il comando può essere qualsiasi nome di istruzione o di procedura SQL.</span><span class="sxs-lookup"><span data-stu-id="528cd-111">The command can be any SQL statement or procedure name.</span></span> <span data-ttu-id="528cd-112">Non tutti i comandi producono un oggetto set di risultati (set di righe).</span><span class="sxs-lookup"><span data-stu-id="528cd-112">Not all commands produce a result set (rowset) object.</span></span> <span data-ttu-id="528cd-113">Comandi come SELECT \* FROM Authors producono un set di risultati.</span><span class="sxs-lookup"><span data-stu-id="528cd-113">Commands such as SELECT \* FROM Authors produce a result set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="528cd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="528cd-114">See Also</span></span>  
 [<span data-ttu-id="528cd-115">Creazione di un'applicazione del provider OLE DB di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="528cd-115">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
