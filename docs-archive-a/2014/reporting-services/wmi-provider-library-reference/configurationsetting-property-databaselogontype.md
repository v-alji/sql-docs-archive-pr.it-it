---
title: Proprietà DatabaseLogonType (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonType
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonType property
ms.assetid: 6b592582-4c35-4029-ab86-982fff47d8d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bb5a4149c29fb7532b7140a2616dd856e6db2b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722339"
---
# <a name="databaselogontype-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="f7a83-102">Proprietà DatabaseLogonType (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="f7a83-102">DatabaseLogonType Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="f7a83-103">Specifica se il server di report usa un account del servizio [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, un account utente di Windows o un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per accedere al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="f7a83-103">Specifies whether the report server uses a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows service account, a Windows user account, or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to access the report server database.</span></span> <span data-ttu-id="f7a83-104">Di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="f7a83-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7a83-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7a83-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonType As Integer  
```  
  
```csharp  
public int DatabaseLogonType;  
```  
  
## <a name="property-values"></a><span data-ttu-id="f7a83-106">Valori della proprietà</span><span class="sxs-lookup"><span data-stu-id="f7a83-106">Property Values</span></span>  
 <span data-ttu-id="f7a83-107">Oggetto `integer` che rappresenta il tipo di accesso.</span><span class="sxs-lookup"><span data-stu-id="f7a83-107">An `integer` object that represents the login type.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="f7a83-108">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="f7a83-108">Example Code</span></span>  
 [<span data-ttu-id="f7a83-109">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="f7a83-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="f7a83-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f7a83-110">Remarks</span></span>  
 <span data-ttu-id="f7a83-111">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="f7a83-111">Values are:</span></span>  
  
-   <span data-ttu-id="f7a83-112">0 per l'account di accesso di Windows</span><span class="sxs-lookup"><span data-stu-id="f7a83-112">0 for Windows login</span></span>  
  
-   <span data-ttu-id="f7a83-113">1 per l'account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7a83-113">1 for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login</span></span>  
  
-   <span data-ttu-id="f7a83-114">2 per accedere come servizio</span><span class="sxs-lookup"><span data-stu-id="f7a83-114">2 to log in as a service</span></span>  
  
 <span data-ttu-id="f7a83-115">Se si specifica 0 (Windows), è necessario impostare il valore nella proprietà [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) su un account utente di Windows valido corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f7a83-115">If you specify 0 (Windows), you must set the value in the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) property to a corresponding a valid Windows user account.</span></span>  
  
 <span data-ttu-id="f7a83-116">Se si specifica 1 (SQL Server), accertarsi che il valore di [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) corrisponda a un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valido.</span><span class="sxs-lookup"><span data-stu-id="f7a83-116">If you specify 1 (SQL Server), make sure the value of the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) corresponds to a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="f7a83-117">Se si specifica 2 (servizio Windows), il server di report usa un account di [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] e l'account del servizio Windows per accedere al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="f7a83-117">If you specify 2 (Windows service), the report server uses an [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account and the Windows service account to access the report server database.</span></span> <span data-ttu-id="f7a83-118">La proprietà DatabaseLogonAccount viene ignorata.</span><span class="sxs-lookup"><span data-stu-id="f7a83-118">The DatabaseLogonAccount property is ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7a83-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7a83-119">Requirements</span></span>  
 <span data-ttu-id="f7a83-120">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7a83-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7a83-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7a83-121">See Also</span></span>  
 [<span data-ttu-id="f7a83-122">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="f7a83-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
