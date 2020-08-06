---
title: Proprietà SMTPServer (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SMTPServer
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SMTPServer property
ms.assetid: 8bcceeba-e1a0-44ef-bda1-600c6925e1db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b706834c80fa0ff126d35beffbfdc84ef92cefe6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722304"
---
# <a name="smtpserver-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="31283-102">Proprietà SMTPServer (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="31283-102">SMTPServer Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="31283-103">Ottiene la proprietà del server SMTP dal file di configurazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="31283-103">Gets the SMTP server property from the report server configuration file.</span></span> <span data-ttu-id="31283-104">Di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="31283-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31283-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31283-105">Syntax</span></span>  
  
```vb  
Public Dim SMTPServer As String  
```  
  
```csharp  
public string SMTPServer;  
```  
  
## <a name="property-values"></a><span data-ttu-id="31283-106">Valori della proprietà</span><span class="sxs-lookup"><span data-stu-id="31283-106">Property Values</span></span>  
 <span data-ttu-id="31283-107">Oggetto di sola lettura `String` che contiene il valore della proprietà `SMTPServer` dal file RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="31283-107">A read-only `String` object containing the value of the `SMTPServer` property from the RSReportServer.config file.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="31283-108">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="31283-108">Example Code</span></span>  
 [<span data-ttu-id="31283-109">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="31283-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="31283-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31283-110">Requirements</span></span>  
 <span data-ttu-id="31283-111">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31283-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31283-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31283-112">See Also</span></span>  
 [<span data-ttu-id="31283-113">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="31283-113">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
