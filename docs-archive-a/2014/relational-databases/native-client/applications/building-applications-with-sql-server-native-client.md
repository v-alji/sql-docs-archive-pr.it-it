---
title: Compilazione di applicazioni con SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], building applications
- SQLNCLI, building applications
- applications [SQL Server Native Client]
- SQL Server Native Client, building applications
ms.assetid: 254a2b48-f0e3-43b5-a48d-3d666c2a779f
author: rothja
ms.author: jroth
ms.openlocfilehash: d08fe1042ab1a79f6b48648f5a774b4fbac49ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629783"
---
# <a name="building-applications-with-sql-server-native-client"></a><span data-ttu-id="d1b3f-102">Compilazione di applicazioni con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b3f-102">Building Applications with SQL Server Native Client</span></span>
  <span data-ttu-id="d1b3f-103">Lo sviluppo di un'applicazione che utilizza la libreria di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client comporta una serie di problemi di cui tenere conto.</span><span class="sxs-lookup"><span data-stu-id="d1b3f-103">When developing an application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library, there are a number of issues that come into play.</span></span> <span data-ttu-id="d1b3f-104">Negli argomenti di questa sezione vengono illustrati alcuni dei problemi riscontrati, incluso l'aggiornamento da MDAC a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client e l'utilizzo dei file di intestazione e di libreria di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client e viene fornita una panoramica delle varie stringhe di connessione che è possibile utilizzare con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="d1b3f-104">The topics in this section discuss many of these issues including upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files, and an overview of the various connection strings that can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1b3f-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d1b3f-105">In This Section</span></span>  
 [<span data-ttu-id="d1b3f-106">Installazione di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b3f-106">Installing SQL Server Native Client</span></span>](installing-sql-server-native-client.md)  
 <span data-ttu-id="d1b3f-107">Vengono descritti l'installazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, i percorsi di installazione dei vari componenti e la disinstallazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="d1b3f-107">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is installed, the locations that various components are installed to, and how to uninstall [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="d1b3f-108">Componenti di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b3f-108">Components of SQL Server Native Client</span></span>](components-of-sql-server-native-client.md)  
 <span data-ttu-id="d1b3f-109">Vengono illustrati i componenti che costituiscono [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, inclusi i file di libreria, di risorse, della Guida e di intestazione.</span><span class="sxs-lookup"><span data-stu-id="d1b3f-109">Discusses the components that make up [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client including library, resource, help, and header files.</span></span>  
  
 [<span data-ttu-id="d1b3f-110">Utilizzo delle parole chiave delle stringhe di connessione con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b3f-110">Using Connection String Keywords with SQL Server Native Client</span></span>](using-connection-string-keywords-with-sql-server-native-client.md)  
 <span data-ttu-id="d1b3f-111">Vengono illustrati i vari tipi di stringhe di connessione che è possibile utilizzare durante la connessione a un database tramite [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="d1b3f-111">Discusses the various types of connection strings that can be used when connecting to a database through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="d1b3f-112">Utilizzo dei file di intestazione e della libreria di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b3f-112">Using the SQL Server Native Client Header and Library Files</span></span>](using-the-sql-server-native-client-header-and-library-files.md)  
 <span data-ttu-id="d1b3f-113">Viene illustrato come utilizzare i file di intestazione e di libreria di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client all'interno di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d1b3f-113">Discusses how to use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files within an application.</span></span>  
  
 [<span data-ttu-id="d1b3f-114">Aggiornamento di un'applicazione da MDAC a SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b3f-114">Updating an Application to SQL Server Native Client from MDAC</span></span>](updating-an-application-to-sql-server-native-client-from-mdac.md)  
 <span data-ttu-id="d1b3f-115">Vengono illustrate le differenze tra [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client e MDAC e vengono descritti i problemi di cui tenere conto durante l'aggiornamento da MDAC a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="d1b3f-115">Discusses the differences between [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and MDAC and issues that should be considered when upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="d1b3f-116">Aggiornamento di un'applicazione da SQL Server 2005 Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b3f-116">Updating an Application from SQL Server 2005 Native Client</span></span>](updating-an-application-from-sql-server-2005-native-client.md)  
 <span data-ttu-id="d1b3f-117">Vengono illustrati i problemi di cui tenere conto durante l'aggiornamento da [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1b3f-117">Discusses issues that should be considered when upgrading from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span>  
  
 [<span data-ttu-id="d1b3f-118">Utilizzo di ADO con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b3f-118">Using ADO with SQL Server Native Client</span></span>](using-ado-with-sql-server-native-client.md)  
 <span data-ttu-id="d1b3f-119">Viene illustrato l'utilizzo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client da parte di ADO per accedere alla funzionalità di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e utilizzarla.</span><span class="sxs-lookup"><span data-stu-id="d1b3f-119">Discusses how ADO can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to access and use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] functionality.</span></span>  
  
 [<span data-ttu-id="d1b3f-120">Criteri di supporto per SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b3f-120">Support Policies for SQL Server Native Client</span></span>](support-policies-for-sql-server-native-client.md)  
 <span data-ttu-id="d1b3f-121">Viene illustrato in che modo è possibile utilizzare i vari componenti di accesso ai dati con diverse versioni di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="d1b3f-121">Discusses how various data-access components can be used with different versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="d1b3f-122">Connessione a un database SQL di Azure usando SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="d1b3f-122">Connecting to an Azure SQL Database Using SQL Server Native Client</span></span>](connecting-to-a-windows-azure-sql-database-using-sql-server-native-client.md)  
 <span data-ttu-id="d1b3f-123">Viene illustrato come connettersi a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] mediante [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="d1b3f-123">Discusses how to connect to a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b3f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1b3f-124">See Also</span></span>  
 <span data-ttu-id="d1b3f-125">[Programmazione SQL Server Native Client](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="d1b3f-125">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 <span data-ttu-id="d1b3f-126">[Procedure per ODBC](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="d1b3f-126">[ODBC How-to Topics](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span></span>  
 [<span data-ttu-id="d1b3f-127">Procedure relative a OLE DB</span><span class="sxs-lookup"><span data-stu-id="d1b3f-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
