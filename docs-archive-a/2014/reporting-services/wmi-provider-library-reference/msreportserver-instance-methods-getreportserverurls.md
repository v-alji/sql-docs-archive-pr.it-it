---
title: Metodo GetReportServerUrls (MSReportServer_Instance WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetReportServerUrls method
ms.assetid: 4865e32c-0114-465a-be8c-be223a7bc09e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f36a5ba10c05276cffabc155e5289d675db8dae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717321"
---
# <a name="getreportserverurls-method-wmi-msreportserver_instance"></a><span data-ttu-id="e5805-102">Metodo GetReportServerUrls (MSReportServer_Instance WMI)</span><span class="sxs-lookup"><span data-stu-id="e5805-102">GetReportServerUrls Method (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="e5805-103">Restituisce un elenco degli URL che è possibile utilizzare per accedere al server di report e alla gestione report.</span><span class="sxs-lookup"><span data-stu-id="e5805-103">Returns a list of URLs users can use to access the report server and report manager.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5805-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5805-104">Syntax</span></span>  
  
```vb  
Public Sub GetReportServerUrls (ByRef ApplicationName() As String, ByRef URLs()_  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetReportServerUrls(out string[] applicationName,   
    out string[] URLs, out int length, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5805-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5805-105">Parameters</span></span>  
 <span data-ttu-id="e5805-106">*ApplicationName[]*</span><span class="sxs-lookup"><span data-stu-id="e5805-106">*ApplicationName[]*</span></span>  
 <span data-ttu-id="e5805-107">Matrice che contiene le applicazioni installate.</span><span class="sxs-lookup"><span data-stu-id="e5805-107">An array that contains the applications that are installed.</span></span> <span data-ttu-id="e5805-108">I valori sono `ReportServerWebService` e `ReportManager`.</span><span class="sxs-lookup"><span data-stu-id="e5805-108">Values are either `ReportServerWebService` or `ReportManager`.</span></span>  
  
 <span data-ttu-id="e5805-109">*URLs[]*</span><span class="sxs-lookup"><span data-stu-id="e5805-109">*URLs[]*</span></span>  
 <span data-ttu-id="e5805-110">Matrice che contiene gli URL registrati correttamente.</span><span class="sxs-lookup"><span data-stu-id="e5805-110">An array that contains the successfully registered Urls.</span></span>  
  
 <span data-ttu-id="e5805-111">*Lunghezza*</span><span class="sxs-lookup"><span data-stu-id="e5805-111">*Length*</span></span>  
 <span data-ttu-id="e5805-112">Valore intero che contiene la lunghezza delle matrici restituite.</span><span class="sxs-lookup"><span data-stu-id="e5805-112">An integer value that contains the length of the arrays returned.</span></span>  
  
 <span data-ttu-id="e5805-113">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="e5805-113">*HRESULT*</span></span>  
 <span data-ttu-id="e5805-114">Valore che indica l'esito positivo o un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e5805-114">A value that indicates success or an error code.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="e5805-115">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="e5805-115">Return Values</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5805-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e5805-116">Remarks</span></span>  
 <span data-ttu-id="e5805-117">I metodi esposti dagli oggetti di gestione WMI vengono chiamati tramite la funzione InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="e5805-117">Methods exposed by WMI management objects are called through the InvokeMethod function.</span></span> <span data-ttu-id="e5805-118">Per altre informazioni, vedere gli argomenti relativi all'esecuzione di metodi in oggetti di gestione all'interno della documentazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework WMI.</span><span class="sxs-lookup"><span data-stu-id="e5805-118">For more information, please see "Executing Methods on Management Objects" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework WMI documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5805-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5805-119">Requirements</span></span>  
 <span data-ttu-id="e5805-120">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5805-120">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5805-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5805-121">See Also</span></span>  
 [<span data-ttu-id="e5805-122">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="e5805-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
