---
title: ICorDebugChain::EnumerateFrames メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc647805fcb7d8354a2540ac9424dc7155853444
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745036"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="e7f30-102">ICorDebugChain::EnumerateFrames メソッド</span><span class="sxs-lookup"><span data-stu-id="e7f30-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="e7f30-103">最新のフレームを開始する、チェーン内のすべてのマネージ スタック フレームを含む列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="e7f30-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f30-104">構文</span><span class="sxs-lookup"><span data-stu-id="e7f30-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7f30-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7f30-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="e7f30-106">[out]スタック フレームの列挙子である ICorDebugFrameEnum オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e7f30-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7f30-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e7f30-107">Remarks</span></span>  
 <span data-ttu-id="e7f30-108">チェーンは、スレッドの物理呼び出し履歴を表します。</span><span class="sxs-lookup"><span data-stu-id="e7f30-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="e7f30-109">`EnumerateFrames`メソッドは、管理対象のチェーンに対してのみ呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7f30-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="e7f30-110">デバッグ API では、非管理対象のチェーンに含まれているフレームを取得するメソッドが提供されません。</span><span class="sxs-lookup"><span data-stu-id="e7f30-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="e7f30-111">デバッガーは、この情報を取得するのにその他の手段を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7f30-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7f30-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="e7f30-112">Requirements</span></span>  
 <span data-ttu-id="e7f30-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7f30-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7f30-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7f30-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7f30-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7f30-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7f30-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7f30-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
