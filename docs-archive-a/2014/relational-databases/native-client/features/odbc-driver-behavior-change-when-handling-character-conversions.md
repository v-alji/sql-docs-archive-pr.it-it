---
title: Modifica del comportamento del driver ODBC quando si gestiscono le conversioni di caratteri | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 682a232a-bf89-4849-88a1-95b2fbac1467
author: rothja
ms.author: jroth
ms.openlocfilehash: 5334b4268559ba155a53b3be655d87f7867779df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714264"
---
# <a name="odbc-driver-behavior-change-when-handling-character-conversions"></a><span data-ttu-id="01977-102">Modifica del comportamento del driver ODBC quando si gestiscono le conversioni di caratteri</span><span class="sxs-lookup"><span data-stu-id="01977-102">ODBC Driver Behavior Change When Handling Character Conversions</span></span>
  <span data-ttu-id="01977-103">Il [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] driver ODBC di Native Client (SQLNCLI11.dll) ha modificato il modo in cui esegue le conversioni SQL_WCHAR \* (nchar/nvarchar/nvarchar (max)) e SQL_CHAR \* (char/varchar/narchar (max)).</span><span class="sxs-lookup"><span data-stu-id="01977-103">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC Driver (SQLNCLI11.dll) changed how it does of SQL_WCHAR\* (NCHAR/NVARCHAR/NVARCHAR(MAX)) and SQL_CHAR\* (CHAR/VARCHAR/NARCHAR(MAX)) conversions.</span></span> <span data-ttu-id="01977-104">Tramite le funzioni ODBC, ad esempio SQLGetData, SQLBindCol, SQLBindParameter viene restituito (-4) SQL_NO_TOTAL come parametro di lunghezza/indicatore quando si utilizza il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client.</span><span class="sxs-lookup"><span data-stu-id="01977-104">ODBC functions, such as SQLGetData, SQLBindCol, SQLBindParameter, return (-4) SQL_NO_TOTAL as the length/indicator parameter when using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2012 Native Client ODBC driver.</span></span> <span data-ttu-id="01977-105">Dalle versioni precedenti del driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client viene restituito un valore di lunghezza che può essere errato.</span><span class="sxs-lookup"><span data-stu-id="01977-105">Prior versions of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver returned a length value, which can be incorrect.</span></span>  
  
## <a name="sqlgetdata-behavior"></a><span data-ttu-id="01977-106">Comportamento di SQLGetData</span><span class="sxs-lookup"><span data-stu-id="01977-106">SQLGetData Behavior</span></span>  
 <span data-ttu-id="01977-107">Tramite le numerose funzioni di Windows è possibile specificare dimensioni del buffer pari a 0 e la lunghezza restituita corrisponde alle dimensioni dei dati restituiti.</span><span class="sxs-lookup"><span data-stu-id="01977-107">Many Windows functions let you specify a buffer size of 0 and the returned length is the size of the returned data.</span></span> <span data-ttu-id="01977-108">Di seguito è riportato un modello comune per i programmatori di Windows:</span><span class="sxs-lookup"><span data-stu-id="01977-108">The following pattern is common for Windows programmers:</span></span>  
  
```  
int iSize = 0;  
BYTE * pBuffer = NULL;  
GetMyFavoriteAPI(pBuffer, &iSize);   // Returns needed size in iSize  
pBuffer = new BYTE[iSize];   // Allocate buffer   
GetMyFavoriteAPI(pBuffer, &iSize);   // Retrieve actual data  
```  
  
 <span data-ttu-id="01977-109">Tuttavia, non è consigliabile utilizzare **SQLGetData** in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="01977-109">However, **SQLGetData** should not be used in this scenario.</span></span> <span data-ttu-id="01977-110">Non è consigliabile utilizzare il modello seguente:</span><span class="sxs-lookup"><span data-stu-id="01977-110">The following pattern should not be used:</span></span>  
  
