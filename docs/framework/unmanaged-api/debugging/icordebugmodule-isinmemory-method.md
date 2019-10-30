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
ms.openlocfilehash: 1384acff4ea3d1aa820b065cd2c56f649f0cbdbb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127924"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="2c042-102">ICorDebugModule::IsInMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="2c042-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="2c042-103">このモジュールがメモリ内にのみ存在するかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="2c042-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c042-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c042-104">Syntax</span></span>  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c042-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c042-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="2c042-106">[out] このモジュールがメモリ内にのみ存在する場合は `true`。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="2c042-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c042-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2c042-107">Remarks</span></span>  
 <span data-ttu-id="2c042-108">共通言語ランタイム (CLR) では、未加工のバイトストリームからのモジュールの読み込みがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2c042-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="2c042-109">このようなモジュールは*メモリ内モジュール*と呼ばれ、ディスク上には存在しません。</span><span class="sxs-lookup"><span data-stu-id="2c042-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c042-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="2c042-110">Requirements</span></span>  
 <span data-ttu-id="2c042-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c042-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c042-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c042-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c042-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c042-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c042-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c042-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c042-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c042-115">See also</span></span>
