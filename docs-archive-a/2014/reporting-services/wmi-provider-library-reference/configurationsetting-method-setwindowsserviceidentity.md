---
title: Metodo SetWindowsServiceIdentity (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetWindowsServiceIdentity method
ms.assetid: 9bbc734c-9e69-48c2-8bec-8abe7c6cc987
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 15d1b7fa5fc6d69a963785cdaf976c80623c47f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722352"
---
# <a name="setwindowsserviceidentity-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="609fb-102">Metodo SetWindowsServiceIdentity (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="609fb-102">SetWindowsServiceIdentity Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="609fb-103">Consente l'esecuzione del servizio Windows ReportServer in base a un utente di Windows specificato e concede a tale account autorizzazioni per il file system sufficienti, in modo da consentire il funzionamento del server di report.</span><span class="sxs-lookup"><span data-stu-id="609fb-103">Makes the Report Server Windows service run as a specified Windows user, and grants this account sufficient file system permissions to allow the report server to operate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="609fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="609fb-104">Syntax</span></span>  
  
```vb  
Public Sub SetWindowsServiceIdentity(UseBuiltInAccount as Boolean, _  
    Account as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetWindowsServiceIdentity(boolean UseBuiltInAccount,   
    string Account, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="609fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="609fb-105">Parameters</span></span>  
 <span data-ttu-id="609fb-106">*UseBuiltInAccount*</span><span class="sxs-lookup"><span data-stu-id="609fb-106">*UseBuiltInAccount*</span></span>  
 <span data-ttu-id="609fb-107">Indica se l'account specificato è un account predefinito di Windows.</span><span class="sxs-lookup"><span data-stu-id="609fb-107">Indicates whether the specified account is a built-in Windows account.</span></span>  
  
 <span data-ttu-id="609fb-108">*Account*</span><span class="sxs-lookup"><span data-stu-id="609fb-108">*Account*</span></span>  
 <span data-ttu-id="609fb-109">Account di Windows da utilizzare per eseguire il servizio Windows, nel formato "DOMAIN\alias."</span><span class="sxs-lookup"><span data-stu-id="609fb-109">The Windows account to use to run the Windows service, in the format "DOMAIN\alias".</span></span>  
  
 <span data-ttu-id="609fb-110">*Password*</span><span class="sxs-lookup"><span data-stu-id="609fb-110">*Password*</span></span>  
 <span data-ttu-id="609fb-111">Password per l'account.</span><span class="sxs-lookup"><span data-stu-id="609fb-111">The password for the account.</span></span>  
  
 <span data-ttu-id="609fb-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="609fb-112">*HRESULT*</span></span>  
 <span data-ttu-id="609fb-113">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="609fb-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="609fb-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="609fb-114">Return Value</span></span>  
 <span data-ttu-id="609fb-115">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="609fb-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="609fb-116">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="609fb-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="609fb-117">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="609fb-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="609fb-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="609fb-118">Remarks</span></span>  
 <span data-ttu-id="609fb-119">Quando il parametro *UseBuiltInAccount* è impostato `true` su e il server di report è in esecuzione in Microsoft [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] o Windows XP, il valore dei parametri *Name*, *Domain*e *password* viene ignorato e viene usato l'account di sistema locale.</span><span class="sxs-lookup"><span data-stu-id="609fb-119">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Microsoft [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] or Windows XP, the value of the *Name*, *Domain*, and *Password* parameters are ignored and the Local system account is used.</span></span>  
  
 <span data-ttu-id="609fb-120">Quando il parametro *UseBuiltInAccount* è impostato su `true` e il server di report è in esecuzione in Windows Server 2003, le proprietà di *dominio* e *password* vengono ignorate e il campo del nome deve contenere "Builtin\System" o "," o "Builtin\LocalService".</span><span class="sxs-lookup"><span data-stu-id="609fb-120">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Windows Server 2003, the *Domain* and *Password* properties are ignored, and the name field must contain either "Builtin\NetworkService" or "Builtin\System" or "Builtin\LocalService".</span></span>  
  
 <span data-ttu-id="609fb-121">Il metodo SetWindowsServiceIdentity imposta le autorizzazioni per i file su file e cartelle nella directory di installazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="609fb-121">The SetWindowsServiceIdentity method sets file permissions on files and folders in the report server installation directory.</span></span>  
  
 <span data-ttu-id="609fb-122">Per l'account specificato nel parametro *account* sono necessari `LogonAsService` i diritti di Windows.</span><span class="sxs-lookup"><span data-stu-id="609fb-122">The account specified in the *Account* parameter requires `LogonAsService` rights in Windows.</span></span> <span data-ttu-id="609fb-123">Il metodo concede questo diritto all'account specificato.</span><span class="sxs-lookup"><span data-stu-id="609fb-123">The method grants this right to the specified account.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="609fb-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="609fb-124">Requirements</span></span>  
 <span data-ttu-id="609fb-125">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="609fb-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="609fb-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="609fb-126">See Also</span></span>  
 [<span data-ttu-id="609fb-127">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="609fb-127">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
