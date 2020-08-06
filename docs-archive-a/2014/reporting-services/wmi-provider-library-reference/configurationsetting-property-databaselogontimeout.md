---
title: Proprietà DatabaseLogonTimeout (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonTimeout Property
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonTimeout property
ms.assetid: 4a65162c-33de-485e-8fd3-2bd6bff8bf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4920f5ef2282478f4d12a19b0806cf6ff9632cac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722340"
---
# <a name="databaselogontimeout-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="403a9-102">Proprietà DatabaseLogonTimeout (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="403a9-102">DatabaseLogonTimeout Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="403a9-103">Specifica il numero di secondi di attesa prima che un tentativo di accesso al database del server di report abbia esito negativo.</span><span class="sxs-lookup"><span data-stu-id="403a9-103">Specifies the number of seconds to wait before an attempt to log on to the report server database fails.</span></span> <span data-ttu-id="403a9-104">Il valore **0** indica un tempo di attesa indefinito.</span><span class="sxs-lookup"><span data-stu-id="403a9-104">A value of **0** indicates an infinite wait time.</span></span> <span data-ttu-id="403a9-105">Sola lettura.</span><span class="sxs-lookup"><span data-stu-id="403a9-105">Read only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="403a9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="403a9-106">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonTimeout As Int32  
```  
  
```csharp  
public Int32 DatabaseLogonTimeout;  
```  
  
## <a name="property-values"></a><span data-ttu-id="403a9-107">Valori della proprietà</span><span class="sxs-lookup"><span data-stu-id="403a9-107">Property Values</span></span>  
 <span data-ttu-id="403a9-108">Oggetto integer a 32 bit con segno che rappresenta il numero di secondi.</span><span class="sxs-lookup"><span data-stu-id="403a9-108">A 32-bit signed integer object that represents the number of seconds.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="403a9-109">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="403a9-109">Example Code</span></span>  
 [<span data-ttu-id="403a9-110">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="403a9-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="403a9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="403a9-111">Requirements</span></span>  
 <span data-ttu-id="403a9-112">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="403a9-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="403a9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="403a9-113">See Also</span></span>  
 [<span data-ttu-id="403a9-114">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="403a9-114">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
