---
title: ICommandWithParameters | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 66644c70-def7-46d8-8c47-b883292a0288
author: rothja
ms.author: jroth
ms.openlocfilehash: df3103181b3cad772e7d1c73068b8864bf591b73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636703"
---
# <a name="icommandwithparameters"></a><span data-ttu-id="b4e47-102">ICommandWithParameters</span><span class="sxs-lookup"><span data-stu-id="b4e47-102">ICommandWithParameters</span></span>
  <span data-ttu-id="b4e47-103">I miglioramenti apportati al motore di database a partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] consentono a ICommandWithParameters::GetParameterInfo di ottenere descrizioni più accurate dei risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="b4e47-103">Improvements in the database engine beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow ICommandWithParameters::GetParameterInfo to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="b4e47-104">È possibile che questi risultati più accurati differiscano dai valori restituiti da CommandWithParameters::GetParameterInfo nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4e47-104">These more accurate results may differ from the values returned by CommandWithParameters::GetParameterInfo in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b4e47-105">Per altre informazioni, vedere [Metadata Discovery](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="b4e47-105">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="b4e47-106">A partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], inoltre, quando si chiama ICommandWithParameters::SetParameterInfo, il valore passato al parametro *pwszName* deve essere un identificatore valido.</span><span class="sxs-lookup"><span data-stu-id="b4e47-106">Also beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], when calling ICommandWithParameters::SetParameterInfo, the value passed to the *pwszName* parameter must be a valid identifier.</span></span> <span data-ttu-id="b4e47-107">Per altre informazioni, vedere [Identificatori del database](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="b4e47-107">For more information, see [Database Identifiers](../databases/database-identifiers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4e47-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4e47-108">See Also</span></span>  
 [<span data-ttu-id="b4e47-109">Interfacce &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b4e47-109">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
