---
title: Abilitare e disabilitare RDL Sandboxing | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d5619e9f-ec5b-4376-9b34-1f74de6fade7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7af1477751093862c99d00978278315e600511e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719619"
---
# <a name="enable-and-disable-rdl-sandboxing"></a><span data-ttu-id="3bc9a-102">Abilitare e disabilitare la funzionalità RDL Sandboxing</span><span class="sxs-lookup"><span data-stu-id="3bc9a-102">Enable and Disable RDL Sandboxing</span></span>
  <span data-ttu-id="3bc9a-103">La caratteristica RDL (Report Definition Language) Sandboxing consente di rilevare e limitare l'utilizzo di tipi specifici di risorse in base a singoli tenant in un ambiente in cui più tenant utilizzano una sola Web farm di server di report.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-103">The RDL (Report Definition Language) Sandboxing feature lets you detect and restrict the usage of specific types of resources, by individual tenants, in an environment of multiple tenants that use a single web farm of report servers.</span></span> <span data-ttu-id="3bc9a-104">Un esempio di questo tipo è rappresentato dai servizi di hosting in cui è possibile gestire una sola Web farm di server di report utilizzati da più tenant e probabilmente da società diverse.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-104">An example of this is a hosting services scenario where you might maintain a single web farm of report servers that are used by multiple tenants, and perhaps different companies.</span></span> <span data-ttu-id="3bc9a-105">L'amministratore del server di report può abilitare questa caratteristica per ottenere gli obiettivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bc9a-105">As a report server administrator, you can enable this feature to help achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="3bc9a-106">Limitare le dimensioni delle risorse esterne.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-106">Restrict external resource sizes.</span></span> <span data-ttu-id="3bc9a-107">Le risorse esterne includono immagini, file con estensione xslt e dati mappa.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-107">External resources include images, .xslt files, and map data.</span></span>  
  
-   <span data-ttu-id="3bc9a-108">Al momento della pubblicazione del report, limitare i tipi e i membri utilizzati nel testo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-108">At report publish time, limit types and members that are used in expression text.</span></span>  
  
-   <span data-ttu-id="3bc9a-109">Al momento dell'elaborazione del report, limitare la lunghezza del testo e le dimensioni del valore restituito per le espressioni.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-109">At report processing time, limit the length of the text and the size of the return value for expressions.</span></span>  
  
 <span data-ttu-id="3bc9a-110">Quando RDL Sandboxing è abilitato, sono disabilitate le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bc9a-110">When RDL Sandboxing is enabled, the following features are disabled:</span></span>  
  
-   <span data-ttu-id="3bc9a-111">Codice personalizzato nell' **\<Code>** elemento di una definizione del report.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-111">Custom code in the **\<Code>** element of a report definition.</span></span>  
  
