---
title: Metodo StartService (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartService method
ms.assetid: 83dfb6bd-dbd5-45d8-aad2-a11926317f91
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4d91646da2ac2c9f636655ff6c65808ba115e28f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717610"
---
# <a name="startservice-method-sqlservice-class"></a><span data-ttu-id="f31aa-102">Metodo StartService (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="f31aa-102">StartService Method (SqlService Class)</span></span>
  <span data-ttu-id="f31aa-103">Esegue un tentativo di avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-103">Attempts to place the service into its started state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f31aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f31aa-104">Syntax</span></span>  
  
```  
  
object  
.StartService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f31aa-105">Parti</span><span class="sxs-lookup"><span data-stu-id="f31aa-105">Parts</span></span>  
 <span data-ttu-id="f31aa-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f31aa-106">*object*</span></span>  
 <span data-ttu-id="f31aa-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f31aa-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f31aa-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f31aa-109">Valore uint32 che specifica uno dei seguenti stati di avvio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-109">A uint32 value that specifies one of the following startup states.</span></span>  
  
 <span data-ttu-id="f31aa-110">0</span><span class="sxs-lookup"><span data-stu-id="f31aa-110">0</span></span>  
 <span data-ttu-id="f31aa-111">Esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f31aa-111">Success.</span></span> <span data-ttu-id="f31aa-112">La richiesta è stata accettata.</span><span class="sxs-lookup"><span data-stu-id="f31aa-112">The request was accepted.</span></span>  
  
 <span data-ttu-id="f31aa-113">1</span><span class="sxs-lookup"><span data-stu-id="f31aa-113">1</span></span>  
 <span data-ttu-id="f31aa-114">Non supportato.</span><span class="sxs-lookup"><span data-stu-id="f31aa-114">Not Supported.</span></span> <span data-ttu-id="f31aa-115">La richiesta non è supportata.</span><span class="sxs-lookup"><span data-stu-id="f31aa-115">The request is not supported.</span></span>  
  
 <span data-ttu-id="f31aa-116">2</span><span class="sxs-lookup"><span data-stu-id="f31aa-116">2</span></span>  
 <span data-ttu-id="f31aa-117">Accesso negato.</span><span class="sxs-lookup"><span data-stu-id="f31aa-117">Access Denied.</span></span> <span data-ttu-id="f31aa-118">L'utente non dispone dei diritti di accesso appropriati.</span><span class="sxs-lookup"><span data-stu-id="f31aa-118">The user did not have appropriate access.</span></span>  
  
 <span data-ttu-id="f31aa-119">3</span><span class="sxs-lookup"><span data-stu-id="f31aa-119">3</span></span>  
 <span data-ttu-id="f31aa-120">Servizi dipendenti in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f31aa-120">Dependent Services Running.</span></span> <span data-ttu-id="f31aa-121">Impossibile arrestare il servizio perché altri servizi in esecuzione dipendono dal servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-121">The service cannot be stopped because other services that are running are dependent on it.</span></span>  
  
 <span data-ttu-id="f31aa-122">4</span><span class="sxs-lookup"><span data-stu-id="f31aa-122">4</span></span>  
 <span data-ttu-id="f31aa-123">Controllo servizio non valido.</span><span class="sxs-lookup"><span data-stu-id="f31aa-123">Invalid Service Control.</span></span> <span data-ttu-id="f31aa-124">Il codice di controllo richiesto non è valido o non è accettabile per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-124">The requested control code is not valid, or it is unacceptable to the service.</span></span>  
  
 <span data-ttu-id="f31aa-125">5</span><span class="sxs-lookup"><span data-stu-id="f31aa-125">5</span></span>  
 <span data-ttu-id="f31aa-126">Il servizio non accetta il controllo.</span><span class="sxs-lookup"><span data-stu-id="f31aa-126">Service Cannot Accept Control.</span></span> <span data-ttu-id="f31aa-127">Impossibile inviare il codice di controllo richiesto al servizio perché lo stato del servizio (Win32_BaseService:State) è uguale a 0, 1 o 2.</span><span class="sxs-lookup"><span data-stu-id="f31aa-127">The requested control code cannot be sent to the service because the state of the service (Win32_BaseService:State) is equal to 0, 1, or 2.</span></span>  
  
 <span data-ttu-id="f31aa-128">6</span><span class="sxs-lookup"><span data-stu-id="f31aa-128">6</span></span>  
 <span data-ttu-id="f31aa-129">Servizio non attivo.</span><span class="sxs-lookup"><span data-stu-id="f31aa-129">Service Not Active.</span></span> <span data-ttu-id="f31aa-130">Il servizio non è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="f31aa-130">The service has not been started.</span></span>  
  
 <span data-ttu-id="f31aa-131">7</span><span class="sxs-lookup"><span data-stu-id="f31aa-131">7</span></span>  
 <span data-ttu-id="f31aa-132">Timeout richiesta servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-132">Service Request Timeout.</span></span> <span data-ttu-id="f31aa-133">Il servizio non ha risposto in tempo utile alla richiesta di avvio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-133">The service did not respond to the start request in a timely fashion.</span></span>  
  
 <span data-ttu-id="f31aa-134">8</span><span class="sxs-lookup"><span data-stu-id="f31aa-134">8</span></span>  
 <span data-ttu-id="f31aa-135">Errore sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f31aa-135">Unknown Failure.</span></span> <span data-ttu-id="f31aa-136">Errore sconosciuto durante l'avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-136">An unknown failure occurred when starting the service.</span></span>  
  
 <span data-ttu-id="f31aa-137">9</span><span class="sxs-lookup"><span data-stu-id="f31aa-137">9</span></span>  
 <span data-ttu-id="f31aa-138">Percorso non trovato.</span><span class="sxs-lookup"><span data-stu-id="f31aa-138">Path Not Found.</span></span> <span data-ttu-id="f31aa-139">Impossibile trovare il percorso di directory del file eseguibile del servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-139">The directory path to the service executable was not found.</span></span>  
  
 <span data-ttu-id="f31aa-140">10</span><span class="sxs-lookup"><span data-stu-id="f31aa-140">10</span></span>  
 <span data-ttu-id="f31aa-141">Servizio già in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f31aa-141">Service Already Running.</span></span> <span data-ttu-id="f31aa-142">Il servizio è già in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f31aa-142">The service is already running.</span></span>  
  
 <span data-ttu-id="f31aa-143">11</span><span class="sxs-lookup"><span data-stu-id="f31aa-143">11</span></span>  
 <span data-ttu-id="f31aa-144">Database del servizio bloccato.</span><span class="sxs-lookup"><span data-stu-id="f31aa-144">Service Database Locked.</span></span> <span data-ttu-id="f31aa-145">Il database a cui aggiungere il nuovo servizio è bloccato.</span><span class="sxs-lookup"><span data-stu-id="f31aa-145">The database to add a new service is locked.</span></span>  
  
 <span data-ttu-id="f31aa-146">12</span><span class="sxs-lookup"><span data-stu-id="f31aa-146">12</span></span>  
 <span data-ttu-id="f31aa-147">Dipendenza del servizio eliminata.</span><span class="sxs-lookup"><span data-stu-id="f31aa-147">Service Dependency Deleted.</span></span> <span data-ttu-id="f31aa-148">Il servizio si basa su una dipendenza che è stata rimossa dal sistema.</span><span class="sxs-lookup"><span data-stu-id="f31aa-148">A dependency on which this service relies has been removed from the system.</span></span>  
  
 <span data-ttu-id="f31aa-149">13</span><span class="sxs-lookup"><span data-stu-id="f31aa-149">13</span></span>  
 <span data-ttu-id="f31aa-150">Errore di dipendenza del servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-150">Service Dependency Failure.</span></span> <span data-ttu-id="f31aa-151">Impossibile trovare un servizio dipendente necessario.</span><span class="sxs-lookup"><span data-stu-id="f31aa-151">The service failed to find the service needed from a dependent service.</span></span>  
  
 <span data-ttu-id="f31aa-152">14</span><span class="sxs-lookup"><span data-stu-id="f31aa-152">14</span></span>  
 <span data-ttu-id="f31aa-153">Servizio disabilitato.</span><span class="sxs-lookup"><span data-stu-id="f31aa-153">Service Disabled.</span></span> <span data-ttu-id="f31aa-154">Il servizio è stato disabilitato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="f31aa-154">The service has been disabled from the system.</span></span>  
  
 <span data-ttu-id="f31aa-155">15</span><span class="sxs-lookup"><span data-stu-id="f31aa-155">15</span></span>  
 <span data-ttu-id="f31aa-156">Errore di accesso del servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-156">Service Logon Failed.</span></span> <span data-ttu-id="f31aa-157">Il servizio non dispone delle credenziali di autenticazione corrette per l'esecuzione nel sistema.</span><span class="sxs-lookup"><span data-stu-id="f31aa-157">The service does not have the correct authentication to run on the system.</span></span>  
  
 <span data-ttu-id="f31aa-158">16</span><span class="sxs-lookup"><span data-stu-id="f31aa-158">16</span></span>  
 <span data-ttu-id="f31aa-159">Servizio contrassegnato per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="f31aa-159">Service Marked For Deletion.</span></span> <span data-ttu-id="f31aa-160">Il servizio verrà rimosso dal sistema.</span><span class="sxs-lookup"><span data-stu-id="f31aa-160">The service is being removed from the system.</span></span>  
  
 <span data-ttu-id="f31aa-161">17</span><span class="sxs-lookup"><span data-stu-id="f31aa-161">17</span></span>  
 <span data-ttu-id="f31aa-162">Nessun thread disponibile per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-162">Service No Thread.</span></span> <span data-ttu-id="f31aa-163">Nessun thread di esecuzione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-163">There is no execution thread for the service.</span></span>  
  
 <span data-ttu-id="f31aa-164">18</span><span class="sxs-lookup"><span data-stu-id="f31aa-164">18</span></span>  
 <span data-ttu-id="f31aa-165">Stato: dipendenza circolare.</span><span class="sxs-lookup"><span data-stu-id="f31aa-165">Status Circular Dependency.</span></span> <span data-ttu-id="f31aa-166">All'avvio del servizio sono state rilevate dipendenze circolari.</span><span class="sxs-lookup"><span data-stu-id="f31aa-166">There are circular dependencies when starting the service.</span></span>  
  
 <span data-ttu-id="f31aa-167">19</span><span class="sxs-lookup"><span data-stu-id="f31aa-167">19</span></span>  
 <span data-ttu-id="f31aa-168">Stato: nome duplicato.</span><span class="sxs-lookup"><span data-stu-id="f31aa-168">Status Duplicate Name.</span></span> <span data-ttu-id="f31aa-169">È presente un servizio in esecuzione con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="f31aa-169">There is a service running under the same name.</span></span>  
  
 <span data-ttu-id="f31aa-170">20</span><span class="sxs-lookup"><span data-stu-id="f31aa-170">20</span></span>  
 <span data-ttu-id="f31aa-171">Stato: nome non valido.</span><span class="sxs-lookup"><span data-stu-id="f31aa-171">Status Invalid Name.</span></span> <span data-ttu-id="f31aa-172">Il nome del servizio contiene caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="f31aa-172">There are characters that are not valid in the name of the service.</span></span>  
  
 <span data-ttu-id="f31aa-173">21</span><span class="sxs-lookup"><span data-stu-id="f31aa-173">21</span></span>  
 <span data-ttu-id="f31aa-174">Stato: parametro non valido.</span><span class="sxs-lookup"><span data-stu-id="f31aa-174">Status Invalid Parameter.</span></span> <span data-ttu-id="f31aa-175">Sono stati passati parametri non validi al servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-175">Parameters that are not valid have been passed to the service.</span></span>  
  
 <span data-ttu-id="f31aa-176">22</span><span class="sxs-lookup"><span data-stu-id="f31aa-176">22</span></span>  
 <span data-ttu-id="f31aa-177">Stato: account di servizio non valido.</span><span class="sxs-lookup"><span data-stu-id="f31aa-177">Status Invalid Service Account.</span></span> <span data-ttu-id="f31aa-178">L'account utilizzato per l'esecuzione del servizio non è valido o non dispone delle autorizzazioni necessarie per eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="f31aa-178">The account which this service is to run under is not valid, or it lacks the permissions to run the service.</span></span>  
  
 <span data-ttu-id="f31aa-179">23</span><span class="sxs-lookup"><span data-stu-id="f31aa-179">23</span></span>  
 <span data-ttu-id="f31aa-180">Stato: servizio già esistente.</span><span class="sxs-lookup"><span data-stu-id="f31aa-180">Status Service Exists.</span></span> <span data-ttu-id="f31aa-181">Il servizio esiste già nel database dei servizi disponibili dal sistema.</span><span class="sxs-lookup"><span data-stu-id="f31aa-181">The service exists in the database of services available from the system.</span></span>  
  
 <span data-ttu-id="f31aa-182">24</span><span class="sxs-lookup"><span data-stu-id="f31aa-182">24</span></span>  
 <span data-ttu-id="f31aa-183">Servizio già sospeso.</span><span class="sxs-lookup"><span data-stu-id="f31aa-183">Service Already Paused.</span></span> <span data-ttu-id="f31aa-184">Il servizio è attualmente sospeso nel sistema.</span><span class="sxs-lookup"><span data-stu-id="f31aa-184">The service is currently paused in the system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f31aa-185">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f31aa-185">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f31aa-186">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f31aa-186">See Also</span></span>  
 <span data-ttu-id="f31aa-187">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f31aa-187">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
