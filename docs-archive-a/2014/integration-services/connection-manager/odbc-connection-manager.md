---
title: Gestione connessione ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ODBC
- ODBC connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], ODBC
ms.assetid: e8c77aa7-6772-485e-918e-cef9eeb18c58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1069e31f3f8ffaf14dde091d913ff6d9f8fa7cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627337"
---
# <a name="odbc-connection-manager"></a><span data-ttu-id="db059-102">gestione connessione ODBC</span><span class="sxs-lookup"><span data-stu-id="db059-102">ODBC Connection Manager</span></span>
  <span data-ttu-id="db059-103">Una gestione connessione ODBC consente la connessione di un pacchetto a un'ampia gamma di sistemi di gestione di database in base alla specifica ODBC (Open Database Connectivity).</span><span class="sxs-lookup"><span data-stu-id="db059-103">An ODBC connection manager enables a package to connect to a variety of database management systems using the Open Database Connectivity specification (ODBC).</span></span>  
  
 <span data-ttu-id="db059-104">Quando si aggiunge una connessione ODBC a un pacchetto e si impostano le proprietà della gestione connessione, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Crea una gestione connessione e la aggiunge alla `Connections` raccolta del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="db059-104">When you add an ODBC connection to a package and set the connection manager properties, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager and adds the connection manager to the `Connections` collection of the package.</span></span> <span data-ttu-id="db059-105">In fase di esecuzione la gestione connessione viene risolta in una connessione ODBC fisica.</span><span class="sxs-lookup"><span data-stu-id="db059-105">At run time the connection manager is resolved as a physical ODBC connection.</span></span>  
  
 <span data-ttu-id="db059-106">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `ODBC`.</span><span class="sxs-lookup"><span data-stu-id="db059-106">The `ConnectionManagerType` property of the connection manager is set to `ODBC`.</span></span>  
  
 <span data-ttu-id="db059-107">Per configurare la gestione connessione ODBC, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="db059-107">You can configure the ODBC connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="db059-108">Specificare una stringa di connessione che fa riferimento al nome di un'origine dei dati utente o di sistema.</span><span class="sxs-lookup"><span data-stu-id="db059-108">Provide a connection string that references a user or system data source name.</span></span>  
  
-   <span data-ttu-id="db059-109">Specificare il server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="db059-109">Specify the server to connect to.</span></span>  
  
-   <span data-ttu-id="db059-110">Indicare se la connessione viene mantenuta in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="db059-110">Indicate whether the connection is retained at run time.</span></span>  
  
## <a name="configuration-of-the-odbc-connection-manager"></a><span data-ttu-id="db059-111">Configurazione della gestione connessione ODBC</span><span class="sxs-lookup"><span data-stu-id="db059-111">Configuration of the ODBC Connection Manager</span></span>  
 <span data-ttu-id="db059-112">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="db059-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="db059-113">Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="db059-113">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="db059-114">Riferimento all'interfaccia utente di Gestione connessione ODBC</span><span class="sxs-lookup"><span data-stu-id="db059-114">ODBC Connection Manager UI Reference</span></span>](../odbc-connection-manager-ui-reference.md)  
  
 <span data-ttu-id="db059-115">Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere l'articolo relativo a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="db059-115">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db059-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db059-116">See Also</span></span>  
 [<span data-ttu-id="db059-117">Connessioni in Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="db059-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
