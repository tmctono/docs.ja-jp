---
title: ICorDebugILFrame4::EnumerateLocalVariablesEx メソッド
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
ms.openlocfilehash: 341a86f4c1c8367f979e193a6284bf89f1b03ca0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178802"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="9acc0-102">ICorDebugILFrame4::EnumerateLocalVariablesEx メソッド</span><span class="sxs-lookup"><span data-stu-id="9acc0-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="9acc0-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="9acc0-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="9acc0-104">フレームのローカル変数の列挙子を取得し、プロファイラー ReJIT インストルメンテーションに追加される変数も含みます。</span><span class="sxs-lookup"><span data-stu-id="9acc0-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9acc0-105">構文</span><span class="sxs-lookup"><span data-stu-id="9acc0-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9acc0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9acc0-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="9acc0-107">[in]プロファイラー ReJIT インストルメンテーションで追加された変数をフレームに含めるかどうかを指定する[ILCodeKind](ilcodekind-enumeration.md)列挙メンバー。</span><span class="sxs-lookup"><span data-stu-id="9acc0-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="9acc0-108">[アウト]このフレーム内のローカル変数の列挙子である "ICorDebugValueEnum" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9acc0-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9acc0-109">解説</span><span class="sxs-lookup"><span data-stu-id="9acc0-109">Remarks</span></span>  
 <span data-ttu-id="9acc0-110">このメソッドは、オプションでプロファイラー ReJIT インストルメンテーションで追加された変数にアクセスする点を除いて、[列挙LocalVariables](icordebugilframe-enumeratelocalvariables-method.md)メソッドに似ています。</span><span class="sxs-lookup"><span data-stu-id="9acc0-110">This method is similar to the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="9acc0-111">に`flags``ILCODE_ORIGINAL_IL`設定することは、呼び出し元[と](icordebugilframe-enumeratelocalvariables-method.md)同じです。</span><span class="sxs-lookup"><span data-stu-id="9acc0-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="9acc0-112">`flags` を `ILCODE_REJIT_IL` に設定することにより、デバッガは プロファイラー ReJIT インストルメンテーションに追加されるローカル変数にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="9acc0-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="9acc0-113">中間言語 (IL) がインストルメント化されていない場合は、列挙子は空になり、メソッドは `S_OK` を返します。</span><span class="sxs-lookup"><span data-stu-id="9acc0-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="9acc0-114">実行中のメソッドにあるすべてのローカル変数が列挙子に含まれない場合がありますが、それは一部のローカル変数が非アクティブである可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="9acc0-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9acc0-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="9acc0-115">Requirements</span></span>  
 <span data-ttu-id="9acc0-116">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9acc0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9acc0-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9acc0-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9acc0-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9acc0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9acc0-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9acc0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9acc0-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="9acc0-120">See also</span></span>

- [<span data-ttu-id="9acc0-121">ICorDebugILFrame4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9acc0-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="9acc0-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9acc0-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9acc0-123">ReJIT:ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="9acc0-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
