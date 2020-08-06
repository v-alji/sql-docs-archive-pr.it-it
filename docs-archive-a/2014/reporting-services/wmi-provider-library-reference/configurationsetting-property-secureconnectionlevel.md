---
title: Proprietà SecureConnectionLevel (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SecureConnectionLevel
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SecureConnectionLevel property
ms.assetid: fd5549e7-b874-41e2-866e-2f58caf6f733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5d1b3bccc8a7fee3899fa21208d83a718a33f5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722316"
---
# <a name="secureconnectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="39b90-102">Proprietà SecureConnectionLevel (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="39b90-102">SecureConnectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="39b90-103">Restituisce il livello di connessione protetta specificato nel file RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="39b90-103">Returns the secure connection level specified in the RSReportServer.config file.</span></span> <span data-ttu-id="39b90-104">Di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="39b90-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b90-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39b90-105">Syntax</span></span>  
  
```vb  
Public Dim SecureConnectionLevel As Integer  
```  
  
```csharp  
public Integer SecureConnectionLevel;  
```  
  
## <a name="property-values"></a><span data-ttu-id="39b90-106">Valori della proprietà</span><span class="sxs-lookup"><span data-stu-id="39b90-106">Property Values</span></span>  
 <span data-ttu-id="39b90-107">Valore `Integer` che rappresenta il livello di connessione protetto.</span><span class="sxs-lookup"><span data-stu-id="39b90-107">An `Integer` value that represents the secure connection level.</span></span> <span data-ttu-id="39b90-108">I valori restituiti indicano se SSL è o non è configurato.</span><span class="sxs-lookup"><span data-stu-id="39b90-108">The return values indicate that the SSL is either configured or not.</span></span> <span data-ttu-id="39b90-109">Il valore maggiore di o pari a 1 indica che SSL è abilitato.</span><span class="sxs-lookup"><span data-stu-id="39b90-109">A value of greater than or equal to 1 indicates that SSL is turned on.</span></span> <span data-ttu-id="39b90-110">Il valore 0 indica che SSL è disattivato.</span><span class="sxs-lookup"><span data-stu-id="39b90-110">A value of 0 indicates that SSL is turned off.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="39b90-111">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="39b90-111">Example Code</span></span>  
 [<span data-ttu-id="39b90-112">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="39b90-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="39b90-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39b90-113">Requirements</span></span>  
 <span data-ttu-id="39b90-114">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39b90-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b90-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39b90-115">See Also</span></span>  
 [<span data-ttu-id="39b90-116">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="39b90-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
