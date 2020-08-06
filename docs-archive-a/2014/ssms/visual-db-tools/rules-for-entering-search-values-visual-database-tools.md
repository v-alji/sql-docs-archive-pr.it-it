---
title: Regole per l'immissione di valori di ricerca (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- time [SQL Server], searches
- date searches
- dates [SQL Server], searches
- embedding apostrophes [SQL Server]
- logical value searches [SQL Server]
- case-sensitive search matches
- search criteria [SQL Server], rules
- text value searches [SQL Server]
- numeric value searches [SQL Server]
ms.assetid: 3c8134b7-83f4-41b4-99c8-e3949a685ff5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 907bcac93863bc5660993e910b37e25e25a129b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624504"
---
# <a name="rules-for-entering-search-values-visual-database-tools"></a><span data-ttu-id="4664b-102">Regole per l'immissione di valori di ricerca (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4664b-102">Rules for Entering Search Values (Visual Database Tools)</span></span>
  <span data-ttu-id="4664b-103">In questo argomento sono illustrate le convenzioni da utilizzare quando si immettono i seguenti tipi di valori letterali in una condizione di ricerca:</span><span class="sxs-lookup"><span data-stu-id="4664b-103">This topic discusses the conventions you must use when entering the following types of literal values for a search condition:</span></span>  
  
-   <span data-ttu-id="4664b-104">Valori di testo</span><span class="sxs-lookup"><span data-stu-id="4664b-104">Text values</span></span>  
  
-   <span data-ttu-id="4664b-105">Valori numerici</span><span class="sxs-lookup"><span data-stu-id="4664b-105">Numeric values</span></span>  
  
-   <span data-ttu-id="4664b-106">Date</span><span class="sxs-lookup"><span data-stu-id="4664b-106">Dates</span></span>  
  
-   <span data-ttu-id="4664b-107">Valori logici</span><span class="sxs-lookup"><span data-stu-id="4664b-107">Logical values</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4664b-108">Le informazioni contenute in questo argomento derivano dalle regole relative a SQL-92 standard.</span><span class="sxs-lookup"><span data-stu-id="4664b-108">The information in this topic is derived from the rules for standard SQL-92.</span></span> <span data-ttu-id="4664b-109">In ogni database è tuttavia possibile implementare SQL in modo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4664b-109">However, each database can implement SQL in its own way.</span></span> <span data-ttu-id="4664b-110">Le indicazioni fornite potrebbero quindi non essere valide per tutti i database.</span><span class="sxs-lookup"><span data-stu-id="4664b-110">Therefore, the guidelines provided here might not apply in every case.</span></span> <span data-ttu-id="4664b-111">In caso di dubbi su come immettere i valori di ricerca per un particolare database, vedere la documentazione del database in uso.</span><span class="sxs-lookup"><span data-stu-id="4664b-111">If you have questions about how to enter search values for a particular database, refer to the documentation for the database that you are using.</span></span>  
  
## <a name="searching-on-text-values"></a><span data-ttu-id="4664b-112">Ricerche su valori di testo</span><span class="sxs-lookup"><span data-stu-id="4664b-112">Searching on Text Values</span></span>  
 <span data-ttu-id="4664b-113">Quando si immettono valori di tipo testo nelle condizioni di ricerca, è necessario tenere presente le seguenti indicazioni:</span><span class="sxs-lookup"><span data-stu-id="4664b-113">The following guidelines apply when you enter text values in search conditions:</span></span>  
  
-   <span data-ttu-id="4664b-114">**Virgolette** Delimitare i valori di tipo testo tra virgolette semplici, come nell’esempio seguente per un cognome:</span><span class="sxs-lookup"><span data-stu-id="4664b-114">**Quotation marks** Enclose text values in single quotation marks, as in this example for a last name:</span></span>  
  
    ```  
    'Smith'  
    ```  
  
     <span data-ttu-id="4664b-115">Se si immette una condizione di ricerca nel [riquadro Criteri](visual-database-tools.md), è sufficiente specificare il valore di testo. Le virgolette verranno inserite automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4664b-115">If you are entering a search condition in the [Criteria Pane](visual-database-tools.md), you can simply type the text value and the Query and View Designer will automatically put single quotation marks around it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4664b-116">In alcuni database le parole tra virgolette singole vengono interpretate come valori letterali, mentre le parole tra virgolette doppie vengono interpretate come oggetti di database quali riferimenti a colonne o tabelle.</span><span class="sxs-lookup"><span data-stu-id="4664b-116">In some databases, terms in single quotation marks are interpreted as literal values, whereas terms in double quotation marks are interpreted as database objects such as column or table references.</span></span> <span data-ttu-id="4664b-117">Di conseguenza, anche se in Progettazione query e Progettazione viste è possibile accettare parole tra virgolette doppie, l'interpretazione potrebbe essere diversa da quella prevista.</span><span class="sxs-lookup"><span data-stu-id="4664b-117">Therefore, even though the Query and View Designer can accept terms in double quotation marks, it might interpret them differently than you expect.</span></span>  
  
