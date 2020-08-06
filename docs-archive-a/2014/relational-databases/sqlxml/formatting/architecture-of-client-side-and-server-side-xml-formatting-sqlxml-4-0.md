---
title: Architettura della formattazione XML sul lato client e sul lato server (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], XML formatting architecture
- SQLOLEDB provider
- client-side XML formatting
- data providers [SQLXML], XML formatting architecture
- SQLNCLI, XML
- server-side XML formatting
- SQL Server Native Client, XML
- SQLXMLOLEDB Provider, XML formatting architecture
ms.assetid: 52440d9e-89fd-4c15-a008-a1ea99f41387
author: rothja
ms.author: jroth
ms.openlocfilehash: ae1a9c60a7a7966f4eff2a08b4557487f5aec58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630421"
---
# <a name="architecture-of-client-side-and-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="3e676-102">Architettura della formattazione XML sul lato client e sul lato server (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3e676-102">Architecture of Client-side and Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="3e676-103">Nell'illustrazione seguente viene mostrata l'architettura della formattazione XML sul lato server.</span><span class="sxs-lookup"><span data-stu-id="3e676-103">The following illustration shows the architecture of XML formatting on the server side.</span></span>  
  
 <span data-ttu-id="3e676-104">![Architettura della formattazione XML sul lato server](../../../database-engine/dev-guide/media/serversidexml.gif "Architettura della formattazione XML sul lato server")</span><span class="sxs-lookup"><span data-stu-id="3e676-104">![Architecture of XML formatting on the server side.](../../../database-engine/dev-guide/media/serversidexml.gif "Architecture of XML formatting on the server side.")</span></span>  
  
 <span data-ttu-id="3e676-105">In questo esempio il comando specificato sul client viene inviato al server.</span><span class="sxs-lookup"><span data-stu-id="3e676-105">In this example, the command that is specified on the client is sent to the server.</span></span> <span data-ttu-id="3e676-106">Il server produce un documento XML e lo restituisce al client.</span><span class="sxs-lookup"><span data-stu-id="3e676-106">The server produces an XML document and returns it to the client.</span></span> <span data-ttu-id="3e676-107">In questo caso, il server dispone di un'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e676-107">In this case, the server has an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3e676-108">Grazie alla formattazione XML sul lato server, è possibile utilizzare il provider SQLXMLOLEDB o il provider SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="3e676-108">With server-side XML formatting, you can use either the SQLXMLOLEDB provider or the SQLOLEDB provider.</span></span>  <span data-ttu-id="3e676-109">Il provider SQLXMLOLEDB utilizza Sqlxml4.dll che è incluso in SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="3e676-109">The SQLXMLOLEDB provider uses Sqlxml4.dll, which is included in SQLXML 4.0.</span></span> <span data-ttu-id="3e676-110">Quando si utilizza il provider SQLOLEDB, per impostazione predefinita si ottiene la funzionalità SQLXML fornita dal file Sqlxmlx.dll incluso in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows o in Microsoft Data Access Components (MDAC) 2.6 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="3e676-110">When you use the SQLOLEDB provider, by default you get the SQLXML functionality provided by Sqlxmlx.dll, which is included with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows or in Microsoft Data Access Components (MDAC) 2.6 or later.</span></span> <span data-ttu-id="3e676-111">Per utilizzare Sqlxml4.dll con SQLOLEDB, è necessario impostare la proprietà SQLXML Version su "SQLXML. 4.0" per l'oggetto connessione SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="3e676-111">To use Sqlxml4.dll with SQLOLEDB, you must set the SQLXML Version property to "SQLXML.4.0" on the SQLOLEDB Connection object.</span></span> <span data-ttu-id="3e676-112">In entrambi i casi, il server produce il documento XML e lo invia al client.</span><span class="sxs-lookup"><span data-stu-id="3e676-112">In either case, the server produces the XML document and sends it to the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e676-113">Gli updategram e le query XPath vengono analizzati sul client.</span><span class="sxs-lookup"><span data-stu-id="3e676-113">XPath queries and updategrams are parsed on the client.</span></span> <span data-ttu-id="3e676-114">Per ottenere il modello XPath o la funzionalità degli updategram in SQLXML 4.0, utilizzare Sqlxml4.dll.</span><span class="sxs-lookup"><span data-stu-id="3e676-114">To get the XPath template or updategram functionality in SQLXML 4.0, use Sqlxml4.dll.</span></span>  
  
 <span data-ttu-id="3e676-115">Nell'illustrazione seguente viene mostrata l'architettura della formattazione XML sul lato client.</span><span class="sxs-lookup"><span data-stu-id="3e676-115">The following illustration shows the architecture of XML formatting on the client side.</span></span>  
  
 <span data-ttu-id="3e676-116">![Architettura della formattazione XML sul lato client](../../../database-engine/dev-guide/media/clientsidexml.gif "Architettura della formattazione XML sul lato client")</span><span class="sxs-lookup"><span data-stu-id="3e676-116">![Architecture of XML formatting on the client side.](../../../database-engine/dev-guide/media/clientsidexml.gif "Architecture of XML formatting on the client side.")</span></span>  
  
 <span data-ttu-id="3e676-117">In questo esempio il client utilizza il provider SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="3e676-117">In this example, the client uses the SQLXMLOLEDB provider.</span></span> <span data-ttu-id="3e676-118">Nella stringa di connessione è necessario impostare la proprietà provider di dati su SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="3e676-118">In the connection string, the Data Provider property must be set to SQLOLEDB.</span></span> <span data-ttu-id="3e676-119">(Questo è l'unico valore accettato in SQLXML 4,0). Il comando eseguito sul client viene inviato al server.</span><span class="sxs-lookup"><span data-stu-id="3e676-119">(This is the only value accepted in SQLXML 4.0.) The command that is executed on the client is sent to the server.</span></span> <span data-ttu-id="3e676-120">Il set di righe generato nel server viene inviato al client.</span><span class="sxs-lookup"><span data-stu-id="3e676-120">The rowset that is generated on the server is sent to the client.</span></span> <span data-ttu-id="3e676-121">Sul client viene eseguita la formattazione del documento XML dal set di righe.</span><span class="sxs-lookup"><span data-stu-id="3e676-121">The formatting of the XML document from the rowset is performed on the client.</span></span>  
  
 <span data-ttu-id="3e676-122">In SQLXML 4.0 è possibile utilizzare [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) o il provider SQLOLEDB come provider di dati.</span><span class="sxs-lookup"><span data-stu-id="3e676-122">In SQLXML 4.0, either the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) or the SQLOLEDB provider can be used as the data provider.</span></span> <span data-ttu-id="3e676-123">È possibile accedere a qualsiasi origine dati.</span><span class="sxs-lookup"><span data-stu-id="3e676-123">You can potentially access any data source.</span></span> <span data-ttu-id="3e676-124">La trasformazione XML può essere applicata al client purché la query restituisca un singolo set di righe.</span><span class="sxs-lookup"><span data-stu-id="3e676-124">As long as the query returns a single rowset, the XML transformation can be applied on the client.</span></span>  
  
  
