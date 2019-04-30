---
title: ICorDebugILFrame4::GetCodeEx メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d61981d26d21ec1e5e24093817586ebf45b129e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988482"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="55eb4-102">ICorDebugILFrame4::GetCodeEx メソッド</span><span class="sxs-lookup"><span data-stu-id="55eb4-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="55eb4-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="55eb4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="55eb4-104">このスタック フレームが実行中のコードに対するポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="55eb4-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55eb4-105">構文</span><span class="sxs-lookup"><span data-stu-id="55eb4-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55eb4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="55eb4-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="55eb4-107">[in][ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)フレームでプロファイラーの ReJIT 要求によって定義された中間言語 (IL) が含まれているかどうかを指定する列挙型メンバー。</span><span class="sxs-lookup"><span data-stu-id="55eb4-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="55eb4-108">[out]このスタック フレームが実行中のコードを表す"ICorDebugCode"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="55eb4-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55eb4-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="55eb4-109">Remarks</span></span>  
 <span data-ttu-id="55eb4-110">このメソッドは、 [icordebugframe::getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)メソッド、必要に応じてアクセスするコード プロファイラーの ReJIT 要求によって定義されている点が異なります。</span><span class="sxs-lookup"><span data-stu-id="55eb4-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="55eb4-111">このメソッドを呼び出すと、`flags`の値`ILCODE_ORIGINAL_IL`呼び出しと同じですが[GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)メソッドがインストルメント化されている場合その IL はアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="55eb4-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="55eb4-112">`ILCODE_REJIT_IL` を使用するとデバッガーは、プロファイラーの ReJIT 要求で定義された IL にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="55eb4-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="55eb4-113">IL がインストルメント化されない場合`ppCode`は**null**、メソッドを返しますと`S_OK`します。</span><span class="sxs-lookup"><span data-stu-id="55eb4-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55eb4-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="55eb4-114">Requirements</span></span>  
 <span data-ttu-id="55eb4-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55eb4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55eb4-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55eb4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55eb4-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55eb4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55eb4-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55eb4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55eb4-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="55eb4-119">See also</span></span>

- [<span data-ttu-id="55eb4-120">ICorDebugILFrame4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55eb4-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="55eb4-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="55eb4-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="55eb4-122">ReJIT:ハウツー ガイド</span><span class="sxs-lookup"><span data-stu-id="55eb4-122">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
