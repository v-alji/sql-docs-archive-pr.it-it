---
title: Proprietà DatabaseQueryTimeout (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseQueryTimeout Property
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseQueryTimeout property
ms.assetid: 96faed97-9799-4bbf-a66f-fdd532d3eace
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e92e3e0f6752ea99fe89c962ebe96e343c0195b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722335"
---
# <a name="databasequerytimeout-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="7c5be-102">Proprietà DatabaseQueryTimeout (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="7c5be-102">DatabaseQueryTimeout Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="7c5be-103">Specifica il numero di secondi di attesa prima che il server di report presuma che il comando non sia riuscito e che sia necessaria una quantità di tempo troppo elevata per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7c5be-103">Specifies the number of seconds that must elapse before the report server assumes the command failed or took too much time to perform.</span></span> <span data-ttu-id="7c5be-104">Il server di report calcola il tempo di esecuzione della query rispetto al catalogo SQL e non rispetto a un'origine dati per il report.</span><span class="sxs-lookup"><span data-stu-id="7c5be-104">The report server is timing the querying against the SQL catalog, not a data source for the report.</span></span> <span data-ttu-id="7c5be-105">Proprietà di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="7c5be-105">Read/write.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c5be-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c5be-106">Syntax</span></span>  
  
```vb  
Public Dim DatabaseQueryTimeout As UInt32  
```  
  
```csharp  
public UInt32 DatabaseQueryTimeout;  
```  
  
## <a name="property-values"></a><span data-ttu-id="7c5be-107">Valori della proprietà</span><span class="sxs-lookup"><span data-stu-id="7c5be-107">Property Values</span></span>  
 <span data-ttu-id="7c5be-108">Oggetto `integer` senza segno a 32 bit che rappresenta il numero di secondi concessi per l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="7c5be-108">A 32-bit unsigned `integer` object that represents the number of seconds that the query is allowed to run.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="7c5be-109">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="7c5be-109">Example Code</span></span>  
 [<span data-ttu-id="7c5be-110">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="7c5be-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="7c5be-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c5be-111">Requirements</span></span>  
 <span data-ttu-id="7c5be-112">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c5be-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c5be-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c5be-113">See Also</span></span>  
 [<span data-ttu-id="7c5be-114">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="7c5be-114">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
