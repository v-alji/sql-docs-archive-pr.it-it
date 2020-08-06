---
title: Personalizzare il comportamento dei word breaker con un dizionario personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: a8e278d1-aeaa-48f1-a0c6-5de232c983e4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9fb02a47da20134925d9b2486ea0c08091af4aa6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716212"
---
# <a name="customize-the-behavior-of-word-breakers-with-a-custom-dictionary"></a><span data-ttu-id="51cc4-102">Personalizzare Comportamento di word breaker con un dizionario personalizzato</span><span class="sxs-lookup"><span data-stu-id="51cc4-102">Customize the Behavior of Word Breakers with a Custom Dictionary</span></span>
  <span data-ttu-id="51cc4-103">È possibile personalizzare il comportamento del word breaker per una particolare lingua creando un file del dizionario personalizzato specifico della lingua.</span><span class="sxs-lookup"><span data-stu-id="51cc4-103">You can customize the behavior of the word breaker for a particular language by creating a language-specific custom dictionary file.</span></span> <span data-ttu-id="51cc4-104">Ad esempio, è possibile impedire l'attività del word breaker per determinati termini o modelli.</span><span class="sxs-lookup"><span data-stu-id="51cc4-104">For example, you can prevent the word breaker from breaking certain terms or patterns.</span></span>  
  
 <span data-ttu-id="51cc4-105">Per ulteriori informazioni, vedere il seguente articolo SharePoint:</span><span class="sxs-lookup"><span data-stu-id="51cc4-105">For more information, see the following SharePoint article:</span></span>  
  
 [<span data-ttu-id="51cc4-106">Creare un dizionario personalizzato (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="51cc4-106">Create a custom dictionary (SharePoint Server 2010)</span></span>](https://go.microsoft.com/fwlink/?LinkId=215011)  
  
 <span data-ttu-id="51cc4-107">Per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], posizionare file del dizionario personalizzato nella seguente cartella:</span><span class="sxs-lookup"><span data-stu-id="51cc4-107">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], place custom dictionary files in the following folder:</span></span>  
  
 `C:\Program Files\Microsoft SQL Server\<instance name>\MSSQL\Binn`  
  
 <span data-ttu-id="51cc4-108">Dopo aver creato o modificato i file del dizionario personalizzato, riavviare l'Utilità di avvio del Daemon Full-text SQL attraverso il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="51cc4-108">After creating or changing custom dictionary files, restart the SQL Full-text Daemon Launcher with the following command:</span></span>  
  
 `exec sp_fulltext_service 'restart_all_fdhosts'`  
  
  
