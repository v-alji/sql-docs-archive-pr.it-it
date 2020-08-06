---
title: Modificare il word breaker usato per le lingue Inglese (Stati Uniti) e Inglese (Regno Unito) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: 6b5d2177-db98-47f5-b32e-4b80a2f74ffe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3b759b90ec834dcb666f7862bfba3857f2fea0d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629325"
---
# <a name="change-the-word-breaker-used-for-us-english-and-uk-english"></a><span data-ttu-id="d2f65-102">Modifica del word breaker utilizzato per le lingue Inglese (Stati Uniti) e Inglese (Regno Unito)</span><span class="sxs-lookup"><span data-stu-id="d2f65-102">Change the Word Breaker Used for US English and UK English</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="d2f65-103">installa una nuova versione (versione 14.0.4999.1038) del word breaker e dello stemmer per la lingua inglese che sostituisce la versione precedente (versione 12.0.6828.0).</span><span class="sxs-lookup"><span data-stu-id="d2f65-103">installs a new version (version 14.0.4999.1038) of the word breaker and stemmer for the English language, replacing the previous version of these components (version 12.0.6828.0).</span></span> <span data-ttu-id="d2f65-104">Per informazioni sul comportamento modificato dei nuovi componenti, vedere [Differenze di comportamento nella ricerca full-text](full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="d2f65-104">For information about the changed behavior of the new components, see [Behavior Changes to Full-Text Search](full-text-search.md).</span></span> <span data-ttu-id="d2f65-105">In questo argomento viene descritto come passare dalla nuova versione di questi componenti alla versione precedente o come tornare alla nuova versione dalla versione precedente.</span><span class="sxs-lookup"><span data-stu-id="d2f65-105">This topic describes how to switch from the new version of these components to the previous version, or to switch back from the previous version to the new version.</span></span> <span data-ttu-id="d2f65-106">Per le installazioni di cluster, queste modifiche devono essere apportate in tutti i nodi primari e passivi.</span><span class="sxs-lookup"><span data-stu-id="d2f65-106">For cluster installations, these changes should be made on all the primary and passive nodes.</span></span>  
  
 <span data-ttu-id="d2f65-107">Le versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzano word breaker diversi rappresentati da CLSID diversi per la lingua inglese Stati Uniti (LCID 1033) e per la lingua inglese Regno Unito (LCID 2057).</span><span class="sxs-lookup"><span data-stu-id="d2f65-107">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] used different word breakers represented by different CLSIDs for US English (LCID 1033) and UK English (LCID 2057).</span></span> <span data-ttu-id="d2f65-108">In questa versione entrambi gli LCID utilizzano gli stessi componenti con gli stessi CLSID, come illustrato nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="d2f65-108">In this release, both LCIDs use the same components with the same CLSIDs, as shown in the following table:</span></span>  
  
