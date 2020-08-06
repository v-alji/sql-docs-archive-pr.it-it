---
title: Gestione di errori e avvisi (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- inline errors [XMLA]
- SOAP faults [XML for Analysis]
- XML for Analysis, errors
- faults [XML for Analysis]
- messages [XML for Analysis]
- XMLA, errors
- warnings [XML for Analysis]
- inline warnings [XMLA]
ms.assetid: ab895282-098d-468e-9460-032598961f45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07b88d800237e5b4b06af0c1ff11cbd0af846600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627480"
---
# <a name="handling-errors-and-warnings-xmla"></a><span data-ttu-id="e9f37-102">Gestione di errori e avvisi (XMLA)</span><span class="sxs-lookup"><span data-stu-id="e9f37-102">Handling Errors and Warnings (XMLA)</span></span>
  <span data-ttu-id="e9f37-103">La gestione degli errori è obbligatoria quando una chiamata al metodo [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) o [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) di XML for Analysis (XMLA) non viene eseguita, viene eseguita correttamente, ma genera errori o avvisi oppure viene eseguita correttamente, ma restituisce risultati che contengono errori.</span><span class="sxs-lookup"><span data-stu-id="e9f37-103">Error handling is required when an XML for Analysis (XMLA) [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) or [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method call does not run, runs successfully but generates errors or warnings, or runs successfully but returns results that contain errors.</span></span>  
  
|<span data-ttu-id="e9f37-104">Errore</span><span class="sxs-lookup"><span data-stu-id="e9f37-104">Error</span></span>|<span data-ttu-id="e9f37-105">Report</span><span class="sxs-lookup"><span data-stu-id="e9f37-105">Reporting</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="e9f37-106">Chiamata al metodo XMLA non eseguita</span><span class="sxs-lookup"><span data-stu-id="e9f37-106">The XMLA method call does not run</span></span>|[!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="e9f37-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] restituisce un messaggio di errore SOAP contenente i dettagli dell'errore.</span><span class="sxs-lookup"><span data-stu-id="e9f37-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns a SOAP fault message that contains the details of the failure.</span></span><br /><br /> <span data-ttu-id="e9f37-108">Per ulteriori informazioni, vedere la sezione relativa alla [gestione degli errori SOAP](#handling_soap_faults).</span><span class="sxs-lookup"><span data-stu-id="e9f37-108">For more information, see the section, [Handling SOAP Faults](#handling_soap_faults).</span></span>|  
|<span data-ttu-id="e9f37-109">Errori o avvisi in una chiamata al metodo eseguita correttamente</span><span class="sxs-lookup"><span data-stu-id="e9f37-109">Errors or warnings on a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="e9f37-110">include un elemento [Error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) o [warning](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) per ogni errore o avviso, rispettivamente, nella proprietà [messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) dell'elemento [radice](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) che contiene i risultati della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="e9f37-110">includes an [error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) or [warning](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) element for each error or warning, respectively, in the [Messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) property of the [root](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) element that contains the results of the method call.</span></span><br /><br /> <span data-ttu-id="e9f37-111">Per ulteriori informazioni, vedere la sezione [gestione di errori e avvisi](#handling_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="e9f37-111">For more information, see the section, [Handling Errors and Warnings](#handling_errors_and_warnings).</span></span>|  
|<span data-ttu-id="e9f37-112">Errori nel risultato di una chiamata al metodo eseguita correttamente</span><span class="sxs-lookup"><span data-stu-id="e9f37-112">Errors in the result for a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="e9f37-113">include un elemento inline `error` o `warning` per l'errore o l'avviso, rispettivamente, all'interno dell'elemento [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) o [Row](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) appropriato dei risultati della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="e9f37-113">includes an inline `error` or `warning` element for the error or warning, respectively, within the appropriate [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) or [row](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) element of the results of the method call.</span></span><br /><br /> <span data-ttu-id="e9f37-114">Per ulteriori informazioni, vedere la sezione [gestione di errori e avvisi inline](#handling_inline_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="e9f37-114">For more information, see the section, [Handling Inline Errors and Warnings](#handling_inline_errors_and_warnings).</span></span>|  
  
##  <a name="handling-soap-faults"></a><a name="handling_soap_faults"></a><span data-ttu-id="e9f37-115">Gestione degli errori SOAP</span><span class="sxs-lookup"><span data-stu-id="e9f37-115">Handling SOAP Faults</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="e9f37-116">restituisce un errore SOAP quando si verificano le situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9f37-116">returns a SOAP fault when the following situations occur:</span></span>  
  
-   <span data-ttu-id="e9f37-117">Il messaggio SOAP che contiene il metodo XMLA non è in formato corretto o non è stato convalidato dall'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9f37-117">The SOAP message that contains the XMLA method was not well-formed or could not be validated by the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="e9f37-118">Si è verificato un errore di comunicazione o di altro tipo relativo al messaggio SOAP che contiene il metodo XMLA.</span><span class="sxs-lookup"><span data-stu-id="e9f37-118">A communications or other error occurred involving the SOAP message that contains the XMLA method.</span></span>  
  
-   <span data-ttu-id="e9f37-119">Il metodo XMLA non è stato eseguito nell'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9f37-119">The XMLA method did not run on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="e9f37-120">Il codice di errore SOAP per XMLstartA inizia con "XMLForAnalysis", seguito da un punto e dal codice esadecimale restituito HRESULT.</span><span class="sxs-lookup"><span data-stu-id="e9f37-120">The SOAP fault codes for XMLstartA start with "XMLForAnalysis", followed by a period and the hexadecimal HRESULT result code.</span></span> <span data-ttu-id="e9f37-121">Un codice di errore "`0x80000005`" viene formattato come "`XMLForAnalysis.0x80000005`".</span><span class="sxs-lookup"><span data-stu-id="e9f37-121">For example, an error code of "`0x80000005`" is formatted as "`XMLForAnalysis.0x80000005`".</span></span> <span data-ttu-id="e9f37-122">Per ulteriori informazioni sul formato degli errori SOAP, vedere l'argomento relativo nel documento Simple Object Access Protocol (SOAP) 1.1 del World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="e9f37-122">For more information about the SOAP fault format, see Soap Fault in the W3C Simple Object Access Protocol (SOAP) 1.1.</span></span>  
  
### <a name="fault-code-information"></a><span data-ttu-id="e9f37-123">Informazioni sul codice di errore</span><span class="sxs-lookup"><span data-stu-id="e9f37-123">Fault Code Information</span></span>  
 <span data-ttu-id="e9f37-124">Nella tabella seguente vengono elencate le informazioni sul codice di errore XMLA contenute nella sezione dei dettagli della risposta SOAP.</span><span class="sxs-lookup"><span data-stu-id="e9f37-124">The following table shows the XMLA fault code information that is contained in the detail section of the SOAP response.</span></span> <span data-ttu-id="e9f37-125">Le colonne rappresentano gli attributi di un errore nella sezione dei dettagli di un errore SOAP.</span><span class="sxs-lookup"><span data-stu-id="e9f37-125">The columns are the attributes of an error in the detail section of a SOAP fault.</span></span>  
  
|<span data-ttu-id="e9f37-126">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="e9f37-126">Column name</span></span>|<span data-ttu-id="e9f37-127">Type</span><span class="sxs-lookup"><span data-stu-id="e9f37-127">Type</span></span>|<span data-ttu-id="e9f37-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9f37-128">Description</span></span>|<span data-ttu-id="e9f37-129">Valore null consentito<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e9f37-129">Null allowed<sup>1</sup></span></span>|  
|-----------------|----------|-----------------|------------------------------|  
|`ErrorCode`|`UnsignedInt`|<span data-ttu-id="e9f37-130">Codice restituito che indica l'esito positivo o negativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="e9f37-130">Return code that indicates the success or failure of the method.</span></span> <span data-ttu-id="e9f37-131">Il valore esadecimale deve essere convertito in un valore `UnsignedInt`.</span><span class="sxs-lookup"><span data-stu-id="e9f37-131">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="e9f37-132">No</span><span class="sxs-lookup"><span data-stu-id="e9f37-132">No</span></span>|  
|`WarningCode`|`UnsignedInt`|<span data-ttu-id="e9f37-133">Codice restituito che indica una condizione di avviso.</span><span class="sxs-lookup"><span data-stu-id="e9f37-133">Return code that indicates a warning condition.</span></span> <span data-ttu-id="e9f37-134">Il valore esadecimale deve essere convertito in un valore `UnsignedInt`.</span><span class="sxs-lookup"><span data-stu-id="e9f37-134">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="e9f37-135">Sì</span><span class="sxs-lookup"><span data-stu-id="e9f37-135">Yes</span></span>|  
|`Description`|`String`|<span data-ttu-id="e9f37-136">Testo o descrizione dell'errore o dell'avviso restituiti dal componente che ha generato l'errore.</span><span class="sxs-lookup"><span data-stu-id="e9f37-136">Error or warning text and description returned by the component that generated the error.</span></span>|<span data-ttu-id="e9f37-137">Sì</span><span class="sxs-lookup"><span data-stu-id="e9f37-137">Yes</span></span>|  
|`Source`|`String`|<span data-ttu-id="e9f37-138">Nome del componente che ha generato l'errore o l'avviso.</span><span class="sxs-lookup"><span data-stu-id="e9f37-138">Name of the component that generated the error or warning.</span></span>|<span data-ttu-id="e9f37-139">Sì</span><span class="sxs-lookup"><span data-stu-id="e9f37-139">Yes</span></span>|  
|`HelpFile`|`String`|<span data-ttu-id="e9f37-140">Percorso o URL del file o dell'argomento della Guida in cui è descritto l'errore o l'avviso.</span><span class="sxs-lookup"><span data-stu-id="e9f37-140">Path or URL to the Help file or topic that describes the error or warning.</span></span>|<span data-ttu-id="e9f37-141">Sì</span><span class="sxs-lookup"><span data-stu-id="e9f37-141">Yes</span></span>|  
  
 <span data-ttu-id="e9f37-142"><sup>1</sup> indica se i dati sono obbligatori e devono essere restituiti o se i dati sono facoltativi ed è consentita una stringa null se la colonna non è applicabile.</span><span class="sxs-lookup"><span data-stu-id="e9f37-142"><sup>1</sup> Indicates whether the data is required and must be returned, or whether the data is optional and a null string is allowed if the column does not apply.</span></span>  
  
 <span data-ttu-id="e9f37-143">Di seguito viene riportato un esempio di errore SOAP che si è verificato quando una chiamata al metodo non è riuscita:</span><span class="sxs-lookup"><span data-stu-id="e9f37-143">The following is an example of a SOAP fault that occurred when a method call failed:</span></span>  
  
```  
<?xml version="1.0"?>  
   <SOAP-ENV:Envelope  
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
   SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
      <SOAP-ENV:Fault>  
         <faultcode>XMLAnalysisError.0x80000005</faultcode>  
         <faultstring>The XML for Analysis provider encountered an error.</faultstring>  
         <faultactor>XML for Analysis Provider</faultactor>  
         <detail>  
<Error  
ErrorCode="2147483653"  
Description="An unexpected error has occurred."  
Source="XML for Analysis Provider"  
HelpFile="" />  
         </detail>  
      </SOAP-ENV:Fault>  
</SOAP-ENV:Envelope>  
```  
  
##  <a name="handling-errors-and-warnings"></a><a name="handling_errors_and_warnings"></a><span data-ttu-id="e9f37-144">Gestione di errori e avvisi</span><span class="sxs-lookup"><span data-stu-id="e9f37-144">Handling Errors and Warnings</span></span>  
 <span data-ttu-id="e9f37-145">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] viene restituita la proprietà `Messages` nell'elemento `root` per un comando se si verificano le situazioni seguenti dopo l'esecuzione del comando:</span><span class="sxs-lookup"><span data-stu-id="e9f37-145">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns the `Messages` property in the `root` element for a command if the following situations occur after that command runs:</span></span>  
  
-   <span data-ttu-id="e9f37-146">Il metodo non ha provocato alcun errore, ma si è verificato un errore nell'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dopo che la chiamata al metodo è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="e9f37-146">The method itself did not fail, but a failure occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the method call succeeded.</span></span>  
  
-   <span data-ttu-id="e9f37-147">L'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] restituisce un avviso quando il comando viene eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e9f37-147">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance returns a warning when the command is successful.</span></span>  
  
 <span data-ttu-id="e9f37-148">La proprietà `Messages` segue tutte le altre proprietà contenute nell'elemento `root` e può contenere uno o più elementi `Message`.</span><span class="sxs-lookup"><span data-stu-id="e9f37-148">The `Messages` property follows all other properties that are contained by the `root` element, and can contain one or more `Message` elements.</span></span> <span data-ttu-id="e9f37-149">A sua volta, ogni elemento `Message` può contenere un unico elemento `error` o `warning` che descrive rispettivamente tutti gli errori o gli avvisi che si sono verificati per il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="e9f37-149">In turn, each `Message` element can contain either a single `error` or `warning` element describing any errors or warnings, respectively, that occurred for the specified command.</span></span>  
  
 <span data-ttu-id="e9f37-150">Per ulteriori informazioni sugli errori e sugli avvisi contenuti nella `Messages` proprietà, vedere [elementi messages &#40;&#41;XMLA ](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="e9f37-150">For more information about errors and warnings that are contained in the `Messages` property, see [Messages Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span></span>  
  
### <a name="handling-errors-during-serialization"></a><span data-ttu-id="e9f37-151">Gestione di errori durante la serializzazione</span><span class="sxs-lookup"><span data-stu-id="e9f37-151">Handling Errors During Serialization</span></span>  
 <span data-ttu-id="e9f37-152">Se si verifica un errore dopo che l' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] istanza ha già iniziato a serializzare l'output di un comando eseguito correttamente, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] restituisce un elemento [Exception](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) in uno spazio dei nomi diverso al momento dell'errore.</span><span class="sxs-lookup"><span data-stu-id="e9f37-152">If an error occurs after the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance has already begun serializing the output of a successfully run command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an [Exception](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) element in a different namespace at the point of the error.</span></span> <span data-ttu-id="e9f37-153">L'istanza [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] chiude quindi tutti gli elementi aperti in modo che il documento XML inviato al client sia un valido.</span><span class="sxs-lookup"><span data-stu-id="e9f37-153">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance then closes all open elements so that the XML document sent to the client is a valid document.</span></span> <span data-ttu-id="e9f37-154">L'istanza restituisce inoltre un elemento `Messages` che contiene la descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="e9f37-154">The instance also returns a `Messages` element that contains the description of the error.</span></span>  
  
##  <a name="handling-inline-errors-and-warnings"></a><a name="handling_inline_errors_and_warnings"></a><span data-ttu-id="e9f37-155">Gestione di errori e avvisi inline</span><span class="sxs-lookup"><span data-stu-id="e9f37-155">Handling Inline Errors and Warnings</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="e9f37-156">restituisce un elemento inline `error` o `warning` per un comando se il metodo XMLA non ha provocato alcun errore, ma si è verificato un errore specifico per un elemento dati nei risultati restituiti dal metodo nell'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dopo che la chiamata al metodo XMLA è stata eseguita in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="e9f37-156">returns an inline `error` or `warning` for a command if the XMLA method itself did not fail, but an error specific to a data element in the results returned by the method occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the XMLA method call succeeded.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="e9f37-157">fornisce elementi inline `error` e `warning` se si verificano problemi specifici di una cella o di altri dati contenuti all'interno di un `root` elemento utilizzando il tipo di dati [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) , ad esempio un errore di sicurezza o un errore di formattazione per una cella.</span><span class="sxs-lookup"><span data-stu-id="e9f37-157">supplies inline `error` and `warning` elements if issues specific to a cell or to other data that are contained within a `root` element using the [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) data type occur, such as a security error or formatting error for a cell.</span></span> <span data-ttu-id="e9f37-158">In questi casi, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] restituisce un elemento `error` o `warning` nell'elemento `Cell` o `row` che contiene rispettivamente l'errore o l'avviso.</span><span class="sxs-lookup"><span data-stu-id="e9f37-158">In these cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an `error` or `warning` element in the `Cell` or `row` element that contains the error or warning, respectively.</span></span>  
  
 <span data-ttu-id="e9f37-159">Nell'esempio seguente viene illustrato un set di risultati contenente un errore nel set di righe restituito da un `Execute` metodo utilizzando il comando [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="e9f37-159">The following example illustrates a result set that contains an error in the rowset returned from an `Execute` method using the [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command.</span></span>  
  
```  
<return>  
   ...  
   <root>  
      ...  
      <CellData>  
      ...  
         <Cell CellOrdinal="10">  
            <Value>  
               <Error>  
                  <ErrorCode>2148497527</ErrorCode>   
                  <Description>Security Error.</Description>   
               </Error>  
            </Value>  
         </Cell>  
      </CellData>  
      ...  
   </root>  
   ...  
</return>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9f37-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9f37-160">See Also</span></span>  
 [<span data-ttu-id="e9f37-161">Sviluppo con XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e9f37-161">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
