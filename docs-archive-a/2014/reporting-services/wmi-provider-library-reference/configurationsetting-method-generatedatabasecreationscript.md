---
title: Metodo GenerateDatabaseCreationScript (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseCreationScript method
ms.assetid: 25232dc7-00fe-4cd1-8a1c-7e36d552de00
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e798aa25bec1cc478a6ec2cbdd0c21f44fa8215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627624"
---
# <a name="generatedatabasecreationscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="7de4e-102">Metodo GenerateDatabaseCreationScript (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="7de4e-102">GenerateDatabaseCreationScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="7de4e-103">Genera uno script SQL che può essere utilizzato per creare un database del server di report.</span><span class="sxs-lookup"><span data-stu-id="7de4e-103">Generates a SQL Script that can be used to create a report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7de4e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7de4e-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseCreationScript(ByVal DatabaseName As String, _  
    ByVal Lcid As Int32, ByVal IsSharePointMode As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseCreationScript(string DatabaseName, Int32 Lcid,   
    Boolean IsSharePointMode, out string Script, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7de4e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7de4e-105">Parameters</span></span>  
 <span data-ttu-id="7de4e-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="7de4e-106">*Databasename*</span></span>  
 <span data-ttu-id="7de4e-107">Stringa che contiene il nome del database del server di report da creare.</span><span class="sxs-lookup"><span data-stu-id="7de4e-107">A string containing the name of the report server database to create.</span></span>  
  
 <span data-ttu-id="7de4e-108">*LCID*</span><span class="sxs-lookup"><span data-stu-id="7de4e-108">*Lcid*</span></span>  
 <span data-ttu-id="7de4e-109">Valore utilizzato per localizzazione dei nomi di ruolo.</span><span class="sxs-lookup"><span data-stu-id="7de4e-109">Value used for localization of role names.</span></span>  
  
 <span data-ttu-id="7de4e-110">*IsSharePointMode*</span><span class="sxs-lookup"><span data-stu-id="7de4e-110">*IsSharePointMode*</span></span>  
 <span data-ttu-id="7de4e-111">Indica se creare database in modalità nativa o in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7de4e-111">Indicates whether to create database in native mode or SharePoint mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7de4e-112">A partire [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] da, *IsSharePointMode* = `True` non è supportato perché in modalità SharePoint, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è un servizio condiviso SharePoint e non è controllato dal provider WMI.</span><span class="sxs-lookup"><span data-stu-id="7de4e-112">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], *IsSharePointMode*=`True` is not supported because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is a SharePoint shared service and is not controlled by the WMI provider.</span></span> <span data-ttu-id="7de4e-113">Questo parametro deve essere impostato sempre su `False`.</span><span class="sxs-lookup"><span data-stu-id="7de4e-113">You should always set this parameter to `False`.</span></span>  
  
 <span data-ttu-id="7de4e-114">*Script*</span><span class="sxs-lookup"><span data-stu-id="7de4e-114">*Script*</span></span>  
 <span data-ttu-id="7de4e-115">[out] Stringa che contiene lo script SQL generato.</span><span class="sxs-lookup"><span data-stu-id="7de4e-115">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="7de4e-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="7de4e-116">*HRESULT*</span></span>  
 <span data-ttu-id="7de4e-117">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="7de4e-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7de4e-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7de4e-118">Return Value</span></span>  
 <span data-ttu-id="7de4e-119">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="7de4e-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="7de4e-120">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="7de4e-120">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="7de4e-121">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="7de4e-121">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7de4e-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7de4e-122">Remarks</span></span>  
 <span data-ttu-id="7de4e-123">Questo metodo genera uno script SQL che crea database del server di report per la versione del server di report attualmente connessa.</span><span class="sxs-lookup"><span data-stu-id="7de4e-123">This method generates an SQL script that creates report server databases for the version of the report server currently connected to.</span></span>  
  
 <span data-ttu-id="7de4e-124">Il valore fornito nel parametro *DatabaseName* deve essere conforme alle convenzioni di denominazione dei database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7de4e-124">The value supplied in the *DatabaseName* parameter must conform to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database naming conventions.</span></span>  
  
 <span data-ttu-id="7de4e-125">Il metodo non verifica l'esistenza del database al momento della generazione dello script.</span><span class="sxs-lookup"><span data-stu-id="7de4e-125">The method does not check the existence of the database when generating the script.</span></span>  
  
 <span data-ttu-id="7de4e-126">Questo metodo non verifica l'esistenza del database del server di report al momento della generazione dello script.</span><span class="sxs-lookup"><span data-stu-id="7de4e-126">This method does not check for the existence of the report server database when generating the script.</span></span>  
  
 <span data-ttu-id="7de4e-127">Lo script generato supporta [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 e [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7de4e-127">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7de4e-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7de4e-128">Requirements</span></span>  
 <span data-ttu-id="7de4e-129">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7de4e-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7de4e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7de4e-130">See Also</span></span>  
 [<span data-ttu-id="7de4e-131">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="7de4e-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
