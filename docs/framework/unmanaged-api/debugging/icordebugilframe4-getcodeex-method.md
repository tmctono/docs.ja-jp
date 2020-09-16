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
ms.openlocfilehash: 06a0a4c788155d6fb909e4537b980f0ba740f21a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554815"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="fa5d7-102">ICorDebugILFrame4::GetCodeEx メソッド</span><span class="sxs-lookup"><span data-stu-id="fa5d7-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="fa5d7-103">[.NET Framework 4.5.2 以降のバージョンでのみでサポート]</span><span class="sxs-lookup"><span data-stu-id="fa5d7-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="fa5d7-104">このスタック フレームが実行中のコードに対するポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="fa5d7-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa5d7-105">構文</span><span class="sxs-lookup"><span data-stu-id="fa5d7-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa5d7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa5d7-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="fa5d7-107">からプロファイラーの ReJIT 要求によって定義された中間言語 (IL) がフレームに含まれるかどうかを指定する [Ilcodekind](ilcodekind-enumeration.md) 列挙体のメンバー。</span><span class="sxs-lookup"><span data-stu-id="fa5d7-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="fa5d7-108">入出力このスタックフレームが実行しているコードを表す "テキストコード" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fa5d7-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa5d7-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="fa5d7-109">Remarks</span></span>  
 <span data-ttu-id="fa5d7-110">このメソッドは、必要に応じて、プロファイラーの ReJIT 要求によって定義されたコードにアクセスする点を除いて、 [GetCode](icordebugframe-getcode-method.md) メソッドに似ています。</span><span class="sxs-lookup"><span data-stu-id="fa5d7-110">This method is similar to the [ICorDebugFrame::GetCode](icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="fa5d7-111">の値を指定してこのメソッドを呼び出す `flags` `ILCODE_ORIGINAL_IL` ことは、 [GetCode](icordebugframe-getcode-method.md)を呼び出すことと同じです。メソッドがインストルメント化されている場合、その IL にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fa5d7-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="fa5d7-112">`ILCODE_REJIT_IL` を使用するとデバッガーは、プロファイラーの ReJIT 要求で定義された IL にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fa5d7-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="fa5d7-113">IL がインストルメント化されていない場合、 `ppCode` は **null**であり、メソッドはを返し `S_OK` ます。</span><span class="sxs-lookup"><span data-stu-id="fa5d7-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa5d7-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="fa5d7-114">Requirements</span></span>  
 <span data-ttu-id="fa5d7-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa5d7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa5d7-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa5d7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa5d7-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa5d7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa5d7-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa5d7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa5d7-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa5d7-119">See also</span></span>

- [<span data-ttu-id="fa5d7-120">ICorDebugILFrame4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa5d7-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="fa5d7-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa5d7-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fa5d7-122">ReJIT: ハウツーガイド</span><span class="sxs-lookup"><span data-stu-id="fa5d7-122">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
