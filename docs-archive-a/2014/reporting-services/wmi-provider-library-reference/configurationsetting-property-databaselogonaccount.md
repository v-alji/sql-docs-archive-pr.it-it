---
title: Proprietà DatabaseLogonAccount (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonAccount
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonAccount property
ms.assetid: 55f2863f-1ac1-4519-b512-e7f11c0ea5ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f9e844ff1d1447bd5abfefad8e82939575c7f47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722348"
---
# <a name="databaselogonaccount-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="4186b-102">Proprietà DatabaseLogonAccount (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="4186b-102">DatabaseLogonAccount Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="4186b-103">Specifica l'account di accesso utilizzato dal server di report al momento della connessione al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="4186b-103">Specifies the logon account that the report server uses when connecting to the report server database.</span></span> <span data-ttu-id="4186b-104">Sola lettura.</span><span class="sxs-lookup"><span data-stu-id="4186b-104">Read only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4186b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4186b-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonAccount As String  
```  
  
```csharp  
public string DatabaseLogonAccount;  
```  
  
## <a name="property-values"></a><span data-ttu-id="4186b-106">Valori della proprietà</span><span class="sxs-lookup"><span data-stu-id="4186b-106">Property Values</span></span>  
 <span data-ttu-id="4186b-107">Oggetto `String` che rappresenta il nome dell'account di accesso.</span><span class="sxs-lookup"><span data-stu-id="4186b-107">A `String` object that represents the logon account name.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="4186b-108">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="4186b-108">Example Code</span></span>  
 [<span data-ttu-id="4186b-109">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="4186b-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="4186b-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4186b-110">Remarks</span></span>  
 <span data-ttu-id="4186b-111">I valori validi per questa proprietà varieranno a seconda del valore della proprietà [DatabaseLogonType](configurationsetting-property-databaselogontype.md) .</span><span class="sxs-lookup"><span data-stu-id="4186b-111">Valid values for this property will vary depending on the value of the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property.</span></span>  
  
 <span data-ttu-id="4186b-112">Questa proprietà viene ignorata se la proprietà [DatabaseLogonType](configurationsetting-property-databaselogontype.md) è impostata su `2 (Service)` .</span><span class="sxs-lookup"><span data-stu-id="4186b-112">This property is ignored if the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property is set to `2 (Service)`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4186b-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4186b-113">Requirements</span></span>  
 <span data-ttu-id="4186b-114">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4186b-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4186b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4186b-115">See Also</span></span>  
 [<span data-ttu-id="4186b-116">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="4186b-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
