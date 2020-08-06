---
title: Metodo GenerateDatabaseUpgradeScript (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseUpgradeScript method
ms.assetid: 88534e8e-2877-41cd-b5c2-b1d33a0fd203
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a619584b9f1cc095f8f624670386d388426e4a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627621"
---
# <a name="generatedatabaseupgradescript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="4eebf-102">Metodo GenerateDatabaseUpgradeScript (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="4eebf-102">GenerateDatabaseUpgradeScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="4eebf-103">Genera uno script che può essere usato per aggiornare il database del server di report allo schema di [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4eebf-103">Generates a script that can be used to upgrade the report server database to the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eebf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4eebf-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseUpgradeScript(DatabaseName as String, _  
    ServerVersion as String, ByRef Script as String, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GenerateDatabaseUpgradeScript (string DatabaseName,   
    string ServerVersion, out string Script,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4eebf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4eebf-105">Parameters</span></span>  
 <span data-ttu-id="4eebf-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="4eebf-106">*Databasename*</span></span>  
 <span data-ttu-id="4eebf-107">Stringa che contiene il nome del database del server di report da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="4eebf-107">A string containing the name of the report server database to upgrade.</span></span>  
  
 <span data-ttu-id="4eebf-108">*ServerVersion*</span><span class="sxs-lookup"><span data-stu-id="4eebf-108">*ServerVersion*</span></span>  
 <span data-ttu-id="4eebf-109">Stringa che contiene la versione del server di report.</span><span class="sxs-lookup"><span data-stu-id="4eebf-109">A string containing the version of the report server.</span></span>  
  
 <span data-ttu-id="4eebf-110">*Script*</span><span class="sxs-lookup"><span data-stu-id="4eebf-110">*Script*</span></span>  
 <span data-ttu-id="4eebf-111">[out] Stringa che contiene lo script SQL generato.</span><span class="sxs-lookup"><span data-stu-id="4eebf-111">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="4eebf-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="4eebf-112">*HRESULT*</span></span>  
 <span data-ttu-id="4eebf-113">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="4eebf-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4eebf-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4eebf-114">Return Value</span></span>  
 <span data-ttu-id="4eebf-115">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="4eebf-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="4eebf-116">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="4eebf-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="4eebf-117">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="4eebf-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4eebf-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4eebf-118">Remarks</span></span>  
 <span data-ttu-id="4eebf-119">Lo script generato supporta [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]e [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4eebf-119">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4eebf-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4eebf-120">Requirements</span></span>  
 <span data-ttu-id="4eebf-121">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eebf-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eebf-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4eebf-122">See Also</span></span>  
 [<span data-ttu-id="4eebf-123">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="4eebf-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
