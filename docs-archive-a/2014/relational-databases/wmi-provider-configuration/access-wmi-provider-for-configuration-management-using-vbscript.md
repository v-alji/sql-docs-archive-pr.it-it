---
title: Modificare le proprietà avanzate del servizio SQL Server tramite VBScript | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- VBScript [WMI]
- modifying SQL Server Service properties
- WMI Provider for Configuration Management, VBScript
ms.assetid: f3c5d981-eaa3-4d34-9b91-37e42636aa81
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2cf722b00a31723b77624c33fef81a82ff0cb926
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637667"
---
# <a name="modify-sql-server-service-advanced-properties-using-vbscript"></a><span data-ttu-id="05afe-102">Modificare le proprietà avanzate del servizio SQL Server utilizzando VBScript</span><span class="sxs-lookup"><span data-stu-id="05afe-102">Modify SQL Server Service Advanced Properties using VBScript</span></span>
  <span data-ttu-id="05afe-103">In questa sezione viene descritto come creare un programma VBScript che elenca la versione delle istanze installate di in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esecuzione in un computer.</span><span class="sxs-lookup"><span data-stu-id="05afe-103">This section describes how to create a VBScript program that lists the version of installed instances of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are running on a computer.</span></span>  
  
 <span data-ttu-id="05afe-104">Nell'esempio di codice vengono elencate le istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione nel computer e la relativa versione.</span><span class="sxs-lookup"><span data-stu-id="05afe-104">The code example lists the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on the computer and its version.</span></span>  
  
### <a name="listing-name-and-version-of-installed-instances-of-sql-server"></a><span data-ttu-id="05afe-105">Elenco del nome e della versione delle istanze installate di SQL Server</span><span class="sxs-lookup"><span data-stu-id="05afe-105">Listing name and version of installed instances of SQL Server</span></span>  
  
1.  <span data-ttu-id="05afe-106">Aprire un nuovo documento in un editor di testo, ad esempio Blocco note di [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05afe-106">Open a new document in a text editor, such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Notepad.</span></span> <span data-ttu-id="05afe-107">Copiare il codice riportato dopo questa procedura e salvare il file con estensione vbs,</span><span class="sxs-lookup"><span data-stu-id="05afe-107">Copy the code that follows this procedure and save the file with a .vbs extension.</span></span> <span data-ttu-id="05afe-108">ad esempio test.vbs.</span><span class="sxs-lookup"><span data-stu-id="05afe-108">This example is called test.vbs.</span></span>  
  
2.  <span data-ttu-id="05afe-109">Connettersi a un'istanza del provider WMI per Gestione computer con la funzione VBScript `GetObject`.</span><span class="sxs-lookup"><span data-stu-id="05afe-109">Connect to an instance of the WMI Provider for Computer Management with the VBScript `GetObject` function.</span></span> <span data-ttu-id="05afe-110">In questo esempio viene effettuata la connessione a un computer remoto denominato mpc. Omettere il nome del computer per connettersi al computer locale: winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span><span class="sxs-lookup"><span data-stu-id="05afe-110">This example connects to a remote computer named mpc, but omit the computer name to connect to the local computer: winmgmts:root\Microsoft\SqlServer\ComputerManagement.</span></span> <span data-ttu-id="05afe-111">Per ulteriori informazioni sulla funzione `GetObject`, vedere l'argomento di riferimento per VBScript.</span><span class="sxs-lookup"><span data-stu-id="05afe-111">For more information about the `GetObject` function, see the VBScript reference.</span></span>  
  
3.  <span data-ttu-id="05afe-112">Utilizzare il metodo `InstancesOf` per enumerare un elenco dei servizi.</span><span class="sxs-lookup"><span data-stu-id="05afe-112">Use the `InstancesOf` method to enumerate a list of the services.</span></span> <span data-ttu-id="05afe-113">È inoltre possibile enumerare i servizi mediante una query WQL semplice e il metodo `ExecQuery` anziché utilizzare il metodo `InstancesOf`.</span><span class="sxs-lookup"><span data-stu-id="05afe-113">The services can also be enumerated by using a simple WQL query and an `ExecQuery` method instead of the `InstancesOf` method.</span></span>  
  
4.  <span data-ttu-id="05afe-114">Utilizzare il metodo `ExecQuery` e una query WQL per recuperare il nome e la versione delle istanze installate di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05afe-114">Use the `ExecQuery` method and a WQL query to retrieve the name and version of the installed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="05afe-115">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="05afe-115">Save the file.</span></span>  
  
6.  <span data-ttu-id="05afe-116">Eseguire lo script digitando `cscript test.vbs` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="05afe-116">Run the script by typing `cscript test.vbs` at the command prompt.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05afe-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="05afe-117">Example</span></span>  
  
```  
set wmi = GetObject("WINMGMTS:\\.\root\Microsoft\SqlServer\ComputerManagement12")  
for each prop in wmi.ExecQuery("select * from SqlServiceAdvancedProperty where SQLServiceType = 1 AND PropertyName = 'VERSION'")  
WScript.Echo prop.ServiceName & " " & prop.PropertyName & ": " & prop.PropertyStrValue  
next  
```  
  
  
