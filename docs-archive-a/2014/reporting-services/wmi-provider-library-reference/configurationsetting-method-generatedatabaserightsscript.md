---
title: Metodo GenerateDatabaseRightsScript (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseRightsScript method
ms.assetid: f2e6dcc9-978f-4c2c-bafe-36c330247fd0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 768e73d13d3b06f7913c3c816fded1b28c56199f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722407"
---
# <a name="generatedatabaserightsscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="1263b-102">Metodo GenerateDatabaseRightsScript (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="1263b-102">GenerateDatabaseRightsScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="1263b-103">Genera uno script SQL che può essere utilizzato per concedere a un utente i diritti per il database del server di report e per gli altri database richiesti affinché un server di report venga eseguito.</span><span class="sxs-lookup"><span data-stu-id="1263b-103">Generates a SQL Script that can be used to grant a user rights to the report server database and other databases required for a report server to run.</span></span> <span data-ttu-id="1263b-104">Il chiamante deve connettersi al server di database [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ed eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="1263b-104">The caller is expected to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and execute the script.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1263b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1263b-105">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseRightsScript(ByVal UserName As String, _  
    ByVal DatabaseName As String, ByVal IsRemote As Boolean, _  
    ByVal IsWindowsUser As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseRightsScript(string UserName, string DatabaseName, bool IsRemote, bool IsWindowsUser, out string Script,   
out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1263b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1263b-106">Parameters</span></span>  
 <span data-ttu-id="1263b-107">*UserName*</span><span class="sxs-lookup"><span data-stu-id="1263b-107">*UserName*</span></span>  
 <span data-ttu-id="1263b-108">Nome utente o ID di sicurezza (SID) di Windows dell'utente al quale lo script concederà i diritti.</span><span class="sxs-lookup"><span data-stu-id="1263b-108">The user name or Windows security identifier (SID) of the user to which the script will grant rights.</span></span>  
  
 <span data-ttu-id="1263b-109">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="1263b-109">*DatabaseName*</span></span>  
 <span data-ttu-id="1263b-110">Nome del database al quale lo script concederà l'accesso all'utente.</span><span class="sxs-lookup"><span data-stu-id="1263b-110">The database name to which the script will grant access to the user.</span></span>  
  
 <span data-ttu-id="1263b-111">*IsRemote*</span><span class="sxs-lookup"><span data-stu-id="1263b-111">*IsRemote*</span></span>  
 <span data-ttu-id="1263b-112">Valore booleano a che indica se il database è remoto per il server di report.</span><span class="sxs-lookup"><span data-stu-id="1263b-112">A Boolean value to indicating whether the database is remote from the report server.</span></span>  
  
 <span data-ttu-id="1263b-113">*IsWindowsUser*</span><span class="sxs-lookup"><span data-stu-id="1263b-113">*IsWindowsUser*</span></span>  
 <span data-ttu-id="1263b-114">Valore booleano che indica se il nome utente specificato è un utente di Windows o un utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1263b-114">A Boolean value indicating whether the specified user name is a Windows user or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user.</span></span>  
  
 <span data-ttu-id="1263b-115">*Script*</span><span class="sxs-lookup"><span data-stu-id="1263b-115">*Script*</span></span>  
 <span data-ttu-id="1263b-116">[out] Stringa che contiene lo script [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generato.</span><span class="sxs-lookup"><span data-stu-id="1263b-116">[out] A string containing the generated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span>  
  
 <span data-ttu-id="1263b-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="1263b-117">*HRESULT*</span></span>  
 <span data-ttu-id="1263b-118">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="1263b-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1263b-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1263b-119">Return Value</span></span>  
 <span data-ttu-id="1263b-120">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="1263b-120">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="1263b-121">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="1263b-121">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="1263b-122">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="1263b-122">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1263b-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1263b-123">Remarks</span></span>  
 <span data-ttu-id="1263b-124">Se *DatabaseName* è vuoto, *IsRemote* viene ignorato e per il nome del database viene usato il valore del file di configurazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="1263b-124">If *DatabaseName* is empty then *IsRemote* is ignored and the report server configuration file value is used for the database name.</span></span>  
  
 <span data-ttu-id="1263b-125">Se *IsWindowsUser* è impostato su `true` , il *nome utente* deve essere nel formato \<domain> \\<nome utente \> .</span><span class="sxs-lookup"><span data-stu-id="1263b-125">If *IsWindowsUser* is set to `true`, *UserName* should be in the format \<domain>\\<username\>.</span></span>  
  
 <span data-ttu-id="1263b-126">Quando *IsWindowsUser* è impostato su `true` , lo script generato concede all'utente i diritti di accesso per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , impostando il database del server di report come database predefinito, e concede il ruolo **RSExec nel** nel database del server di report, nel database temporaneo del server di report, nel database master e nel database di sistema msdb.</span><span class="sxs-lookup"><span data-stu-id="1263b-126">When *IsWindowsUser* is set to `true`, the generated script grants login rights to the user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], setting the report server database as the default database, and grants the **RSExec** role on the report server database, the report server temporary database, the master database and the MSDB system database.</span></span>  
  
 <span data-ttu-id="1263b-127">Quando *IsWindowsUser* è impostato su `true` , il metodo accetta come input i SID standard di Windows.</span><span class="sxs-lookup"><span data-stu-id="1263b-127">When *IsWindowsUser* is set to `true`, the method accepts standard Windows SIDs as input.</span></span> <span data-ttu-id="1263b-128">Quando viene fornito un SID standard di Windows o un nome dell'account di servizio, questo viene convertito in una stringa del nome utente.</span><span class="sxs-lookup"><span data-stu-id="1263b-128">When a standard Windows SID or service account name is supplied, it is translated to a user name string.</span></span> <span data-ttu-id="1263b-129">Se il database è locale, l'account viene convertito nella rappresentazione localizzata corretta dell'account.</span><span class="sxs-lookup"><span data-stu-id="1263b-129">If the database is local, the account is translated to the correct localized representation of the account.</span></span> <span data-ttu-id="1263b-130">Se il database è remoto, l'account viene rappresentato come account del computer.</span><span class="sxs-lookup"><span data-stu-id="1263b-130">If the database is remote, the account is represented as the computer's account.</span></span>  
  
 <span data-ttu-id="1263b-131">Nella tabella seguente vengono mostrati gli account convertiti e la relativa rappresentazione remota.</span><span class="sxs-lookup"><span data-stu-id="1263b-131">The following table shows accounts that are translated and their remote representation.</span></span>  
  
|<span data-ttu-id="1263b-132">Account / SID convertito</span><span class="sxs-lookup"><span data-stu-id="1263b-132">Account / SID that is translated</span></span>|<span data-ttu-id="1263b-133">Nome comune</span><span class="sxs-lookup"><span data-stu-id="1263b-133">Common Name</span></span>|<span data-ttu-id="1263b-134">Nome remoto</span><span class="sxs-lookup"><span data-stu-id="1263b-134">Remote Name</span></span>|  
|---------------------------------------|-----------------|-----------------|  
|<span data-ttu-id="1263b-135">(S-1-5-18)</span><span class="sxs-lookup"><span data-stu-id="1263b-135">(S-1-5-18)</span></span>|<span data-ttu-id="1263b-136">Sistema locale</span><span class="sxs-lookup"><span data-stu-id="1263b-136">Local System</span></span>|<span data-ttu-id="1263b-137">\<Domain>\\<nomecomputer\>$</span><span class="sxs-lookup"><span data-stu-id="1263b-137">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="1263b-138">.\LocalSystem</span><span class="sxs-lookup"><span data-stu-id="1263b-138">.\LocalSystem</span></span>|<span data-ttu-id="1263b-139">Sistema locale</span><span class="sxs-lookup"><span data-stu-id="1263b-139">Local System</span></span>|<span data-ttu-id="1263b-140">\<Domain>\\<nomecomputer\>$</span><span class="sxs-lookup"><span data-stu-id="1263b-140">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="1263b-141">ComputerName\LocalSystem</span><span class="sxs-lookup"><span data-stu-id="1263b-141">ComputerName\LocalSystem</span></span>|<span data-ttu-id="1263b-142">Sistema locale</span><span class="sxs-lookup"><span data-stu-id="1263b-142">Local System</span></span>|<span data-ttu-id="1263b-143">\<Domain>\\<nomecomputer\>$</span><span class="sxs-lookup"><span data-stu-id="1263b-143">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="1263b-144">LocalSystem</span><span class="sxs-lookup"><span data-stu-id="1263b-144">LocalSystem</span></span>|<span data-ttu-id="1263b-145">Sistema locale</span><span class="sxs-lookup"><span data-stu-id="1263b-145">Local System</span></span>|<span data-ttu-id="1263b-146">\<Domain>\\<nomecomputer\>$</span><span class="sxs-lookup"><span data-stu-id="1263b-146">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="1263b-147">(S-1-5-20)</span><span class="sxs-lookup"><span data-stu-id="1263b-147">(S-1-5-20)</span></span>|<span data-ttu-id="1263b-148">Servizio di rete</span><span class="sxs-lookup"><span data-stu-id="1263b-148">Network Service</span></span>|<span data-ttu-id="1263b-149">\<Domain>\\<nomecomputer\>$</span><span class="sxs-lookup"><span data-stu-id="1263b-149">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="1263b-150">NT AUTHORITY\NetworkService</span><span class="sxs-lookup"><span data-stu-id="1263b-150">NT AUTHORITY\NetworkService</span></span>|<span data-ttu-id="1263b-151">Servizio di rete</span><span class="sxs-lookup"><span data-stu-id="1263b-151">Network Service</span></span>|<span data-ttu-id="1263b-152">\<Domain>\\<nomecomputer\>$</span><span class="sxs-lookup"><span data-stu-id="1263b-152">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="1263b-153">(S-1-5-19)</span><span class="sxs-lookup"><span data-stu-id="1263b-153">(S-1-5-19)</span></span>|<span data-ttu-id="1263b-154">Servizio locale</span><span class="sxs-lookup"><span data-stu-id="1263b-154">Local Service</span></span>|<span data-ttu-id="1263b-155">Errore, vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="1263b-155">Error - see below.</span></span>|  
|<span data-ttu-id="1263b-156">NT AUTHORITY\LocalService</span><span class="sxs-lookup"><span data-stu-id="1263b-156">NT AUTHORITY\LocalService</span></span>|<span data-ttu-id="1263b-157">Servizio locale</span><span class="sxs-lookup"><span data-stu-id="1263b-157">Local Service</span></span>|<span data-ttu-id="1263b-158">Errore, vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="1263b-158">Error - see below.</span></span>|  
  
 <span data-ttu-id="1263b-159">In [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)], se si utilizza un account predefinito e il database del server di report è remoto, viene restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="1263b-159">On [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)], if you are using a built-in account and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="1263b-160">Se l'account `LocalService` predefinito è specificato e il database del server di report è remoto, viene restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="1263b-160">If the `LocalService` built-in account is specified and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="1263b-161">Quando *IsWindowsUser* è True e il valore fornito in *UserName* deve essere convertito, il provider WMI determina se il database del server di report si trova sullo stesso computer o su un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="1263b-161">When *IsWindowsUser* is true and the value supplied in *UserName* needs to be translated, the WMI provider determines whether the report server database is located on the same computer or on a remote computer.</span></span> <span data-ttu-id="1263b-162">Per determinare se l'installazione è locale, il provider WMI valuta la proprietà DatabaseServerName rispetto al seguente elenco di valori.</span><span class="sxs-lookup"><span data-stu-id="1263b-162">To determine if the installation is local, the WMI provider evaluates the DatabaseServerName property against the following list of values.</span></span> <span data-ttu-id="1263b-163">Se viene rilevata una corrispondenza, il database è locale.</span><span class="sxs-lookup"><span data-stu-id="1263b-163">If a match is found, the database is local.</span></span> <span data-ttu-id="1263b-164">In caso contrario, è remoto.</span><span class="sxs-lookup"><span data-stu-id="1263b-164">Otherwise, it is remote.</span></span> <span data-ttu-id="1263b-165">Il confronto non fa distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="1263b-165">The comparison is case-insensitive.</span></span>  
  
|<span data-ttu-id="1263b-166">Valore di DatabaseServerName</span><span class="sxs-lookup"><span data-stu-id="1263b-166">Value of DatabaseServerName</span></span>|<span data-ttu-id="1263b-167">Esempio</span><span class="sxs-lookup"><span data-stu-id="1263b-167">Example</span></span>|  
|---------------------------------|-------------|  
|<span data-ttu-id="1263b-168">"."</span><span class="sxs-lookup"><span data-stu-id="1263b-168">"."</span></span>||  
|<span data-ttu-id="1263b-169">"(local)"</span><span class="sxs-lookup"><span data-stu-id="1263b-169">"(local)"</span></span>||  
|<span data-ttu-id="1263b-170">"LOCAL"</span><span class="sxs-lookup"><span data-stu-id="1263b-170">"LOCAL"</span></span>||  
|<span data-ttu-id="1263b-171">localhost</span><span class="sxs-lookup"><span data-stu-id="1263b-171">localhost</span></span>||  
|\<Machinename>|<span data-ttu-id="1263b-172">testlab14</span><span class="sxs-lookup"><span data-stu-id="1263b-172">testlab14</span></span>|  
|\<MachineFQDN>|<span data-ttu-id="1263b-173">example.redmond.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1263b-173">example.redmond.microsoft.com</span></span>|  
|\<IPAddress>|<span data-ttu-id="1263b-174">180.012.345,678</span><span class="sxs-lookup"><span data-stu-id="1263b-174">180.012.345,678</span></span>|  
  
 <span data-ttu-id="1263b-175">Quando *IsWindowsUser* è impostato su `true` , il provider WMI chiama LookupAccountName per ottenere il SID per l'account e quindi chiama LookupAccountSid per ottenere il nome da inserire nello [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span><span class="sxs-lookup"><span data-stu-id="1263b-175">When *IsWindowsUser* is set to `true`, the WMI provider calls LookupAccountName to get the SID for the account and then calls LookupAccountSID to get the name to put in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span> <span data-ttu-id="1263b-176">In questo modo si garantisce che il nome account utilizzato passerà la convalida [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1263b-176">This ensures that the account name used will pass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] validation.</span></span>  
  
 <span data-ttu-id="1263b-177">Quando *IsWindowsUser* è impostato su `false` , lo script generato concede il ruolo **RSExec nel** nel database del server di report, nel database temporaneo del server di report e nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="1263b-177">When *IsWindowsUser* is set to `false`, the generated script grants the **RSExec** role on the report server database, the report server temporary database, and the MSDB database.</span></span>  
  
 <span data-ttu-id="1263b-178">Quando *IsWindowsUser* è impostato su `false` , l'utente SQL Server deve esistere già nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per eseguire correttamente lo script.</span><span class="sxs-lookup"><span data-stu-id="1263b-178">When *IsWindowsUser* is set to `false`, the SQL Server user must already exist on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the script to run successfully.</span></span>  
  
 <span data-ttu-id="1263b-179">Se il server di report non dispone di un database del server di report specificato, la chiamata a GrantRightsToDatabaseUser restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="1263b-179">If the report server does not have a report server database specified, calling GrantRightsToDatabaseUser returns an error.</span></span>  
  
 <span data-ttu-id="1263b-180">Lo script generato supporta [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 e [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1263b-180">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1263b-181">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1263b-181">Requirements</span></span>  
 <span data-ttu-id="1263b-182">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1263b-182">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1263b-183">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1263b-183">See Also</span></span>  
 [<span data-ttu-id="1263b-184">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="1263b-184">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
