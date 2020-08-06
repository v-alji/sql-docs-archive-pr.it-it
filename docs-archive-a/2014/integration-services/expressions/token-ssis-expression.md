---
title: TOKEN (espressione SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 9fdd06bf-5bc9-445c-95bf-709e0ca5989b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5c0598c3832e4bf6f838087be4fee541663c8bff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716452"
---
# <a name="token--ssis-expression"></a><span data-ttu-id="c0b7d-102">TOKEN (espressione SSIS)</span><span class="sxs-lookup"><span data-stu-id="c0b7d-102">TOKEN  (SSIS Expression)</span></span>
  <span data-ttu-id="c0b7d-103">Restituisce un token (sottostringa) da una stringa in base ai delimitatori specificati che separano i token nella stringa e al numero del token che indica quale token deve essere restituito.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-103">Returns a token (substring) from a string based on the specified delimiters that separate tokens in the string and the number of the token that denotes which token to be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0b7d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0b7d-104">Syntax</span></span>  
  
```  
TOKEN(character_expression, delimiter_string, occurrence)  
```  
  
## <a name="arguments"></a><span data-ttu-id="c0b7d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c0b7d-105">Arguments</span></span>  
 <span data-ttu-id="c0b7d-106">*character_expression*</span><span class="sxs-lookup"><span data-stu-id="c0b7d-106">*character_expression*</span></span>  
 <span data-ttu-id="c0b7d-107">Stringa che contiene token separati da delimitatori.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-107">A string that contains tokens separated by delimiters.</span></span>  
  
 <span data-ttu-id="c0b7d-108">*delimiter_string*</span><span class="sxs-lookup"><span data-stu-id="c0b7d-108">*delimiter_string*</span></span>  
 <span data-ttu-id="c0b7d-109">Stringa che contiene caratteri delimitatori.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-109">A string that contains delimiter characters.</span></span> <span data-ttu-id="c0b7d-110">Ad esempio, "; ," contiene i caratteri delimitatori punto e virgola, spazio e virgola.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-110">For example, "; ," contains three delimiter characters semi-colon, a blank space, and a comma.</span></span>  
  
 <span data-ttu-id="c0b7d-111">*occurrence*</span><span class="sxs-lookup"><span data-stu-id="c0b7d-111">*occurrence*</span></span>  
 <span data-ttu-id="c0b7d-112">Intero con segno o senza segno che specifica il token da restituire.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-112">A signed or unsigned integer that specifies the token to be returned.</span></span> <span data-ttu-id="c0b7d-113">Ad esempio, se si specifica 3 come valore per questo parametro, viene restituito il terzo token nella stringa.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-113">For example, if you specify 3 as a value for this parameter, the third token in the string is returned.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c0b7d-114">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="c0b7d-114">Result Types</span></span>  
 <span data-ttu-id="c0b7d-115">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="c0b7d-115">DT_WSTR</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0b7d-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c0b7d-116">Remarks</span></span>  
 <span data-ttu-id="c0b7d-117">Questa funzione suddivide la stringa <character_expression> in un set di token separati dai delimitatori specificati nella <delimiter_string>, quindi restituisce l'N token dove N è il numero di occorrenze del token specificato dal parametro \<occurrence>.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-117">This function splits up the <character_expression> string into a set of tokens separated by the delimiters specified in the <delimiter_string> and then returns the Nth token where N is the number of occurrence of the token specified by the \<occurrence> parameter.</span></span> <span data-ttu-id="c0b7d-118">Per utilizzi di esempio di questa funzione, vedere la sezione Esempi.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-118">See Examples section for sample usages of this function.</span></span>  
  
 <span data-ttu-id="c0b7d-119">Le osservazioni seguenti riguardano la funzione TOKEN:</span><span class="sxs-lookup"><span data-stu-id="c0b7d-119">The following remarks apply to the TOKEN function:</span></span>  
  
-   <span data-ttu-id="c0b7d-120">La stringa di delimitazione può contenere uno o più caratteri delimitatori.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-120">The delimiter string can contain one or more delimiter characters.</span></span>  
  
-   <span data-ttu-id="c0b7d-121">Se il valore del parametro \<occurrence> è maggiore del numero totale di token nella stringa, la funzione restituisce NULL.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-121">If the value of \<occurrence> parameter is higher than the total number of tokens in the string, the function returns NULL.</span></span>  
  
-   <span data-ttu-id="c0b7d-122">I delimitatori iniziali vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-122">Leading delimiters are skipped.</span></span>  
  
-   <span data-ttu-id="c0b7d-123">La funzione TOKEN può essere utilizzata solo con il tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-123">TOKEN works only with the DT_WSTR data type.</span></span> <span data-ttu-id="c0b7d-124">Se l'argomento *character_expression* è un valore letterale stringa o una colonna di dati con tipo di dati DT_STR, prima di eseguire l'operazione prevista da TOKEN verrà eseguito il cast implicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-124">A *character_expression* argument that is a string literal or a data column with the DT_STR data type is implicitly cast to the DT_WSTR data type before TOKEN performs its operation.</span></span> <span data-ttu-id="c0b7d-125">Per gli altri tipi di dati è necessario il cast esplicito al tipo di dati DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-125">Other data types must be explicitly cast to the DT_WSTR data type.</span></span>  
  
-   <span data-ttu-id="c0b7d-126">TOKEN restituisce un risultato Null se character_expression è Null.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-126">TOKEN returns a null result if the character_expression is null.</span></span>  
  
-   <span data-ttu-id="c0b7d-127">È possibile utilizzare variabili e colonne come valori di tutti gli argomenti dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-127">You can use variables and columns as values of all arguments in the expression.</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="c0b7d-128">Esempi di espressione</span><span class="sxs-lookup"><span data-stu-id="c0b7d-128">Expression Examples</span></span>  
 <span data-ttu-id="c0b7d-129">Nell'esempio seguente la funzione TOKEN restituisce "a".</span><span class="sxs-lookup"><span data-stu-id="c0b7d-129">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="c0b7d-130">La stringa "a little white dog" contiene 4 token ("a", "little", "white", "dog") separati dal delimitatore " " (spazio).</span><span class="sxs-lookup"><span data-stu-id="c0b7d-130">The string "a little white dog" has 4 tokens "a", "little", "white", "dog" separated by the delimiter " " (space character).</span></span> <span data-ttu-id="c0b7d-131">Il secondo argomento, una stringa delimitatore, specifica il solo delimitatore, lo spazio, da utilizzare per suddividere la stringa di input in token.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-131">The second argument, a delimiter string, specifies only one delimiter, the space character, to be used in splitting the input string into tokens.</span></span> <span data-ttu-id="c0b7d-132">L'ultimo argomento, 1, specifica che deve essere restituito il primo token.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-132">The last argument, 1, specifies that the first token to be returned.</span></span> <span data-ttu-id="c0b7d-133">In questa stringa di esempio, il primo token è "a".</span><span class="sxs-lookup"><span data-stu-id="c0b7d-133">The first token is "a" in this sample string.</span></span>  
  
```  
TOKEN("a little white dog"," ",1)  
```  
  
 <span data-ttu-id="c0b7d-134">Nell'esempio seguente la funzione TOKEN restituisce "dog".</span><span class="sxs-lookup"><span data-stu-id="c0b7d-134">In the following example, the TOKEN function returns "dog".</span></span> <span data-ttu-id="c0b7d-135">In questo esempio la stringa di delimitazione contiene 5 delimitatori.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-135">The delimiter string in this example contains 5 delimiters.</span></span> <span data-ttu-id="c0b7d-136">La stringa di input contiene 4 token: "a", "little", "white", "dog".</span><span class="sxs-lookup"><span data-stu-id="c0b7d-136">The input string contains 4 tokens: "a", "little", "white", "dog".</span></span>  
  
```  
TOKEN("a:little|white dog","| ,.:",4)  
```  
  
 <span data-ttu-id="c0b7d-137">Nell'esempio seguente la funzione TOKEN restituisce"" (una stringa vuota) perché non ci sono 99 token nella stringa.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-137">In the following example, the TOKEN function returns "" (an empty string) because there are no 99 tokens in the string.</span></span>  
  
```  
TOKEN("a little white dog"," ",99)  
```  
  
 <span data-ttu-id="c0b7d-138">Nell'esempio seguente la funzione TOKEN restituisce l'intera stringa.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-138">In the following example, the TOKEN function returns the full string.</span></span> <span data-ttu-id="c0b7d-139">La funziona cerca i delimitatori nella stringa di input e poiché non ve ne sono, aggiunge l'intera stringa come primo token.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-139">The function parses the input string for delimiters and since there are none in the string, it just adds the entire string as the first token.</span></span>  
  
```  
TOKEN("a little white dog","|",1)  
```  
  
 <span data-ttu-id="c0b7d-140">Nell'esempio seguente la funzione TOKEN restituisce "a".</span><span class="sxs-lookup"><span data-stu-id="c0b7d-140">In the following example, the TOKEN function returns "a".</span></span> <span data-ttu-id="c0b7d-141">Tutti gli spazi iniziali vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-141">It ignores all the leading space characters.</span></span>  
  
```  
TOKEN("        a little white dog", " ", 1)  
```  
  
 <span data-ttu-id="c0b7d-142">Nell'esempio seguente la funzione TOKEN restituisce l'anno da una stringa di data.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-142">In the following example, the TOKEN function returns the year from a date string.</span></span>  
  
```  
TOKEN("2009/01/01", "/"), 1  
```  
  
 <span data-ttu-id="c0b7d-143">Nell'esempio seguente la funzione TOKEN restituisce il nome file dal percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="c0b7d-143">In the following example, the TOKEN function returns the file name from the specified path.</span></span> <span data-ttu-id="c0b7d-144">Se il valore di User::Path è "c:\programmi\data\myfile.txt", ad esempio, la funzione TOKEN restituisce "myfile.txt".</span><span class="sxs-lookup"><span data-stu-id="c0b7d-144">For example, if the value of User::Path is "c:\program files\data\myfile.txt", the TOKEN function returns "myfile.txt".</span></span> <span data-ttu-id="c0b7d-145">La funzione TOKENCOUNT restituisce 4, mentre la funzione TOKEN restituisce il quarto token, "myfile.txt".</span><span class="sxs-lookup"><span data-stu-id="c0b7d-145">The TOKENCOUNT function returns 4 and the TOKEN function return the 4th token, "myfile.txt".</span></span>  
  
```  
TOKEN(@[User::Path], "\\", TOKENCOUNT(@[User::Path], "\\"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0b7d-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0b7d-146">See Also</span></span>  
 [<span data-ttu-id="c0b7d-147">Funzioni &#40;espressione SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="c0b7d-147">Functions &#40;SSIS Expression&#41;</span></span>](functions-ssis-expression.md)  
  
  
