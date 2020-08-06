---
title: SQL Server Native Client origini dati ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, about data sources
- ODBC data sources, names
- data sources [SQL Server Native Client]
- names [ODBC]
- ODBC applications, data sources
- SQL Server Native Client ODBC driver, data sources
- ODBC data sources
ms.assetid: a6a50fd0-d439-43fd-b76f-16ec02f478c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 6960118e13f0843640b18056bda655726cbbbd29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628649"
---
# <a name="sql-server-native-client-odbc-data-sources"></a><span data-ttu-id="bca71-102">Origini dati ODBC di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="bca71-102">SQL Server Native Client ODBC Data Sources</span></span>
  <span data-ttu-id="bca71-103">Un nome di origine dati (DSN, Data Source Name) di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] identifica un'origine dati ODBC che contiene tutte le informazioni necessarie a un'applicazione ODBC per connettersi a un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un server specifico.</span><span class="sxs-lookup"><span data-stu-id="bca71-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source name (DSN) identifies an ODBC data source containing all of the information that an ODBC application needs to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a specific server.</span></span> <span data-ttu-id="bca71-104">Per definire un nome di origine dati ODBC, è possibile procedere in due modi diversi:</span><span class="sxs-lookup"><span data-stu-id="bca71-104">There are two ways you can define an ODBC data source name:</span></span>  
  
-   <span data-ttu-id="bca71-105">In un computer client, aprire strumenti di amministrazione nel pannello di controllo e fare doppio clic su **origini dati (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="bca71-105">On a client computer, open Administrative Tools in Control Panel, and double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="bca71-106">Verrà visualizzato Amministratore origine dati ODBC, in cui è possibile creare un nome di origine dati.</span><span class="sxs-lookup"><span data-stu-id="bca71-106">This will open the ODBC Data Source Administrator, which you can use to create a DSN.</span></span>  
  
-   <span data-ttu-id="bca71-107">In un'applicazione ODBC, chiamare [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="bca71-107">In an ODBC application, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="bca71-108">Un'origine dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contiene gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bca71-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source contains:</span></span>  
  
-   <span data-ttu-id="bca71-109">Nome dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="bca71-109">The name of the data source.</span></span>  
  
-   <span data-ttu-id="bca71-110">Tutte le informazioni necessarie per connettersi a un'istanza specifica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bca71-110">Any information needed to connect to a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="bca71-111">Database predefinito da utilizzare in un'istanza specifica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="bca71-111">The default database to use on a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (optional).</span></span>  
  
-   <span data-ttu-id="bca71-112">Impostazioni quali le opzioni ANSI da utilizzare, la registrazione o meno delle statistiche sulle prestazioni e così via (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="bca71-112">Settings such as which ANSI options to use, whether to log performance statistics, and so on (optional).</span></span>  
  
 <span data-ttu-id="bca71-113">Un'applicazione ODBC non è necessaria per connettersi tramite un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="bca71-113">An ODBC application is not required to connect through a data source.</span></span> <span data-ttu-id="bca71-114">L'applicazione, tuttavia, deve fornire le stesse informazioni sulla connettività a una funzione di connessione ODBC altrimenti individuate dal driver in un nome di origine dati.</span><span class="sxs-lookup"><span data-stu-id="bca71-114">However, the application must provide the same connectivity information to an ODBC connect function that the driver would otherwise find in a DSN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca71-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bca71-115">See Also</span></span>  
 [<span data-ttu-id="bca71-116">Comunicazione con SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="bca71-116">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
