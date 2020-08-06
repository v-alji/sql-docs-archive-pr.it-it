---
title: Proprietà SqlServiceType (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: dbff2968-3011-41d6-a141-52d814af0213
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 18e0fc741d19eefbb93dbcb7fb6fd4a221ce86d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717622"
---
# <a name="sqlservicetype-property-sqlservice-class"></a><span data-ttu-id="2911a-102">Proprietà SqlServiceType (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="2911a-102">SqlServiceType Property (SqlService Class)</span></span>
  <span data-ttu-id="2911a-103">Ottiene il tipo del servizio gestito.</span><span class="sxs-lookup"><span data-stu-id="2911a-103">Gets the type of the managed service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2911a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2911a-104">Syntax</span></span>  
  
```  
  
object  
.SqlServiceType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="2911a-105">Parti</span><span class="sxs-lookup"><span data-stu-id="2911a-105">Parts</span></span>  
 <span data-ttu-id="2911a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="2911a-106">*object*</span></span>  
 <span data-ttu-id="2911a-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="2911a-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2911a-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2911a-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="2911a-109">Valore uint32 che specifica il tipo di servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2911a-109">A uint32 value that specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2911a-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2911a-110">Remarks</span></span>  
 <span data-ttu-id="2911a-111">I possibili valori restituiti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2911a-111">Return values can be one of the following:</span></span>  
  
|<span data-ttu-id="2911a-112">Type</span><span class="sxs-lookup"><span data-stu-id="2911a-112">Type</span></span>|<span data-ttu-id="2911a-113">Definizione</span><span class="sxs-lookup"><span data-stu-id="2911a-113">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="2911a-114">*1*</span><span class="sxs-lookup"><span data-stu-id="2911a-114">*1*</span></span>|<span data-ttu-id="2911a-115">MSSQLSERVER è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2911a-115">MSSQLSERVER is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="2911a-116">*2*</span><span class="sxs-lookup"><span data-stu-id="2911a-116">*2*</span></span>|<span data-ttu-id="2911a-117">SQLSERVERAGENT è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="2911a-117">SQLSERVERAGENT is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service.</span></span>|  
|<span data-ttu-id="2911a-118">*3*</span><span class="sxs-lookup"><span data-stu-id="2911a-118">*3*</span></span>|<span data-ttu-id="2911a-119">MSFTESQL è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] del motore di ricerca full-text.</span><span class="sxs-lookup"><span data-stu-id="2911a-119">MSFTESQL is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Full-text Search Engine service.</span></span>|  
|<span data-ttu-id="2911a-120">*4*</span><span class="sxs-lookup"><span data-stu-id="2911a-120">*4*</span></span>|<span data-ttu-id="2911a-121">MsDtsServer è il servizio [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2911a-121">MsDtsServer is the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="2911a-122">*5*</span><span class="sxs-lookup"><span data-stu-id="2911a-122">*5*</span></span>|<span data-ttu-id="2911a-123">MSSQLServerOLAPService è il servizio [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2911a-123">MSSQLServerOLAPService is the [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="2911a-124">*6*</span><span class="sxs-lookup"><span data-stu-id="2911a-124">*6*</span></span>|<span data-ttu-id="2911a-125">ReportServer è il servizio [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2911a-125">ReportServer is the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service.</span></span>|  
|<span data-ttu-id="2911a-126">*7*</span><span class="sxs-lookup"><span data-stu-id="2911a-126">*7*</span></span>|<span data-ttu-id="2911a-127">SQLBrowser è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser.</span><span class="sxs-lookup"><span data-stu-id="2911a-127">SQLBrowser is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2911a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2911a-128">See Also</span></span>  
 <span data-ttu-id="2911a-129">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="2911a-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