```  
// bad  
int iSize = 0;  
WCHAR * pBuffer = NULL;  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)0x1, 0, &iSize);   // Get storage size needed  
pBuffer = new WCHAR[(iSize/sizeof(WCHAR)) + 1];   // Allocate buffer  
SQLGetData(hstmt, SQL_W_CHAR, ...., (SQLPOINTER*)pBuffer, iSize, &iSize);   // Retrieve data  
```  
  
 <span data-ttu-id="01977-111">**SQLGetData** può essere chiamato solo per recuperare i blocchi di dati effettivi.</span><span class="sxs-lookup"><span data-stu-id="01977-111">**SQLGetData** can only be called to retrieve chunks of actual data.</span></span> <span data-ttu-id="01977-112">L'utilizzo di **SQLGetData** per ottenere le dimensioni dei dati non è supportato.</span><span class="sxs-lookup"><span data-stu-id="01977-112">Using **SQLGetData** to get the size of data is not unsupported.</span></span>  
  
 <span data-ttu-id="01977-113">Di seguito viene illustrato l'impatto della modifica del driver quando si utilizza il modello errato.</span><span class="sxs-lookup"><span data-stu-id="01977-113">The following shows the impact of the driver change when you use the incorrect pattern.</span></span> <span data-ttu-id="01977-114">Tramite questa applicazione viene eseguita una query su una colonna `varchar` e su un'associazione come Unicode (SQL_UNICODE/SQL_WCHAR):</span><span class="sxs-lookup"><span data-stu-id="01977-114">This application queries a `varchar` column and binding as Unicode (SQL_UNICODE/SQL_WCHAR):</span></span>  
  
 <span data-ttu-id="01977-115">Query`select convert(varchar(36), '123')`</span><span class="sxs-lookup"><span data-stu-id="01977-115">Query:  `select convert(varchar(36), '123')`</span></span>  
  
```  
SQLGetData(hstmt, SQL_WCHAR, ....., (SQLPOINTER*) 0x1, 0 , &iSize);   // Attempting to determine storage size needed  
```  
  
|<span data-ttu-id="01977-116">Versione del driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="01977-116">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="01977-117">Risultato della lunghezza o dell'indicatore</span><span class="sxs-lookup"><span data-stu-id="01977-117">Length or Indicator Outcome</span></span>|<span data-ttu-id="01977-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01977-118">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="01977-119">Native Client o versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="01977-119">Native Client or earlier</span></span>|<span data-ttu-id="01977-120">6</span><span class="sxs-lookup"><span data-stu-id="01977-120">6</span></span>|<span data-ttu-id="01977-121">È stato erroneamente presupposto dal driver che la conversione di CHAR in WCHAR potesse essere effettuata come lunghezza \* 2.</span><span class="sxs-lookup"><span data-stu-id="01977-121">The driver incorrectly assumed that converting CHAR to WCHAR could be accomplished as length \* 2.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="01977-122">Native Client (versione 11.0.2100.60) o successive</span><span class="sxs-lookup"><span data-stu-id="01977-122">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="01977-123">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="01977-123">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="01977-124">Il driver non presuppone più che la conversione da CHAR a WCHAR o WCHAR a CHAR sia un'azione (moltiplicazione) \* 2 o (divisione)/2.</span><span class="sxs-lookup"><span data-stu-id="01977-124">The driver no longer assumes that converting from CHAR to WCHAR or WCHAR to CHAR is a (multiply) \*2 or (divide)/2 action.</span></span><br /><br /> <span data-ttu-id="01977-125">La chiamata a **SQLGetData** non restituisce più la lunghezza della conversione prevista.</span><span class="sxs-lookup"><span data-stu-id="01977-125">Calling **SQLGetData** no longer returns the length of the expected conversion.</span></span> <span data-ttu-id="01977-126">Tramite il driver viene rilevata la conversione a o da CHAR e WCHAR e viene restituito (-4) SQL_NO_TOTAL anziché il comportamento \*2 o /2 che potrebbe essere errato.</span><span class="sxs-lookup"><span data-stu-id="01977-126">The driver detects the conversion to or from CHAR and WCHAR and returns (-4) SQL_NO_TOTAL instead of \*2 or /2 behavior that could be incorrect.</span></span>|  
  
 <span data-ttu-id="01977-127">Utilizzare **SQLGetData** per recuperare i blocchi di dati.</span><span class="sxs-lookup"><span data-stu-id="01977-127">Use **SQLGetData** to retrieve the chunks of the data.</span></span> <span data-ttu-id="01977-128">(di seguito è riportato uno pseudocodice):</span><span class="sxs-lookup"><span data-stu-id="01977-128">(Pseudo code shown:)</span></span>  
  
```  
while( (SQL_SUCCESS or SQL_SUCCESS_WITH_INFO) == SQLFetch(...) ) {  
   SQLNumCols(...iTotalCols...)  
   for(int iCol = 1; iCol < iTotalCols; iCol++) {  
      WCHAR* pBufOrig, pBuffer = new WCHAR[100];  
      SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get original chunk  
      while(NOT ALL DATA RETREIVED (SQL_NO_TOTAL, ...) ) {  
         pBuffer += 50;   // Advance buffer for data retrieved  
         // May need to realloc the buffer when you reach current size  
         SQLGetData(.... iCol ... pBuffer, 100, &iSize);   // Get next chunk  
      }  
   }  
}  
```  
  
