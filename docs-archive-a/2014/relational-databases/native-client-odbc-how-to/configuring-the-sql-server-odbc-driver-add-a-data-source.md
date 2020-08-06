---
title: Aggiungere un'origine dati (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: b4ac6f0e-8e6a-4b1a-9a7e-60e0a69b2180
author: rothja
ms.author: jroth
ms.openlocfilehash: 519990e9dd9d84f75c4efc6c76b910f0a359f52f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626751"
---
# <a name="add-a-data-source-odbc"></a><span data-ttu-id="baec5-102">Aggiungere un'origine dei dati (ODBC)</span><span class="sxs-lookup"><span data-stu-id="baec5-102">Add a Data Source (ODBC)</span></span>
  <span data-ttu-id="baec5-103">È possibile aggiungere un'origine dati tramite amministratore ODBC, a livello di codice (tramite [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) o creando un file.</span><span class="sxs-lookup"><span data-stu-id="baec5-103">You can add a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by creating a file.</span></span>  
  
### <a name="to-add-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="baec5-104">Per aggiungere un'origine dati tramite Amministratore ODBC.</span><span class="sxs-lookup"><span data-stu-id="baec5-104">To add a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="baec5-105">Dal **Pannello di controllo**accedere a **strumenti di amministrazione** e quindi a **origini dati (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="baec5-105">From the **Control Panel**, access **Administrative Tools** and then **Data Sources (ODBC)**.</span></span> <span data-ttu-id="baec5-106">In alternativa, è possibile richiamare odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="baec5-106">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="baec5-107">Fare clic sulla scheda **DSN utente**, **DSN di sistema**o **DSN su file** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="baec5-107">Click the **User DSN**, **System DSN**, or **File DSN** tab, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="baec5-108">Fare clic su **SQL Server**, quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="baec5-108">Click **SQL Server**, and then click **Finish**.</span></span>  
  
4.  <span data-ttu-id="baec5-109">Completare i passaggi della procedura guidata Crea una nuova origine dati per un server SQL.</span><span class="sxs-lookup"><span data-stu-id="baec5-109">Complete the Steps in the Create a New Data Source to SQL Server Wizard.</span></span>  
  
### <a name="to-add-a-data-source-programmatically"></a><span data-ttu-id="baec5-110">Per aggiungere un'origine dati a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="baec5-110">To add a data source programmatically</span></span>  
  
1.  <span data-ttu-id="baec5-111">Chiamare [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) con il secondo parametro impostato su ODBC_ADD_DSN o ODBC_ADD_SYS_DSN.</span><span class="sxs-lookup"><span data-stu-id="baec5-111">Call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) with the second parameter set to either ODBC_ADD_DSN or ODBC_ADD_SYS_DSN.</span></span>  
  
### <a name="to-add-a-file-data-source"></a><span data-ttu-id="baec5-112">Per aggiungere un 'origine dati file</span><span class="sxs-lookup"><span data-stu-id="baec5-112">To add a file data source</span></span>  
  
1.  <span data-ttu-id="baec5-113">Chiamare [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) con un parametro SAVEFILE = file_name nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="baec5-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) with a SAVEFILE=file_name parameter in the connect string.</span></span> <span data-ttu-id="baec5-114">Se la connessione viene eseguita correttamente, il driver ODBC crea un'origine dati file con i parametri di connessione nel percorso a cui punta il parametro SAVEFILE.</span><span class="sxs-lookup"><span data-stu-id="baec5-114">If the connect is successful, the ODBC driver creates a file data source with the connection parameters in the location pointed to by the SAVEFILE parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baec5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baec5-115">See Also</span></span>  
 [<span data-ttu-id="baec5-116">Configurazione delle procedure del driver ODBC di SQL Server</span><span class="sxs-lookup"><span data-stu-id="baec5-116">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
