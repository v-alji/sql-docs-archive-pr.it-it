---
title: ISSCommandWithParameters::GetParameterProperties (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::GetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetParameterProperties method
ms.assetid: 7f4cc5ea-d028-4fe5-9192-bd153ab3c26c
author: rothja
ms.author: jroth
ms.openlocfilehash: 2160c93748375a4aa3bee3d530d441182204134a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626743"
---
# <a name="isscommandwithparametersgetparameterproperties-ole-db"></a><span data-ttu-id="c3670-102">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="c3670-102">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="c3670-103">Restituisce una matrice di strutture di set di proprietà SSPARAMPROPS, un set di proprietà SSPARAMPROPS per ogni tipo definito dall'utente o parametro XML.</span><span class="sxs-lookup"><span data-stu-id="c3670-103">Returns an array of SSPARAMPROPS property set structures, one SSPARAMPROPS property set for each UDT or XML parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3670-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3670-104">Syntax</span></span>  
  
```  
  
HRESULT GetParameterProperties(  
DB_UPARAMS *pcParams,  
SSPARAMPROPS **prgParamProperties);  
```  
  
## <a name="arguments"></a><span data-ttu-id="c3670-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c3670-105">Arguments</span></span>  
 <span data-ttu-id="c3670-106">*pcParams*[out][in]</span><span class="sxs-lookup"><span data-stu-id="c3670-106">*pcParams*[out][in]</span></span>  
 <span data-ttu-id="c3670-107">Puntatore alla memoria contenente il numero di strutture SSPARAMPROPS restituite in *prgParamProperties*.</span><span class="sxs-lookup"><span data-stu-id="c3670-107">A pointer to memory that contains the number of SSPARAMPROPS structures returned in *prgParamProperties*.</span></span>  
  
 <span data-ttu-id="c3670-108">*prgParamProperties*[out]</span><span class="sxs-lookup"><span data-stu-id="c3670-108">*prgParamProperties*[out]</span></span>  
 <span data-ttu-id="c3670-109">Puntatore alla memoria nel quale viene restituita una matrice di strutture SSPARAMPROPS.</span><span class="sxs-lookup"><span data-stu-id="c3670-109">A pointer to memory in which an array of SSPARAMPROPS structures is returned.</span></span> <span data-ttu-id="c3670-110">Il provider alloca memoria per le strutture e restituisce l'indirizzo alla memoria. il consumer rilascia la memoria con **IMalloc:: Free** quando non necessita più delle strutture.</span><span class="sxs-lookup"><span data-stu-id="c3670-110">The provider allocates memory for the structures and returns the address to this memory; the consumer releases this memory with **IMalloc::Free** when it no longer needs the structures.</span></span> <span data-ttu-id="c3670-111">Prima di chiamare **IMalloc:: Free** per *prgParamProperties*, il consumer deve chiamare anche **VariantClear** per la proprietà *vValue* di ogni struttura DBPROP per evitare una perdita di memoria nei casi in cui la variante contiene un tipo di riferimento, ad esempio un BSTR. Se *pcParams* è zero nell'output o si verifica un errore diverso da DB_E_ERRORSOCCURRED, il provider non alloca alcuna memoria e assicura che *prgParamProperties* sia un puntatore null nell'output.</span><span class="sxs-lookup"><span data-stu-id="c3670-111">Before calling **IMalloc::Free** for *prgParamProperties*, the consumer must also call **VariantClear** for the *vValue* property of each DBPROP structure in order to prevent a memory leak in cases where the variant contains a reference type (such as a BSTR.) If *pcParams* is zero on output or an error other than DB_E_ERRORSOCCURRED occurs, the provider does not allocate any memory and ensures that *prgParamProperties* is a null pointer on output.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="c3670-112">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="c3670-112">Return Code Values</span></span>  
 <span data-ttu-id="c3670-113">Il metodo **GetParameterProperties** restituisce gli stessi codici di errore del metodo Core OLE DB **ICommandProperties:: GetProperties** , ad eccezione del fatto che non è possibile generare DB_S_ERRORSOCCURRED e DB_E_ERRORSOCCURED.</span><span class="sxs-lookup"><span data-stu-id="c3670-113">The **GetParameterProperties** method returns the same error codes as the core OLE DB **ICommandProperties::GetProperties** method, except that DB_S_ERRORSOCCURRED and DB_E_ERRORSOCCURED cannot be raised.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3670-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c3670-114">Remarks</span></span>  
 <span data-ttu-id="c3670-115">**ISSCommandWithParameters:: GetParameterProperties** si comporta in modo coerente rispetto a **GetParameterInfo**.</span><span class="sxs-lookup"><span data-stu-id="c3670-115">**ISSCommandWithParameters::GetParameterProperties** behaves consistently with respect to **GetParameterInfo**.</span></span> <span data-ttu-id="c3670-116">Se [ISSCommandWithParameters:: SetParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) o **sqlparameterinfo** non sono stati chiamati o sono stati chiamati con cParams uguale a zero, **GetParameterInfo** deriva le informazioni sui parametri e restituisce this.</span><span class="sxs-lookup"><span data-stu-id="c3670-116">If [ISSCommandWithParameters::SetParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) or **SetParameterInfo** have not been called or have been called with cParams equal to zero, **GetParameterInfo** derives parameter information and returns this.</span></span> <span data-ttu-id="c3670-117">Se **ISSCommandWithParameters:: SetParameterProperties** o **separameterinfo** è stato chiamato per almeno un parametro, **ISSCommandWithParameters:: GetParameterProperties** restituisce proprietà solo per i parametri per i quali è stato chiamato **ISSCommandWithParameters:: SetParameterProperties** .</span><span class="sxs-lookup"><span data-stu-id="c3670-117">If **ISSCommandWithParameters::SetParameterProperties** or **SetParameterInfo** have been called for at least one parameter, **ISSCommandWithParameters::GetParameterProperties** returns properties only for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span> <span data-ttu-id="c3670-118">Se **ISSCommandWithParameters:: SetParameterProperties** viene chiamato dopo **ISSCommandWithParameters:: GetParameterProperties** o **GetParameterInfo**, le chiamate successive a **ISSCommandWithParameters:: GetParameterProperties** restituiscono i valori sottoposti a override per i parametri per i quali è stato chiamato **ISSCommandWithParameters:: SetParameterProperties** .</span><span class="sxs-lookup"><span data-stu-id="c3670-118">If **ISSCommandWithParameters::SetParameterProperties** is called after **ISSCommandWithParameters::GetParameterProperties** or **GetParameterInfo**, subsequent calls to **ISSCommandWithParameters::GetParameterProperties** return the overridden values for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span>  
  
 <span data-ttu-id="c3670-119">La struttura SSPARAMPROPS viene definita nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c3670-119">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
|<span data-ttu-id="c3670-120">Membro</span><span class="sxs-lookup"><span data-stu-id="c3670-120">Member</span></span>|<span data-ttu-id="c3670-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3670-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c3670-122">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="c3670-122">*iOrdinal*</span></span>|<span data-ttu-id="c3670-123">Numero ordinale del parametro passato.</span><span class="sxs-lookup"><span data-stu-id="c3670-123">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="c3670-124">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="c3670-124">*cPropertySets*</span></span>|<span data-ttu-id="c3670-125">Numero di strutture DBPROPSET in *rgPropertySets*.</span><span class="sxs-lookup"><span data-stu-id="c3670-125">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="c3670-126">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="c3670-126">*rgPropertySets*</span></span>|<span data-ttu-id="c3670-127">Puntatore alla memoria nel quale restituire una matrice di strutture DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="c3670-127">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3670-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3670-128">See Also</span></span>  
 [<span data-ttu-id="c3670-129">ISSCommandWithParameters &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="c3670-129">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
