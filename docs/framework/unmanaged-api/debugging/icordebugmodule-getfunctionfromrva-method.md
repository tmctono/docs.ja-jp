---
title: ICorDebugModule::GetFunctionFromRVA メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromRVA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromRVA
helpviewer_keywords:
- GetFunctionFromRVA method [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromRVA method [.NET Framework debugging]
ms.assetid: f5a34517-2422-484f-be89-2ce0b4bce195
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: edd9407f05e30eb420e83fb042c2412e99b0a022
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770660"
---
# <a name="icordebugmodulegetfunctionfromrva-method"></a><span data-ttu-id="de108-102">ICorDebugModule::GetFunctionFromRVA メソッド</span><span class="sxs-lookup"><span data-stu-id="de108-102">ICorDebugModule::GetFunctionFromRVA Method</span></span>
<span data-ttu-id="de108-103">このメソッドは、.NET Framework の現在のバージョンで実装されていません。</span><span class="sxs-lookup"><span data-stu-id="de108-103">This method has not been implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de108-104">構文</span><span class="sxs-lookup"><span data-stu-id="de108-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromRVA(  
    [in]  CORDB_ADDRESS      rva,  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="de108-105">必要条件</span><span class="sxs-lookup"><span data-stu-id="de108-105">Requirements</span></span>  
 <span data-ttu-id="de108-106">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de108-106">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de108-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="de108-107">See also</span></span>
