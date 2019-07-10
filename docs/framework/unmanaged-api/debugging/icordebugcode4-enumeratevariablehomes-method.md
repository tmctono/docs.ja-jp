---
title: ICorDebugCode4::EnumerateVariableHomes メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e6acdf6996f437c85b629b0af886287b1aef03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748559"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="8826e-102">ICorDebugCode4::EnumerateVariableHomes メソッド</span><span class="sxs-lookup"><span data-stu-id="8826e-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="8826e-103">ローカル変数と引数を関数内の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="8826e-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8826e-104">構文</span><span class="sxs-lookup"><span data-stu-id="8826e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8826e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8826e-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="8826e-106">アドレスへのポインター、 [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)インターフェイス オブジェクトは、ローカル変数と関数の引数の列挙子です。</span><span class="sxs-lookup"><span data-stu-id="8826e-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8826e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8826e-107">Remarks</span></span>  
 <span data-ttu-id="8826e-108">[ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)インターフェイス オブジェクトを列挙できるようにする"ICorDebugEnum"インターフェイスから派生した標準の列挙子は、 [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8826e-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="8826e-109">コレクションが複数あります[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)関数は、さまざまなポイントで異なるホームがある場合は、同じスロットまたは引数のインデックスのオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="8826e-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8826e-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="8826e-110">Requirements</span></span>  
 <span data-ttu-id="8826e-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8826e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8826e-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8826e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8826e-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8826e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8826e-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8826e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8826e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="8826e-115">See also</span></span>

- [<span data-ttu-id="8826e-116">ICorDebugCode4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8826e-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [<span data-ttu-id="8826e-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8826e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
