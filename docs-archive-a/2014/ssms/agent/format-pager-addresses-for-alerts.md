---
title: Formattare gli indirizzi di cercapersone per gli avvisi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- pager addresses [SQL Server]
- SQL Server Agent, alerts
- formats [SQL Server], pager addresses
- pager notifications [SQL Server]
- addresses [SQL Server]
- alerts [SQL Server], pager addresses
ms.assetid: a9797d01-1050-442c-9038-ed4bfee1e76a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471f9a4958f51491b312d89239a2204c907e25e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623718"
---
# <a name="format-pager-addresses-for-alerts"></a><span data-ttu-id="26f42-102">Formattare gli indirizzi di cercapersone per gli avvisi</span><span class="sxs-lookup"><span data-stu-id="26f42-102">Format Pager Addresses for Alerts</span></span>
  <span data-ttu-id="26f42-103">In questo argomento viene descritto come formattare gli indirizzi cercapersone per gli [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avvisi di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26f42-103">This topic describes how to format pager addresses for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="26f42-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="26f42-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="26f42-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="26f42-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="26f42-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="26f42-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="26f42-107">**Per formattare gli indirizzi di cercapersone utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="26f42-107">**To format pager addresses, using:**</span></span>  
  
     [<span data-ttu-id="26f42-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26f42-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="26f42-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="26f42-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="26f42-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="26f42-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="26f42-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="26f42-111">Permissions</span></span>  
 <span data-ttu-id="26f42-112">Per impostazione predefinita, i membri del ruolo predefinito del server **sysadmin** possono visualizzare le informazioni su un avviso.</span><span class="sxs-lookup"><span data-stu-id="26f42-112">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="26f42-113">Gli altri utenti devono appartenere al ruolo predefinito del database **SQLAgentOperatorRole** nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="26f42-113">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="26f42-114">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="26f42-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-format-pager-addresses"></a><span data-ttu-id="26f42-115">Per formattare gli indirizzi di cercapersone</span><span class="sxs-lookup"><span data-stu-id="26f42-115">To format pager addresses</span></span>  
  
1.  <span data-ttu-id="26f42-116">In **Esplora oggetti**fare clic sul segno più per espandere il server che contiene l'avviso da inviare a un cercapersone.</span><span class="sxs-lookup"><span data-stu-id="26f42-116">In **Object Explorer**, click the plus sign to expand the server that contains the alert that you want to send to a pager.</span></span>  
  
2.  <span data-ttu-id="26f42-117">Fare clic con il pulsante destro del mouse **SQL Server Agent** e scegliere **Proprietà**</span><span class="sxs-lookup"><span data-stu-id="26f42-117">Right-click **SQL Server Agent** and select **Properties**</span></span>  
  
3.  <span data-ttu-id="26f42-118">In **Selezione pagina**selezionare **Sistema avvisi**.</span><span class="sxs-lookup"><span data-stu-id="26f42-118">Under **Select a page**, select **Alert System**.</span></span>  
  
4.  <span data-ttu-id="26f42-119">Nelle caselle **Riga A:** e **Riga Cc:** del campo **Formato indirizzo per messaggi di posta elettronica tramite cercapersone** digitare il prefisso o il suffisso dell'indirizzo di cercapersone.</span><span class="sxs-lookup"><span data-stu-id="26f42-119">In the **To line** and **CC line** boxes of the **Address formatting for pager e-mails** field, enter the pager address prefix or suffix.</span></span> <span data-ttu-id="26f42-120">L'indirizzo effettivo del cercapersone dell'operatore viene inserito al momento dell'invio di una notifica.</span><span class="sxs-lookup"><span data-stu-id="26f42-120">The operator's actual pager address is inserted when a notification is sent.</span></span>  
  
5.  <span data-ttu-id="26f42-121">Immettere il prefisso o il suffisso per la riga dell'oggetto nella casella **Oggetto** .</span><span class="sxs-lookup"><span data-stu-id="26f42-121">In the **Subject** box, enter the subject line prefix or suffix.</span></span>  
  
6.  <span data-ttu-id="26f42-122">Selezionare **Includi corpo del messaggio nel messaggio di notifica** per includere l'intero messaggio di posta elettronica nel messaggio inviato al cercapersone (invece del solo oggetto).</span><span class="sxs-lookup"><span data-stu-id="26f42-122">Select the **Include body of e-mail in notification page** check box to include the full e-mail message with the pager message (as opposed to the subject line only).</span></span>  
  
7.  <span data-ttu-id="26f42-123">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="26f42-123">When finished, click **OK**.</span></span>  
  
  