-   <span data-ttu-id="4664b-118">**Incorporamento di apostrofi** Se i dati da cercare contengono una virgoletta singola (un apostrofo), è possibile immettere due virgolette singole per indicare che la virgoletta singola deve essere interpretata come un valore letterale e non come delimitatore.</span><span class="sxs-lookup"><span data-stu-id="4664b-118">**Embedding apostrophes** If the data you are searching for contains a single quotation mark (an apostrophe), you can enter two single quotation marks to indicate that you mean the single quotation mark as a literal value and not a delimiter.</span></span> <span data-ttu-id="4664b-119">La seguente condizione ricerca ad esempio il valore "Swann's Way":</span><span class="sxs-lookup"><span data-stu-id="4664b-119">For example, the following condition searches for the value "Swann's Way:"</span></span>  
  
    ```  
    ='Swann''s Way'  
    ```  
  
-   <span data-ttu-id="4664b-120">**Limiti di lunghezza** Quando si immettono stringhe lunghe non si deve superare la lunghezza massima delle istruzioni SQL per il database in uso.</span><span class="sxs-lookup"><span data-stu-id="4664b-120">**Length limits** Do not exceed the maximum length of the SQL statement for your database when entering long strings.</span></span>  
  
-   <span data-ttu-id="4664b-121">**Distinzione tra maiuscole e minuscole** È necessario seguire le regole di distinzione tra maiuscole e minuscole per il database che si sta usando.</span><span class="sxs-lookup"><span data-stu-id="4664b-121">**Case sensitivity** Follow the case sensitivity rules for the database you are using.</span></span> <span data-ttu-id="4664b-122">Il database in uso determina se le ricerche di elementi di testo distinguono fra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="4664b-122">The database you are using determines whether text searches are case sensitive.</span></span> <span data-ttu-id="4664b-123">Alcuni database interpretano, ad esempio, l'operatore "=" come corrispondenza di maiuscole e minuscole, mentre altri consentono la ricerca di qualsiasi combinazione di caratteri maiuscoli e minuscoli.</span><span class="sxs-lookup"><span data-stu-id="4664b-123">For example, some databases interpret the operator "=" to mean an exact case-sensitive match, but others will allow matches on any combination of uppercase and lowercase characters.</span></span>  
  
     <span data-ttu-id="4664b-124">Se non si è certi dell'utilizzo delle maiuscole e delle minuscole nel database in uso, è possibile utilizzare le funzioni UPPER o LOWER nelle condizioni di ricerca per convertire i dati della ricerca, come mostrato nel seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="4664b-124">If you are unsure about whether the database uses a case-sensitive search, you can use the UPPER or LOWER functions in the search condition to convert the case of the search data, as illustrated in the following example:</span></span>  
  
    ```  
    WHERE UPPER(lname) = 'SMITH'  
    ```  
  
## <a name="searching-on-numeric-values"></a><span data-ttu-id="4664b-125">Ricerche su valori numerici</span><span class="sxs-lookup"><span data-stu-id="4664b-125">Searching on Numeric Values</span></span>  
 <span data-ttu-id="4664b-126">Quando si immettono valori numerici nelle condizioni di ricerca, è necessario tenere presente le seguenti indicazioni:</span><span class="sxs-lookup"><span data-stu-id="4664b-126">The following guidelines apply when you enter numeric values in search conditions:</span></span>  
  
-   <span data-ttu-id="4664b-127">**Virgolette** Non racchiudere i numeri tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="4664b-127">**Quotation marks** Do not enclose numbers in quotation marks.</span></span>  
  
