---
title: ISSCommandWithParameters::SetParameterProperties (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::SetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- SetParameterProperties method
ms.assetid: 4cd0281a-a2a0-43df-8e46-eb478b64cb4b
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bf8e5cde9885a5d9b55d84c6384b76aecf50b8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713115"
---
# <a name="isscommandwithparameterssetparameterproperties-ole-db"></a><span data-ttu-id="1b8b3-102">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="1b8b3-102">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="1b8b3-103">Imposta le proprietà dei parametri per i singoli parametri in base al numero ordinale oppure imposta proprietà dei parametri bulk specificando una matrice di strutture SSPARAMPROPS.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-103">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of SSPARAMPROPS structures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b8b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b8b3-104">Syntax</span></span>  
  
```  
  
HRESULT SetParameterProperties(  
DB_UPARAMS cParams,   
SSPARAMPROPS rgParamProperties[]);  
```  
  
## <a name="arguments"></a><span data-ttu-id="1b8b3-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1b8b3-105">Arguments</span></span>  
 <span data-ttu-id="1b8b3-106">*cParams*[in]</span><span class="sxs-lookup"><span data-stu-id="1b8b3-106">*cParams*[in]</span></span>  
 <span data-ttu-id="1b8b3-107">Numero di strutture SSPARAMPROPS nella matrice *rgParamProperties*.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-107">The number of SSPARAMPROPS structures in the *rgParamProperties* array.</span></span> <span data-ttu-id="1b8b3-108">Se questo numero è zero, eliminerà `ISSCommandWithParameters::SetParameterProperties` tutte le proprietà che potrebbero essere state specificate per tutti i parametri nel comando.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-108">If this number is zero, `ISSCommandWithParameters::SetParameterProperties` will delete all properties that might have been specified for any parameters in the command.</span></span>  
  
 <span data-ttu-id="1b8b3-109">*rgParamProperties*[in]</span><span class="sxs-lookup"><span data-stu-id="1b8b3-109">*rgParamProperties*[in]</span></span>  
 <span data-ttu-id="1b8b3-110">Matrice di strutture SSPARAMPROPS da impostare.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-110">An array of SSPARAMPROPS structures to be set.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="1b8b3-111">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="1b8b3-111">Return Code Values</span></span>  
 <span data-ttu-id="1b8b3-112">Il `ISSCommandWithParameters::SetParameterProperties` metodo restituisce gli stessi codici di errore del metodo core OLE DB **ICommandProperties:: seproperties** .</span><span class="sxs-lookup"><span data-stu-id="1b8b3-112">The `ISSCommandWithParameters::SetParameterProperties` method returns the same error codes as the core OLE DB **ICommandProperties::SetProperties** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b8b3-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1b8b3-113">Remarks</span></span>  
 <span data-ttu-id="1b8b3-114">L'impostazione delle proprietà dei parametri con questo metodo è consentita per ogni parametro in base al numero ordinale oppure con una singola `ISSCommandWithParameters::SetParameterProperties` chiamata dopo che il SSPARAMPROPS è stato compilato dalla matrice di proprietà.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-114">Setting parameter properties with this method is allowed on a per parameter basis by ordinal, or with a single `ISSCommandWithParameters::SetParameterProperties` call once the SSPARAMPROPS has been built from the property array.</span></span>  
  
 <span data-ttu-id="1b8b3-115">Il metodo SetValue deve essere chiamato **prima di chiamare** il `ISSCommandWithParameters::SetParameterProperties` metodo.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-115">The **SetParameterInfo** method must be called before calling the `ISSCommandWithParameters::SetParameterProperties` method.</span></span> <span data-ttu-id="1b8b3-116">Se si chiama `SetParameterProperties(0, NULL)`, si cancellano tutte le proprietà di parametro specificate, mentre se si chiama `SetParameterInfo(0,NULL,NULL)`, si cancellano tutte le informazioni di parametro che includono le proprietà che potrebbero essere associate a un parametro.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-116">Calling `SetParameterProperties(0, NULL)` clears all specified parameter properties, while calling `SetParameterInfo(0,NULL,NULL)` clears all the parameter info including any properties that might be associated with a parameter.</span></span>  
  
 <span data-ttu-id="1b8b3-117">`ISSCommandWithParameters::SetParameterProperties`La chiamata a per specificare le proprietà per un parametro che non è di tipo DBTYPE_XML o DBTYPE_UDT restituisce DB_E_ERRORSOCCURRED o DB_S_ERRORSOCCURRED e contrassegna il campo *dwStatus* di tutti DBPROPS contenuti in SSPARAMPROPS per il parametro con DBPROPSTATUS_NOTSET.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-117">Calling `ISSCommandWithParameters::SetParameterProperties` to specify properties for a parameter which is not of type DBTYPE_XML or DBTYPE_UDT returns DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED and marks the *dwStatus* field of all DBPROPs contained in SSPARAMPROPS for that parameter with DBPROPSTATUS_NOTSET.</span></span> <span data-ttu-id="1b8b3-118">È necessario attraversare la matrice DBPROP di ogni proprietà DBPROPSET contenuta nella struttura SSPARAMPROPS per individuare il parametro al quale DB_E_ERRORSOCCURRED o DB_S_ERRORSOCCURRED fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-118">The DBPROP array of each DBPROPSET contained in SSPARAMPROPS should be traversed to detect which parameter the DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED refers to.</span></span>  
  
 <span data-ttu-id="1b8b3-119">Se `ISSCommandWithParameters::SetParameterProperties` viene chiamato il metodo per specificare le proprietà dei parametri le cui informazioni sui parametri non sono ancora state impostate con il metodo **sqlparameterinfo**, il provider restituisce E_UNEXPECTED con il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="1b8b3-119">If `ISSCommandWithParameters::SetParameterProperties` is called to specify the properties of parameters whose parameter info have not been set yet with **SetParameterInfo**, the provider returns E_UNEXPECTED with the following error message:</span></span>  
  
 <span data-ttu-id="1b8b3-120">Impossibile chiamare il metodo SetParameterProperties per i parametri specificati senza chiamare prima il metodo SetParameterInfo.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-120">SetParameterProperties method cannot be called for the specified parameters without first calling SetParameterInfo method.</span></span> <span data-ttu-id="1b8b3-121">È necessario impostare le informazioni sui parametri prima di impostare le proprietà dei parametri stessi.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-121">The parameter information must be set before setting the parameter properties.</span></span>  
  
 <span data-ttu-id="1b8b3-122">Se la chiamata a `ISSCommandWithParameters::SetParameterProperties` contiene alcuni parametri in cui sono state impostate le informazioni sul parametro e alcuni parametri in cui non sono state impostate le informazioni sul parametro, le proprietà dwStatus in DBPROPSET del set di proprietà SSPARAMPROPS restituiranno con DBSTATUS_NOTSET.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-122">If the call to `ISSCommandWithParameters::SetParameterProperties` contains some parameters where the parameter info has been set, and some parameters where the parameter info has not been set, the dwStatus properties in the DBPROPSET of the SSPARAMPROPS property set will return with DBSTATUS_NOTSET.</span></span>  
  
 <span data-ttu-id="1b8b3-123">La struttura SSPARAMPROPS viene definita nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1b8b3-123">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
 <span data-ttu-id="1b8b3-124">I miglioramenti apportati al motore di database a partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] consentono a ISSCommandWithParameters::SetParameterProperties di ottenere descrizioni più accurate dei risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-124">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow ISSCommandWithParameters::SetParameterProperties to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="1b8b3-125">È possibile che questi risultati più accurati differiscano dai valori restituiti da ISSCommandWithParameters::SetParameterProperties nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b8b3-125">These more accurate results may differ from the values returned by ISSCommandWithParameters::SetParameterProperties in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1b8b3-126">Per altre informazioni, vedere [Metadata Discovery](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="1b8b3-126">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
|<span data-ttu-id="1b8b3-127">Membro</span><span class="sxs-lookup"><span data-stu-id="1b8b3-127">Member</span></span>|<span data-ttu-id="1b8b3-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b8b3-128">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1b8b3-129">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="1b8b3-129">*iOrdinal*</span></span>|<span data-ttu-id="1b8b3-130">Numero ordinale del parametro passato.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-130">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="1b8b3-131">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="1b8b3-131">*cPropertySets*</span></span>|<span data-ttu-id="1b8b3-132">Numero di strutture DBPROPSET in *rgPropertySets*.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-132">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="1b8b3-133">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="1b8b3-133">*rgPropertySets*</span></span>|<span data-ttu-id="1b8b3-134">Puntatore alla memoria nel quale restituire una matrice di strutture DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="1b8b3-134">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b8b3-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b8b3-135">See Also</span></span>  
 [<span data-ttu-id="1b8b3-136">ISSCommandWithParameters &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1b8b3-136">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
