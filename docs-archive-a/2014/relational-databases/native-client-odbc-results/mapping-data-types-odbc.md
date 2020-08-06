---
title: Mapping di tipi di dati (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- mapping data types [ODBC]
- result sets [ODBC], data types
- ODBC data types, mapping
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- data types [ODBC], mapping
- sql_variant data type
- SQL Server Native Client ODBC driver, data types
ms.assetid: 4ba0924d-9fca-4c48-aced-0a8d817b3dde
author: rothja
ms.author: jroth
ms.openlocfilehash: 545e738afb6b3283b2ff2f3830921da8ed13202f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725655"
---
# <a name="mapping-data-types-odbc"></a><span data-ttu-id="fad2d-102">Mapping dei tipi di dati (ODBC)</span><span class="sxs-lookup"><span data-stu-id="fad2d-102">Mapping Data Types (ODBC)</span></span>
  <span data-ttu-id="fad2d-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client esegue il mapping dei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipi di dati SQL ai tipi di dati SQL ODBC.</span><span class="sxs-lookup"><span data-stu-id="fad2d-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types to ODBC SQL data types.</span></span> <span data-ttu-id="fad2d-104">Nelle sezioni seguenti vengono illustrati i tipi di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL e i tipi di dati SQL ODBC con i quali eseguono il mapping.</span><span class="sxs-lookup"><span data-stu-id="fad2d-104">The sections below discuss the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types and the ODBC SQL data types to which they map.</span></span> <span data-ttu-id="fad2d-105">Vengono inoltre illustrati i tipi di dati SQL ODBC e i tipi di dati C ODBC corrispondenti, nonché le conversioni supportate e quelle predefinite.</span><span class="sxs-lookup"><span data-stu-id="fad2d-105">They also discuss the ODBC SQL data types and their corresponding ODBC C data types, and the supported and default conversions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fad2d-106">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo di dati **timestamp** viene mappato al tipo di dati SQL_BINARY o SQL_VARBINARY ODBC perché i valori nelle colonne **timestamp** non sono valori **DateTime** , ma i valori **Binary (8)** o **varbinary (8)** che indicano la sequenza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attività nella riga.</span><span class="sxs-lookup"><span data-stu-id="fad2d-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**timestamp** data type maps to the SQL_BINARY or SQL_VARBINARY ODBC data type because the values in **timestamp** columns are not **datetime** values, but **binary(8)** or **varbinary(8)** values that indicate the sequence of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity on the row.</span></span> <span data-ttu-id="fad2d-107">Se il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client rileva un valore SQL_C_WCHAR (Unicode) che corrisponde a un numero dispari di byte, il byte dispari finale viene troncato.</span><span class="sxs-lookup"><span data-stu-id="fad2d-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver encounters a SQL_C_WCHAR (Unicode) value that is an odd number of bytes, the trailing odd byte is truncated.</span></span>  
  
## <a name="dealing-with-sql_variant-data-type-in-odbc"></a><span data-ttu-id="fad2d-108">Gestione del tipo di dati sql_variant in ODBC</span><span class="sxs-lookup"><span data-stu-id="fad2d-108">Dealing with sql_variant Data Type in ODBC</span></span>  
 <span data-ttu-id="fad2d-109">La colonna **sql_variant** tipo di dati può contenere qualsiasi tipo di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad eccezione di Large Objects (LOB), ad esempio **Text**, **ntext**e **Image**.</span><span class="sxs-lookup"><span data-stu-id="fad2d-109">The **sql_variant** data type column can contain any of the data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except large objects (LOBs), such as **text**, **ntext**, and **image**.</span></span> <span data-ttu-id="fad2d-110">La colonna può ad esempio contenere valori **smallint** per alcune righe, valori **float** per altre righe e valori **Char/nchar** nel resto.</span><span class="sxs-lookup"><span data-stu-id="fad2d-110">For example, the column could contain **smallint** values for some rows, **float** values for other rows, and **char/nchar** values in the remainder.</span></span>  
  
 <span data-ttu-id="fad2d-111">Il tipo di dati **sql_variant** è simile al tipo di dati **variant** in Microsoft Visual Basic??.</span><span class="sxs-lookup"><span data-stu-id="fad2d-111">The **sql_variant** data type is similar to the **Variant** data type in Microsoft Visual Basic??.</span></span>  
  
### <a name="retrieving-data-from-the-server"></a><span data-ttu-id="fad2d-112">Recupero di dati dal server</span><span class="sxs-lookup"><span data-stu-id="fad2d-112">Retrieving Data from the Server</span></span>  
 <span data-ttu-id="fad2d-113">ODBC non dispone di un concetto di tipi Variant, limitando l'utilizzo del tipo di dati **sql_variant** con un driver ODBC in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fad2d-113">ODBC does not have a concept of variant types, limiting the use of the **sql_variant** data type with an ODBC driver in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fad2d-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , se si specifica binding, il tipo di dati **sql_variant** deve essere associato a uno dei tipi di dati ODBC documentati.</span><span class="sxs-lookup"><span data-stu-id="fad2d-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if binding is specified, the **sql_variant** data type must be bound to one of the documented ODBC data types.</span></span> <span data-ttu-id="fad2d-115">**SQL_CA_SS_VARIANT_TYPE**, un nuovo attributo specifico del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client, restituisce all'utente il tipo di dati di un'istanza nella colonna **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="fad2d-115">**SQL_CA_SS_VARIANT_TYPE**, a new attribute specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, returns the data type of an instance in the **sql_variant** column to the user.</span></span>  
  
 <span data-ttu-id="fad2d-116">Se non viene specificata alcuna associazione, la funzione [SQLGetData](../native-client-odbc-api/sqlgetdata.md) può essere utilizzata per determinare il tipo di dati di un'istanza nella colonna **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="fad2d-116">If no binding is specified, the [SQLGetData](../native-client-odbc-api/sqlgetdata.md) function can be used to determine the data type of an instance in the **sql_variant** column.</span></span>  
  
 <span data-ttu-id="fad2d-117">Per recuperare **sql_variant** dati, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="fad2d-117">To retrieve **sql_variant** data follow these steps.</span></span>  
  
1.  <span data-ttu-id="fad2d-118">Chiamare **SQLFetch** per posizionarsi sulla riga recuperata.</span><span class="sxs-lookup"><span data-stu-id="fad2d-118">Call **SQLFetch** to position to the row retrieved.</span></span>  
  
2.  <span data-ttu-id="fad2d-119">Chiamare **SQLGetData**, specificando SQL_C_BINARY per il tipo e 0 per la lunghezza dei dati.</span><span class="sxs-lookup"><span data-stu-id="fad2d-119">Call **SQLGetData**, specifying SQL_C_BINARY for the type and 0 for the data length.</span></span> <span data-ttu-id="fad2d-120">Questa operazione impone al driver di leggere l'intestazione **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="fad2d-120">This forces the driver to read the **sql_variant** header.</span></span> <span data-ttu-id="fad2d-121">L'intestazione fornisce il tipo di dati di tale istanza nella colonna **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="fad2d-121">The header provides the data type of that instance in the **sql_variant** column.</span></span> <span data-ttu-id="fad2d-122">**SQLGetData** restituisce le dimensioni (in byte) del valore.</span><span class="sxs-lookup"><span data-stu-id="fad2d-122">**SQLGetData** returns the size (in bytes) of the value.</span></span>  
  
3.  <span data-ttu-id="fad2d-123">Chiamare [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) specificando **SQL_CA_SS_VARIANT_TYPE** come valore di attributo.</span><span class="sxs-lookup"><span data-stu-id="fad2d-123">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) by specifying **SQL_CA_SS_VARIANT_TYPE** as its attribute value.</span></span> <span data-ttu-id="fad2d-124">Questa funzione restituirà al client il tipo di dati C dell'istanza nella colonna **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="fad2d-124">This function will return the C data type of the instance in the **sql_variant** column to the client.</span></span>  
  
 <span data-ttu-id="fad2d-125">Di seguito viene riportato un segmento di codice nel quale vengono mostrate le operazioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="fad2d-125">Here is a code segment showing the preceding steps.</span></span>  
  
