---
title: Metodo SetUnattendedExecutionAccount (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetUnattendedExecutionAccount method
ms.assetid: 1ba6be6f-b05c-4ea0-af98-cd0780290b70
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 73cf4c633c51de1e3e6b878c66d73ee710e98df6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722368"
---
# <a name="setunattendedexecutionaccount-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="f1f6d-102">Metodo SetUnattendedExecutionAccount (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="f1f6d-102">SetUnattendedExecutionAccount Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="f1f6d-103">Specifica l'account utilizzato per l'esecuzione automatica dei report.</span><span class="sxs-lookup"><span data-stu-id="f1f6d-103">Specifies the account used to execute reports unattended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f6d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1f6d-104">Syntax</span></span>  
  
```vb  
Public Sub SetUnattendedExecutionAccount(UserName as String, _  
    Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetUnattendedExecutionAccount (string UserName,   
    string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1f6d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1f6d-105">Parameters</span></span>  
 <span data-ttu-id="f1f6d-106">*UserName*</span><span class="sxs-lookup"><span data-stu-id="f1f6d-106">*UserName*</span></span>  
 <span data-ttu-id="f1f6d-107">Account di Windows da utilizzare per le esecuzioni automatiche.</span><span class="sxs-lookup"><span data-stu-id="f1f6d-107">A Windows account to be used for unattended executions.</span></span>  
  
 <span data-ttu-id="f1f6d-108">*Password*</span><span class="sxs-lookup"><span data-stu-id="f1f6d-108">*Password*</span></span>  
 <span data-ttu-id="f1f6d-109">Password per l'account specificato.</span><span class="sxs-lookup"><span data-stu-id="f1f6d-109">The password for the specified account.</span></span>  
  
 <span data-ttu-id="f1f6d-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="f1f6d-110">*HRESULT*</span></span>  
 <span data-ttu-id="f1f6d-111">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="f1f6d-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1f6d-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f1f6d-112">Return Value</span></span>  
 <span data-ttu-id="f1f6d-113">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="f1f6d-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="f1f6d-114">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="f1f6d-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="f1f6d-115">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="f1f6d-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1f6d-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f1f6d-116">Remarks</span></span>  
 <span data-ttu-id="f1f6d-117">Il metodo SetUnattendedExecutionAccount non verifica se il server di report può accedere come utente specificato.</span><span class="sxs-lookup"><span data-stu-id="f1f6d-117">The SetUnattendedExecutionAccount method does not verify whether the report server can log in as the specified user.</span></span>  
  
 <span data-ttu-id="f1f6d-118">Non è possibile usare il metodo SetUnattendedExecutionAccount per effettuare esecuzioni automatiche nel contesto del servizio Windows del server di report.</span><span class="sxs-lookup"><span data-stu-id="f1f6d-118">It is not possible to use the SetUnattendedExecutionAccount method to run unattended executions in the context of the report server Windows service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1f6d-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1f6d-119">Requirements</span></span>  
 <span data-ttu-id="f1f6d-120">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1f6d-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f6d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1f6d-121">See Also</span></span>  
 [<span data-ttu-id="f1f6d-122">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="f1f6d-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
