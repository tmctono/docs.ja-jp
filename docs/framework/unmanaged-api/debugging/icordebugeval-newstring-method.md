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
ms.openlocfilehash: db609bdee7975b6c067271f99529e2cf2240f720
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480183"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="0d5fd-102">ICorDebugEval::NewString メソッド</span><span class="sxs-lookup"><span data-stu-id="0d5fd-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="0d5fd-103">指定した内容を含む新しい文字列インスタンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d5fd-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d5fd-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d5fd-104">Syntax</span></span>  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d5fd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d5fd-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="0d5fd-106">[in]文字列の内容へのポインター。</span><span class="sxs-lookup"><span data-stu-id="0d5fd-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d5fd-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0d5fd-107">Remarks</span></span>  
 <span data-ttu-id="0d5fd-108">文字列が現在のスレッドが実行されているアプリケーション ドメインで常に作成されます。</span><span class="sxs-lookup"><span data-stu-id="0d5fd-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d5fd-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0d5fd-109">Requirements</span></span>  
 <span data-ttu-id="0d5fd-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d5fd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d5fd-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d5fd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d5fd-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d5fd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d5fd-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d5fd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
