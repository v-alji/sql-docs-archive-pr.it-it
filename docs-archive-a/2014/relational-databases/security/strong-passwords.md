---
title: Password complesse | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logins [SQL Server], passwords
- passwords [SQL Server], strong
- symbols [SQL Server]
- security [SQL Server], passwords
- passwords [SQL Server], symbols
- characters [SQL Server], password policies
- strong passwords [SQL Server]
ms.assetid: 338548f4-c4d8-47ca-b597-5c9c0f2fa205
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5e878e0de5ee1f496dcc981182d42f5898838c64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713984"
---
# <a name="strong-passwords"></a><span data-ttu-id="c6afa-102">Password complesse</span><span class="sxs-lookup"><span data-stu-id="c6afa-102">Strong Passwords</span></span>
  <span data-ttu-id="c6afa-103">Le password possono costituire il punto debole nell'ambito distribuzione della sicurezza in un server.</span><span class="sxs-lookup"><span data-stu-id="c6afa-103">Passwords can be the weakest link in a server security deployment.</span></span> <span data-ttu-id="c6afa-104">È dunque necessario prestare grande attenzione alla scelta delle password.</span><span class="sxs-lookup"><span data-stu-id="c6afa-104">You should always take great care when you select a password.</span></span> <span data-ttu-id="c6afa-105">Una password complessa ha le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6afa-105">A strong password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="c6afa-106">È composta da almeno 8 caratteri.</span><span class="sxs-lookup"><span data-stu-id="c6afa-106">Is at least 8 characters long.</span></span>  
  
-   <span data-ttu-id="c6afa-107">È costituita da una combinazione di lettere, numeri e simboli.</span><span class="sxs-lookup"><span data-stu-id="c6afa-107">Combines letters, numbers, and symbol characters within the password.</span></span>  
  
-   <span data-ttu-id="c6afa-108">Non è una parola presente nei dizionari.</span><span class="sxs-lookup"><span data-stu-id="c6afa-108">Is not found in a dictionary.</span></span>  
  
-   <span data-ttu-id="c6afa-109">Non è il nome di un comando.</span><span class="sxs-lookup"><span data-stu-id="c6afa-109">Is not the name of a command.</span></span>  
  
-   <span data-ttu-id="c6afa-110">Non è il nome di una persona.</span><span class="sxs-lookup"><span data-stu-id="c6afa-110">Is not the name of a person.</span></span>  
  
-   <span data-ttu-id="c6afa-111">Non è il nome di un utente.</span><span class="sxs-lookup"><span data-stu-id="c6afa-111">Is not the name of a user.</span></span>  
  
-   <span data-ttu-id="c6afa-112">Non è il nome di un computer.</span><span class="sxs-lookup"><span data-stu-id="c6afa-112">Is not the name of a computer.</span></span>  
  
-   <span data-ttu-id="c6afa-113">Viene modificata regolarmente.</span><span class="sxs-lookup"><span data-stu-id="c6afa-113">Is changed regularly.</span></span>  
  
-   <span data-ttu-id="c6afa-114">Presenta differenze sostanziali rispetto alle password precedenti.</span><span class="sxs-lookup"><span data-stu-id="c6afa-114">Is significantly different from previous passwords.</span></span>  
  
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="c6afa-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] le password possono contenere fino a 128 caratteri, compresi lettere, simboli e cifre.</span><span class="sxs-lookup"><span data-stu-id="c6afa-115">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] passwords can contain up to 128 characters, including letters, symbols, and digits.</span></span> <span data-ttu-id="c6afa-116">Poiché gli account di accesso, i nomi utente, i ruoli e le password vengono spesso utilizzati in istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] , è necessario racchiudere alcuni simboli tra virgolette doppie (") o parentesi quadre ([ ]).</span><span class="sxs-lookup"><span data-stu-id="c6afa-116">Because logins, user names, roles, and passwords are frequently used in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, certain symbols must be enclosed by double quotation marks (") or square brackets ([ ]).</span></span> <span data-ttu-id="c6afa-117">Utilizzare questi delimitatori nelle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] quando l'account di accesso, l'utente, il ruolo o la password di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] presenta le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="c6afa-117">Use these delimiters in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login, user, role, or password has the following characteristics:</span></span>  
  
-   <span data-ttu-id="c6afa-118">Include o inizia con uno spazio.</span><span class="sxs-lookup"><span data-stu-id="c6afa-118">Contains or starts with a space character.</span></span>  
  
-   <span data-ttu-id="c6afa-119">Inizia con il carattere $ o \@.</span><span class="sxs-lookup"><span data-stu-id="c6afa-119">Starts with the $ or \@ character.</span></span>  
  
 <span data-ttu-id="c6afa-120">Gli account di accesso e le password usati in una stringa di connessione OLE DB o ODBC non devono contenere i caratteri seguenti: [] {}() , ; ?</span><span class="sxs-lookup"><span data-stu-id="c6afa-120">If used in an OLE DB or ODBC connection string, a login or password must not contain the following characters: [] {}() , ; ?</span></span> <span data-ttu-id="c6afa-121">\* !</span><span class="sxs-lookup"><span data-stu-id="c6afa-121">\* !</span></span> <span data-ttu-id="c6afa-122">\@.</span><span class="sxs-lookup"><span data-stu-id="c6afa-122">\@.</span></span> <span data-ttu-id="c6afa-123">Questi caratteri vengono utilizzati per inizializzare una connessione o per separare i relativi valori.</span><span class="sxs-lookup"><span data-stu-id="c6afa-123">These characters are used to either initialize a connection or separate connection values.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="c6afa-124">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="c6afa-124">Related Content</span></span>  
 [<span data-ttu-id="c6afa-125">Criteri password</span><span class="sxs-lookup"><span data-stu-id="c6afa-125">Password Policy</span></span>](password-policy.md)  
  
  
