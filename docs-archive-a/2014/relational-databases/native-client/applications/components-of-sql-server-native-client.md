---
title: Componenti di SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], components
- components [SQL Server Native Client]
- SQLNCLI, about SQL Server Native Client
ms.assetid: 65f932d5-daa1-4eff-b6df-ee633fcf2a7c
author: rothja
ms.author: jroth
ms.openlocfilehash: 32438b9fb5473d9251acd0aceddb46db373f3548
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629784"
---
# <a name="components-of-sql-server-native-client"></a><span data-ttu-id="11414-102">Componenti di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="11414-102">Components of SQL Server Native Client</span></span>
  <span data-ttu-id="11414-103">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client sono inclusi i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="11414-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client contains the following components:</span></span>  
  
|<span data-ttu-id="11414-104">Componente</span><span class="sxs-lookup"><span data-stu-id="11414-104">Component</span></span>|<span data-ttu-id="11414-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11414-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11414-106">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="11414-106">sqlncli11.dll</span></span>|<span data-ttu-id="11414-107">File della libreria di collegamento dinamico (DLL) che contiene tutte le funzionalità di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="11414-107">The dynamic-link library (DLL) file that contains all of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client functionality.</span></span> <span data-ttu-id="11414-108">Sono inclusi il provider OLE DB di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client e il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="11414-108">This includes the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>|  
|<span data-ttu-id="11414-109">sqlnclir11.rll</span><span class="sxs-lookup"><span data-stu-id="11414-109">sqlnclir11.rll</span></span>|<span data-ttu-id="11414-110">File di risorse associato per la libreria di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="11414-110">The accompanying resource file for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library.</span></span>|  
|<span data-ttu-id="11414-111">s10ch_sqlncli.chm</span><span class="sxs-lookup"><span data-stu-id="11414-111">s10ch_sqlncli.chm</span></span>|<span data-ttu-id="11414-112">File della Guida della Creazione guidata origine dati in cui viene illustrato come creare un'origine dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizzando il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client o il provider OLE DB di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="11414-112">The Data Source Wizard help file that documents how to create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data source using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>|  
|<span data-ttu-id="11414-113">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="11414-113">sqlncli.h</span></span>|<span data-ttu-id="11414-114">File di intestazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client che contiene tutte le nuove definizioni necessarie per utilizzare [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="11414-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header file that contains all of the new definitions needed in order to use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="11414-115">Questo file di intestazione sostituisce entrambi i file di intestazione, odbcss.h e sqloledb.h.</span><span class="sxs-lookup"><span data-stu-id="11414-115">This header file replaces both the odbcss.h and the sqloledb.h header files.</span></span> <span data-ttu-id="11414-116">**Nota:**  Non è possibile fare riferimento a sqlncli. h e ODBCs. h nello stesso programma, ma è possibile fare riferimento a sqlncli. h e SQLOLEDB. h nello stesso programma purché sia definito per primo SQLOLEDB. h.</span><span class="sxs-lookup"><span data-stu-id="11414-116">**Note:**  You cannot reference sqlncli.h and odbcss.h in the same program, but you can reference sqlncli.h and sqloledb.h in same program as long as sqloledb.h is defined first.</span></span>|  
|<span data-ttu-id="11414-117">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="11414-117">sqlncli11.lib</span></span>|<span data-ttu-id="11414-118">File di libreria necessario per chiamare direttamente le funzioni dell'utilità **bcp** che fanno parte del [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC di Native Client.</span><span class="sxs-lookup"><span data-stu-id="11414-118">The library file needed to directly call the **bcp** utility functions that are part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="11414-119">**Nota:**  Se si fa riferimento al file sqlncli11. lib nel codice di programmazione, è necessario assicurarsi che il file di sqlncli11.dll si trovi nel percorso di sistema e nel percorso di sistema degli utenti che usano l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="11414-119">**Note:**  If you do reference the sqlncli11.lib file in your programming code, you need to make sure that the sqlncli11.dll file is in your system path, and in the system path of the users that make use of your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11414-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11414-120">See Also</span></span>  
 [<span data-ttu-id="11414-121">Compilazione di applicazioni con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="11414-121">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
