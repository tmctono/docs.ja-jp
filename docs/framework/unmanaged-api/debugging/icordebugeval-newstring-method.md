---
title: ICorDebugEval::NewString メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50a18f435063b74b837dbfe9e4f1d986bb735039
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753347"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="dc62d-102">ICorDebugEval::NewString メソッド</span><span class="sxs-lookup"><span data-stu-id="dc62d-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="dc62d-103">指定した内容を含む新しい文字列インスタンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dc62d-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc62d-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc62d-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc62d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc62d-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="dc62d-106">[in]文字列の内容へのポインター。</span><span class="sxs-lookup"><span data-stu-id="dc62d-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc62d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="dc62d-107">Remarks</span></span>  
 <span data-ttu-id="dc62d-108">文字列が現在のスレッドが実行されているアプリケーション ドメインで常に作成されます。</span><span class="sxs-lookup"><span data-stu-id="dc62d-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc62d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc62d-109">Requirements</span></span>  
 <span data-ttu-id="dc62d-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc62d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc62d-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc62d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc62d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc62d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc62d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc62d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