|<span data-ttu-id="d2f65-109">LCID</span><span class="sxs-lookup"><span data-stu-id="d2f65-109">LCID</span></span>|<span data-ttu-id="d2f65-110">Word breaker installato tramite le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="d2f65-110">Word breaker installed by previous versions</span></span><br /><br /> <span data-ttu-id="d2f65-111">Versione 12.0.6828.0</span><span class="sxs-lookup"><span data-stu-id="d2f65-111">version 12.0.6828.0</span></span>|<span data-ttu-id="d2f65-112">Stemmer installato tramite le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="d2f65-112">Stemmer installed by previous versions</span></span>|<span data-ttu-id="d2f65-113">Word breaker installato tramite questa versione</span><span class="sxs-lookup"><span data-stu-id="d2f65-113">Word breaker installed by this version</span></span><br /><br /> <span data-ttu-id="d2f65-114">Versione 14.0.4999.1038</span><span class="sxs-lookup"><span data-stu-id="d2f65-114">version 14.0.4999.1038</span></span>|<span data-ttu-id="d2f65-115">Stemmer installato tramite questa versione</span><span class="sxs-lookup"><span data-stu-id="d2f65-115">Stemmer installed by this version</span></span>|  
|----------|-------------------------------------------------------------------------|--------------------------------------------|-----------------------------------------------------------------------|---------------------------------------|  
|<span data-ttu-id="d2f65-116">1033</span><span class="sxs-lookup"><span data-stu-id="d2f65-116">1033</span></span><br /><span data-ttu-id="d2f65-117">(inglese Stati Uniti)</span><span class="sxs-lookup"><span data-stu-id="d2f65-117">(US English)</span></span>|<span data-ttu-id="d2f65-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span><span class="sxs-lookup"><span data-stu-id="d2f65-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span></span>|<span data-ttu-id="d2f65-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="d2f65-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="d2f65-120">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="d2f65-120">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="d2f65-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="d2f65-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
|<span data-ttu-id="d2f65-122">2057</span><span class="sxs-lookup"><span data-stu-id="d2f65-122">2057</span></span><br /><span data-ttu-id="d2f65-123">(inglese Regno Unito)</span><span class="sxs-lookup"><span data-stu-id="d2f65-123">(UK English)</span></span>|<span data-ttu-id="d2f65-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span><span class="sxs-lookup"><span data-stu-id="d2f65-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span></span>|<span data-ttu-id="d2f65-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="d2f65-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="d2f65-126">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="d2f65-126">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="d2f65-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="d2f65-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
  
 <span data-ttu-id="d2f65-128">I componenti descritti in questo argomento sono file DLL installati nella cartella `MSSQL\Binn` per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d2f65-128">The components described in this topic are DLL files that are installed in the `MSSQL\Binn` folder for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="d2f65-129">Il percorso completo è in genere `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span><span class="sxs-lookup"><span data-stu-id="d2f65-129">The full path is typically `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span></span>  
  
 <span data-ttu-id="d2f65-130">Per informazioni generali su word breaker e stemmer, vedere [Configurare e gestire word breaker e stemmer per la ricerca](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span><span class="sxs-lookup"><span data-stu-id="d2f65-130">For more information about word breakers and stemmers, see [Configure and Manage Word Breakers and Stemmers for Search](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span></span>  
  
## <a name="switching-from-the-current-english-word-breaker-to-the-previous-english-word-breakers"></a><span data-ttu-id="d2f65-131">Passaggio dal word breaker per la lingua inglese corrente ai word breaker per la lingua inglese precedenti</span><span class="sxs-lookup"><span data-stu-id="d2f65-131">Switching from the current English word breaker to the previous English word breakers</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-us-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="d2f65-132">Per passare dalla versione corrente del word breaker per la lingua inglese Stati Uniti alla versione precedente</span><span class="sxs-lookup"><span data-stu-id="d2f65-132">To switch from the current version of the US English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="d2f65-133">Nel Registro di sistema spostarsi sul nodo seguente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<RadiceIstanza\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-133">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="d2f65-134">Utilizzare i passaggi seguenti per aggiungere nuove chiavi per i ClassID COM per le interfacce del word breaker e dello stemmer per la lingua inglese Stati Uniti precedenti per l'LCID 1033:</span><span class="sxs-lookup"><span data-stu-id="d2f65-134">Use the following steps to add new keyS for the COM ClassIDs for the previous US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="d2f65-135">Aggiungere una nuova chiave con il valore **{188D6CC5-CB03-4C01-912E-47D21295D77E}** per il word breaker precedente.</span><span class="sxs-lookup"><span data-stu-id="d2f65-135">Add a new key with the value **{188D6CC5-CB03-4C01-912E-47D21295D77E}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="d2f65-136">Aggiornare i dati (predefiniti) del valore della chiave a **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-136">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="d2f65-137">Aggiungere una nuova chiave con il valore **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** per lo stemmer precedente.</span><span class="sxs-lookup"><span data-stu-id="d2f65-137">Add a new key with the value **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="d2f65-138">Aggiornare i dati (predefiniti) del valore della chiave a **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-138">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="d2f65-139">Nel Registro di sistema spostarsi sul nodo seguente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<RadiceIstanza\>\MSSearch\Language\enu**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-139">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\enu**.</span></span>  
  
4.  <span data-ttu-id="d2f65-140">Aggiornare il valore della chiave **WBreakerClass** a **{188D6CC5-CB03-4C01-912E-47D21295D77E}** .</span><span class="sxs-lookup"><span data-stu-id="d2f65-140">Update the **WBreakerClass** key value to **{188D6CC5-CB03-4C01-912E-47D21295D77E}**.</span></span>  
  
5.  <span data-ttu-id="d2f65-141">Aggiornare il valore della chiave **StemmerClass** a **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="d2f65-141">Update the **StemmerClass** key value to **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="d2f65-142">Riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2f65-142">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-uk-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="d2f65-143">Per passare dalla versione corrente del word breaker per la lingua inglese Regno Unito alla versione precedente</span><span class="sxs-lookup"><span data-stu-id="d2f65-143">To switch from the current version of the UK English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="d2f65-144">Nel Registro di sistema spostarsi sul nodo seguente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<RadiceIstanza\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-144">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="d2f65-145">Utilizzare i passaggi seguenti per aggiungere una nuova chiave per i ClassID COM per le interfacce del word breaker e dello stemmer per la lingua inglese Regno Unito precedenti per l'LCID 2057:</span><span class="sxs-lookup"><span data-stu-id="d2f65-145">Use the following steps to add a new key for the COM ClassIDs for the previous UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="d2f65-146">Aggiungere una nuova chiave con il valore **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** per il word breaker precedente.</span><span class="sxs-lookup"><span data-stu-id="d2f65-146">Add a new key with the value **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="d2f65-147">Aggiornare i dati (predefiniti) del valore della chiave a **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-147">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="d2f65-148">Aggiungere una nuova chiave con il valore **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** per lo stemmer precedente.</span><span class="sxs-lookup"><span data-stu-id="d2f65-148">Add a new key with the value **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="d2f65-149">Aggiornare i dati (predefiniti) del valore della chiave a **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-149">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="d2f65-150">Nel Registro di sistema passare al nodo seguente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<RadiceIstanza\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-150">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="d2f65-151">Aggiornare il valore della chiave **WBreakerClass** a **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** .</span><span class="sxs-lookup"><span data-stu-id="d2f65-151">Update the **WBreakerClass** key value to **{173C97E2-AEBE-437C-9445-01B237ABF2F6}**.</span></span>  
  
5.  <span data-ttu-id="d2f65-152">Aggiornare il valore della chiave **StemmerClass** a **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="d2f65-152">Update the **StemmerClass** key value to **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="d2f65-153">Riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2f65-153">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="switching-back-from-the-previous-english-word-breakers-to-the-current-english-word-breaker"></a><span data-ttu-id="d2f65-154">Passaggio dai word breaker per la lingua inglese precedenti al word breaker per la lingua inglese corrente</span><span class="sxs-lookup"><span data-stu-id="d2f65-154">Switching back from the previous English word breakers to the current English word breaker</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-us-english-word-breaker-to-the-current-version"></a><span data-ttu-id="d2f65-155">Per tornare alla versione corrente del word breaker per la lingua inglese Stati Uniti dalla versione precedente</span><span class="sxs-lookup"><span data-stu-id="d2f65-155">To switch back from the previous version of the US English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="d2f65-156">Nel Registro di sistema spostarsi sul nodo seguente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<RadiceIstanza\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-156">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="d2f65-157">Se le chiavi seguenti non sono presenti, utilizzare la procedura indicata di seguito per aggiungere una nuova chiave per i ClassID COM per le interfacce del word breaker e dello stemmer per la lingua inglese Stati Uniti correnti per l'LCID 1033:</span><span class="sxs-lookup"><span data-stu-id="d2f65-157">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="d2f65-158">Aggiungere una nuova chiave con il valore **{9faed859-0b30-4434-ae65-412e14a16fb8}** per il word breaker corrente.</span><span class="sxs-lookup"><span data-stu-id="d2f65-158">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="d2f65-159">Aggiornare i dati (predefiniti) del valore della chiave a **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-159">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="d2f65-160">Aggiungere una nuova chiave con il valore **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** per lo stemmer corrente.</span><span class="sxs-lookup"><span data-stu-id="d2f65-160">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="d2f65-161">Aggiornare i dati (predefiniti) del valore della chiave a **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-161">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="d2f65-162">Nel Registro di sistema passare al nodo seguente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<RadiceIstanza\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-162">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="d2f65-163">Aggiornare il valore della chiave **WBreakerClass** a **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="d2f65-163">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="d2f65-164">Aggiornare il valore della chiave **StemmerClass** a **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="d2f65-164">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="d2f65-165">Riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2f65-165">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-uk-english-word-breaker-to-the-current-version"></a><span data-ttu-id="d2f65-166">Per tornare alla versione corrente del word breaker per la lingua inglese Regno Unito dalla versione precedente</span><span class="sxs-lookup"><span data-stu-id="d2f65-166">To switch back from the previous version of the UK English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="d2f65-167">Nel Registro di sistema spostarsi sul nodo seguente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<RadiceIstanza\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-167">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="d2f65-168">Se le chiavi seguenti non sono presenti, utilizzare la procedura indicata di seguito per aggiungere una nuova chiave per i ClassID COM per le interfacce del word breaker e dello stemmer per la lingua inglese Regno Unito correnti per l'LCID 2057:</span><span class="sxs-lookup"><span data-stu-id="d2f65-168">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="d2f65-169">Aggiungere una nuova chiave con il valore **{9faed859-0b30-4434-ae65-412e14a16fb8}** per il word breaker corrente.</span><span class="sxs-lookup"><span data-stu-id="d2f65-169">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="d2f65-170">Aggiornare i dati (predefiniti) del valore della chiave a **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-170">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="d2f65-171">Aggiungere una nuova chiave con il valore **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** per lo stemmer corrente.</span><span class="sxs-lookup"><span data-stu-id="d2f65-171">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="d2f65-172">Aggiornare i dati (predefiniti) del valore della chiave a **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-172">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="d2f65-173">Nel Registro di sistema passare al nodo seguente: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<RadiceIstanza\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="d2f65-173">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="d2f65-174">Aggiornare il valore della chiave **WBreakerClass** a **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="d2f65-174">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="d2f65-175">Aggiornare il valore della chiave **StemmerClass** a **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="d2f65-175">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="d2f65-176">Riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2f65-176">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2f65-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2f65-177">See Also</span></span>  
 <span data-ttu-id="d2f65-178">[Ripristinare i word breaker utilizzati dalla ricerca alla versione precedente](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span><span class="sxs-lookup"><span data-stu-id="d2f65-178">[Revert the Word Breakers Used by Search to the Previous Version](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span></span>  
 [<span data-ttu-id="d2f65-179">Differenze di comportamento nella ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="d2f65-179">Behavior Changes to Full-Text Search</span></span>](full-text-search.md)  
  
  
