---
title: ICorDebugModule::IsInMemory メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 223989d883c421be228fb3d6a608643a5246c060
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763701"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="f2cc9-102">ICorDebugModule::IsInMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="f2cc9-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="f2cc9-103">このモジュールは、メモリ内にのみ存在するかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f2cc9-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cc9-104">構文</span><span class="sxs-lookup"><span data-stu-id="f2cc9-104">Syntax</span></span>  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2cc9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f2cc9-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="f2cc9-106">[out]`true`メモリ内でのみこのモジュールが存在する場合は、それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="f2cc9-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2cc9-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2cc9-107">Remarks</span></span>  
 <span data-ttu-id="f2cc9-108">共通言語ランタイム (CLR) は、生のバイト ストリームからのモジュールの読み込みをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f2cc9-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="f2cc9-109">このようなモジュールが呼び出されます*メモリ内モジュール*ディスク上に存在しないとします。</span><span class="sxs-lookup"><span data-stu-id="f2cc9-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2cc9-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f2cc9-110">Requirements</span></span>  
 <span data-ttu-id="f2cc9-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2cc9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2cc9-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2cc9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2cc9-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2cc9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2cc9-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2cc9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2cc9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2cc9-115">See also</span></span>
