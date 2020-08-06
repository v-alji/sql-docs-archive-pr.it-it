---
title: Metodo SetDatabaseConnection (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseConnection method
ms.assetid: c040aa78-92b8-41e4-9ae2-eff9fcdddc5b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5c62777edd1fab2b0cb3babc13ab09f7bcf32a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722388"
---
# <a name="setdatabaseconnection-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="9f5b3-102">Metodo SetDatabaseConnection (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="9f5b3-102">SetDatabaseConnection Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="9f5b3-103">Imposta la connessione al database del server di report su un database del server di report specifico.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-103">Sets the report server database connection to a particular report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f5b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f5b3-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseConnection(Server as String, _  
    DatabaseName as string, CredentialsType as Integer, _  
    Username as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void BackupEncryptionKey(string Server,   
    string DatabaseName, Int32 CredentialsType,   
    string UserName, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f5b3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9f5b3-105">Parameters</span></span>  
 <span data-ttu-id="9f5b3-106">*Server*</span><span class="sxs-lookup"><span data-stu-id="9f5b3-106">*Server*</span></span>  
 <span data-ttu-id="9f5b3-107">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usata per ospitare il database del server di report.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-107">The name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is used to host the report server database.</span></span>  
  
 <span data-ttu-id="9f5b3-108">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="9f5b3-108">*DatabaseName*</span></span>  
 <span data-ttu-id="9f5b3-109">Nome del database del server di report.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-109">The name of the report server database.</span></span>  
  
 <span data-ttu-id="9f5b3-110">*CredentialsType*</span><span class="sxs-lookup"><span data-stu-id="9f5b3-110">*CredentialsType*</span></span>  
 <span data-ttu-id="9f5b3-111">Tipo di credenziali da utilizzare per la connessione.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-111">The type of credentials to use for the connection.</span></span> <span data-ttu-id="9f5b3-112">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="9f5b3-112">Values can be:</span></span>  
  
-   <span data-ttu-id="9f5b3-113">0: Windows</span><span class="sxs-lookup"><span data-stu-id="9f5b3-113">0 - Windows</span></span>  
  
-   <span data-ttu-id="9f5b3-114">1: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f5b3-114">1 - [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="9f5b3-115">2: servizio Windows</span><span class="sxs-lookup"><span data-stu-id="9f5b3-115">2 - Windows Service</span></span>  
  
 <span data-ttu-id="9f5b3-116">*UserName*</span><span class="sxs-lookup"><span data-stu-id="9f5b3-116">*UserName*</span></span>  
 <span data-ttu-id="9f5b3-117">Nome account utilizzato per la connessione al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-117">The account name used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="9f5b3-118">*Password*</span><span class="sxs-lookup"><span data-stu-id="9f5b3-118">*Password*</span></span>  
 <span data-ttu-id="9f5b3-119">Password utilizzata per la connessione al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-119">The password used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="9f5b3-120">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="9f5b3-120">*HRESULT*</span></span>  
 <span data-ttu-id="9f5b3-121">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-121">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f5b3-122">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9f5b3-122">Return Value</span></span>  
 <span data-ttu-id="9f5b3-123">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-123">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="9f5b3-124">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-124">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="9f5b3-125">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-125">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f5b3-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9f5b3-126">Remarks</span></span>  
 <span data-ttu-id="9f5b3-127">Quando il parametro *CredentialsType* è impostato su 0 (Windows), è necessario impostare i parametri *UserName* e *Password* .</span><span class="sxs-lookup"><span data-stu-id="9f5b3-127">When the *CredentialsType* parameter is set to 0 (Windows), the *UserName* and *Password* parameters must be set.</span></span> <span data-ttu-id="9f5b3-128">Il parametro *UserName* deve avere il formato "dominio\nomeutente" e il valore deve rappresentare un account di accesso di Windows valido.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-128">The *UserName* parameter must be in the form "domain\username", and the value must represent a valid Windows logon.</span></span>  
  
 <span data-ttu-id="9f5b3-129">Quando il parametro *CredentialsType* è impostato su 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), il valore passato nel parametro *UserName* deve essere conforme ai requisiti di un nome account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9f5b3-129">When the *CredentialsType* parameter is set to 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the value passed in the *UserName* parameter must conform to the requirements of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login name.</span></span>  
  
 <span data-ttu-id="9f5b3-130">Quando il parametro *CredentialsType* è impostato su 2 (servizio Windows), il server di report usa la sicurezza integrata per la connessione al database del server di report e i parametri *UserName* e *Password* vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-130">When the *CredentialsType* parameter is set to 2 (Windows Service), the report server uses integrated security to connect to the report server database and the *UserName* and *Password* parameters are ignored.</span></span> <span data-ttu-id="9f5b3-131">Il servizio Web ReportServer userà l'account [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] o l'account del pool di applicazioni e l'account del servizio Windows per accedere al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-131">The Reporting Server Web service will use either the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account or an application pool's account and the Windows service account to access the report server database.</span></span>  
  
 <span data-ttu-id="9f5b3-132">Quando viene chiamato, il metodo SetDatabaseConnection crittografa e archivia le credenziali e le informazioni di database nel file di configurazione per il server di report specificato.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-132">When called, the SetDatabaseConnection method encrypts and stores the credentials and database information in the configuration file for the specified report server.</span></span>  
  
 <span data-ttu-id="9f5b3-133">Il metodo SetDatabaseConnection non verifica che il server di report sia in grado di connettersi al database del server di report tramite i dati specificati.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-133">The SetDatabaseConnection method does not check that the report server can connect to the report server database using the data specified.</span></span>  
  
 <span data-ttu-id="9f5b3-134">Quando viene impostata per la prima volta, la proprietà ConnectionPoolSize viene impostata in base ai seguenti processori: ConnectionPoolSize = #Processors \* 75.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-134">When set for the first time, the ConnectionPoolSize property is set based on the following processors: ConnectionPoolSize = #Processors \* 75.</span></span>  
  
 <span data-ttu-id="9f5b3-135">Il metodo SetDatabaseConnection non concede autorizzazioni agli account specificati.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-135">The SetDatabaseConnection method does not grant permissions to the specified account(s).</span></span> <span data-ttu-id="9f5b3-136">È necessario chiamare il metodo [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) per ogni account che richiede l'accesso al database del server di report ed eseguire lo script risultante.</span><span class="sxs-lookup"><span data-stu-id="9f5b3-136">You must call the [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) method for each account that requires access to the report server database and run the resulting script.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f5b3-137">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f5b3-137">Requirements</span></span>  
 <span data-ttu-id="9f5b3-138">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f5b3-138">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f5b3-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f5b3-139">See Also</span></span>  
 [<span data-ttu-id="9f5b3-140">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="9f5b3-140">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
