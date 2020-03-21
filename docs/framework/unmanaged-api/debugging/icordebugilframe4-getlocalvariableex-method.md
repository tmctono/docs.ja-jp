---
title: ICorDebugILFrame4::GetLocalVariableEx メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
ms.openlocfilehash: ee263e8c49cd6da7278bd2299557336629720d2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178780"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="feb6c-102">ICorDebugILFrame4::GetLocalVariableEx メソッド</span><span class="sxs-lookup"><span data-stu-id="feb6c-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="feb6c-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="feb6c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="feb6c-104">この中間言語 (IL) スタック フレーム内の指定されたローカル変数の値を取得して、オプションでプロファイラー ReJIT インストルメンテーションに追加された変数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="feb6c-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feb6c-105">構文</span><span class="sxs-lookup"><span data-stu-id="feb6c-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,
   [in] DWORD dwIndex,
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="feb6c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="feb6c-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="feb6c-107">[in]プロファイラー ReJIT インストルメンテーションに追加された変数をフレームに含めるかどうかを指定する[ILCodeKind](ilcodekind-enumeration.md)列挙メンバー。</span><span class="sxs-lookup"><span data-stu-id="feb6c-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="feb6c-108">[in] IL スタック フレーム内のローカル変数のインデックス。</span><span class="sxs-lookup"><span data-stu-id="feb6c-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="feb6c-109">[アウト]取得した値を表す "ICorDebugValue" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="feb6c-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="feb6c-110">解説</span><span class="sxs-lookup"><span data-stu-id="feb6c-110">Remarks</span></span>  
 <span data-ttu-id="feb6c-111">このメソッドは、オプションでプロファイラー ReJIT インストルメンテーションで追加された変数にアクセスする点を除いて[、GetLocalVariable](icordebugilframe-getlocalvariable-method.md)メソッドに似ています。</span><span class="sxs-lookup"><span data-stu-id="feb6c-111">This method is similar to the [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="feb6c-112">の値を指定して`flags`このメソッド`ILCODE_ORIGINAL_IL`を呼び出すことは[、GetLocalVariable](icordebugilframe-getlocalvariable-method.md)を呼び出すことと同じです。メソッドに追加のローカル変数がインストルメント化されている場合、これらの変数にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="feb6c-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="feb6c-113">`ILCODE_REJIT_IL` は、デバッガーがプロファイラー ReJIT インストルメンテーションに追加されたローカル変数にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="feb6c-113">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="feb6c-114">IL がインストルメントされていない場合、メソッドは `E_INVALIDARG` を返します。</span><span class="sxs-lookup"><span data-stu-id="feb6c-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feb6c-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="feb6c-115">Requirements</span></span>  
 <span data-ttu-id="feb6c-116">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feb6c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="feb6c-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="feb6c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="feb6c-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="feb6c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="feb6c-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="feb6c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feb6c-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="feb6c-120">See also</span></span>

- [<span data-ttu-id="feb6c-121">ICorDebugILFrame4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="feb6c-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="feb6c-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="feb6c-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="feb6c-123">ReJIT:ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="feb6c-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