-   <span data-ttu-id="4664b-128">**Caratteri non numerici** Non inserire caratteri non numerici, tranne il separatore decimale (come definito nella finestra di dialogo **Impostazioni internazionali** del Pannello di controllo di Windows) e il segno negativo (-).</span><span class="sxs-lookup"><span data-stu-id="4664b-128">**Non-numeric characters** Do not include non-numeric characters except the decimal separator (as defined in the **Regional Settings** dialog box of Windows Control Panel) and negative sign (-).</span></span> <span data-ttu-id="4664b-129">Non inserire simboli di raggruppamento di cifre (quale il separatore delle migliaia) o simboli di valuta.</span><span class="sxs-lookup"><span data-stu-id="4664b-129">Do not include digit grouping symbols (such as a comma between thousands) or currency symbols.</span></span>  
  
-   <span data-ttu-id="4664b-130">**Separatore decimale** Se si stanno immettendo numeri interi, è possibile inserire un separatore decimale, sia che il valore che si sta cercando sia un valore intero sia che si tratti di un numero reale.</span><span class="sxs-lookup"><span data-stu-id="4664b-130">**Decimal marks** If you are entering whole numbers, you can include a decimal mark, whether the value you are searching for is an integer or a real number.</span></span>  
  
-   <span data-ttu-id="4664b-131">**Notazione scientifica** È possibile immettere numeri molto grandi o molto piccoli usando la notazione scientifica, come nell’esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4664b-131">**Scientific notation** You can enter very large or very small numbers using scientific notation, as in this example:</span></span>  
  
    ```  
    > 1.23456e-9  
    ```  
  
## <a name="searching-on-dates"></a><span data-ttu-id="4664b-132">Ricerche su date</span><span class="sxs-lookup"><span data-stu-id="4664b-132">Searching on Dates</span></span>  
 <span data-ttu-id="4664b-133">Il formato da utilizzare per immettere le date dipende dal database in uso e dal riquadro di Progettazione query e Progettazione viste in cui si sta immettendo la data.</span><span class="sxs-lookup"><span data-stu-id="4664b-133">The format you use to enter dates depends on the database you are using and in what pane of the Query and View Designer you are entering the date.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4664b-134">Se non si conosce il formato utilizzato dall'origine dati, digitare una data nella colonna Filtro del riquadro Criteri in un formato conosciuto.</span><span class="sxs-lookup"><span data-stu-id="4664b-134">If you don't know which format your data source uses, type a date into the filter column of the Criteria pane in any format familiar to you.</span></span> <span data-ttu-id="4664b-135">La maggior parte di queste voci verrà convertita automaticamente nel formato appropriato.</span><span class="sxs-lookup"><span data-stu-id="4664b-135">The designer will convert most of such entries into the appropriate format.</span></span>  
  
 <span data-ttu-id="4664b-136">È possibile utilizzare i seguenti formati di data:</span><span class="sxs-lookup"><span data-stu-id="4664b-136">The Query and View Designer can work with the following date formats:</span></span>  
  
-   <span data-ttu-id="4664b-137">**Specifico delle impostazioni locali** Formato specificato per le date nella finestra di dialogo delle **Proprietà delle impostazioni internazionali di Windows** .</span><span class="sxs-lookup"><span data-stu-id="4664b-137">**Locale-specific** The format specified for dates in the **Windows Regional Settings Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="4664b-138">**Specifico del database** Qualsiasi formato supportato dal database.</span><span class="sxs-lookup"><span data-stu-id="4664b-138">**Database-specific** Any format understood by the database.</span></span>  
  
-   <span data-ttu-id="4664b-139">**Data standard ANSI** Formato che usa parentesi graffe, il marcatore "d" per identificare la data e una stringa della data come nell’esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4664b-139">**ANSI standard date** A format that uses braces, the marker 'd' to designate the date, and a date string, as in the following example:</span></span>  
  
    ```  
    { d '1990-12-31' }  
    ```  
  
-   <span data-ttu-id="4664b-140">**Data/ora standard ANSI** Analogo alla data standard ANSI, ma usa "ts" al posto di 'd' e aggiunge le ore, i minuti e i secondi alla data (usando una notazione di 24 ore), come nell'esempio seguente per 31 dicembre 1990:</span><span class="sxs-lookup"><span data-stu-id="4664b-140">**ANSI standard datetime** Similar to ANSI-standard date, but uses 'ts' instead of 'd' and adds hours, minutes, and seconds to the date (using a 24-hour clock), as in this example for December 31, 1990:</span></span>  
  
    ```  
    { ts '1990-12-31 00:00:00' }  
    ```  
  
     <span data-ttu-id="4664b-141">In generale, il formato di data standard ANSI viene utilizzato con i database che rappresentano le date con un tipo di date reali.</span><span class="sxs-lookup"><span data-stu-id="4664b-141">In general, the ANSI standard date format is used with databases that represent dates using a true date data type.</span></span> <span data-ttu-id="4664b-142">Il formato datetime viene invece utilizzato con database che supportano un tipo di dati datetime.</span><span class="sxs-lookup"><span data-stu-id="4664b-142">In contrast, the datetime format is used with databases that support a datetime data type.</span></span>  
  
 <span data-ttu-id="4664b-143">Nella tabella riportata di seguito sono elencati i formati di data utilizzabili nei diversi riquadri di Progettazione query e Progettazione viste.</span><span class="sxs-lookup"><span data-stu-id="4664b-143">The following table summarizes the date format that you can use in different panes of the Query and View Designer.</span></span>  
  
