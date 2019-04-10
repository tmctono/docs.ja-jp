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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6594bb72ce9cd2fbfa9cdafebc152a90618b810
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193084"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="6aed8-102">ICorDebugILFrame4::GetLocalVariableEx メソッド</span><span class="sxs-lookup"><span data-stu-id="6aed8-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="6aed8-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="6aed8-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="6aed8-104">この中間言語 (IL) スタック フレーム内の指定されたローカル変数の値を取得して、オプションでプロファイラー ReJIT インストルメンテーションに追加された変数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6aed8-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aed8-105">構文</span><span class="sxs-lookup"><span data-stu-id="6aed8-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aed8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6aed8-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="6aed8-107">[in][ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)プロファイラー ReJIT インストルメンテーションに追加された変数がフレーム内に含まれるかどうかを指定する列挙型メンバー。</span><span class="sxs-lookup"><span data-stu-id="6aed8-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="6aed8-108">[in] IL スタック フレーム内のローカル変数のインデックス。</span><span class="sxs-lookup"><span data-stu-id="6aed8-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="6aed8-109">[out]取得した値を表す"ICorDebugValue"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6aed8-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6aed8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="6aed8-110">Remarks</span></span>  
 <span data-ttu-id="6aed8-111">このメソッドは、 [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)メソッド、点を除いてことが必要に応じてプロファイラー ReJIT インストルメンテーションに追加された変数にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6aed8-111">This method is similar to the [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="6aed8-112">このメソッドを呼び出すと、`flags`の値`ILCODE_ORIGINAL_IL`呼び出しと同じですが[GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)ローカル変数を追加、メソッドがインストルメント化されている場合これらの変数にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6aed8-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> `ILCODE_REJIT_IL` <span data-ttu-id="6aed8-113">により、デバッガーは、プロファイラー ReJIT インストルメンテーションに追加されたローカル変数にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6aed8-113">allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="6aed8-114">IL がインストルメントされていない場合、メソッドは `E_INVALIDARG` を返します。</span><span class="sxs-lookup"><span data-stu-id="6aed8-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aed8-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="6aed8-115">Requirements</span></span>  
 <span data-ttu-id="6aed8-116">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6aed8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aed8-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6aed8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6aed8-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6aed8-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6aed8-119">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="6aed8-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6aed8-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="6aed8-120">See also</span></span>

- [<span data-ttu-id="6aed8-121">ICorDebugILFrame4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6aed8-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="6aed8-122">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="6aed8-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6aed8-123">ReJIT:ハウツー ガイド</span><span class="sxs-lookup"><span data-stu-id="6aed8-123">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
