---
title: Esplora modelli | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.wb.templates.f1
- sql12.swb.templates.explorer.f1
helpviewer_keywords:
- templates [SQL Server]
- SQL Server Management Studio [SQL Server], Template Explorer
- Template Explorer
- templates [Transact-SQL]
- templates [SQL Server], Template Explorer
ms.assetid: b9ee55c5-bb44-4f76-90ac-792d8d83b4c8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35e7ee1e6261c759580df3a836f9cc4b500a77ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630215"
---
# <a name="template-explorer"></a><span data-ttu-id="81d91-102">Esplora modelli</span><span class="sxs-lookup"><span data-stu-id="81d91-102">Template Explorer</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="81d91-103">offre un'ampia gamma di modelli.</span><span class="sxs-lookup"><span data-stu-id="81d91-103">provides a variety of templates.</span></span> <span data-ttu-id="81d91-104">I modelli sono file preimpostati contenenti script SQL che agevolano la creazione degli oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="81d91-104">Templates are boilerplate files containing SQL scripts that help you create objects in a database.</span></span> <span data-ttu-id="81d91-105">Alla prima apertura di Esplora modelli, una copia dei modelli viene inserita nella cartella dell'utente in C:\Users in AppData\Roaming\Microsoft\SQL Server Management Studio\120\Templates.</span><span class="sxs-lookup"><span data-stu-id="81d91-105">The first time the template explorer is opened, a copy of the templates are placed in the user's folder in C:\Users, under AppData\Roaming\Microsoft\SQL Server Management Studio\120\Templates.</span></span>  
  
 <span data-ttu-id="81d91-106">È possibile esplorare i modelli disponibili in Esplora modelli, quindi aprire un modello per incorporare il codice in una finestra dell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="81d91-106">You can browse the available templates in Template Explorer, then open a template to incorporate the code into a code editor window.</span></span> <span data-ttu-id="81d91-107">È inoltre possibile creare modelli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="81d91-107">You can also create custom templates.</span></span>  
  
## <a name="benefits-of-templates"></a><span data-ttu-id="81d91-108">Vantaggi dei modelli</span><span class="sxs-lookup"><span data-stu-id="81d91-108">Benefits of Templates</span></span>  
 <span data-ttu-id="81d91-109">Sono disponibili modelli per soluzioni, progetti e diversi tipi di editor del codice.</span><span class="sxs-lookup"><span data-stu-id="81d91-109">Templates are available for solutions, projects, and various types of code editors.</span></span> <span data-ttu-id="81d91-110">I modelli inclusi nell'applicazione consentono di creare oggetti, ad esempio database, tabelle, viste, indici, stored procedure, trigger, statistiche e funzioni.</span><span class="sxs-lookup"><span data-stu-id="81d91-110">Templates are available to create objects like databases, tables, views, indexes, stored procedures, triggers, statistics, and functions.</span></span> <span data-ttu-id="81d91-111">Sono inoltre disponibili modelli che facilitano la gestione del server mediante la creazione di proprietà estese, server collegati, account di accesso, ruoli, utenti e modelli per [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81d91-111">In addition, there are templates that help you to manage your server by creating extended properties, linked servers, logins, roles, users, and templates for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="81d91-112">Gli script modello disponibili in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] includono parametri che consentono di personalizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="81d91-112">The template scripts provided with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] contain parameters to help you customize the code.</span></span> <span data-ttu-id="81d91-113">Dopo avere aperto il modello, usare la finestra di dialogo **Sostituisci parametri modello** per sostituire i parametri del modello con i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="81d91-113">When you open a template, Use the **Replace Template Parameters** dialog box to insert values into the script.</span></span>  
  
 <span data-ttu-id="81d91-114">Creare modelli personalizzati per le attività eseguite di frequente.</span><span class="sxs-lookup"><span data-stu-id="81d91-114">Create custom templates for tasks you perform frequently.</span></span> <span data-ttu-id="81d91-115">Organizzare gli script personalizzati in cartelle esistenti oppure creare una nuova struttura di cartelle.</span><span class="sxs-lookup"><span data-stu-id="81d91-115">Organize your custom scripts into the existing folders or create a new folder structure.</span></span>  
  
 <span data-ttu-id="81d91-116">L'editor di query del [!INCLUDE[ssDE](../../includes/ssde-md.md)] supporta anche frammenti di codice che possono essere inseriti in percorsi specifici in uno script facendo clic con il pulsante destro del mouse sul percorso.</span><span class="sxs-lookup"><span data-stu-id="81d91-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query editor also supports code snippets, which can be inserted at specific locations in a script by right-clicking at that location.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="81d91-117">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="81d91-117">Related Tasks</span></span>  
 <span data-ttu-id="81d91-118">Utilizzare i seguenti argomenti per ottenere un'introduzione ai modelli.</span><span class="sxs-lookup"><span data-stu-id="81d91-118">Use the following topics to get started with templates</span></span>  
  
|<span data-ttu-id="81d91-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="81d91-119">**Description**</span></span>|<span data-ttu-id="81d91-120">**Argomento**</span><span class="sxs-lookup"><span data-stu-id="81d91-120">**Topic**</span></span>|  
|---------------------|---------------|  
|<span data-ttu-id="81d91-121">Viene descritto come incorporare il codice da un modello in una finestra dell'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="81d91-121">Describes how to incorporate the code from a template into a code editor window.</span></span>|[<span data-ttu-id="81d91-122">Aprire un modello</span><span class="sxs-lookup"><span data-stu-id="81d91-122">Open a Template</span></span>](open-a-template.md)|  
|<span data-ttu-id="81d91-123">Si descrive come sostituire valori del parametro di modello dopo aver aperto un modello in un editor di codice.</span><span class="sxs-lookup"><span data-stu-id="81d91-123">Describes how to replace template parameter values after opening a template in a code editor.</span></span>|[<span data-ttu-id="81d91-124">Sostituire i parametri del modello</span><span class="sxs-lookup"><span data-stu-id="81d91-124">Replace Template Parameters</span></span>](replace-template-parameters.md)|  
  
  