|<span data-ttu-id="4664b-144">**Riquadro**</span><span class="sxs-lookup"><span data-stu-id="4664b-144">**Pane**</span></span>|<span data-ttu-id="4664b-145">**Formato data**</span><span class="sxs-lookup"><span data-stu-id="4664b-145">**Date format**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="4664b-146">Criteri</span><span class="sxs-lookup"><span data-stu-id="4664b-146">Criteria</span></span>|<span data-ttu-id="4664b-147">Specifico delle impostazioni locali? Specifico del database ?Standard ANSI</span><span class="sxs-lookup"><span data-stu-id="4664b-147">Locale-specific Database-specific ANSI standard</span></span><br /><br /> <span data-ttu-id="4664b-148">Le date immesse nel [riquadro Criteri](visual-database-tools.md) vengono convertite in un formato compatibile con il database nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="4664b-148">Dates entered in the [Criteria Pane](visual-database-tools.md) are converted to a database-compatible format in the SQL pane.</span></span>|  
|<span data-ttu-id="4664b-149">SQL</span><span class="sxs-lookup"><span data-stu-id="4664b-149">SQL</span></span>|<span data-ttu-id="4664b-150">Specifico del database ?Standard ANSI</span><span class="sxs-lookup"><span data-stu-id="4664b-150">Database-specific ANSI standard</span></span>|  
|<span data-ttu-id="4664b-151">Risultati</span><span class="sxs-lookup"><span data-stu-id="4664b-151">Results</span></span>|<span data-ttu-id="4664b-152">Specifico delle impostazioni locali</span><span class="sxs-lookup"><span data-stu-id="4664b-152">Locale-specific</span></span>|  
  
## <a name="searching-on-logical-values"></a><span data-ttu-id="4664b-153">Ricerche su valori logici</span><span class="sxs-lookup"><span data-stu-id="4664b-153">Searching on Logical Values</span></span>  
 <span data-ttu-id="4664b-154">Il formato dei dati logici varia da database a database.</span><span class="sxs-lookup"><span data-stu-id="4664b-154">The format of logical data varies from database to database.</span></span> <span data-ttu-id="4664b-155">Molto spesso, un valore False viene memorizzato come zero (0).</span><span class="sxs-lookup"><span data-stu-id="4664b-155">Very frequently, a value of False is stored as zero (0).</span></span> <span data-ttu-id="4664b-156">Un valore True viene generalmente archiviato come 1 e talvolta come -1.</span><span class="sxs-lookup"><span data-stu-id="4664b-156">A value of True is most frequently stored as 1 and occasionally as -1.</span></span> <span data-ttu-id="4664b-157">Quando si immettono valori logici nelle condizioni di ricerca, è consigliabile attenersi alle indicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4664b-157">The following guidelines apply when you enter logical values in search conditions:</span></span>  
  
-   <span data-ttu-id="4664b-158">Per cercare un valore False, utilizzare uno zero, come nel seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="4664b-158">To search for a value of False, use a zero, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 0  
    ```  
  
-   <span data-ttu-id="4664b-159">Se non si è certi del formato da utilizzare quando si cerca un valore True, provare a utilizzare 1, come nel seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="4664b-159">If you are not sure what format to use when searching for a True value, try using 1, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 1  
    ```  
  
-   <span data-ttu-id="4664b-160">In alternativa, è possibile ampliare l'ambito della ricerca cercando tutti i valori diversi da zero, come nel seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="4664b-160">Alternatively, you can broaden the scope of the search by searching for any non-zero value, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract <> 0  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4664b-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4664b-161">See Also</span></span>  
 [<span data-ttu-id="4664b-162">Specifica dei criteri di ricerca &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4664b-162">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
