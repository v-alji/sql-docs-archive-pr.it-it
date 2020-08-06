---
title: Proprietà SqlServiceType (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: 20f1663a-9a14-4f14-8c1b-8aa133e272c3
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 774c8599fd21e330fa3228336ab1ed3c73d65c85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637672"
---
# <a name="sqlservicetype-property-sqlserviceadvancedproperty-class"></a><span data-ttu-id="97adf-102">Proprietà SqlServiceType (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="97adf-102">SqlServiceType Property (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="97adf-103">Ottiene il tipo del servizio gestito associato alla proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="97adf-103">Gets the type of the managed service associated with the advanced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97adf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97adf-104">Syntax</span></span>  
  
```  
  
object  
.SetBoolValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="97adf-105">Parti</span><span class="sxs-lookup"><span data-stu-id="97adf-105">Parts</span></span>  
 <span data-ttu-id="97adf-106">*object*</span><span class="sxs-lookup"><span data-stu-id="97adf-106">*object*</span></span>  
 <span data-ttu-id="97adf-107">Oggetto della [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) che rappresenta una proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="97adf-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="97adf-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="97adf-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="97adf-109">Valore uint32 che specifica il tipo di servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97adf-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97adf-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="97adf-110">Remarks</span></span>  
 <span data-ttu-id="97adf-111">I possibili valori restituiti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="97adf-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="97adf-112">Type</span><span class="sxs-lookup"><span data-stu-id="97adf-112">Type</span></span>|<span data-ttu-id="97adf-113">Definizione</span><span class="sxs-lookup"><span data-stu-id="97adf-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="97adf-114">*1*</span><span class="sxs-lookup"><span data-stu-id="97adf-114">*1*</span></span>|<span data-ttu-id="97adf-115">MSSQLSERVER è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97adf-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="97adf-116">*2*</span><span class="sxs-lookup"><span data-stu-id="97adf-116">*2*</span></span>|<span data-ttu-id="97adf-117">SQLSERVERAGENT è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="97adf-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="97adf-118">*3*</span><span class="sxs-lookup"><span data-stu-id="97adf-118">*3*</span></span>|<span data-ttu-id="97adf-119">MSFTESQL è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] del motore di ricerca full-text.</span><span class="sxs-lookup"><span data-stu-id="97adf-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="97adf-120">*4*</span><span class="sxs-lookup"><span data-stu-id="97adf-120">*4*</span></span>|<span data-ttu-id="97adf-121">MsDtsServer è il servizio [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97adf-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="97adf-122">*5*</span><span class="sxs-lookup"><span data-stu-id="97adf-122">*5*</span></span>|<span data-ttu-id="97adf-123">MSSQLServerOLAPService è il servizio [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97adf-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="97adf-124">*6*</span><span class="sxs-lookup"><span data-stu-id="97adf-124">*6*</span></span>|<span data-ttu-id="97adf-125">ReportServer è il servizio [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="97adf-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="97adf-126">*7*</span><span class="sxs-lookup"><span data-stu-id="97adf-126">*7*</span></span>|<span data-ttu-id="97adf-127">SQLBrowser è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="97adf-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97adf-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97adf-128">See Also</span></span>  
 <span data-ttu-id="97adf-129">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="97adf-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
