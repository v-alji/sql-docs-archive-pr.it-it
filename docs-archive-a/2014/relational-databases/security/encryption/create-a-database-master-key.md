---
title: Creare la chiave master di un database | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2019
ms.prod: sql-server-2014
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], creating
ms.assetid: 8cb24263-e97d-4e4d-9429-6cf494a4d5eb
author: jaszymas
ms.author: jaszymas
ms.reviewer: carlrab
ms.openlocfilehash: cb8305d9d5a3c72e6dffafd231f21110a5abdd14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725396"
---
# <a name="create-a-database-master-key"></a><span data-ttu-id="b9908-102">Creazione della chiave master di un database</span><span class="sxs-lookup"><span data-stu-id="b9908-102">Create a Database Master Key</span></span>

<span data-ttu-id="b9908-103">In questo argomento viene descritto come creare una chiave master del database nel `master` database in utilizzando [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9908-103">This topic describes how to create a database master key in the `master` database in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>

<span data-ttu-id="b9908-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="b9908-104">**In This Topic**</span></span>

- <span data-ttu-id="b9908-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="b9908-105">**Before you begin:**</span></span>

  [<span data-ttu-id="b9908-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b9908-106">Security</span></span>](#Security)

- [<span data-ttu-id="b9908-107">Per creare una chiave master del database utilizzando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9908-107">To create a database master key using Transact-SQL</span></span>](#TsqlProcedure)

## <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b9908-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b9908-108">Before You Begin</span></span>

### <a name="security"></a><a name="Security"></a> <span data-ttu-id="b9908-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b9908-109">Security</span></span>

#### <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b9908-110">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b9908-110">Permissions</span></span>

<span data-ttu-id="b9908-111">È richiesta l'autorizzazione CONTROL per il database.</span><span class="sxs-lookup"><span data-stu-id="b9908-111">Requires CONTROL permission on the database.</span></span>

## <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b9908-112">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9908-112">Using Transact-SQL</span></span>

### <a name="to-create-a-database-master-key"></a><span data-ttu-id="b9908-113">Per creare la chiave master di un database</span><span class="sxs-lookup"><span data-stu-id="b9908-113">To create a database master key</span></span>

1. <span data-ttu-id="b9908-114">Scegliere una password per la crittografia della copia della chiave master che verrà archiviata nel database.</span><span class="sxs-lookup"><span data-stu-id="b9908-114">Choose a password for encrypting the copy of the master key that will be stored in the database.</span></span>
2. <span data-ttu-id="b9908-115">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9908-115">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>
3. <span data-ttu-id="b9908-116">Espandere **Database di sistema**, fare clic con il pulsante destro del mouse su `master` e quindi scegliere **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="b9908-116">Expand **System Databases**, right-click `master` and then click **New Query**.</span></span>
4. <span data-ttu-id="b9908-117">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b9908-117">Copy and paste the following example into the query window and click **Execute**.</span></span>

  ```sql
  -- Creates the master key.
  -- The key is encrypted using the password "23987hxJ#KL95234nl0zBe."
  CREATE MASTER KEY ENCRYPTION BY PASSWORD = '23987hxJ#KL95234nl0zBe';
```

<span data-ttu-id="b9908-118">Per altre informazioni, vedere [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b9908-118">For more information, see [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql).</span></span>
