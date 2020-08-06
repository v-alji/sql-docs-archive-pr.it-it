---
title: Creare le credenziali - Eseguire l'autenticazione nel servizio di archiviazione Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backuptourl.createcred.f1
ms.assetid: 0622619d-27c5-4ff0-83e5-cde31648c27a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: afdbf2647c79e07cf3f190ec6710eeb6b7718f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723944"
---
# <a name="create-credential---authenticate-to-azure-storage"></a><span data-ttu-id="3eaa1-102">Creare le credenziali - Eseguire l'autenticazione nel servizio di archiviazione Azure</span><span class="sxs-lookup"><span data-stu-id="3eaa1-102">Create Credential - Authenticate to Azure Storage</span></span>
  <span data-ttu-id="3eaa1-103">Usare la finestra di dialogo **Backup su URL - Creazione credenziali** per creare nuove credenziali SQL.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-103">Use the **Backup to URL - Create Credential** dialog box to create a new SQL Credential.</span></span>  
  
 <span data-ttu-id="3eaa1-104">Quando si usa questa finestra di dialogo per creare le credenziali, è necessario specificare un certificato di gestione di Azure aggiunto all'archivio certificati locale o un profilo di pubblicazione scaricato nel computer per convalidare la sottoscrizione e le informazioni sull'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-104">When using this dialog box to create a credential, you must provide an Azure Management Certificate added to the local certificate store or a publishing profile downloaded to your computer to validate the subscription and the storage account information.</span></span>  
  
 <span data-ttu-id="3eaa1-105">**Credenziali SQL**</span><span class="sxs-lookup"><span data-stu-id="3eaa1-105">**SQL Credential**</span></span>  
 <span data-ttu-id="3eaa1-106">Specificare il nome delle credenziali SQL che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-106">Specify the name of the SQL Credential you want to create.</span></span>  
  
## <a name="azure-credentials"></a><span data-ttu-id="3eaa1-107">Credenziali Azure</span><span class="sxs-lookup"><span data-stu-id="3eaa1-107">Azure Credentials</span></span>  
 <span data-ttu-id="3eaa1-108">**Certificato di gestione**</span><span class="sxs-lookup"><span data-stu-id="3eaa1-108">**Management Certificate**</span></span>  
 <span data-ttu-id="3eaa1-109">Usare questa opzione per specificare un certificato dall'archivio certificati locale corrispondente al certificato di gestione di Azure.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-109">Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span> <span data-ttu-id="3eaa1-110">Per altre informazioni sul certificato di gestione di Azure, vedere [Creare e caricare un certificato di gestione per Azure](https://go.microsoft.com/fwlink/?LinkId=320781).</span><span class="sxs-lookup"><span data-stu-id="3eaa1-110">For more information on Azure management certificate, see [Create and Upload a Management Certificate for Azure](https://go.microsoft.com/fwlink/?LinkId=320781).</span></span>  
  
 <span data-ttu-id="3eaa1-111">**Sottoscrizione**</span><span class="sxs-lookup"><span data-stu-id="3eaa1-111">**Subscription**</span></span>  
 <span data-ttu-id="3eaa1-112">Selezionare, digitare o incollare l'ID sottoscrizione di Azure corrispondente al certificato di gestione dall'archivio certificati locale.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-112">Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store.</span></span>  
  
 <span data-ttu-id="3eaa1-113">**Profilo di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="3eaa1-113">**Publishing Profile**</span></span>  
 <span data-ttu-id="3eaa1-114">Utilizzare questa opzione se si dispone di un profilo di pubblicazione scaricato nel computer.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-114">Use this option if you have a publishing profile downloaded to your computer.</span></span> <span data-ttu-id="3eaa1-115">Se si utilizza questa opzione, l'ID sottoscrizione e il certificato vengono inseriti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-115">If you use this option, the subscription ID, and the certificate are auto populated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="3eaa1-116">SQL Server supporta attualmente la versione del profilo di pubblicazione 2.0.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-116">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="3eaa1-117">Per scaricare la versione supportata del profilo di pubblicazione, vedere [Download del profilo di pubblicazione 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="3eaa1-117">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
## <a name="storage-account"></a><span data-ttu-id="3eaa1-118">Account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="3eaa1-118">Storage Account</span></span>  
 <span data-ttu-id="3eaa1-119">Selezionare l'account di archiviazione da utilizzare per archiviare i file di backup.</span><span class="sxs-lookup"><span data-stu-id="3eaa1-119">Select the storage account you want to use to store the backup files on.</span></span>  
  
  
