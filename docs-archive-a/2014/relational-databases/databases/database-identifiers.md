---
title: Identificatori del database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- regular identifiers [SQL Server]
- identifiers [SQL Server]
- names [SQL Server], identifiers
- identifiers [SQL Server], about identifiers
- SQL Server identifiers
- Transact-SQL identifiers
- database objects [SQL Server], names
ms.assetid: 171291bb-f57f-4ad1-8cea-0b092d5d150c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 347b20c12a0ac5edd82172741377617aa0fe12c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627819"
---
# <a name="database-identifiers"></a><span data-ttu-id="14357-102">Identificatori del database</span><span class="sxs-lookup"><span data-stu-id="14357-102">Database Identifiers</span></span>
  <span data-ttu-id="14357-103">Il nome di un oggetto di database rappresenta l'identificatore dell'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="14357-103">The database object name is referred to as its identifier.</span></span> <span data-ttu-id="14357-104">È possibile associare un identificatore a qualunque elemento di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)],</span><span class="sxs-lookup"><span data-stu-id="14357-104">Everything in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can have an identifier.</span></span> <span data-ttu-id="14357-105">ad esempio server, database e oggetti di database quali tabelle, viste, colonne, indici, trigger, procedure, vincoli, regole e così via.</span><span class="sxs-lookup"><span data-stu-id="14357-105">Servers, databases, and database objects, such as tables, views, columns, indexes, triggers, procedures, constraints, and rules, can have identifiers.</span></span> <span data-ttu-id="14357-106">Gli identificatori sono richiesti con la maggior parte degli oggetti. Per alcuni oggetti, quali i vincoli, sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="14357-106">Identifiers are required for most objects, but are optional for some objects such as constraints.</span></span>  
  
 <span data-ttu-id="14357-107">L'identificatore viene creato in fase di definizione dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="14357-107">An object identifier is created when the object is defined.</span></span> <span data-ttu-id="14357-108">e viene successivamente utilizzato per fare riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="14357-108">The identifier is then used to reference the object.</span></span> <span data-ttu-id="14357-109">Ad esempio, l'istruzione seguente crea una tabella a cui viene associato l'identificatore `TableX`e due colonne a cui vengono associati gli identificatori `KeyCol` e `Description`:</span><span class="sxs-lookup"><span data-stu-id="14357-109">For example, the following statement creates a table with the identifier `TableX`, and two columns with the identifiers `KeyCol` and `Description`:</span></span>  
  
```  
CREATE TABLE TableX  
(KeyCol INT PRIMARY KEY, Description nvarchar(80))  
```  
  
 <span data-ttu-id="14357-110">La tabella include inoltre un vincolo senza nome.</span><span class="sxs-lookup"><span data-stu-id="14357-110">This table also has an unnamed constraint.</span></span> <span data-ttu-id="14357-111">Il vincolo `PRIMARY KEY` è privo di identificatore.</span><span class="sxs-lookup"><span data-stu-id="14357-111">The `PRIMARY KEY` constraint has no identifier.</span></span>  
  
 <span data-ttu-id="14357-112">Le regole di confronto di un identificatore dipendono dal livello nel quale viene definito.</span><span class="sxs-lookup"><span data-stu-id="14357-112">The collation of an identifier depends on the level at which it is defined.</span></span> <span data-ttu-id="14357-113">Agli identificatori degli oggetti a livello di istanza, quali gli account di accesso e i nomi di database, vengono assegnate le regole di confronto predefinite dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="14357-113">Identifiers of instance-level objects, such as logins and database names, are assigned the default collation of the instance.</span></span> <span data-ttu-id="14357-114">Agli identificatori degli oggetti di un database, quali tabelle, viste e nomi di colonna, vengono assegnate le regole di confronto predefinite del database.</span><span class="sxs-lookup"><span data-stu-id="14357-114">Identifiers of objects in a database, such as tables, views, and column names, are assigned the default collation of the database.</span></span> <span data-ttu-id="14357-115">Ad esempio, due tabelle i cui nomi si differenziano soltanto per l'utilizzo del maiuscolo e del minuscolo possono essere create in un database con regole di confronto in cui l'uso di maiuscole e minuscole è rilevante, ma non in un database con regole di confronto in cui l'uso di maiuscole e minuscole non è rilevante.</span><span class="sxs-lookup"><span data-stu-id="14357-115">For example, two tables with names that differ only in case can be created in a database that has case-sensitive collation, but cannot be created in a database that has case-insensitive collation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14357-116">È necessario che i nomi di variabili o i parametri di funzioni e stored procedure siano conformi alle regole relative agli identificatori [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14357-116">The names of variables, or the parameters of functions and stored procedures must comply with the rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
