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
ms.openlocfilehash: aef28af3eff6aba03003f156b9226b61a8e72d5b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213752"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="b29b1-102">ICorDebugILFrame4::EnumerateLocalVariablesEx メソッド</span><span class="sxs-lookup"><span data-stu-id="b29b1-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="b29b1-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="b29b1-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b29b1-104">フレームのローカル変数の列挙子を取得し、プロファイラー ReJIT インストルメンテーションに追加される変数も含みます。</span><span class="sxs-lookup"><span data-stu-id="b29b1-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b29b1-105">構文</span><span class="sxs-lookup"><span data-stu-id="b29b1-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b29b1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b29b1-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="b29b1-107">からプロファイラー ReJIT インストルメンテーションに追加された変数がフレームに含まれるかどうかを指定する[Ilcodekind](ilcodekind-enumeration.md)列挙型のメンバー。</span><span class="sxs-lookup"><span data-stu-id="b29b1-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="b29b1-108">入出力このフレーム内のローカル変数の列挙子である "テキスト" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b29b1-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b29b1-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b29b1-109">Remarks</span></span>  
 <span data-ttu-id="b29b1-110">このメソッドは、 [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md)メソッドに似ていますが、プロファイラー rejit インストルメンテーションに追加された変数にオプションでアクセスする点が異なります。</span><span class="sxs-lookup"><span data-stu-id="b29b1-110">This method is similar to the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="b29b1-111">をに設定すること `flags` `ILCODE_ORIGINAL_IL` は、 [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md)を呼び出した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="b29b1-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="b29b1-112">`flags` を `ILCODE_REJIT_IL` に設定することにより、デバッガは プロファイラー ReJIT インストルメンテーションに追加されるローカル変数にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="b29b1-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="b29b1-113">中間言語 (IL) がインストルメント化されていない場合は、列挙子は空になり、メソッドは `S_OK` を返します。</span><span class="sxs-lookup"><span data-stu-id="b29b1-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="b29b1-114">実行中のメソッドにあるすべてのローカル変数が列挙子に含まれない場合がありますが、それは一部のローカル変数が非アクティブである可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="b29b1-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b29b1-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="b29b1-115">Requirements</span></span>  
 <span data-ttu-id="b29b1-116">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b29b1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b29b1-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b29b1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b29b1-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b29b1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b29b1-119">**.NET Framework のバージョン:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b29b1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b29b1-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="b29b1-120">See also</span></span>

- [<span data-ttu-id="b29b1-121">ICorDebugILFrame4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b29b1-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="b29b1-122">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="b29b1-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b29b1-123">ReJIT: ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="b29b1-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