```  
while ((retcode = SQLFetch (hstmt))==SQL_SUCCESS)  
{  
    if (retcode != SQL_SUCCESS && retcode != SQL_SUCCESS_WITH_INFO)  
    {  
        SQLError (NULL, NULL, hstmt, NULL,   
                    &lNativeError,szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    retcode = SQLGetData (hstmt, 1, SQL_C_BINARY,   
                                pBuff,0,&Indicator);//Figure out the length  
    if (retcode != SQL_SUCCESS_WITH_INFO && retcode != SQL_SUCCESS)  
    {  
        SQLError (NULL, NULL, hstmt, NULL, &lNativeError,   
                    szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    printf_s ("Byte length : %d ",Indicator); //Print out the byte length  
  
    int iValue = 0;  
    retcode = SQLColAttribute (hstmt, 1, SQL_CA_SS_VARIANT_TYPE, NULL,   
                                        NULL,NULL,&iValue);  //Figure out the type  
    printf_s ("Sub type = %d ",iValue);//Print the type, the return is C_type of the column]  
  
// Set up a new binding or do the SQLGetData on that column with   
// the appropriate type  
}  
```  
  
 <span data-ttu-id="fad2d-126">Se l'utente crea l'associazione utilizzando [SQLBindCol](../native-client-odbc-api/sqlbindcol.md), il driver legge i metadati e i dati.</span><span class="sxs-lookup"><span data-stu-id="fad2d-126">If the user creates the binding using [SQLBindCol](../native-client-odbc-api/sqlbindcol.md), the driver reads the metadata and the data.</span></span> <span data-ttu-id="fad2d-127">Il driver converte quindi i dati nel tipo ODBC appropriato specificato nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="fad2d-127">The driver then converts the data to the appropriate ODBC type specified in the binding.</span></span>  
  
### <a name="sending-data-to-the-server"></a><span data-ttu-id="fad2d-128">Invio dei dati al server</span><span class="sxs-lookup"><span data-stu-id="fad2d-128">Sending Data to the Server</span></span>  
 <span data-ttu-id="fad2d-129">**SQL_SS_VARIANT**, un nuovo tipo di dati specifico del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client, viene utilizzato per i dati inviati a una colonna **sql_variant** .</span><span class="sxs-lookup"><span data-stu-id="fad2d-129">**SQL_SS_VARIANT**, a new data type specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, is used for data sent to an **sql_variant** column.</span></span> <span data-ttu-id="fad2d-130">Quando si inviano dati al server utilizzando parametri (ad esempio, INSERT INTO TableName VALUEs (?,?)), [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) viene utilizzato per specificare le informazioni sui parametri, inclusi il tipo C e il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="fad2d-130">When sending data to the server using parameters (for example, INSERT INTO TableName VALUES (?,?)), [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) is used to specify the parameter information including the C type and the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type.</span></span> <span data-ttu-id="fad2d-131">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client converte il tipo di dati C in uno dei sottotipi di **sql_variant** appropriati.</span><span class="sxs-lookup"><span data-stu-id="fad2d-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will convert the C data type to one of the appropriate **sql_variant** subtypes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad2d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fad2d-132">See Also</span></span>  
 [<span data-ttu-id="fad2d-133">Elaborazione dei risultati &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="fad2d-133">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