## <a name="classes-of-identifiers"></a><span data-ttu-id="14357-117">Classi di identificatori</span><span class="sxs-lookup"><span data-stu-id="14357-117">Classes of Identifiers</span></span>  
 <span data-ttu-id="14357-118">Esistono due classi di identificatori:</span><span class="sxs-lookup"><span data-stu-id="14357-118">There are two classes of identifiers:</span></span>  
  
 <span data-ttu-id="14357-119">Identificatori regolari</span><span class="sxs-lookup"><span data-stu-id="14357-119">Regular identifiers</span></span>  
 <span data-ttu-id="14357-120">Sono conformi alle regole relative al formato degli identificatori.</span><span class="sxs-lookup"><span data-stu-id="14357-120">Comply with the rules for the format of identifiers.</span></span> <span data-ttu-id="14357-121">Gli identificatori regolari non vengono delimitati quando vengono utilizzati in istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14357-121">Regular identifiers are not delimited when they are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
```  
SELECT *  
FROM TableX  
WHERE KeyCol = 124  
```  
  
 <span data-ttu-id="14357-122">Identificatori delimitati</span><span class="sxs-lookup"><span data-stu-id="14357-122">Delimited identifiers</span></span>  
 <span data-ttu-id="14357-123">Sono racchiusi tra virgolette doppie (") o tra parentesi quadre ([ ]).</span><span class="sxs-lookup"><span data-stu-id="14357-123">Are enclosed in double quotation marks (") or brackets ([ ]).</span></span> <span data-ttu-id="14357-124">Gli identificatori conformi alle regole relative al formato degli identificatori possono non essere delimitati.</span><span class="sxs-lookup"><span data-stu-id="14357-124">Identifiers that comply with the rules for the format of identifiers might not be delimited.</span></span> <span data-ttu-id="14357-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="14357-125">For example:</span></span>  
  
```  
SELECT *  
FROM [TableX]         --Delimiter is optional.  
WHERE [KeyCol] = 124  --Delimiter is optional.  
```  
  
 <span data-ttu-id="14357-126">All'interno di un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] è necessario che gli identificatori non conformi alle regole relative agli identificatori siano delimitati.</span><span class="sxs-lookup"><span data-stu-id="14357-126">Identifiers that do not comply with all the rules for identifiers must be delimited in a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="14357-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="14357-127">For example:</span></span>  
  
```  
SELECT *  
FROM [My Table]      --Identifier contains a space and uses a reserved keyword.  
WHERE [order] = 10   --Identifier is a reserved keyword.  
```  
  
 <span data-ttu-id="14357-128">Sia gli identificatori regolari che quelli delimitati devono includere da 1 a 128 caratteri.</span><span class="sxs-lookup"><span data-stu-id="14357-128">Both regular and delimited identifiers must contain from 1 through 128 characters.</span></span> <span data-ttu-id="14357-129">Gli identificatori delle tabelle temporanee locali possono includere al massimo 116 caratteri.</span><span class="sxs-lookup"><span data-stu-id="14357-129">For local temporary tables, the identifier can have a maximum of 116 characters.</span></span>  
  
