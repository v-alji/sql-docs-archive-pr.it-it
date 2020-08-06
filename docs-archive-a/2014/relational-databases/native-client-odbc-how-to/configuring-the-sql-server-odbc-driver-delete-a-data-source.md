---
title: Eliminare un'origine dati (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: 910e3e16-7b91-49d8-80bb-b4243926afaa
author: rothja
ms.author: jroth
ms.openlocfilehash: 6e8acd6414b39b317ff0fcfe1b7b9fbab38ae0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626749"
---
# <a name="delete-a-data-source-odbc"></a><span data-ttu-id="8316f-102">Eliminare un'origine dati (ODBC)</span><span class="sxs-lookup"><span data-stu-id="8316f-102">Delete a Data Source (ODBC)</span></span>
  <span data-ttu-id="8316f-103">È possibile eliminare un'origine dati tramite l'amministratore ODBC, a livello di codice (tramite [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) oppure eliminando un file (se il nome dell'origine dati è un file).</span><span class="sxs-lookup"><span data-stu-id="8316f-103">You can delete a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by deleting a file (if a file data source name).</span></span>  
  
### <a name="to-delete-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="8316f-104">Per eliminare un'origine dati tramite Amministratore ODBC.</span><span class="sxs-lookup"><span data-stu-id="8316f-104">To delete a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="8316f-105">Nel **Pannello di controllo**aprire **strumenti di amministrazione**, quindi fare doppio clic su **origini dati (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="8316f-105">In **Control Panel**, open **Administrative Tools**, and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="8316f-106">In alternativa, è possibile eseguire odbcad32.exe dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="8316f-106">Alternatively, you can run odbcad32.exe from the command prompt.</span></span>  
  
2.  <span data-ttu-id="8316f-107">Fare clic sulla scheda DSN **utente**, **DSN di sistema**o **DSN su file** .</span><span class="sxs-lookup"><span data-stu-id="8316f-107">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="8316f-108">Fare clic sull'origine dati da eliminare.</span><span class="sxs-lookup"><span data-stu-id="8316f-108">Click the data source to delete.</span></span>  
  
4.  <span data-ttu-id="8316f-109">Fare clic su **Rimuovi**, quindi confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="8316f-109">Click **Remove**, and then confirm the deletion.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8316f-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="8316f-110">Example</span></span>  
 <span data-ttu-id="8316f-111">Per eliminare un'origine dati a livello di codice, chiamare [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) usando ODBC_REMOVE_DSN o ODBC_REMOVE_SYS_DSN come secondo parametro.</span><span class="sxs-lookup"><span data-stu-id="8316f-111">To programmatically delete a data source, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) using either ODBC_REMOVE_DSN or ODBC_REMOVE_SYS_DSN as the second parameter.</span></span>  
  
 <span data-ttu-id="8316f-112">Nell'esempio seguente viene illustrato come è possibile eliminare un'origine dati a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="8316f-112">The following sample shows how you can programmatically delete a data source.</span></span>  
  
```  
// remove_odbc_data_source.cpp  
// compile with: ODBCCP32.lib user32.lib  
#include <iostream>  
#include <windows.h>  
#include <odbcinst.h>  
  
int main() {   
   LPCSTR provider = "SQL Server";   // Windows SQL Server Driver  
   LPCSTR provider = "SQL Server";   // Windows SQL Server driver  
   LPCSTR provider2 = "SQL Server Native Client 11.0";   // SQL Server 2012 Native Client driver  
   LPCSTR dsnname = "DSN=data2";  
   BOOL retval = SQLConfigDataSource(NULL, ODBC_REMOVE_DSN, provider, dsnname);  
   std::cout << retval;   // 1 if successful  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8316f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8316f-113">See Also</span></span>  
 [<span data-ttu-id="8316f-114">Configurazione delle procedure del driver ODBC di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8316f-114">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
