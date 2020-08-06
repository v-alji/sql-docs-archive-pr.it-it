---
title: Informazioni di rappresentazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42319d60-ccd0-46b8-af0b-f0968c390d8a
author: minewiskan
ms.author: owend
ms.openlocfilehash: f9226fdbe8656aecf0f9173976c67ee386040d6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712604"
---
# <a name="impersonation-information"></a><span data-ttu-id="8e9b7-102">Impostazioni di rappresentazione</span><span class="sxs-lookup"><span data-stu-id="8e9b7-102">Impersonation Information</span></span>
  <span data-ttu-id="8e9b7-103">Usare la pagina **Impostazioni di rappresentazione** per specificare le credenziali usate da Analysis Services per la connessione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-103">Use the **Impersonation Information** page to specify the credentials that Analysis Services will use to connect to the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8e9b7-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8e9b7-104">Options</span></span>  
 <span data-ttu-id="8e9b7-105">**Usa nome utente e password specifici di Windows**</span><span class="sxs-lookup"><span data-stu-id="8e9b7-105">**Use a specific Windows user name and password**</span></span>  
 <span data-ttu-id="8e9b7-106">Selezionare questa opzione per fare in modo che l'oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] usi le credenziali di sicurezza di un account utente di Windows specificato.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-106">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of a specified Windows user account.</span></span> <span data-ttu-id="8e9b7-107">Le credenziali specificate verranno usate per l'elaborazione, le query ROLAP, le associazioni out-of-line, i cubi locali, i modelli di data mining, le partizioni remote, gli oggetti collegati e la sincronizzazione dalla destinazione all’origine.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-107">The specified credentials will be used for processing, ROLAP queries, out-of-line bindings, local cubes, mining models, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="8e9b7-108">Per le istruzioni DMX (Data Mining Extensions) OPENQUERY, invece, questa opzione viene ignorata e verranno usate le credenziali dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-108">However, for Data Mining Extensions (DMX) OPENQUERY statements, this option is ignored and the credentials of the current user will be used.</span></span>  
  
 <span data-ttu-id="8e9b7-109">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="8e9b7-109">**User name**</span></span>  
 <span data-ttu-id="8e9b7-110">Digitare il dominio e il nome dell'account utente che verranno usati dall'oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] selezionato.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-110">Type the domain and name of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="8e9b7-111">Utilizzare il seguente formato:</span><span class="sxs-lookup"><span data-stu-id="8e9b7-111">Use the following format:</span></span>  
  
 <span data-ttu-id="8e9b7-112">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="8e9b7-112">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="8e9b7-113">Questa opzione è abilitata solo se si seleziona l'opzione **Usa nome utente e password specifici** .</span><span class="sxs-lookup"><span data-stu-id="8e9b7-113">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="8e9b7-114">**Password**</span><span class="sxs-lookup"><span data-stu-id="8e9b7-114">**Password**</span></span>  
 <span data-ttu-id="8e9b7-115">Digitare la password dell'account utente che verrà utilizzata dall'oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] selezionato.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-115">Type the password of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="8e9b7-116">Questa opzione è abilitata solo se si seleziona l'opzione **Usa nome utente e password specifici** .</span><span class="sxs-lookup"><span data-stu-id="8e9b7-116">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="8e9b7-117">**Usa account del servizio**</span><span class="sxs-lookup"><span data-stu-id="8e9b7-117">**Use the service account**</span></span>  
 <span data-ttu-id="8e9b7-118">Selezionare questa opzione per fare in modo che l'oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utilizzi le credenziali di sicurezza associate al servizio di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] che gestisce l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-118">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] service that manages the object.</span></span> <span data-ttu-id="8e9b7-119">Le credenziali dell'account del servizio verranno utilizzate per l'elaborazione, le query ROLAP, le partizioni remote, gli oggetti collegati e la sincronizzazione da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-119">The service account credentials will be used for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="8e9b7-120">Per le istruzioni DMX (Data Mining Extensions) OPENQUERY, i cubi locali, i modelli di data mining, verranno utilizzate invece le credenziali dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-120">However, for Data Mining Extensions (DMX) OPENQUERY statements, local cubes, and mining models, the credentials of the current user will be used.</span></span> <span data-ttu-id="8e9b7-121">Questa opzione non è supportata per le associazioni out-of-line.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-121">This option is not supported for out-of-line bindings.</span></span>  
  
 <span data-ttu-id="8e9b7-122">**Usa credenziali dell'utente corrente**</span><span class="sxs-lookup"><span data-stu-id="8e9b7-122">**Use the credentials of the current user**</span></span>  
 <span data-ttu-id="8e9b7-123">Selezionare questa opzione per fare in modo che l'oggetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utilizzi le credenziali di sicurezza dell'utente corrente per le associazioni out-of-line, le istruzioni DMX OPENQUERY, i cubi locali e i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-123">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of the current user for out-of-line bindings, DMX OPENQUERY, local cubes, and mining models.</span></span> <span data-ttu-id="8e9b7-124">Questa opzione non è supportata per l'elaborazione, le query ROLAP, le partizioni remote, gli oggetti collegati e la sincronizzazione da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-124">This option is not supported for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span>  
  
 <span data-ttu-id="8e9b7-125">**Ereditare**</span><span class="sxs-lookup"><span data-stu-id="8e9b7-125">**Inherit**</span></span>  
 <span data-ttu-id="8e9b7-126">Selezionare questa opzione per utilizzare il comportamento della rappresentazione, definito al livello del database impostato dall'amministratore del server utilizzando la proprietà del database `DataSourceImpersonation`.</span><span class="sxs-lookup"><span data-stu-id="8e9b7-126">Select this option to use the impersonation behavior, defined at the database level, which has been set by the server administrator using the `DataSourceImpersonation` database property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e9b7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e9b7-127">See Also</span></span>  
 <span data-ttu-id="8e9b7-128">[Origini dati nei modelli multidimensionali](multidimensional-models/data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="8e9b7-128">[Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="8e9b7-129">Origini dati supportate &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="8e9b7-129">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
