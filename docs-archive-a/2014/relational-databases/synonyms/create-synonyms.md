---
title: Creare sinonimi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
f1_keywords:
- sql12.swb.synonym.general.f1
helpviewer_keywords:
- creating synonyms
- synonyms [SQL Server], creating
ms.assetid: fedfa7a5-d0b6-4e2b-90f4-a08122958e33
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3dc18c9d0d6048c4190ba56725dd332f2dfb629e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623108"
---
# <a name="create-synonyms"></a><span data-ttu-id="ea4c7-102">Creare sinonimi</span><span class="sxs-lookup"><span data-stu-id="ea4c7-102">Create Synonyms</span></span>
  <span data-ttu-id="ea4c7-103">In questo argomento viene descritto come creare un sinonimo in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea4c7-103">This topic describes how to create a synonym in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ea4c7-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ea4c7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ea4c7-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ea4c7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ea4c7-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ea4c7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ea4c7-107">**Per creare un sinonimo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="ea4c7-107">**To create a synonym, using:**</span></span>  
  
     [<span data-ttu-id="ea4c7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ea4c7-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ea4c7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ea4c7-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ea4c7-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ea4c7-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ea4c7-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ea4c7-111">Security</span></span>  
 <span data-ttu-id="ea4c7-112">Per poter creare un sinonimo in un determinato schema, un utente deve disporre dell'autorizzazione CREATE SYNONYM, oltre a disporre della proprietà dello schema o dell'autorizzazione ALTER SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-112">To create a synonym in a given schema, a user must have CREATE SYNONYM permission and either own the schema or have ALTER SCHEMA permission.</span></span> <span data-ttu-id="ea4c7-113">L'autorizzazione CREATE SYNONYM è un'autorizzazione che può essere concessa.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-113">The CREATE SYNONYM permission is a grantable permission.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ea4c7-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ea4c7-114">Permissions</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ea4c7-115">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ea4c7-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="ea4c7-116">Per creare un sinonimo</span><span class="sxs-lookup"><span data-stu-id="ea4c7-116">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="ea4c7-117">In **Esplora oggetti**espandere il database in cui si desidera creare la nuova vista.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-117">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="ea4c7-118">Fare clic con il pulsante destro del mouse sulla cartella **Sinonimi**, quindi selezionare **Nuovo sinonimo...** .</span><span class="sxs-lookup"><span data-stu-id="ea4c7-118">Right-click the **Synonyms** folder, then click **New Synonym...**.</span></span>  
  
3.  <span data-ttu-id="ea4c7-119">Nella finestra di dialogo **Aggiungi sinonimo** immettere le informazioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-119">In the **Add Synonym** dialog box, enter the following information.</span></span>  
  
     <span data-ttu-id="ea4c7-120">**Nome sinonimo**</span><span class="sxs-lookup"><span data-stu-id="ea4c7-120">**Synonym name**</span></span>  
     <span data-ttu-id="ea4c7-121">Digitare il nuovo nome che verrà utilizzato per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-121">Type the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="ea4c7-122">**Schema sinonimo**</span><span class="sxs-lookup"><span data-stu-id="ea4c7-122">**Synonym schema**</span></span>  
     <span data-ttu-id="ea4c7-123">Digitare lo schema del nuovo nome che verrà utilizzato per questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-123">Type the schema of the new name you will use for this object.</span></span>  
  
     <span data-ttu-id="ea4c7-124">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="ea4c7-124">**Server name**</span></span>  
     <span data-ttu-id="ea4c7-125">Digitare l'istanza del server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-125">Type the server instance to connect to.</span></span>  
  
     <span data-ttu-id="ea4c7-126">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="ea4c7-126">**Database name**</span></span>  
     <span data-ttu-id="ea4c7-127">Digitare o selezionare il database contenente l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-127">Type or select the database containing the object.</span></span>  
  
     <span data-ttu-id="ea4c7-128">**Schema**</span><span class="sxs-lookup"><span data-stu-id="ea4c7-128">**Schema**</span></span>  
     <span data-ttu-id="ea4c7-129">Digitare o selezionare lo schema proprietario dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-129">Type or select the schema that owns the object.</span></span>  
  
     <span data-ttu-id="ea4c7-130">**Tipo oggetto**</span><span class="sxs-lookup"><span data-stu-id="ea4c7-130">**Object type**</span></span>  
     <span data-ttu-id="ea4c7-131">Selezionare il tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-131">Select the type of object.</span></span>  
  
     <span data-ttu-id="ea4c7-132">**Nome oggetto**</span><span class="sxs-lookup"><span data-stu-id="ea4c7-132">**Object name**</span></span>  
     <span data-ttu-id="ea4c7-133">Digitare il nome dell'oggetto al quale fa riferimento il sinonimo.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-133">Type the name of the object to which the synonym refers.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ea4c7-134">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ea4c7-134">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-synonym"></a><span data-ttu-id="ea4c7-135">Per creare un sinonimo</span><span class="sxs-lookup"><span data-stu-id="ea4c7-135">To Create a Synonym</span></span>  
  
1.  <span data-ttu-id="ea4c7-136">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea4c7-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ea4c7-137">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ea4c7-138">Copiare e incollare gli esempi seguenti nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-138">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="ea4c7-139">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="ea4c7-139">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="ea4c7-140">Nell'esempio seguente viene creato un sinonimo per una tabella esistente nel database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea4c7-140">The following example creates a synonym for an existing table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="ea4c7-141">Il sinonimo viene quindi utilizzato negli esempi successivi.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-141">The synonym is then used in subsequent examples.</span></span>  
  
```  
USE tempdb;  
GO  
CREATE SYNONYM MyAddressType  
FOR AdventureWorks2012.Person.AddressType;  
GO  
```  
  
 <span data-ttu-id="ea4c7-142">Nell'esempio seguente viene inserita una riga nella tabella di base cui fa riferimento il sinonimo `MyAddressType` .</span><span class="sxs-lookup"><span data-stu-id="ea4c7-142">The following example inserts a row into the base table that is referenced by the `MyAddressType` synonym.</span></span>  
  
```  
USE tempdb;  
GO  
INSERT INTO MyAddressType (Name)  
VALUES ('Test');  
GO  
```  
  
 <span data-ttu-id="ea4c7-143">Nell'esempio seguente viene illustrato il modo in cui è possibile fare riferimento a un sinonimo in un'istruzione nel linguaggio SQL dinamico.</span><span class="sxs-lookup"><span data-stu-id="ea4c7-143">The following example demonstrates how a synonym can be referenced in dynamic SQL.</span></span>  
  
```  
USE tempdb;  
GO  
EXECUTE ('SELECT Name FROM MyAddressType');  
GO  
```  
  
  
