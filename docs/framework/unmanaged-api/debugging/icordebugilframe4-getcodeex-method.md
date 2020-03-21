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
ms.openlocfilehash: ef2e4bc0caddd6b13c8dbe8edb59e0673519421b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178793"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="5fb7a-102">ICorDebugILFrame4::GetCodeEx メソッド</span><span class="sxs-lookup"><span data-stu-id="5fb7a-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="5fb7a-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="5fb7a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="5fb7a-104">このスタック フレームが実行中のコードに対するポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5fb7a-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fb7a-105">構文</span><span class="sxs-lookup"><span data-stu-id="5fb7a-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fb7a-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5fb7a-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="5fb7a-107">[in]プロファイラーの ReJIT 要求によって定義された中間言語 (IL) がフレームに含まれるかどうかを指定する[ILCodeKind](ilcodekind-enumeration.md)列挙メンバー。</span><span class="sxs-lookup"><span data-stu-id="5fb7a-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="5fb7a-108">[アウト]このスタック フレームが実行しているコードを表す "ICorDebugCode" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5fb7a-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fb7a-109">解説</span><span class="sxs-lookup"><span data-stu-id="5fb7a-109">Remarks</span></span>  
 <span data-ttu-id="5fb7a-110">このメソッドは、プロファイラーの ReJIT 要求によって定義されたコードにオプションでアクセスする点を除いて[、ICorDebugFrame::GetCode](icordebugframe-getcode-method.md)メソッドに似ています。</span><span class="sxs-lookup"><span data-stu-id="5fb7a-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="5fb7a-111">の値を指定して`flags`このメソッド`ILCODE_ORIGINAL_IL`を呼び出すことは[、GetCode](icordebugframe-getcode-method.md)を呼び出すことと同じです。メソッドがインストルメント化されている場合、IL はアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="5fb7a-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="5fb7a-112">`ILCODE_REJIT_IL` を使用するとデバッガーは、プロファイラーの ReJIT 要求で定義された IL にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5fb7a-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="5fb7a-113">IL がインストルメント化`ppCode`されていない場合は**null**になり`S_OK`、メソッドはを返します。</span><span class="sxs-lookup"><span data-stu-id="5fb7a-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fb7a-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="5fb7a-114">Requirements</span></span>  
 <span data-ttu-id="5fb7a-115">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fb7a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fb7a-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fb7a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fb7a-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fb7a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fb7a-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fb7a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb7a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fb7a-119">See also</span></span>

- [<span data-ttu-id="5fb7a-120">ICorDebugILFrame4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5fb7a-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="5fb7a-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5fb7a-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5fb7a-122">ReJIT:ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="5fb7a-122">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
