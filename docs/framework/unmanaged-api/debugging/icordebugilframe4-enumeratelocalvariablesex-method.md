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
ms.openlocfilehash: afeec3df03fc2b122ca8deb8123b79314b5e3837
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782427"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="4726e-102">ICorDebugILFrame4::EnumerateLocalVariablesEx メソッド</span><span class="sxs-lookup"><span data-stu-id="4726e-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="4726e-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="4726e-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4726e-104">フレームのローカル変数の列挙子を取得し、プロファイラー ReJIT インストルメンテーションに追加される変数も含みます。</span><span class="sxs-lookup"><span data-stu-id="4726e-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4726e-105">構文</span><span class="sxs-lookup"><span data-stu-id="4726e-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4726e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4726e-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="4726e-107">からプロファイラー ReJIT インストルメンテーションに追加された変数がフレームに含まれるかどうかを指定する[Ilcodekind](ilcodekind-enumeration.md)列挙型のメンバー。</span><span class="sxs-lookup"><span data-stu-id="4726e-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="4726e-108">入出力このフレーム内のローカル変数の列挙子である "テキスト" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="4726e-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4726e-109">コメント</span><span class="sxs-lookup"><span data-stu-id="4726e-109">Remarks</span></span>  
 <span data-ttu-id="4726e-110">このメソッドは、 [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md)メソッドに似ていますが、プロファイラー rejit インストルメンテーションに追加された変数にオプションでアクセスする点が異なります。</span><span class="sxs-lookup"><span data-stu-id="4726e-110">This method is similar to the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="4726e-111">`flags` を `ILCODE_ORIGINAL_IL` に設定することは、 [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md)を呼び出した場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="4726e-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="4726e-112">`flags` を `ILCODE_REJIT_IL` に設定することにより、デバッガは プロファイラー ReJIT インストルメンテーションに追加されるローカル変数にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="4726e-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="4726e-113">中間言語 (IL) がインストルメント化されていない場合は、列挙子は空になり、メソッドは `S_OK` を返します。</span><span class="sxs-lookup"><span data-stu-id="4726e-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="4726e-114">実行中のメソッドにあるすべてのローカル変数が列挙子に含まれない場合がありますが、それは一部のローカル変数が非アクティブである可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="4726e-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4726e-115">要件</span><span class="sxs-lookup"><span data-stu-id="4726e-115">Requirements</span></span>  
 <span data-ttu-id="4726e-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4726e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4726e-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4726e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4726e-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4726e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4726e-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4726e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4726e-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4726e-120">See also</span></span>

- [<span data-ttu-id="4726e-121">ICorDebugILFrame4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4726e-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="4726e-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4726e-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4726e-123">ReJIT: ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="4726e-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
