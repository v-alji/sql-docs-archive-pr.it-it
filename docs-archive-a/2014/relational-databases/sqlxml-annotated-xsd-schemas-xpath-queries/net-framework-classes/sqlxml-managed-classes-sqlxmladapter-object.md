---
title: Oggetto SqlXmlAdapter (classi gestite SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- void Update(DataSet ds) method
- SqlXmlAdapter object
- void Fill(DataSet ds) method
- SQLXML Managed Classes, SqlXmlAdapter object
- Managed Classes [SQLXML], SqlXmlAdapter object
ms.assetid: 0a16eddf-fc26-4d92-82d4-359b5fb905d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 1357ab7d070c7c2e451e31bccfda22c58eac42d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624004"
---
# <a name="sqlxmladapter-object-sqlxml-managed-classes"></a><span data-ttu-id="7ecf0-102">Oggetto SqlXmlAdapter (classi gestite SQLXML)</span><span class="sxs-lookup"><span data-stu-id="7ecf0-102">SqlXmlAdapter Object (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="7ecf0-103">Questo oggetto fornisce metodi che facilitano l'interazione con il set di dati in [!INCLUDE[msCoName](../../../includes/msconame-md.md)].NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7ecf0-103">This object provides methods that facilitate interaction with the dataset in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="7ecf0-104">Per un esempio funzionante, vedere [accesso alla funzionalità SQLXML nell'ambiente .NET](accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7ecf0-104">For a working sample, see [Accessing SQLXML Functionality in the .NET Environment](accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
 <span data-ttu-id="7ecf0-105">L'oggetto SqlXmlAdapter supporta questi metodi:</span><span class="sxs-lookup"><span data-stu-id="7ecf0-105">The SqlXmlAdapter object supports these methods:</span></span>  
  
 <span data-ttu-id="7ecf0-106">Riempimento void (set di dati DS)</span><span class="sxs-lookup"><span data-stu-id="7ecf0-106">void Fill(DataSet ds)</span></span>  
 <span data-ttu-id="7ecf0-107">Inserisce nel set di dati di .NET Framework i dati XML recuperati da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ecf0-107">Fills the dataset in the .NET Framework with the XML data retrieved from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7ecf0-108">Aggiornamento void (set di dati DS)</span><span class="sxs-lookup"><span data-stu-id="7ecf0-108">void Update(DataSet ds)</span></span>  
 <span data-ttu-id="7ecf0-109">Applica aggiornamenti ai record in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dai dati del set di dati.</span><span class="sxs-lookup"><span data-stu-id="7ecf0-109">Applies updates to records in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from the data in the dataset.</span></span>  
  
 <span data-ttu-id="7ecf0-110">L'oggetto SqlXmlAdapter supporta i costruttori seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ecf0-110">The SqlXmlAdapter object supports these constructors:</span></span>  
  
```  
public SqlXmlAdapter(SqlXmlCommand  cmd)   
  
public SqlXmlAdapter(  
                     string commandText,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                      )   
  
public SqlXmlAdapter(  
                     Stream commandStream,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                     )   
```  
  
## <a name="see-also"></a><span data-ttu-id="7ecf0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ecf0-111">See Also</span></span>  
 <span data-ttu-id="7ecf0-112">[Oggetto SqlXmlCommand &#40;classi gestite SQLXML&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="7ecf0-112">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 [<span data-ttu-id="7ecf0-113">Oggetto SqlXmlParameter &#40;classi gestite SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="7ecf0-113">SqlXmlParameter Object &#40;SQLXML Managed Classes&#41;</span></span>](sqlxml-managed-classes-sqlxmlparameter-object.md)  
  
  
