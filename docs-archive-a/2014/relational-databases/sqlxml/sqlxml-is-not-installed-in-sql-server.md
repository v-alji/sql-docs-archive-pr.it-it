---
title: SQLXML non è installato in SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 3dbb4f65-41de-48b8-ad62-47c9d7932de3
author: rothja
ms.author: jroth
ms.openlocfilehash: ffa4cfd8b18dbfd9b4ba05599e2a973ac5f6e888
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630409"
---
# <a name="sqlxml-is-not-installed-in-sql-server"></a><span data-ttu-id="98c13-102">Installazione di SQLXML non inclusa in SQL Server</span><span class="sxs-lookup"><span data-stu-id="98c13-102">SQLXML Is Not Installed in SQL Server</span></span>
  <span data-ttu-id="98c13-103">Prima di [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], SQLXML 4.0 veniva rilasciato con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e faceva parte dell'installazione predefinita di tutte le versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ad eccezione di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98c13-103">Before [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], SQLXML 4.0 was released with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and was part of the default installation of all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versions except for [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="98c13-104">A partire da [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], la versione più recente di SQLXML (SQLXML 4.0 SP1) non è più inclusa in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98c13-104">Starting with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the latest version of SQLXML (SQLXML 4.0 SP1) is no longer included in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="98c13-105">Per installare SQLXML 4,0 SP1 quando è disponibile, scaricarlo dal [percorso di installazione per SQLXML SP1](https://www.microsoft.com/download/details.aspx?id=44272).</span><span class="sxs-lookup"><span data-stu-id="98c13-105">To install SQLXML 4.0 SP1 when it is available, download it from [Install Location for SQLXML SP1](https://www.microsoft.com/download/details.aspx?id=44272).</span></span>  
  
 <span data-ttu-id="98c13-106">Se per un'applicazione eseguita su [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è richiesto SQLXML 4.0 e nel computer non è presente [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], è necessario scaricare e installare SQLXML 4.0 SP1.</span><span class="sxs-lookup"><span data-stu-id="98c13-106">If an application runs on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and requires SQLXML 4.0, and if the computer does not have [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you must download and install SQLXML 4.0 SP1.</span></span>  
  
## <a name="sqlxml-40-sp1-behavior-with-new-data-types-using-sqloledb-and-sql-server-native-client-ole-db-provider"></a><span data-ttu-id="98c13-107">Comportamento di SQLXML 4.0 SP1 con i nuovi tipi di dati quando si utilizzano il provider OLE DB di SQL Server Native Client e SQLOLEDB</span><span class="sxs-lookup"><span data-stu-id="98c13-107">SQLXML 4.0 SP1 Behavior with New Data Types Using SQLOLEDB and SQL Server Native Client OLE DB Provider</span></span>  
 <span data-ttu-id="98c13-108">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] vengono introdotti i tipi di dati seguenti che possono essere impiegati dagli sviluppatori che utilizzano SQLXML:</span><span class="sxs-lookup"><span data-stu-id="98c13-108">[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduces the following data types, which developers using SQLXML might want to use:</span></span>  
  
-   `Date`  
  
-   `Time`  
  
-   `DateTime2`  
  
-   `DateTimeOffset`  
  
 <span data-ttu-id="98c13-109">Quando si utilizza SQLXML 4.0 SP1 con SQLOLEDB (da Windows Data Access Components, prima noto come Microsoft Data Access Components) o con il provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], i nuovi tipi vengono visualizzati sotto forma di stringhe agli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="98c13-109">When using SQLXML 4.0 SP1 with either SQLOLEDB (from Windows Data Access Components, formerly Microsoft Data Access Components) or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], these new types will appear as strings to a developer.</span></span> <span data-ttu-id="98c13-110">I quattro nuovi tipi di dati vengono abilitati come tipi scalari predefiniti quando SQLXML 4.0 SP1 viene utilizzato con il provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0</span><span class="sxs-lookup"><span data-stu-id="98c13-110">SQLXML 4.0 SP1 will enable these four new data types as built-in scalar types when used with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider 11.0.</span></span> <span data-ttu-id="98c13-111">Se non si scarica SQLXML 4.0 SP1, l'esecuzione del mapping di questi tipi ai tipi non stringa può causare il troncamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="98c13-111">Until you download SQLXML 4.0 SP1, mapping these types to non-string types might cause truncation of some data.</span></span> <span data-ttu-id="98c13-112">Ad esempio, il mapping a provocherà `DateTime2` `xsd:date` il troncamento dei dati alla [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] `DateTime` precisione di 3,33 millisecondi.</span><span class="sxs-lookup"><span data-stu-id="98c13-112">For example, mapping `DateTime2` to `xsd:date` will cause data to be truncated to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] `DateTime` precision of 3.33 milliseconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98c13-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98c13-113">See Also</span></span>  
 [<span data-ttu-id="98c13-114">Concetti relativi alla programmazione SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="98c13-114">SQLXML 4.0 Programming Concepts</span></span>](sqlxml-4-0-programming-concepts.md)  
  
  
