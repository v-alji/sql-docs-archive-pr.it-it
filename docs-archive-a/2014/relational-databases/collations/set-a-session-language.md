---
title: Impostare una lingua di sessione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- errors [SQL Server], international considerations
- globalization [SQL Server], sessions
- time [SQL Server]
- sessions [SQL Server], languages
- international considerations [SQL Server], sessions
- dates [SQL Server], session languages
- global considerations [SQL Server], sessions
- client-side session language
- time [SQL Server], session languages
- messages [SQL Server], international considerations
- server-side session language
ms.assetid: de7f2c90-8f4f-4cfc-94cc-4933a7fd2bde
author: stevestein
ms.author: sstein
ms.openlocfilehash: da8d6adce66ac5b97e533b5afaefabda40e4b966
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637912"
---
# <a name="set-a-session-language"></a><span data-ttu-id="7fe7e-102">Impostazione di una lingua di sessione</span><span class="sxs-lookup"><span data-stu-id="7fe7e-102">Set a Session Language</span></span>
  <span data-ttu-id="7fe7e-103">È possibile utilizzare la lingua di sessione per impostare la modalità di visualizzazione degli elementi seguenti nel server, in base a preferenze linguistiche e impostazioni locali:</span><span class="sxs-lookup"><span data-stu-id="7fe7e-103">The session language can be used to set how the following elements are displayed on the server, based on language and cultural preference:</span></span>  
  
-   <span data-ttu-id="7fe7e-104">Lingua che verrà utilizzata per messaggi di errore e altri messaggi di sistema.</span><span class="sxs-lookup"><span data-stu-id="7fe7e-104">The language that will be used for error and other system messages.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7fe7e-105">supporta più copie di tutte le stringhe di errore e dei messaggi del sistema in tutte le lingue in cui è disponibile [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7fe7e-105">supports having multiple copies of all system error strings and messages in all the languages in which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is available.</span></span> <span data-ttu-id="7fe7e-106">Questi messaggi possono essere visualizzati nella vista del catalogo [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) .</span><span class="sxs-lookup"><span data-stu-id="7fe7e-106">These messages can be viewed in the [sys.messages](/sql/relational-databases/system-catalog-views/messages-for-errors-catalog-views-sys-messages) catalog view.</span></span> <span data-ttu-id="7fe7e-107">Quando si installa una versione localizzata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], questi messaggi di sistema vengono tradotti nella lingua della versione installata.</span><span class="sxs-lookup"><span data-stu-id="7fe7e-107">When you install a localized version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], these system messages are translated for the language version that you install.</span></span> <span data-ttu-id="7fe7e-108">Per impostazione predefinita, è disponibile anche il set dei messaggi in inglese (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="7fe7e-108">By default, you also obtain the U.S. English set of these messages.</span></span> <span data-ttu-id="7fe7e-109">È inoltre possibile aggiungere messaggi definiti dall'utente in una lingua specifica usando [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7fe7e-109">Additionally, you can add user-defined messages in a specific language by using [sp_addmessage](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql).</span></span>  
  
-   <span data-ttu-id="7fe7e-110">Il formato di data e ora.</span><span class="sxs-lookup"><span data-stu-id="7fe7e-110">The format of date and time data.</span></span>  
  
-   <span data-ttu-id="7fe7e-111">I nomi dei giorni e dei mesi, incluse le abbreviazioni.</span><span class="sxs-lookup"><span data-stu-id="7fe7e-111">The names of days and months, including abbreviations.</span></span>  
  
-   <span data-ttu-id="7fe7e-112">Il primo giorno della settimana.</span><span class="sxs-lookup"><span data-stu-id="7fe7e-112">The first day of the week.</span></span>  
  
-   <span data-ttu-id="7fe7e-113">Le informazioni di valuta.</span><span class="sxs-lookup"><span data-stu-id="7fe7e-113">Currency data.</span></span>  
  
 <span data-ttu-id="7fe7e-114">Sono disponibili 33 lingue per le impostazioni di sessione.</span><span class="sxs-lookup"><span data-stu-id="7fe7e-114">There are 33 languages available for use as session settings.</span></span> <span data-ttu-id="7fe7e-115">Per un elenco completo, vedere [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7fe7e-115">For a list of languages, see [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-server"></a><span data-ttu-id="7fe7e-116">Impostazione della lingua di sessione dal server</span><span class="sxs-lookup"><span data-stu-id="7fe7e-116">Setting the Session Language from the Server</span></span>  
 <span data-ttu-id="7fe7e-117">Per impostare la lingua di sessione dal lato server, utilizzare l'istruzione [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7fe7e-117">To set the session language from the server side, use [SET LANGUAGE](/sql/t-sql/statements/set-language-transact-sql).</span></span>  
  
## <a name="setting-the-session-language-from-the-client"></a><span data-ttu-id="7fe7e-118">Impostazione della lingua di sessione dal client</span><span class="sxs-lookup"><span data-stu-id="7fe7e-118">Setting the Session Language from the Client</span></span>  
 <span data-ttu-id="7fe7e-119">È possibile impostare la lingua di sessione dal client utilizzando OLE DB, ODBC o ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="7fe7e-119">The session language can be set on the client side by using OLE DB, ODBC or ADO.NET.</span></span> <span data-ttu-id="7fe7e-120">Per OLE DB, utilizzare la proprietà SSPROP_INIT_CURRENTLANGUAGE.</span><span class="sxs-lookup"><span data-stu-id="7fe7e-120">For OLE DB, use the SSPROP_INIT_CURRENTLANGUAGE property.</span></span> <span data-ttu-id="7fe7e-121">Per altre informazioni, vedere [Proprietà di inizializzazione e di autorizzazione](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7fe7e-121">For more information, see [Initialization and Authorization Properties](../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span></span>  
  
 <span data-ttu-id="7fe7e-122">Per ODBC, utilizzare la parola chiave Language.</span><span class="sxs-lookup"><span data-stu-id="7fe7e-122">For ODBC, use the Language keyword.</span></span> <span data-ttu-id="7fe7e-123">Per altre informazioni, vedere [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="7fe7e-123">For more information, see [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="7fe7e-124">Per ADO.NET, usare il parametro **Current Language** dell'oggetto **ConnectionString** .</span><span class="sxs-lookup"><span data-stu-id="7fe7e-124">For ADO.NET, use the **Current Language** parameter of the **ConnectionString** object.</span></span> <span data-ttu-id="7fe7e-125">Per ulteriori informazioni, vedere la documentazione relativa al Software Development Kit (SDK) di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access Components (MDAC).</span><span class="sxs-lookup"><span data-stu-id="7fe7e-125">For more information, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Data Access Components (MDAC) software development kit (SDK) documentation.</span></span>  
  
  