-   <span data-ttu-id="3bc9a-112">Modalità di compatibilità con le versioni precedenti di RDL per gli elementi di report personalizzati di [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3bc9a-112">RDL backward compatibility mode for [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] custom report items.</span></span>  
  
-   <span data-ttu-id="3bc9a-113">Parametri denominati nelle espressioni.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-113">Named parameters in expressions.</span></span>  
  
 <span data-ttu-id="3bc9a-114">In questo argomento viene descritto ogni elemento dell' `RDLSandboxing` elemento <> nel file RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-114">This topic describes each element in the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span> <span data-ttu-id="3bc9a-115">Per altre informazioni su come modificare questo file, vedere [Modificare un file di configurazione di Reporting Services &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="3bc9a-115">For more information about how to modify this file, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="3bc9a-116">Attività dei record del log di traccia del server correlata alla caratteristica RDL Sandboxing.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-116">A server trace log records activity related to the RDL Sandboxing feature.</span></span> <span data-ttu-id="3bc9a-117">Per altre informazioni sui log di traccia, vedere [Log di traccia del servizio del server di report](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="3bc9a-117">For more information about trace logs, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="3bc9a-118">Configurazione di esempio</span><span class="sxs-lookup"><span data-stu-id="3bc9a-118">Example Configuration</span></span>  
 <span data-ttu-id="3bc9a-119">Nell'esempio seguente vengono illustrate le impostazioni e i valori di esempio per l' `RDLSandboxing` elemento> <nel file RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-119">The following example shows the settings and example values for the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span>  
  
```  
<RDLSandboxing>  
   <MaxExpressionLength>5000</MaxExpressionLength>  
   <MaxResourceSize>5000</MaxResourceSize>  
   <MaxStringResultLength>3000</MaxStringResultLength>  
   <MaxArrayResultLength>250</MaxArrayResultLength>  
   <Types>  
      <Allow Namespace="System.Drawing" AllowNew="True">Bitmap</Allow>  
      <Allow Namespace="TypeConverters.Custom" AllowNew="True">*</Allow>  
   </Types>  
   <Members>  
      <Deny>Format</Deny>  
      <Deny>StrDup</Deny>  
   </Members>  
</RDLSandboxing>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="3bc9a-120">Impostazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="3bc9a-120">Configuration Settings</span></span>  
 <span data-ttu-id="3bc9a-121">Nella tabella seguente sono contenute le informazioni sulle impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-121">The following table provides information about configuration settings.</span></span> <span data-ttu-id="3bc9a-122">Le impostazioni sono elencate nell'ordine in cui vengono visualizzate nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-122">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="3bc9a-123">Impostazione</span><span class="sxs-lookup"><span data-stu-id="3bc9a-123">Setting</span></span>|<span data-ttu-id="3bc9a-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3bc9a-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3bc9a-125">**MaxExpressionLength**</span><span class="sxs-lookup"><span data-stu-id="3bc9a-125">**MaxExpressionLength**</span></span>|<span data-ttu-id="3bc9a-126">Numero massimo di caratteri consentiti nelle espressioni RDL.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-126">Maximum number of characters allowed in RDL expressions.</span></span><br /><br /> <span data-ttu-id="3bc9a-127">Valore predefinito: 1000</span><span class="sxs-lookup"><span data-stu-id="3bc9a-127">Default: 1000</span></span>|  
|<span data-ttu-id="3bc9a-128">**MaxResourceSize**</span><span class="sxs-lookup"><span data-stu-id="3bc9a-128">**MaxResourceSize**</span></span>|<span data-ttu-id="3bc9a-129">Numero massimo di KB consentiti per una risorsa esterna.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-129">Maximum number of KB allowed for an external resource.</span></span><br /><br /> <span data-ttu-id="3bc9a-130">Valore predefinito: 100</span><span class="sxs-lookup"><span data-stu-id="3bc9a-130">Default: 100</span></span>|  
|<span data-ttu-id="3bc9a-131">**MaxStringResultLength**</span><span class="sxs-lookup"><span data-stu-id="3bc9a-131">**MaxStringResultLength**</span></span>|<span data-ttu-id="3bc9a-132">Numero massimo di caratteri consentiti in un valore restituito per un'espressione RDL.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-132">Maximum number of characters allowed in a return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="3bc9a-133">Valore predefinito: 1000</span><span class="sxs-lookup"><span data-stu-id="3bc9a-133">Default: 1000</span></span>|  
|<span data-ttu-id="3bc9a-134">**MaxArrayResultLength**</span><span class="sxs-lookup"><span data-stu-id="3bc9a-134">**MaxArrayResultLength**</span></span>|<span data-ttu-id="3bc9a-135">Numero massimo di elementi consentiti in un valore restituito della matrice per un'espressione RDL.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-135">Maximum number of items allowed in an array return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="3bc9a-136">Valore predefinito: 100</span><span class="sxs-lookup"><span data-stu-id="3bc9a-136">Default: 100</span></span>|  
|<span data-ttu-id="3bc9a-137">**Tipi**</span><span class="sxs-lookup"><span data-stu-id="3bc9a-137">**Types**</span></span>|<span data-ttu-id="3bc9a-138">Elenco di membri da consentire nelle espressioni RDL.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-138">The list of members to allow within RDL expressions.</span></span>|  
|<span data-ttu-id="3bc9a-139">**Consentito**</span><span class="sxs-lookup"><span data-stu-id="3bc9a-139">**Allow**</span></span>|<span data-ttu-id="3bc9a-140">Tipo o set di tipi da consentire nelle espressioni RDL.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-140">A type or set of types to allow in RDL expressions.</span></span>|  
|<span data-ttu-id="3bc9a-141">**Spazio dei nomi**</span><span class="sxs-lookup"><span data-stu-id="3bc9a-141">**Namespace**</span></span>|<span data-ttu-id="3bc9a-142">Attributo per **Allow** che è lo spazio dei nomi contenente uno o più tipi applicabili a Value.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-142">Attribute for **Allow** that is the namespace that contains one or more types that apply to Value.</span></span> <span data-ttu-id="3bc9a-143">Questa proprietà supporta la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-143">This property is case-insensitive.</span></span>|  
|`AllowNew`|<span data-ttu-id="3bc9a-144">Attributo booleano per **Allow** che controlla se le nuove istanze del tipo possono essere create in espressioni RDL o in un elemento RDL **\<Class>** .</span><span class="sxs-lookup"><span data-stu-id="3bc9a-144">Boolean attribute for **Allow** that controls whether new instances of the type are allowed to be created in RDL expressions or in an RDL **\<Class>** element.</span></span><br /><br /> <span data-ttu-id="3bc9a-145">Nota: quando `RDLSandboxing` è abilitato, non è possibile creare nuove matrici nelle espressioni RDL, indipendentemente dall'impostazione di `AllowNew` .</span><span class="sxs-lookup"><span data-stu-id="3bc9a-145">Note: When `RDLSandboxing` is enabled, new arrays cannot be created in RDL expressions, regardless of the setting of `AllowNew`.</span></span>|  
|<span data-ttu-id="3bc9a-146">**Valore**</span><span class="sxs-lookup"><span data-stu-id="3bc9a-146">**Value**</span></span>|<span data-ttu-id="3bc9a-147">Valore per **Allow** che è il nome del tipo da consentire nelle espressioni RDL.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-147">Value for **Allow** that is the name of the type to allow in RDL expressions.</span></span> <span data-ttu-id="3bc9a-148">Il valore **\*** indica che sono consentiti tutti i tipi nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-148">The value **\*** indicates that all types in the namespace are allowed.</span></span> <span data-ttu-id="3bc9a-149">Questa proprietà supporta la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-149">This property is case-insensitive.</span></span>|  
|<span data-ttu-id="3bc9a-150">**Membri**</span><span class="sxs-lookup"><span data-stu-id="3bc9a-150">**Members**</span></span>|<span data-ttu-id="3bc9a-151">Per l'elenco dei tipi inclusi nell' **\<Types>** elemento, l'elenco dei nomi dei membri non consentiti nelle espressioni RDL.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-151">For the list of types that are include in the **\<Types>** element, the list of member names that are not allowed in RDL expressions.</span></span>|  
|<span data-ttu-id="3bc9a-152">**Nega**</span><span class="sxs-lookup"><span data-stu-id="3bc9a-152">**Deny**</span></span>|<span data-ttu-id="3bc9a-153">Nome di un membro non consentito nelle espressioni RDL.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-153">The name of a member that is not allowed in RDL expressions.</span></span> <span data-ttu-id="3bc9a-154">Questa proprietà supporta la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-154">This property is case-insensitive.</span></span><br /><br /> <span data-ttu-id="3bc9a-155">Nota: quando per un membro è specificato **Deny** , non è consentito alcun membro con questo nome per nessun tipo.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-155">Note: When **Deny** is specified for a member, all members with this name for all types are not allowed.</span></span>|  
  
## <a name="working-with-expressions-when-rdl-sandboxing-is-enabled"></a><span data-ttu-id="3bc9a-156">Utilizzo delle espressioni con RDL Sandboxing abilitato</span><span class="sxs-lookup"><span data-stu-id="3bc9a-156">Working with Expressions when RDL Sandboxing is Enabled</span></span>  
 <span data-ttu-id="3bc9a-157">È possibile modificare la caratteristica RDL Sandboxing per facilitare la gestione delle risorse utilizzate da un'espressione nelle modalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bc9a-157">You can modify the RDL Sandboxing feature to help manage the resources that are used by an expression in the following ways:</span></span>  
  
-   <span data-ttu-id="3bc9a-158">Limitare il numero di caratteri utilizzati per un'espressione.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-158">Restrict the number of characters that are used for an expression.</span></span>  
  
-   <span data-ttu-id="3bc9a-159">Limitare le dimensioni del risultato restituito da un'espressione.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-159">Restrict the size of the result returned by an expression.</span></span>  
  
-   <span data-ttu-id="3bc9a-160">Consentire un elenco specifico di tipi che possono essere utilizzati in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-160">Allow a specific list of types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="3bc9a-161">Limitare l'elenco dei membri in base al nome per l'elenco dei tipi consentiti che possono essere utilizzati in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-161">Restrict the list of members by name for the list of allowed types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="3bc9a-162">La caratteristica RDL Sandboxing consente di creare un elenco di tipi approvati e un elenco di membri non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-162">The RDL Sandboxing feature enables you to create a list of approved types and a list of denied members.</span></span> <span data-ttu-id="3bc9a-163">L'elenco dei tipi approvati viene denominato elenco consentiti</span><span class="sxs-lookup"><span data-stu-id="3bc9a-163">The list of approved types is called an allow list.</span></span> <span data-ttu-id="3bc9a-164">mentre l'elenco di membri non autorizzati viene denominato elenco bloccati.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-164">The list of denied members is called a block list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3bc9a-165">Nella definizione del report, un computer non può conoscere il tipo di ogni istanza di un riferimento all'espressione.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-165">In the report definition, a computer cannot know the type of each instances of an expression reference.</span></span> <span data-ttu-id="3bc9a-166">Quando si aggiunge un membro all'elenco bloccati, vengono negati tutti i membri con quel nome in tutti i tipi nell'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-166">When you add a member to the block list, you are denying all members of that name across all types in the allow list.</span></span>  
  
 <span data-ttu-id="3bc9a-167">I risultati dell'espressione RDL vengono verificati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-167">RDL expression results are verified at run time.</span></span> <span data-ttu-id="3bc9a-168">Le espressioni RDL vengono verificate nella definizione del report durante la pubblicazione di quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-168">RDL expressions are verified in the report definition when the report is published.</span></span> <span data-ttu-id="3bc9a-169">Monitorare il log di traccia del server di report relativamente alle violazioni.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-169">Monitor the report server trace log for violations.</span></span> <span data-ttu-id="3bc9a-170">Per altre informazioni, vedere [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="3bc9a-170">For more information, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
### <a name="working-with-types"></a><span data-ttu-id="3bc9a-171">Utilizzo dei tipi</span><span class="sxs-lookup"><span data-stu-id="3bc9a-171">Working with Types</span></span>  
 <span data-ttu-id="3bc9a-172">Quando si aggiunge un tipo all'elenco consentiti, vengono controllati i punti di ingresso seguenti per l'accesso alle espressioni RDL:</span><span class="sxs-lookup"><span data-stu-id="3bc9a-172">When you add a type to the allow list, you are controlling the following entry points to access RDL expressions:</span></span>  
  
-   <span data-ttu-id="3bc9a-173">Membri statici di un tipo.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-173">Static members of a type.</span></span>  
  
-   <span data-ttu-id="3bc9a-174">[!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` Metodo.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-174">The [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` method.</span></span>  
  
-   <span data-ttu-id="3bc9a-175">**\<Classes>** Elemento nella definizione del report.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-175">The **\<Classes>** element in the report definition.</span></span>  
  
-   <span data-ttu-id="3bc9a-176">Membri aggiunti all'elenco bloccati per un tipo nell'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-176">Members that you have added to the block list for a type in the allow list.</span></span>  
  
 <span data-ttu-id="3bc9a-177">L'elenco consentiti non controlla i punti di ingresso seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bc9a-177">The allow list does not control the following entry points:</span></span>  
  
-   <span data-ttu-id="3bc9a-178">Set di dati del report.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-178">Report datasets.</span></span> <span data-ttu-id="3bc9a-179">I campi nei set di dati del report restituiti dalle query potrebbero contenere qualsiasi tipo RDL valido.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-179">Fields in report datasets that are returned from queries might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="3bc9a-180">Parametri di report.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-180">Report parameters.</span></span> <span data-ttu-id="3bc9a-181">I valori dei parametri forniti dall'utente potrebbero contenere qualsiasi tipo RDL valido.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-181">User-supplied parameter values might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="3bc9a-182">Membri di un tipo abilitato non inclusi nell'elenco bloccati.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-182">Members of an enabled type that are not in the block list.</span></span> <span data-ttu-id="3bc9a-183">Per impostazione predefinita, vengono abilitati tutti i membri di tutti i tipi nell'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-183">By default, all members of all types in the allow list are enabled.</span></span> <span data-ttu-id="3bc9a-184">Quando si aggiunge il nome di un membro all'elenco bloccati, vengono negati tutti i membri con quel nome in tutti i tipi nell'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-184">When you add a member name to the block list, you are denying all members with that name across all types that are in the allow list.</span></span>  
  
 <span data-ttu-id="3bc9a-185">Per abilitare un membro di un tipo ma negare un membro con lo stesso nome per un tipo diverso, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bc9a-185">To enable a member of one type but deny a member with the same name for a different type, you must do the following:</span></span>  
  
-   <span data-ttu-id="3bc9a-186">Aggiungere un **\<Deny>** elemento per il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-186">Add a **\<Deny>** element for the member name.</span></span>  
  
-   <span data-ttu-id="3bc9a-187">Creare un membro proxy con un nome diverso in una classe di un assembly personalizzato per il membro che si desidera abilitare.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-187">Create a proxy member with a different name on a class in a custom assembly for the member that you want to enable.</span></span>  
  
-   <span data-ttu-id="3bc9a-188">Aggiungere la nuova classe all'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-188">Add that new class to the allow list.</span></span>  
  
 <span data-ttu-id="3bc9a-189">Per aggiungere funzioni .NET Framework di [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] all'elenco degli elementi consentiti, aggiungere i tipi corrispondenti dallo spazio dei nomi Microsoft.VisualBasic all'elenco.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-189">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework functions to the allow list, add the corresponding types from the Microsoft.VisualBasic namespace to the allow list.</span></span>  
  
 <span data-ttu-id="3bc9a-190">Per aggiungere le parole chiave tipo di [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework all'elenco consentiti, aggiungere il tipo CLR corrispondente all'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-190">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework type keywords to the allow list, add the corresponding CLR type to the allow list.</span></span> <span data-ttu-id="3bc9a-191">Ad esempio, per usare la [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] parola chiave .NET Framework `Integer` , aggiungere il frammento XML seguente all' **\<RDLSandboxing>** elemento:</span><span class="sxs-lookup"><span data-stu-id="3bc9a-191">For example, to use the [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework keyword `Integer`, add the following XML fragment to the **\<RDLSandboxing>** element:</span></span>  
  
```  
<Allow Namespace="System">Int32</Allow>  
```  
  
 <span data-ttu-id="3bc9a-192">Per aggiungere un tipo che ammette valori Null o un tipo generico .NET Framework di [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] , è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bc9a-192">To add a generic or a [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type to the allow list, you must do the following:</span></span>  
  
-   <span data-ttu-id="3bc9a-193">Creare un tipo proxy per il tipo generico o che ammette valori Null di [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-193">Create a proxy type for the generic or [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type.</span></span>  
  
-   <span data-ttu-id="3bc9a-194">Aggiungere il tipo di proxy all'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-194">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="3bc9a-195">L'aggiunta di un tipo da un assembly personalizzato all'elenco consentiti non concede in modo implicito autorizzazioni di esecuzione sull'assembly.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-195">Adding a type from a custom assembly to the allow list does not implicitly grant execute permission on the assembly.</span></span> <span data-ttu-id="3bc9a-196">È necessario modificare in modo specifico il file di sicurezza per l'accesso al codice e fornire autorizzazioni di esecuzione all'assembly.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-196">You must specifically modify the code access security file and provide execute permission to your assembly.</span></span> <span data-ttu-id="3bc9a-197">Per altre informazioni, vedere [Sicurezza dall'accesso di codice in Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3bc9a-197">For more information, see [Code Access Security in Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span></span>  
  
#### <a name="maintaining-the-deny-list-of-members"></a><span data-ttu-id="3bc9a-198">Gestione dell' \<Deny> elenco di membri</span><span class="sxs-lookup"><span data-stu-id="3bc9a-198">Maintaining the \<Deny> List of Members</span></span>  
 <span data-ttu-id="3bc9a-199">Quando si aggiunge un nuovo tipo all'elenco consentiti, attenersi all'elenco seguente per determinare quando potrebbe essere necessario aggiornare l'elenco dei membri bloccati:</span><span class="sxs-lookup"><span data-stu-id="3bc9a-199">When you add a new type to the allow list, use the following list to determine when you might have to update the block list of members:</span></span>  
  
-   <span data-ttu-id="3bc9a-200">Quando si aggiorna un assembly personalizzato con una versione che introduce nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-200">When you update a custom assembly with a version that introduces new types.</span></span>  
  
-   <span data-ttu-id="3bc9a-201">Quando si aggiungono membri ai tipi nell'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-201">When you add members to the types in the allow list.</span></span>  
  
-   <span data-ttu-id="3bc9a-202">Quando si aggiorna [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] nel server di report.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-202">When you update the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] on the report server.</span></span>  
  
-   <span data-ttu-id="3bc9a-203">Quando si aggiorna il server di report a una versione successiva di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bc9a-203">When you upgrade the report server to a later version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="3bc9a-204">Quando si aggiorna un server di report per gestire uno schema RDL successivamente, dal momento che è probabile che nuovi membri siano stati aggiunti ai tipi RDL.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-204">When you update a report server to handle a later RDL schema, because new members might have been added to RDL types.</span></span>  
  
### <a name="working-with-operators-and-new"></a><span data-ttu-id="3bc9a-205">Utilizzo di operatori e dell'operatore New</span><span class="sxs-lookup"><span data-stu-id="3bc9a-205">Working with Operators and New</span></span>  
 <span data-ttu-id="3bc9a-206">Per impostazione predefinita, gli operatori di linguaggio di [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework sono sempre consentiti, eccetto per `New`.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-206">By default, [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework language operators, except for `New`, are always allowed.</span></span> <span data-ttu-id="3bc9a-207">L' `New` operatore è controllato dall' `AllowNew` attributo sull' **\<Allow>** elemento.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-207">The `New` operator is controlled by the `AllowNew` attribute on the **\<Allow>** element.</span></span> <span data-ttu-id="3bc9a-208">Sono sempre consentiti altri operatori di linguaggio, ad esempio l'operatore della funzione di accesso alla raccolta predefinito `!` e [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework le macro di cast, ad esempio `CInt` .</span><span class="sxs-lookup"><span data-stu-id="3bc9a-208">Other language operators, such as the default collection accessor operator `!` and [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework cast macros such as `CInt`, are always allowed.</span></span>  
  
 <span data-ttu-id="3bc9a-209">L'aggiunta di operatori, inclusi quelli personalizzati, a un elenco bloccati non è supportata.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-209">Adding operators to a block list, including custom operators, is not supported.</span></span> <span data-ttu-id="3bc9a-210">Per escludere operatori per un tipo, è necessario effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bc9a-210">To exclude operators for a type, you must do the following:</span></span>  
  
-   <span data-ttu-id="3bc9a-211">Creare un tipo di proxy che non implementa gli operatori che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-211">Create a proxy type that does not implement the operators that you want to exclude.</span></span>  
  
-   <span data-ttu-id="3bc9a-212">Aggiungere il tipo di proxy all'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-212">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="3bc9a-213">Per creare una nuova matrice in un'espressione RDL, creare la matrice in un metodo in una classe definita e aggiungere quella classe all'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-213">To create a new array in an RDL expression, create the array in a method on a class that you define, and add that class to the allow list.</span></span>  
  
 <span data-ttu-id="3bc9a-214">Per creare una nuova matrice in un'espressione RDL, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bc9a-214">To create a new array in an RDL expression, you must do the following:</span></span>  
  
-   <span data-ttu-id="3bc9a-215">Definire una nuova classe e creare la matrice in un metodo in quella classe.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-215">Define a new class and create the array in a method on that class.</span></span>  
  
-   <span data-ttu-id="3bc9a-216">Aggiungere la classe all'elenco consentiti.</span><span class="sxs-lookup"><span data-stu-id="3bc9a-216">Add the class to the allow list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc9a-217">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bc9a-217">See Also</span></span>  
 <span data-ttu-id="3bc9a-218">[File di configurazione RSReportServer](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="3bc9a-218">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 [<span data-ttu-id="3bc9a-219">Report Server Service Trace Log</span><span class="sxs-lookup"><span data-stu-id="3bc9a-219">Report Server Service Trace Log</span></span>](report-server/report-server-service-trace-log.md)  
  
  
