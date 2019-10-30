---
title: ICorDebugProcess5::EnableNGENPolicy メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
ms.openlocfilehash: 583819e8e7ab16a8ac1ce72892f4353e3043ce3d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129695"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="1a1d8-102">ICorDebugProcess5::EnableNGENPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="1a1d8-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="1a1d8-103">マネージデバッガーで実行中にアプリケーションがネイティブイメージを読み込む方法を決定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="1a1d8-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a1d8-104">構文</span><span class="sxs-lookup"><span data-stu-id="1a1d8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a1d8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1a1d8-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="1a1d8-106">からマネージデバッガーで実行中にアプリケーションがネイティブイメージを読み込む方法を決定する[Cordebugngenpolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)定数。</span><span class="sxs-lookup"><span data-stu-id="1a1d8-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a1d8-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1a1d8-107">Remarks</span></span>  
 <span data-ttu-id="1a1d8-108">ポリシーが正常に設定されている場合、メソッドは `S_OK`を返します。</span><span class="sxs-lookup"><span data-stu-id="1a1d8-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="1a1d8-109">`ePolicy` が[Cordebugngenpolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)によって定義された列挙値の範囲外にある場合、メソッドは `E_INVALIDARG` を返し、メソッドの呼び出しは無効になります。</span><span class="sxs-lookup"><span data-stu-id="1a1d8-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="1a1d8-110">ネイティブイメージジェネレーター (Ngen.exe) のポリシーを更新できない場合、メソッドは `E_FAIL`を返します。</span><span class="sxs-lookup"><span data-stu-id="1a1d8-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="1a1d8-111">`ICorDebugProcess5::EnableNGenPolicy` メソッドは、プロセスの有効期間中はいつでも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="1a1d8-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="1a1d8-112">ポリシーは、ポリシーが設定された後に読み込まれるすべてのモジュールに対して有効です。</span><span class="sxs-lookup"><span data-stu-id="1a1d8-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a1d8-113">［要件］</span><span class="sxs-lookup"><span data-stu-id="1a1d8-113">Requirements</span></span>  
 <span data-ttu-id="1a1d8-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a1d8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a1d8-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a1d8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a1d8-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a1d8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a1d8-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a1d8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a1d8-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a1d8-118">See also</span></span>

- [<span data-ttu-id="1a1d8-119">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a1d8-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="1a1d8-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a1d8-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1a1d8-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="1a1d8-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