## <a name="rules-for-regular-identifiers"></a><span data-ttu-id="14357-130">Regole relative agli identificatori regolari</span><span class="sxs-lookup"><span data-stu-id="14357-130">Rules for Regular Identifiers</span></span>  
 <span data-ttu-id="14357-131">È necessario che i nomi di variabili, funzioni e stored procedure siano conformi alle seguenti regole relative agli identificatori [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14357-131">The names of variables, functions, and stored procedures must comply with the following rules for [!INCLUDE[tsql](../../includes/tsql-md.md)] identifiers.</span></span>  
  
1.  <span data-ttu-id="14357-132">Il primo carattere deve essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="14357-132">The first character must be one of the following:</span></span>  
  
    -   <span data-ttu-id="14357-133">Una lettera definita dallo standard Unicode 3,2,</span><span class="sxs-lookup"><span data-stu-id="14357-133">A letter as defined by the Unicode Standard 3.2.</span></span> <span data-ttu-id="14357-134">ovvero i caratteri dell'alfabeto latino a-z e A-Z e i caratteri di altre lingue.</span><span class="sxs-lookup"><span data-stu-id="14357-134">The Unicode definition of letters includes Latin characters from a through z, from A through Z, and also letter characters from other languages.</span></span>  
  
    -   <span data-ttu-id="14357-135">Il carattere di sottolineatura (_), il simbolo di chiocciola (@) o il simbolo di cancelletto (#).</span><span class="sxs-lookup"><span data-stu-id="14357-135">The underscore (_), at sign (@), or number sign (#).</span></span>  
  
         <span data-ttu-id="14357-136">Alcuni caratteri utilizzati all'inizio di un identificatore assumono un significato particolare in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14357-136">Certain symbols at the beginning of an identifier have special meaning in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="14357-137">Un identificatore regolare che inizia con il carattere @ indica sempre una variabile locale o un parametro e non può essere utilizzato per il nome di un tipo di oggetto diverso.</span><span class="sxs-lookup"><span data-stu-id="14357-137">A regular identifier that starts with the at sign always denotes a local variable or parameter and cannot be used as the name of any other type of object.</span></span> <span data-ttu-id="14357-138">il carattere # indica una tabella o una procedura temporanea,</span><span class="sxs-lookup"><span data-stu-id="14357-138">An identifier that starts with a number sign denotes a temporary table or procedure.</span></span> <span data-ttu-id="14357-139">mentre due simboli di cancelletto (##) indicano un oggetto temporaneo globale.</span><span class="sxs-lookup"><span data-stu-id="14357-139">An identifier that starts with double number signs (##) denotes a global temporary object.</span></span> <span data-ttu-id="14357-140">Nonostante sia possibile usare uno o due simboli di cancelletto all'inizio dei nomi di altri tipi di oggetti, è consigliabile non adottare questa tecnica.</span><span class="sxs-lookup"><span data-stu-id="14357-140">Although the number sign or double number sign characters can be used to begin the names of other types of objects, we do not recommend this practice.</span></span>  
  
         <span data-ttu-id="14357-141">I nomi di alcune funzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] iniziano con due simboli di chiocciola (@@).</span><span class="sxs-lookup"><span data-stu-id="14357-141">Some [!INCLUDE[tsql](../../includes/tsql-md.md)] functions have names that start with double at signs (@@).</span></span> <span data-ttu-id="14357-142">Per evitare confusione in merito a tali funzioni, è consigliabile non usare nomi che iniziano con @@.</span><span class="sxs-lookup"><span data-stu-id="14357-142">To avoid confusion with these functions, you should not use names that start with @@.</span></span>  
  
2.  <span data-ttu-id="14357-143">I caratteri successivi possono includere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="14357-143">Subsequent characters can include the following:</span></span>  
  
    -   <span data-ttu-id="14357-144">Lettere definite nello standard Unicode 3,2.</span><span class="sxs-lookup"><span data-stu-id="14357-144">Letters as defined in the Unicode Standard 3.2.</span></span>  
  
    -   <span data-ttu-id="14357-145">Numeri decimali inclusi nell'alfabeto Latino di base o in altri alfabeti nazionali.</span><span class="sxs-lookup"><span data-stu-id="14357-145">Decimal numbers from either Basic Latin or other national scripts.</span></span>  
  
    -   <span data-ttu-id="14357-146">Il simbolo di chiocciola, il simbolo di dollaro ($), il simbolo di cancelletto o il carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="14357-146">The at sign, dollar sign ($), number sign, or underscore.</span></span>  
  
3.  <span data-ttu-id="14357-147">L'identificatore non deve essere una parola riservata [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14357-147">The identifier must not be a [!INCLUDE[tsql](../../includes/tsql-md.md)] reserved word.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="14357-148">riserva sia le versioni maiuscole sia quelle minuscole delle parole riservate.</span><span class="sxs-lookup"><span data-stu-id="14357-148">reserves both the uppercase and lowercase versions of reserved words.</span></span> <span data-ttu-id="14357-149">Quando vengono utilizzati in istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] , gli identificatori non conformi a queste regole devono essere racchiusi tra virgolette doppie o parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="14357-149">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span> <span data-ttu-id="14357-150">Le parole riservate dipendono dal livello di compatibilità del database.</span><span class="sxs-lookup"><span data-stu-id="14357-150">The words that are reserved depend on the database compatibility level.</span></span> <span data-ttu-id="14357-151">Questo livello può essere impostato usando l'istruzione [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) .</span><span class="sxs-lookup"><span data-stu-id="14357-151">This level can be set by using the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level) statement.</span></span>  
  
4.  <span data-ttu-id="14357-152">Non sono consentiti spazi incorporati o caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="14357-152">Embedded spaces or special characters are not allowed.</span></span>  
  
5.  <span data-ttu-id="14357-153">Non sono consentiti caratteri supplementari.</span><span class="sxs-lookup"><span data-stu-id="14357-153">Supplementary characters are not allowed.</span></span>  
  
 <span data-ttu-id="14357-154">Quando vengono utilizzati in istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] , gli identificatori non conformi a queste regole devono essere racchiusi tra virgolette doppie o parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="14357-154">When identifiers are used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, the identifiers that do not comply with these rules must be delimited by double quotation marks or brackets.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14357-155">Alcune regole relative al formato degli identificatori regolari dipendono dal livello di compatibilità del database.</span><span class="sxs-lookup"><span data-stu-id="14357-155">Some rules for the format of regular identifiers depend on the database compatibility level.</span></span> <span data-ttu-id="14357-156">È possibile impostare tale livello con [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="14357-156">This level can be set by using [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14357-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14357-157">See Also</span></span>  
 <span data-ttu-id="14357-158">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-158">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 <span data-ttu-id="14357-159">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-159">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="14357-160">[CREATE DEFAULT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-default-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-160">[CREATE DEFAULT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-default-transact-sql) </span></span>  
 <span data-ttu-id="14357-161">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-161">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="14357-162">[CREATE RULE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-rule-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-162">[CREATE RULE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-rule-transact-sql) </span></span>  
 <span data-ttu-id="14357-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="14357-164">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-164">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="14357-165">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-165">[CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) </span></span>  
 <span data-ttu-id="14357-166">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-166">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="14357-167">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-167">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="14357-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-168">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="14357-169">[Parole chiave riservate &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-169">[Reserved Keywords &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reserved-keywords-transact-sql) </span></span>  
 <span data-ttu-id="14357-170">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="14357-170">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="14357-171">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="14357-171">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