## <a name="sqlbindcol-behavior"></a><span data-ttu-id="01977-129">Comportamento di SQLBindCol</span><span class="sxs-lookup"><span data-stu-id="01977-129">SQLBindCol Behavior</span></span>  
 <span data-ttu-id="01977-130">Query`select convert(varchar(36), '1234567890')`</span><span class="sxs-lookup"><span data-stu-id="01977-130">Query:  `select convert(varchar(36), '1234567890')`</span></span>  
  
```  
SQLBindCol(... SQL_W_CHAR, ...)   // Only bound a buffer of WCHAR[4] - Expecting String Data Right Truncation behavior  
```  
  
|<span data-ttu-id="01977-131">Versione del driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="01977-131">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="01977-132">Risultato della lunghezza o dell'indicatore</span><span class="sxs-lookup"><span data-stu-id="01977-132">Length or Indicator Outcome</span></span>|<span data-ttu-id="01977-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01977-133">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="01977-134">Native Client o versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="01977-134">Native Client or earlier</span></span>|<span data-ttu-id="01977-135">20</span><span class="sxs-lookup"><span data-stu-id="01977-135">20</span></span>|<span data-ttu-id="01977-136">-   **SQLFetch** segnala la presenza di un troncamento sul lato destro dei dati.</span><span class="sxs-lookup"><span data-stu-id="01977-136">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="01977-137">-Length è la lunghezza dei dati restituiti, non quello archiviato (presuppone la conversione da \* 2 CHAR a WCHAR, che può non essere corretta per i glifi).</span><span class="sxs-lookup"><span data-stu-id="01977-137">-   Length is the length of the data returned, not what was stored (assumes \*2 CHAR to WCHAR conversion which can be incorrect for glyphs).</span></span><br /><span data-ttu-id="01977-138">-I dati archiviati nel buffer sono 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="01977-138">-   Data stored in buffer is 123\0.</span></span> <span data-ttu-id="01977-139">Viene garantito che la terminazione del buffer sia NULL.</span><span class="sxs-lookup"><span data-stu-id="01977-139">Buffer is guaranteed to be NULL terminated.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="01977-140">Native Client (versione 11.0.2100.60) o successive</span><span class="sxs-lookup"><span data-stu-id="01977-140">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="01977-141">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="01977-141">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="01977-142">-   **SQLFetch** segnala la presenza di un troncamento sul lato destro dei dati.</span><span class="sxs-lookup"><span data-stu-id="01977-142">-   **SQLFetch** reports that there is a truncation on the right side of the data.</span></span><br /><span data-ttu-id="01977-143">-Length indica-4 (SQL_NO_TOTAL) perché il resto dei dati non è stato convertito.</span><span class="sxs-lookup"><span data-stu-id="01977-143">-   Length indicates -4 (SQL_NO_TOTAL) because the rest of the data was not converted.</span></span><br /><span data-ttu-id="01977-144">-I dati archiviati nel buffer sono 123 \ 0.</span><span class="sxs-lookup"><span data-stu-id="01977-144">-   Data stored in the buffer is 123\0.</span></span> <span data-ttu-id="01977-145">- Viene garantito che la terminazione del buffer sia NULL.</span><span class="sxs-lookup"><span data-stu-id="01977-145">- Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="sqlbindparameter-output-parameter-behavior"></a><span data-ttu-id="01977-146">SQLBindParameter (comportamento del parametro OUTPUT)</span><span class="sxs-lookup"><span data-stu-id="01977-146">SQLBindParameter (OUTPUT Parameter Behavior)</span></span>  
 <span data-ttu-id="01977-147">Query`create procedure spTest @p1 varchar(max) OUTPUT`</span><span class="sxs-lookup"><span data-stu-id="01977-147">Query:  `create procedure spTest @p1 varchar(max) OUTPUT`</span></span>  
  
 `select @p1 = replicate('B', 1234)`  
  
```  
SQLBindParameter(... SQL_W_CHAR, ...)   // Only bind up to first 64 characters  
```  
  
