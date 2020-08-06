---
title: Proprietà Detail | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Detail property
- SoapException class
ms.assetid: c1ddaeb6-c540-49fa-b06e-b6359d377ee8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 060fbaba2b8d4f5a5171e8aa7995432622ba2ba0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719535"
---
# <a name="detail-property"></a><span data-ttu-id="34ab1-102">Proprietà Detail</span><span class="sxs-lookup"><span data-stu-id="34ab1-102">Detail Property</span></span>
  <span data-ttu-id="34ab1-103">La proprietà **Detail** della classe [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException** ha la struttura XML seguente:</span><span class="sxs-lookup"><span data-stu-id="34ab1-103">The **Detail** property of the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException** class has the following XML structure:</span></span>  
  
## <a name="elements"></a><span data-ttu-id="34ab1-104">Elementi</span><span class="sxs-lookup"><span data-stu-id="34ab1-104">Elements</span></span>  
 <span data-ttu-id="34ab1-105">**Dettaglio**</span><span class="sxs-lookup"><span data-stu-id="34ab1-105">**Detail**</span></span>  
 <span data-ttu-id="34ab1-106">Elemento di livello principale che contiene tutti gli altri elementi relativi ai dettagli dell'errore.</span><span class="sxs-lookup"><span data-stu-id="34ab1-106">The top-level element that contains all other error detail elements.</span></span>  
  
 <span data-ttu-id="34ab1-107">**ErrorCode**</span><span class="sxs-lookup"><span data-stu-id="34ab1-107">**ErrorCode**</span></span>  
 <span data-ttu-id="34ab1-108">Codice di errore specifico di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34ab1-108">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-specific error code.</span></span>  
  
 <span data-ttu-id="34ab1-109">**HttpStatus**</span><span class="sxs-lookup"><span data-stu-id="34ab1-109">**HttpStatus**</span></span>  
 <span data-ttu-id="34ab1-110">Codice di stato HTTP.</span><span class="sxs-lookup"><span data-stu-id="34ab1-110">The HTTP status code.</span></span>  
  
 <span data-ttu-id="34ab1-111">**Message**</span><span class="sxs-lookup"><span data-stu-id="34ab1-111">**Message**</span></span>  
 <span data-ttu-id="34ab1-112">Messaggio di errore e codice di errore assegnati dal server di report.</span><span class="sxs-lookup"><span data-stu-id="34ab1-112">The error message and the error code assigned by the report server.</span></span>  
  
 <span data-ttu-id="34ab1-113">**HelpLink**</span><span class="sxs-lookup"><span data-stu-id="34ab1-113">**HelpLink**</span></span>  
 <span data-ttu-id="34ab1-114">URL di collegamento alla Guida che rimanda a un sito Web in cui è possibile trovare ulteriori informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="34ab1-114">The Help link URL to a Web site at which further information about the error can be found.</span></span> <span data-ttu-id="34ab1-115">Per altre informazioni, vedere [Elemento HelpLink](helplink-element.md).</span><span class="sxs-lookup"><span data-stu-id="34ab1-115">For more information, see [HelpLink Element](helplink-element.md).</span></span>  
  
 <span data-ttu-id="34ab1-116">**LinkID**</span><span class="sxs-lookup"><span data-stu-id="34ab1-116">**LinkID**</span></span>  
 <span data-ttu-id="34ab1-117">ID assegnato al collegamento.</span><span class="sxs-lookup"><span data-stu-id="34ab1-117">The ID assigned to the link.</span></span>  
  
 <span data-ttu-id="34ab1-118">**ProductName**</span><span class="sxs-lookup"><span data-stu-id="34ab1-118">**ProductName**</span></span>  
 <span data-ttu-id="34ab1-119">Nome del prodotto.</span><span class="sxs-lookup"><span data-stu-id="34ab1-119">The name of the product.</span></span> <span data-ttu-id="34ab1-120">Il valore predefinito è **Microsoft SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="34ab1-120">The default value is **Microsoft SQL Server Reporting Services**.</span></span>  
  
 <span data-ttu-id="34ab1-121">**ProductVersion**</span><span class="sxs-lookup"><span data-stu-id="34ab1-121">**ProductVersion**</span></span>  
 <span data-ttu-id="34ab1-122">Versione di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34ab1-122">The version of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="34ab1-123">La lunghezza massima è di 15 caratteri.</span><span class="sxs-lookup"><span data-stu-id="34ab1-123">The maximum length is 15 characters.</span></span> <span data-ttu-id="34ab1-124">Il formato del numero di versione deve essere analogo a 8.00.0xxx.00.</span><span class="sxs-lookup"><span data-stu-id="34ab1-124">The format of the version number should be as follows: 8.00.0xxx.00.</span></span>  
  
 <span data-ttu-id="34ab1-125">**ProductLocaleId**</span><span class="sxs-lookup"><span data-stu-id="34ab1-125">**ProductLocaleId**</span></span>  
 <span data-ttu-id="34ab1-126">ID delle impostazioni locali o della lingua della DLL INTL dell'applicazione (ad esempio, 0x41A).</span><span class="sxs-lookup"><span data-stu-id="34ab1-126">The locale ID or language ID of the application's INTL DLL (for example, 0x41A).</span></span>  
  
 <span data-ttu-id="34ab1-127">**OperatingSystem**</span><span class="sxs-lookup"><span data-stu-id="34ab1-127">**OperatingSystem**</span></span>  
 <span data-ttu-id="34ab1-128">Sistema operativo in cui è installato [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34ab1-128">The operating system [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is installed on.</span></span> <span data-ttu-id="34ab1-129">I valori validi includono **0** per indicare una versione indipendente dal sistema operativo, **1** per [!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)] e **16** per Windows XP.</span><span class="sxs-lookup"><span data-stu-id="34ab1-129">Valid values include **0** for operating system independent, **1** for [!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)], and **16** for Windows XP.</span></span>  
  
 <span data-ttu-id="34ab1-130">**CountryLocaleId**</span><span class="sxs-lookup"><span data-stu-id="34ab1-130">**CountryLocaleId**</span></span>  
 <span data-ttu-id="34ab1-131">ID delle impostazioni locali o della lingua del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="34ab1-131">The locale ID or language ID of the operating system.</span></span> <span data-ttu-id="34ab1-132">Il valore della versione francese di Windows è ad esempio 0x040c.</span><span class="sxs-lookup"><span data-stu-id="34ab1-132">For example, the value for the French version of Windows is 0x040c.</span></span>  
  
 <span data-ttu-id="34ab1-133">**MoreInformation**</span><span class="sxs-lookup"><span data-stu-id="34ab1-133">**MoreInformation**</span></span>  
 <span data-ttu-id="34ab1-134">Stringa XML contenente eccezioni nidificate che si sono verificate durante l'esecuzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="34ab1-134">An XML string that contains nested exceptions that occurred while the method ran.</span></span>  
  
 <span data-ttu-id="34ab1-135">**Origine**</span><span class="sxs-lookup"><span data-stu-id="34ab1-135">**Source**</span></span>  
 <span data-ttu-id="34ab1-136">Elemento figlio di **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="34ab1-136">A child element of **MoreInformation**.</span></span> <span data-ttu-id="34ab1-137">Indica l'origine dell'errore.</span><span class="sxs-lookup"><span data-stu-id="34ab1-137">The source of the error.</span></span>  
  
 <span data-ttu-id="34ab1-138">**Message**</span><span class="sxs-lookup"><span data-stu-id="34ab1-138">**Message**</span></span>  
 <span data-ttu-id="34ab1-139">Elemento figlio di **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="34ab1-139">A child element of **MoreInformation**.</span></span> <span data-ttu-id="34ab1-140">Indica il messaggio di errore di un'eccezione nidificata.</span><span class="sxs-lookup"><span data-stu-id="34ab1-140">The error message of a nested exception.</span></span> <span data-ttu-id="34ab1-141">Questo elemento include gli attributi XML per **ErrorCode** e **HelpLink**.</span><span class="sxs-lookup"><span data-stu-id="34ab1-141">This element includes XML attributes for **ErrorCode** and **HelpLink**.</span></span>  
  
 <span data-ttu-id="34ab1-142">**Avvisi**</span><span class="sxs-lookup"><span data-stu-id="34ab1-142">**Warnings**</span></span>  
 <span data-ttu-id="34ab1-143">Stringa XML contenente gli avvisi restituiti dall'elaborazione del report.</span><span class="sxs-lookup"><span data-stu-id="34ab1-143">An XML string that contains the warnings returned from report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ab1-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34ab1-144">See Also</span></span>  
 <span data-ttu-id="34ab1-145">[Introduzione alla gestione delle eccezioni in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="34ab1-145">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 <span data-ttu-id="34ab1-146">[Reporting Services classe SoapException](reporting-services-soapexception-class.md) </span><span class="sxs-lookup"><span data-stu-id="34ab1-146">[Reporting Services SoapException Class](reporting-services-soapexception-class.md) </span></span>  
 [<span data-ttu-id="34ab1-147">Utilizzo della proprietà Detail per la gestione di errori specifici</span><span class="sxs-lookup"><span data-stu-id="34ab1-147">Using the Detail Property to Handle Specific Errors</span></span>](../best-practices/using-the-detail-property-to-handle-specific-errors.md)  
  
  
