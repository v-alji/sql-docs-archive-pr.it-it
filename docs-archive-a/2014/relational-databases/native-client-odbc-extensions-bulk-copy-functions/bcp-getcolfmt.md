---
title: bcp_getcolfmt | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_getcolfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_getcolfmt function
ms.assetid: f8bdada5-7b2d-4475-8c98-f93e9d77b130
author: rothja
ms.author: jroth
ms.openlocfilehash: aabc811a5aa0babe5119c4ef0ed0e649586d73cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626766"
---
# <a name="bcp_getcolfmt"></a><span data-ttu-id="a6a33-102">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="a6a33-102">bcp_getcolfmt</span></span>
  <span data-ttu-id="a6a33-103">Utilizzato per trovare il valore della proprietà di formato di colonna.</span><span class="sxs-lookup"><span data-stu-id="a6a33-103">Used to find the column format property value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6a33-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6a33-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_getcolfmt (  
HDBC   
hdbc  
,  
INT   
field  
,  
INT   
property  
,  
void*   
pValue  
,  
INT   
cbvalue,  
INT*   
pcbLen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a6a33-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a6a33-105">Arguments</span></span>  
 <span data-ttu-id="a6a33-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="a6a33-106">*hdbc*</span></span>  
 <span data-ttu-id="a6a33-107">Handle di connessione ODBC abilitato per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="a6a33-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="a6a33-108">*campo*</span><span class="sxs-lookup"><span data-stu-id="a6a33-108">*field*</span></span>  
 <span data-ttu-id="a6a33-109">Numero di colonna per cui viene recuperata la proprietà.</span><span class="sxs-lookup"><span data-stu-id="a6a33-109">Is the column number for which the property is retrieved.</span></span>  
  
 <span data-ttu-id="a6a33-110">*property*</span><span class="sxs-lookup"><span data-stu-id="a6a33-110">*property*</span></span>  
 <span data-ttu-id="a6a33-111">Una delle costanti di proprietà.</span><span class="sxs-lookup"><span data-stu-id="a6a33-111">Is one of the property constants.</span></span>  
  
 <span data-ttu-id="a6a33-112">*pValue*</span><span class="sxs-lookup"><span data-stu-id="a6a33-112">*pValue*</span></span>  
 <span data-ttu-id="a6a33-113">Puntatore al buffer dal quale recuperare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="a6a33-113">Is the pointer to the buffer from which to retrieve the property value.</span></span>  
  
 <span data-ttu-id="a6a33-114">*cbValue*</span><span class="sxs-lookup"><span data-stu-id="a6a33-114">*cbValue*</span></span>  
 <span data-ttu-id="a6a33-115">Lunghezza in byte del buffer delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="a6a33-115">Is the length of the property buffer in bytes.</span></span>  
  
 <span data-ttu-id="a6a33-116">*pcbLen*</span><span class="sxs-lookup"><span data-stu-id="a6a33-116">*pcbLen*</span></span>  
 <span data-ttu-id="a6a33-117">IIndicatore di misura relativo alla lunghezza dei dati restituiti nel buffer delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="a6a33-117">Pointer to length of the data that is being returned in the property buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="a6a33-118">Restituisce</span><span class="sxs-lookup"><span data-stu-id="a6a33-118">Returns</span></span>  
 <span data-ttu-id="a6a33-119">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="a6a33-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6a33-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a6a33-120">Remarks</span></span>  
 <span data-ttu-id="a6a33-121">I valori delle proprietà di formato della colonna sono elencati nell'argomento [bcp_setcolfmt](bcp-setcolfmt.md) .</span><span class="sxs-lookup"><span data-stu-id="a6a33-121">Column format property values are listed in the [bcp_setcolfmt](bcp-setcolfmt.md) topic.</span></span> <span data-ttu-id="a6a33-122">I valori delle proprietà di formato della colonna vengono impostati chiamando la funzione **bcp_setcolfmt** e viene utilizzata la funzione **bcp_getcolfmt** per individuare il valore della proprietà formato colonna.</span><span class="sxs-lookup"><span data-stu-id="a6a33-122">The column format property values are set by calling the **bcp_setcolfmt** function, and the **bcp_getcolfmt** function is used to find the column format property value.</span></span>  
  
 <span data-ttu-id="a6a33-123">Le modifiche del comportamento possono essere osservate quando ci si connette a un [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] computer server (o versione successiva) rispetto alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="a6a33-123">Behavior changes may be observed when connecting to a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] (or later) server computer, compared to earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versions.</span></span> <span data-ttu-id="a6a33-124">Per altre informazioni, vedere [Metadata Discovery](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="a6a33-124">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="bcp_getcolfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="a6a33-125">Supporto di bcp_getcolfmt per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="a6a33-125">bcp_getcolfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="a6a33-126">I tipi utilizzati con la `BCP_FMT_TYPE` proprietà per i tipi data/ora sono specificati nelle [modifiche della copia bulk per i tipi di data e ora avanzati &#40;OLE DB e&#41;ODBC ](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a6a33-126">The types used with the `BCP_FMT_TYPE` property for date/time types are as specified in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="a6a33-127">Per ulteriori informazioni, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a6a33-127">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a33-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6a33-128">See Also</span></span>  
 [<span data-ttu-id="a6a33-129">Funzioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="a6a33-129">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
