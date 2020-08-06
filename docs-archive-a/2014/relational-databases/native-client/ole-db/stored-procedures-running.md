---
title: Esecuzione di stored procedure (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [OLE DB], executing
- OLE DB, stored procedures
- SQL Server Native Client OLE DB provider, stored procedures
ms.assetid: c77d9be9-2176-4438-8c7a-04b63ebece08
author: rothja
ms.author: jroth
ms.openlocfilehash: 2e6ce951f343002feea5aa793d0cc2092422b819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722695"
---
# <a name="running-stored-procedures-ole-db"></a><span data-ttu-id="59acc-102">Esecuzione di stored procedure (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="59acc-102">Running Stored Procedures (OLE DB)</span></span>
  <span data-ttu-id="59acc-103">Durante l'esecuzione di istruzioni, la chiamata a una stored procedure nell'origine dati, in alternativa all'esecuzione o alla preparazione diretta di un'istruzione nell'applicazione client, può offrire i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="59acc-103">When executing statements, calling a stored procedure on the data source (instead of executing or preparing a statement in the client application directly) can provide:</span></span>  
  
-   <span data-ttu-id="59acc-104">Prestazioni più elevate.</span><span class="sxs-lookup"><span data-stu-id="59acc-104">Higher performance.</span></span>  
  
-   <span data-ttu-id="59acc-105">Overhead di rete ridotto.</span><span class="sxs-lookup"><span data-stu-id="59acc-105">Reduced network overhead.</span></span>  
  
-   <span data-ttu-id="59acc-106">Maggiore consistenza.</span><span class="sxs-lookup"><span data-stu-id="59acc-106">Better consistency.</span></span>  
  
-   <span data-ttu-id="59acc-107">Maggiore precisione.</span><span class="sxs-lookup"><span data-stu-id="59acc-107">Better accuracy.</span></span>  
  
-   <span data-ttu-id="59acc-108">Maggior numero di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="59acc-108">Added functionality.</span></span>  
  
 <span data-ttu-id="59acc-109">Il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta tre dei meccanismi [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizzati dalle stored procedure per restituire i dati:</span><span class="sxs-lookup"><span data-stu-id="59acc-109">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports three of the mechanisms that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] stored procedures use to return data:</span></span>  
  
-   <span data-ttu-id="59acc-110">Ogni istruzione SELECT nella procedura genera un set di risultati.</span><span class="sxs-lookup"><span data-stu-id="59acc-110">Every SELECT statement in the procedure generates a result set.</span></span>  
  
-   <span data-ttu-id="59acc-111">La procedura può restituire dati tramite parametri di output.</span><span class="sxs-lookup"><span data-stu-id="59acc-111">The procedure can return data through output parameters.</span></span>  
  
-   <span data-ttu-id="59acc-112">La procedura può avere un codice restituito di tipo integer.</span><span class="sxs-lookup"><span data-stu-id="59acc-112">The procedure can have an integer return code.</span></span>  
  
 <span data-ttu-id="59acc-113">L'applicazione deve essere in grado di gestire tutti questi output dalle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="59acc-113">The application must be able to handle all of these outputs from stored procedures.</span></span>  
  
 <span data-ttu-id="59acc-114">Provider OLE DB diversi restituiscono parametri di output e valori in momenti diversi durante l'elaborazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="59acc-114">Different OLE DB providers return output parameters and return values at different times during result processing.</span></span> <span data-ttu-id="59acc-115">Nel caso del [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native client, i parametri di output e i codici restituiti non vengono forniti fino a quando il consumer non ha recuperato o annullato i set di risultati restituiti dall'stored procedure.</span><span class="sxs-lookup"><span data-stu-id="59acc-115">In case of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the output parameters and return codes are not supplied until after the consumer has retrieved or canceled the result sets returned by the stored procedure.</span></span> <span data-ttu-id="59acc-116">I codici e i parametri di output vengono restituiti nell'ultimo pacchetto TDS dal server.</span><span class="sxs-lookup"><span data-stu-id="59acc-116">The return codes and the output parameters are returned in the last TDS packet from the server.</span></span>  
  
 <span data-ttu-id="59acc-117">I provider utilizzano la proprietà DBPROP_OUTPUTPARAMETERAVAILABILITY per segnalare la restituzione di parametri di output e valori.</span><span class="sxs-lookup"><span data-stu-id="59acc-117">Providers use the DBPROP_OUTPUTPARAMETERAVAILABILITY property to report when it returns output parameters and return values.</span></span> <span data-ttu-id="59acc-118">Questa proprietà è inclusa nel set di proprietà DBPROPSET_DATASOURCEINFO.</span><span class="sxs-lookup"><span data-stu-id="59acc-118">This property is in the DBPROPSET_DATASOURCEINFO property set.</span></span>  
  
 <span data-ttu-id="59acc-119">Il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client imposta la proprietà DBPROP_OUTPUTPARAMETERAVAILABILITY su DBPROPVAL_OA_ATROWRELEASE per indicare che i codici restituiti e i parametri di output non vengono restituiti finché il set di risultati non viene elaborato o rilasciato.</span><span class="sxs-lookup"><span data-stu-id="59acc-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider sets the DBPROP_OUTPUTPARAMETERAVAILABILITY property to DBPROPVAL_OA_ATROWRELEASE to indicate that return codes and output parameters are not returned until the result set is processed or released.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59acc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59acc-120">See Also</span></span>  
 [<span data-ttu-id="59acc-121">Stored procedure</span><span class="sxs-lookup"><span data-stu-id="59acc-121">Stored Procedures</span></span>](stored-procedures.md)  
  
  