|<span data-ttu-id="01977-148">Versione del driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="01977-148">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC Driver version</span></span>|<span data-ttu-id="01977-149">Risultato della lunghezza o dell'indicatore</span><span class="sxs-lookup"><span data-stu-id="01977-149">Length or Indicator Outcome</span></span>|<span data-ttu-id="01977-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01977-150">Description</span></span>|  
|-----------------------------------------------------------------|---------------------------------|-----------------|  
|[!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] <span data-ttu-id="01977-151">Native Client o versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="01977-151">Native Client or earlier</span></span>|<span data-ttu-id="01977-152">2468</span><span class="sxs-lookup"><span data-stu-id="01977-152">2468</span></span>|<span data-ttu-id="01977-153">-   **SQLFetch** non restituisce più dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="01977-153">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="01977-154">-   **SQLMoreResults** non restituisce più dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="01977-154">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="01977-155">-Length indica le dimensioni dei dati restituiti dal server, non archiviati nel buffer.</span><span class="sxs-lookup"><span data-stu-id="01977-155">-   Length indicates the size of the data returned from server, not stored in buffer.</span></span><br /><span data-ttu-id="01977-156">-Il buffer originale contiene 63 byte e un carattere di terminazione NULL.</span><span class="sxs-lookup"><span data-stu-id="01977-156">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="01977-157">Viene garantito che la terminazione del buffer sia NULL.</span><span class="sxs-lookup"><span data-stu-id="01977-157">Buffer is guaranteed to be NULL terminated.</span></span>|  
|[!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] <span data-ttu-id="01977-158">Native Client (versione 11.0.2100.60) o successive</span><span class="sxs-lookup"><span data-stu-id="01977-158">Native Client (version 11.0.2100.60) or later</span></span>|<span data-ttu-id="01977-159">-4 (SQL_NO_TOTAL)</span><span class="sxs-lookup"><span data-stu-id="01977-159">-4 (SQL_NO_TOTAL)</span></span>|<span data-ttu-id="01977-160">-   **SQLFetch** non restituisce più dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="01977-160">-   **SQLFetch** returns no more data available.</span></span><br /><span data-ttu-id="01977-161">-   **SQLMoreResults** non restituisce più dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="01977-161">-   **SQLMoreResults** returns no more data available.</span></span><br /><span data-ttu-id="01977-162">-Length indica (-4) SQL_NO_TOTAL perché il resto dei dati non è stato convertito.</span><span class="sxs-lookup"><span data-stu-id="01977-162">-   Length indicates (-4) SQL_NO_TOTAL because the rest of the data was not converted.</span></span><br /><span data-ttu-id="01977-163">-Il buffer originale contiene 63 byte e un carattere di terminazione NULL.</span><span class="sxs-lookup"><span data-stu-id="01977-163">-   Original buffer contains 63 bytes and a NULL terminator.</span></span> <span data-ttu-id="01977-164">Viene garantito che la terminazione del buffer sia NULL.</span><span class="sxs-lookup"><span data-stu-id="01977-164">Buffer is guaranteed to be NULL terminated.</span></span>|  
  
## <a name="performing-char-and-wchar-conversions"></a><span data-ttu-id="01977-165">Esecuzione delle conversioni CHAR e WCHAR</span><span class="sxs-lookup"><span data-stu-id="01977-165">Performing CHAR and WCHAR Conversions</span></span>  
 <span data-ttu-id="01977-166">Nel driver ODBC di [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client sono disponibili diverse modalità di esecuzione delle conversioni CHAR e WCHAR.</span><span class="sxs-lookup"><span data-stu-id="01977-166">The [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] Native Client ODBC driver offers several ways to perform CHAR and WCHAR conversions.</span></span> <span data-ttu-id="01977-167">La logica è simile alla manipolazione dei BLOB (varchar (max), nvarchar (max),...):</span><span class="sxs-lookup"><span data-stu-id="01977-167">The logic is similar to manipulating blobs (varchar(max), nvarchar(max), ...):</span></span>  
  
-   <span data-ttu-id="01977-168">I dati vengono salvati o troncati nel buffer specificato quando si esegue l'associazione con **SQLBindCol** o **SQLBindParameter**.</span><span class="sxs-lookup"><span data-stu-id="01977-168">Data is saved or truncated into the specified buffer when binding with **SQLBindCol** or **SQLBindParameter**.</span></span>  
  
-   <span data-ttu-id="01977-169">Se non si esegue l'associazione, è possibile recuperare i dati in blocchi utilizzando **SQLGetData** e **SQLParamData**.</span><span class="sxs-lookup"><span data-stu-id="01977-169">If you do not bind, you can retrieve the data in chunks by using **SQLGetData** and **SQLParamData**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01977-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01977-170">See Also</span></span>  
 [<span data-ttu-id="01977-171">Funzionalità di SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="01977-171">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
