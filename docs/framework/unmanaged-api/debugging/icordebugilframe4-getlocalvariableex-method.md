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
ms.openlocfilehash: 017c14e9170087f3c3c9de64f50d165fc91aa297
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782415"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a><span data-ttu-id="91f44-102">ICorDebugILFrame4::GetLocalVariableEx メソッド</span><span class="sxs-lookup"><span data-stu-id="91f44-102">ICorDebugILFrame4::GetLocalVariableEx Method</span></span>
<span data-ttu-id="91f44-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="91f44-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="91f44-104">この中間言語 (IL) スタック フレーム内の指定されたローカル変数の値を取得して、オプションでプロファイラー ReJIT インストルメンテーションに追加された変数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="91f44-104">Gets the value of the specified local variable in this intermediate language (IL) stack frame, and optionally accesses a variable added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f44-105">構文</span><span class="sxs-lookup"><span data-stu-id="91f44-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91f44-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91f44-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="91f44-107">からプロファイラー ReJIT インストルメンテーションに追加された変数がフレームに含まれるかどうかを指定する[Ilcodekind](ilcodekind-enumeration.md)列挙体のメンバー。</span><span class="sxs-lookup"><span data-stu-id="91f44-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether a variable added in profiler ReJIT instrumentation is included in the frame.</span></span>  
  
 `dwIndex`  
 <span data-ttu-id="91f44-108">[in] IL スタック フレーム内のローカル変数のインデックス。</span><span class="sxs-lookup"><span data-stu-id="91f44-108">[in] The index of the local variable in the IL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="91f44-109">入出力取得された値を表す "ICorDebugValue" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="91f44-109">[out] A pointer to the address of an "ICorDebugValue" object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91f44-110">コメント</span><span class="sxs-lookup"><span data-stu-id="91f44-110">Remarks</span></span>  
 <span data-ttu-id="91f44-111">このメソッドは、オプションでプロファイラー ReJIT インストルメンテーションに追加された変数にアクセスする点を除いて、 [Getlocalvariable](icordebugilframe-getlocalvariable-method.md)メソッドに似ています。</span><span class="sxs-lookup"><span data-stu-id="91f44-111">This method is similar to the [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) method, except that it optionally accesses a variable added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="91f44-112">値を指定し`flags`てこのメソッドを呼び出すことは、[getlocalvariable](icordebugilframe-getlocalvariable-method.md)を呼び出すことと同じです。メソッドが追加のローカル変数でインストルメント化されている場合、これらの変数にはアクセスできませ`ILCODE_ORIGINAL_IL`ん。</span><span class="sxs-lookup"><span data-stu-id="91f44-112">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetLocalVariable](icordebugilframe-getlocalvariable-method.md); if the method is instrumented with additional local variables, those variables cannot be accessed.</span></span> <span data-ttu-id="91f44-113">`ILCODE_REJIT_IL` は、デバッガーがプロファイラー ReJIT インストルメンテーションに追加されたローカル変数にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="91f44-113">`ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="91f44-114">IL がインストルメントされていない場合、メソッドは `E_INVALIDARG` を返します。</span><span class="sxs-lookup"><span data-stu-id="91f44-114">If the IL is not instrumented, the method returns `E_INVALIDARG`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91f44-115">要件</span><span class="sxs-lookup"><span data-stu-id="91f44-115">Requirements</span></span>  
 <span data-ttu-id="91f44-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91f44-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91f44-117">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91f44-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91f44-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91f44-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91f44-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91f44-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f44-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="91f44-120">See also</span></span>

- [<span data-ttu-id="91f44-121">ICorDebugILFrame4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="91f44-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="91f44-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="91f44-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="91f44-123">ReJIT: ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="91f44-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
