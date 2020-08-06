---
title: Gestione connessione SQL Server Compact Edition | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Compact, connection manager
- connections [Integration Services], SQL Server Compact
- connection managers [Integration Services], SQL Server Compact
ms.assetid: ba627d4d-41f4-49fc-a921-f534cde67770
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d4feb001cc7c0fd0bd8b6e60d5ab22b33ad2eb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724867"
---
# <a name="sql-server-compact-edition-connection-manager"></a><span data-ttu-id="330b8-102">Gestione connessione SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="330b8-102">SQL Server Compact Edition Connection Manager</span></span>
  <span data-ttu-id="330b8-103">Una gestione connessione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact consente la connessione tra un pacchetto e un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="330b8-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager enables a package to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span> <span data-ttu-id="330b8-104">La destinazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact inclusa in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa questa gestione connessione per caricare dati in una tabella di un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="330b8-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager to load data into a table in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="330b8-105">In un computer a 64 bit è necessario eseguire pacchetti che si connettono a origini dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact in modalità a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="330b8-105">On a 64-bit computer, you must run packages that connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources in 32-bit mode.</span></span> <span data-ttu-id="330b8-106">Il provider [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact usato in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per la connessione a origini dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact è disponibile solo nella versione a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="330b8-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact provider that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] uses to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources is available only in a 32-bit version.</span></span>  
  
## <a name="configuration-the-sql-server-compact-edition-connection-manager"></a><span data-ttu-id="330b8-107">Configurazione della gestione connessione SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="330b8-107">Configuration the SQL Server Compact Edition Connection Manager</span></span>  
 <span data-ttu-id="330b8-108">Quando si aggiunge una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gestione connessione compatta a un pacchetto, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Crea una gestione connessione che in fase di esecuzione verrà risolta in una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connessione compatta, imposta le proprietà della gestione connessione e la aggiunge alla `Connections` raccolta del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="330b8-108">When you add a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="330b8-109">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `SQLMOBILE`.</span><span class="sxs-lookup"><span data-stu-id="330b8-109">The `ConnectionManagerType` property of the connection manager is set to `SQLMOBILE`.</span></span>  
  
 <span data-ttu-id="330b8-110">Per configurare la gestione connessione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="330b8-110">You can configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="330b8-111">Immettere una stringa di connessione che specifica il percorso del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="330b8-111">Provide a connection string that specifies the location of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
-   <span data-ttu-id="330b8-112">Se il database è protetto da password, specificare una password.</span><span class="sxs-lookup"><span data-stu-id="330b8-112">Provide a password for a password-protected database.</span></span>  
  
-   <span data-ttu-id="330b8-113">Specificare il server in cui è archiviato il database.</span><span class="sxs-lookup"><span data-stu-id="330b8-113">Specify the server on which the database is stored.</span></span>  
  
-   <span data-ttu-id="330b8-114">Indicare se la connessione creata dalla gestione connessione deve essere mantenuta in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="330b8-114">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="330b8-115">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="330b8-115">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="330b8-116">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="330b8-116">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="330b8-117">Editor gestione connessione SQL Server Compact Edition &#40;pagina Connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="330b8-117">SQL Server Compact Edition Connection Manager Editor &#40;Connection Page&#41;</span></span>](../sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
-   [<span data-ttu-id="330b8-118">Editor gestione connessione SQL Server Compact Edition &#40;pagina Tutte&#41;</span><span class="sxs-lookup"><span data-stu-id="330b8-118">SQL Server Compact Edition Connection Manager Editor &#40;All Page&#41;</span></span>](../sql-server-compact-edition-connection-manager-editor-all-page.md)  
  
 <span data-ttu-id="330b8-119">Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere l'articolo relativo a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="330b8-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
