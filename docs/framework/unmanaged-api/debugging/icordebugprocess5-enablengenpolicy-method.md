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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d8e848a7664e3573bd369addce2b2f5a8c91821
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481496"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="2cfee-102">ICorDebugProcess5::EnableNGENPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="2cfee-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="2cfee-103">アプリケーションがマネージ デバッガーで実行中にネイティブ イメージを読み込む方法を決定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2cfee-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cfee-104">構文</span><span class="sxs-lookup"><span data-stu-id="2cfee-104">Syntax</span></span>  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cfee-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2cfee-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="2cfee-106">[in]A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)アプリケーションがマネージ デバッガーで実行中にネイティブ イメージを読み込む方法を決定する定数。</span><span class="sxs-lookup"><span data-stu-id="2cfee-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cfee-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2cfee-107">Remarks</span></span>  
 <span data-ttu-id="2cfee-108">メソッドを返しますのかどうか、ポリシーが正常に設定されて、`S_OK`します。</span><span class="sxs-lookup"><span data-stu-id="2cfee-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="2cfee-109">場合`ePolicy`によって定義された列挙値の範囲外です[CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)、メソッドを返します`E_INVALIDARG`なり、メソッドの呼び出しに効力はありません。</span><span class="sxs-lookup"><span data-stu-id="2cfee-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="2cfee-110">ネイティブ イメージ ジェネレーター (Ngen.exe) のポリシーを更新できないかどうか、メソッドを返します`E_FAIL`します。</span><span class="sxs-lookup"><span data-stu-id="2cfee-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="2cfee-111">`ICorDebugProcess5::EnableNGenPolicy`メソッドは、プロセスの有効期間中にいつでも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2cfee-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="2cfee-112">ポリシーは、有効なポリシーを設定した後に読み込まれたモジュールの。</span><span class="sxs-lookup"><span data-stu-id="2cfee-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cfee-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="2cfee-113">Requirements</span></span>  
 <span data-ttu-id="2cfee-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cfee-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cfee-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cfee-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cfee-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cfee-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cfee-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cfee-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cfee-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2cfee-118">See also</span></span>
- [<span data-ttu-id="2cfee-119">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2cfee-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="2cfee-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2cfee-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2cfee-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2cfee-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
